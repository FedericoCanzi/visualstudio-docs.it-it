---
title: Usare Build and Release Management per l&quot;esecuzione di test automatizzati | Microsoft Docs
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automated testing, lab management, test lab
ms.assetid: F34B0D19-B430-4C01-B402-62A861007E71
caps.latest.revision: 56
ms.author: douge
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 45d36934cf1c46902cac566203cddf4a118b7fe4
ms.openlocfilehash: 77a0339e1aae3036990f0d9d133a1fcb68844486
ms.contentlocale: it-it
ms.lasthandoff: 06/02/2017

---
# <a name="use-build-and-release-management-instead-of-lab-management-for-automated-testing"></a>Usare Build and Release Management per l'esecuzione di test automatizzati

Se si usano Microsoft Test Manager (MTM) e Lab Management per l'esecuzione di test automatizzati o per l'automazione delle operazioni di compilazione/distribuzione/test, questo argomento descrive come ottenere gli stessi risultati tramite le funzionalità di [Build &amp; Release](https://www.visualstudio.com/team-services/continuous-integration/) in Team Foundation Server (TFS) e Visual Studio Team Services:

* [Automazione delle operazioni di compilazione/distribuzione/test](#bdtautomation)

* [Gestione self-service di ambienti SCVMM](#managescvmm)

Build and Release Management non supporta la creazione self-service di ambienti SCVMM con isolamento rete e questo supporto non è previsto per il futuro. Esistono tuttavia alcune [alternative suggerite](#isolatedenvir).

<a name="bdtautomation"></a>
## <a name="build-deploy-test-automation"></a>Automazione delle operazioni di compilazione/distribuzione/test

Per l'automazione della compilazione, della distribuzione e del test delle applicazioni, MTM e Lab Management si basano su una definizione di compilazione XAML.
Per raggiungere questo obiettivo, la compilazione XAML si basa su diversi costrutti creati in MTM, ad esempio un ambiente lab e gruppi e impostazioni di test, e sui vari componenti di infrastruttura, ad esempio un controller di compilazione, agenti di compilazione, un controller di test e agenti di test. È possibile ottenere lo stesso risultato con un numero inferiore di passaggi tramite Build and Release Management in TFS e in Team Services.

| Passaggi | Con la compilazione XAML | Con Build and Release Management |
|-------|----------------------|-----------------|
| Identificare i computer in cui distribuire la compilazione ed eseguire i test. | Creare un ambiente lab standard in MTM con questi computer. | n/d |
| Identificare i test da eseguire. | Creare un gruppo di test in MTM, creare i test case e associare l'automazione a ogni test case. Creare le impostazioni di test in MTM identificando il ruolo dei computer nell'ambiente lab in cui devono essere eseguiti i test. | Se si prevede di gestire l'esecuzione dei test tramite piani di test, creare un gruppo di test automatizzati in MTM nello stesso modo. In alternativa, è possibile evitare questo passaggio se i test devono essere eseguiti direttamente da file binari di test generati dalle compilazioni. In entrambi i casi non è necessario creare impostazioni di test. |
| Automatizzare la distribuzione e l'esecuzione di test. | Creare una definizione di compilazione XAML tramite LabDefaultTemplate.*.xaml. Specificare la compilazione, i gruppi di test e l'ambiente lab nella definizione di compilazione. | Creare una [definizione di compilazione o una versione di versione](https://www.visualstudio.com/team-services/continuous-integration/) con un unico ambiente. Eseguire lo stesso script di distribuzione (dalla definizione di compilazione XAML) tramite l'attività Riga di comando ed eseguire test automatizzati tramite le attività Distribuzione agente di test ed Esegui test funzionali. Come input per queste attività, specificare l'elenco dei computer e le relative credenziali. |

Ecco alcuni dei vantaggi dell'uso di Build and Release Management per questo scenario:

* Non è necessario alcun controller di compilazione o di test.
* L'agente di test viene installato tramite un'attività compresa nella compilazione o nella versione.
* È facile personalizzare i passaggi di distribuzione. È ora possibile usare più di uno script. È anche possibile usufruire delle numerose attività disponibili nel prodotto e in Visual Studio Marketplace.
* Non è necessario gestire gruppi di test. È possibile eseguire i test direttamente dai file binari.
* Per i test eseguiti all'interno di ogni compilazione o di ogni versione è possibile ottenere un'esperienza di report inline più esaustiva.
* È possibile tenere traccia delle risorse (versione, compilazione, elementi di lavoro, commit) distribuite e sottoposte a test in ogni ambiente.
* È possibile personalizzare ed estendere l'automazione per distribuire con facilità più ambienti di test e persino l'ambiente di produzione.
* È possibile pianificare l'automazione in modo che venga eseguita ogni volta che viene effettuata un'archiviazione o un commit oppure ogni giorno a un'ora specifica.

<a name="managescvmm"></a>
## <a name="self-service-management-of-scvmm-environments"></a>Gestione self-service di ambienti SCVMM

[Centro Lab in Microsoft Test Manager](https://msdn.microsoft.com/library/dd997438.aspx) supporta la possibilità di gestire una libreria di modelli di ambiente, nonché di eseguire il provisioning di ambienti su richiesta tramite un [server SCVMM](https://technet.microsoft.com/system-center-docs/vmm/vmm).

Le funzionalità di provisioning self-service di Centro lab hanno due obiettivi distinti:

* Fornire un modo più semplice per gestire l'infrastruttura. La gestione di modelli di macchine virtuali e di ambienti e la creazione automatica di reti private per isolare i cloni degli ambienti l'uno dall'altro sono esempi di gestione dell'infrastruttura.

* Consentire ai team di utilizzare macchine virtuali in modo più semplice per le attività di test e distribuzione. La possibilità di accedere agli ambienti lab con lo stesso modello di sicurezza dei progetti team e l'uso integrato delle macchine virtuali negli scenari di test sono esempi di utilizzo semplificato.

Tuttavia, data l'evoluzione di sistemi più avanzati di gestione del cloud pubblico e privato, come esempio [Microsoft Azure](https://azure.microsoft.com/) e [Microsoft Azure Stack](https://azure.microsoft.com/overview/azure-stack/), per le funzionalità di gestione dell'infrastruttura di TFS 2017 e versioni successive non è prevista un'evoluzione. Viene invece ancora dedicata molta attenzione alla facilità di utilizzo delle risorse gestite tramite questo tipo di infrastrutture cloud.

La tabella seguente offre un riepilogo delle attività più comuni eseguite in passato in Centro lab e del modo in cui è possibile eseguire queste attività tramite SCVMM o Azure (nel caso di attività di gestione dell'infrastruttura) o tramite TFS e Team Services (nel caso di attività di test o distribuzione):

| Passaggi | Con Centro lab | Con Build and Release Management |
|-------|----------------------|-----------------|
| Gestire una libreria di modelli di ambiente. | Creare un ambiente lab. Installare il software necessario nelle macchine virtuali. Eseguire Sysprep e archiviare l'ambiente come modello nella libreria. | Usare direttamente la console di amministrazione di SCVMM per creare e gestire modelli di macchine virtuali o modelli di servizi. Se si usa Azure, selezionare uno dei [modelli di Azure Resource Manager](https://azure.microsoft.com/documentation/templates/) predefiniti da [Azure Marketplace](https://azure.microsoft.com/marketplace/) o dai [modelli di avvio rapido di Azure](https://azure.microsoft.com/documentation/templates/). |
| Creare un ambiente lab. | Selezionare un modello di ambiente nella libreria e distribuirlo. Specificare i parametri necessari per personalizzare le configurazioni delle macchine virtuali. | Usare direttamente la console di amministrazione di SCVMM per creare macchine virtuali o istanze del servizio da modelli. Usare direttamente il portale di Azure per creare risorse. In alternativa, creare una definizione di versione con un ambiente. Usare una o più attività di Azure dall'[estensione SCVMM Integration](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) per creare nuove macchine virtuali. Creare una nuova versione di questa definizione equivale alla creazione di un nuovo ambiente in Centro lab. |
| Connettersi ai computer. | Aprire l'ambiente lab nel Visualizzatore dell'ambiente. | Usare direttamente la console di amministrazione di SCVMM per connettersi alle macchine virtuali. In alternativa, usare l'indirizzo IP o il nome DNS delle macchine virtuali per aprire sessioni di Desktop remoto. |
| Acquisire un checkpoint di un ambiente o ripristinare un checkpoint pulito per un ambiente. | Aprire l'ambiente lab nel Visualizzatore dell'ambiente. Selezionare l'opzione relativa all'acquisizione di un checkpoint o al ripristino di un checkpoint precedente. | Usare direttamente la console di amministrazione di SCVMM per eseguire queste operazioni all'interno di macchine virtuali. Oppure, per eseguire questi passaggi nell'ambito di un'automazione più ampia, includere le attività di checkpoint dell'[estensione SCVMM Integration](https://marketplace.visualstudio.com/items?itemname=ms-vscs-rm.scvmmapp) in una definizione di versione come parte dell'ambiente. |

<a name="isolatedenvir"></a>
## <a name="self-service-creation-of-network-isolated-environments"></a>Creazione self-service di ambienti con isolamento rete

Un ambiente lab con isolamento rete è un gruppo di macchine virtuali SCVMM che possono essere clonate in sicurezza senza creare conflitti di rete. Questa attività è stata eseguita in MTM in base a una serie di istruzioni che usavano un set di schede di interfaccia di rete per configurare le macchine virtuali in una rete privata e un altro set di schede di interfaccia di rete per configurare le macchine virtuali in una rete pubblica.

Con l'evoluzione di sistemi di gestione del cloud pubblico e privato più avanzati, come [Microsoft Azure](https://azure.microsoft.com/) e [Microsoft Azure Stack](https://azure.microsoft.com/overview/azure-stack/), è possibile ampliare l'uso diretto degli strumenti di gestione del cloud per questo tipo di funzionalità. Non esiste un modo equivalente per raggiungere questo obiettivo in Build and Release Management.

Se è necessario adottare l'isolamento rete, è consigliabile prendere in considerazione le alternative seguenti:

* Uno dei motivi per l'adozione dell'isolamento rete è la facilità di configurazione di più cloni. Poiché ogni clone è una replica esatta dell'originale, il nome computer e le impostazioni di configurazione vengono mantenute esattamente come sono. Questo facilita la configurazione di nuovi ambienti. Questo vantaggio, tuttavia causa problemi più avanti nel ciclo di vita (ad esempio, nell'ambiente di produzione), perché il modo in cui le applicazioni vengono infine distribuite non è lo stesso. **In alternativa**, prendere in considerazione la possibilità di configurare i nuovi ambienti nello stesso modo dell'ambiente di produzione, evitando l'uso dell'isolamento rete.

* Usare un'infrastruttura di cloud pubblico, ad esempio [Microsoft Azure](https://azure.microsoft.com/) per le esigenze di test. È possibile usare facilmente [modelli di Azure Resource Manager](https://azure.microsoft.com/documentation/templates/) da [Azure Marketplace](https://azure.microsoft.com/marketplace/) o dai [modelli di avvio rapido di Azure](https://azure.microsoft.com/documentation/templates/) per impostare gruppi di macchine virtuali connessi tramite una rete privata ed esposti alla rete pubblica solo tramite un proxy o un 'jumpbox'.

