---
title: "Verifica e debug del codice in modalità SharePoint | Documenti Microsoft"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- unit testing [SharePoint development in Visual Studio]
- IntelliTrace [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, IntelliTrace
- SharePoint development in Visual Studio, unit testing
ms.assetid: b5f3bce2-6a51-41b1-a292-9e384bae420c
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8ab25807ffaf62773b6c02f22c548fb5e5c769ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="verifying-and-debugging-sharepoint-code"></a>Verifica e debug del codice di SharePoint
  Con IntelliTrace e il testing unità è possibile eseguire più facilmente il debug delle soluzioni SharePoint, nonché garantire il corretto funzionamento di ogni singolo metodo in esse. È possibile utilizzare queste funzionalità per i progetti SharePoint in [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] seguendo le stesse procedure utilizzate per altri tipi di progetti.  
  
## <a name="intellitrace"></a>IntelliTrace  
 Con IntelliTrace è possibile determinare non solo lo stato corrente della soluzione SharePoint ma anche gli eventi generati in passato e il contesto in cui si sono verificati. È possibile scorrere i diversi momenti della soluzione SharePoint in cui sono stati registrati eventi di interesse, esaminando gli stati e i valori delle variabili in ogni punto. Grazie a questa navigazione dinamica, il debug delle soluzioni SharePoint è più facile e rapido, senza la necessità di impostare numerosi punti di interruzione. È inoltre possibile salvare la sessione di debug in un file di log IntelliTrace (con estensione iTrace), aprirlo in un secondo momento in Visual Studio Ultimate ed eseguire il debug post-arresto anomalo. Il file. iTrace include informazioni dettagliate su quando e dove si sono verificati errori specifici di SharePoint, in modo che è possibile determinare la causa di errori. Le informazioni contenute nel file con estensione iTrace sono un subset del log degli errori completo creato dal Servizio di registrazione unificato in SharePoint. Queste informazioni prevedono eventi specifici di SharePoint, ad esempio quando un profilo utente viene aperto o chiuso e quando le proprietà in un progetto SharePoint vengono caricate, lette o modificate. È possibile configurare quali eventi vengono registrati da IntelliTrace. Per ulteriori informazioni, vedere [utilizzo dati di IntelliTrace salvato](/visualstudio/debugger/using-saved-intellitrace-data) e [configurare IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
 Quando si verifica un errore in SharePoint, nella finestra di dialogo dell'errore viene visualizzato un identificatore "ID correlazione" di questo errore specifico. È inoltre possibile ottenere gli ID correlazione dagli eventi elencati nel file con estensione iTrace. Per visualizzare un elenco di tutti gli eventi che si sono verificati con un ID di correlazione specificato, è possibile immettere l'ID nel **Analysis** sezione della pagina di riepilogo di IntelliTrace. In questa sezione è possibile scegliere se visualizzare solo i nomi degli eventi che si sono verificati o i nomi degli eventi con le informazioni sulle chiamate, ad esempio il nome della funzione, i punti di uscita e ingresso, i parametri e i valori restituiti.  
  
 È possibile ottenere gli eventi di Visual Studio in IntelliTrace scegliendo il **F5** chiave. Per ottenere gli eventi specifici di SharePoint, tuttavia, è necessario raccogliere i dati IntelliTrace nelle soluzioni SharePoint tramite Microsoft Monitoring Agent. Con questo strumento è possibile raccogliere dati IntelliTrace e creare file con estensione iTrace per le applicazioni distribuite all'esterno di Visual Studio. Per ulteriori informazioni, vedere [funzionalità IntelliTrace](/visualstudio/debugger/intellitrace-features) e [utilizzando l'agente di raccolta autonomo IntelliTrace](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector).  
  
## <a name="unit-testing"></a>Testing unità  
 È possibile trovare più facilmente gli errori nel codice mediante l'esecuzione di unit test, in cui scrivere ed eseguire il codice di test all'interno di metodi di test. Questi metodi sono contenute variabili vuote e un'istruzione Assert che è possibile utilizzare per verificare la logica e le funzionalità del progetto basato sul modello a oggetti SharePoint. Per altre informazioni, vedere [Eseguire unit test del codice](/visualstudio/test/unit-test-your-code).  
  
### <a name="support-for-microsoft-fakes-framework"></a>Supporto per framework Microsoft Fakes  
 I progetti SharePoint supportano Microsoft Fakes, vale a dire un framework di isolamento in cui è possibile creare shim e test stub basati su delegati in applicazioni basate su .NET Framework. Utilizzando il framework Fakes, è possibile creare, gestire e inserire implementazioni fittizie negli unit test. Tramite questi stub e shim è possibile isolare gli unit test dall'ambiente. È possibile creare stub per testare il codice tramite cui vengono utilizzate interfacce o classi non sealed con metodi che possono essere sottoposti a override. È possibile creare shim per reindirizzare le chiamate hardcoded a classi sealed con metodi statici o non sottoponibili a override in un'implementazione alternativa di shim. È inoltre possibile utilizzare i delegati con tipi di stub e di shim per personalizzare dinamicamente il comportamento di singoli membri stub. Per ulteriori informazioni, vedere [isolamento del codice sotto Test con Microsoft Fakes](/visualstudio/test/isolating-code-under-test-with-microsoft-fakes).  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-----------|-----------------|  
|[IntelliTrace](/visualstudio/debugger/intellitrace)|Viene descritto come eseguire più facilmente il debug delle soluzioni di Visual Studio utilizzando IntelliTrace.|  
|[Procedura dettagliata: debug di un'applicazione di SharePoint tramite IntelliTrace](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)|Viene illustrato come utilizzare IntelliTrace per individuare errori di codice in un progetto SharePoint.|  
|[Eseguire unit test del codice](/visualstudio/test/unit-test-your-code)|Viene descritto come individuare gli errori di logica nel codice tramite unit test.|  
  
## <a name="see-also"></a>Vedere anche  
 [Migliorare la qualità del codice](/visualstudio/test/improve-code-quality)  
  
  