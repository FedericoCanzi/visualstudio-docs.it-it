---
title: 'Procedura: Specificare opzioni di strumentazione aggiuntive | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.advanced
helpviewer_keywords:
- instrumentation, options
- profiling tools, session options
- performance sessions, options
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8052c0538619588f60fd21802209d57bd7fdf80d
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-specify-additional-instrumentation-options"></a>Procedura: Specificare opzioni di strumentazione aggiuntive

È possibile instrumentare i file binari tramite l'IDE di Visual Studio o usando gli strumenti da riga di comando. Se si instrumenta un file binario dall'IDE, è possibile controllare il volume dei dati raccolti durante la strumentazione specificando opzioni di strumentazione aggiuntive per lo strumento [VSInstr](../profiling/vsinstr.md). Queste opzioni sono disponibili a livello di sessione o di destinazione. Ad esempio, per includere o escludere funzioni specifiche durante il processo di strumentazione, è possibile usare l'opzione di strumentazione aggiuntiva a livello di destinazione.

> [!IMPORTANT]
> Ogni probe inserito modifica leggermente il comportamento del programma originale, causando un sovraccarico in fase di analisi. Benché venga sottratta un'approssimazione di questo sovraccarico, si verificano comunque effetti minimi in termini di tempo sulle applicazioni con multithreading. Le opzioni dello strumento [VSInstr](../profiling/vsinstr.md) consentono di controllare la raccolta dei dati durante la profilatura.

## <a name="to-specify-additional-instrumentation-option"></a>Per specificare un'opzione di strumentazione aggiuntiva

1. In **Esplora prestazioni** selezionare **Sessione prestazioni** e quindi fare clic con il pulsante destro del mouse e selezionare **Proprietà**.

2. In **Pagine delle proprietà** fare clic sulle proprietà di **Avanzate**.

3. Digitare le opzioni nella casella **Opzioni di strumentazione aggiuntive**.

     Ad esempio, usare /CONTROL:THREAD per specificare il livello di profilatura. Per un elenco completo di opzioni, vedere [VSInstr](../profiling/vsinstr.md).

4. Fare clic su **OK**.

## <a name="see-also"></a>Vedere anche

[Configurazione di sessioni di prestazioni](../profiling/configuring-performance-sessions.md)  
[Profilatura dalla riga di comando](../profiling/using-the-profiling-tools-from-the-command-line.md)