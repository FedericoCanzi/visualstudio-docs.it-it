---
title: 'Procedura: Raccogliere i dati dei contatori CPU | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.property.cpucounters
helpviewer_keywords:
- profiling tools, using portable CPU counters
- performance tools, portable CPU counters
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: be2add4c277b99b6eb1361dac4f9227fb868c2e3
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-collect-cpu-counter-data"></a>Procedura: Raccogliere i dati dei contatori CPU

Un contatore di eventi CPU viene usato per raccogliere i dati relativi alle prestazioni dell'hardware. Questo argomento illustra come raccogliere i dati del contatore degli eventi quando si usa il metodo di profilatura della strumentazione.

Si verificano due tipi di eventi del contatore CPU:

- Eventi portabili: eventi della CPU che possono essere raccolti indipendentemente dal tipo di CPU.

- Eventi piattaforma: eventi della CPU associati a un particolare tipo di CPU.

 Gli eventi portabili includono eventi generali, ad esempio le istruzioni ritirate e i cicli non interrotti, eventi del buffer della CPU, eventi di diramazione ed eventi della cache L2. I contatori degli eventi piattaforma disponibili sono determinati dal produttore del processore.

 Le categorie di eventi possono essere condivise tra contatori portabili e di piattaforma. Ad esempio, le categorie di dati seguenti sono spesso comuni a entrambi i tipi:

- Eventi memoria.

- Eventi front-end.

- Eventi di diramazione.

 Nel profiler è possibile raccogliere i dati del contatore di prestazioni in due modi:

- Raccogliere i dati da uno o più contatori quando si esegue la profilatura tramite strumentazione.

- Specificare un evento di contatore come intervallo di campionamento quando si esegue la profilatura mediante campionamento. Per altre informazioni, vedere [Procedura: Scegliere eventi di campionamento](../profiling/how-to-choose-sampling-events.md).

## <a name="to-collect-cpu-performance-counter-data-when-you-profile-by-instrumentation"></a>Per raccogliere i dati dei contatori di prestazioni CPU quando si esegue la profilatura tramite strumentazione

1. In **Pagine delle proprietà** per la sessione di prestazioni fare clic su **Contatori CPU**.

2. Selezionare la casella di controllo **Raccogli contatori CPU**.

3. Espandere l'albero **Contatori di prestazioni disponibili** fino a individuare gli eventi di campionamento da raccogliere.

4. Per ogni evento di cui si vogliono raccogliere i dati, selezionare l'evento e quindi fare clic sulla freccia DESTRA per aggiungere l'evento all'elenco **Contatori selezionati**.

    > [!NOTE]
    > L'opzione **Contatori di prestazioni disponibili** è abilitata solo se si seleziona la casella di controllo **Raccogli contatori CPU**.

## <a name="see-also"></a>Vedere anche

[Configurazione di sessioni di prestazioni](../profiling/configuring-performance-sessions.md)  
[Proprietà della sessione di prestazioni](../profiling/performance-session-properties.md)  
[Contatori CPU e Windows](../profiling/cpu-and-windows-counters.md)  
[Procedura: Scegliere eventi di campionamento](../profiling/how-to-choose-sampling-events.md)