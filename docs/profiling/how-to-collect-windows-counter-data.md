---
title: "Procedura: Raccogliere i dati dei contatori Windows | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.property.syscounter"
  - "vs.performance.property.wincounter"
helpviewer_keywords: 
  - "Windows (contatori)"
  - "strumenti per le prestazioni, uso dei contatori Windows"
  - "strumenti per la profilatura, uso dei contatori Windows"
ms.assetid: db4fbac2-bea5-4558-aa8b-160fcccf4b33
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Procedura: Raccogliere i dati dei contatori Windows
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

I contatori Windows sono contatori di prestazioni del sistema che possono essere raccolti a intervalli regolari durante l'analisi.  Nella visualizzazione Contrassegni del rapporto Strumenti di profilatura è presente una riga etichettata **AutoMark** per ogni intervallo della raccolta.  Nella riga sono contenute delle colonne che descrivono i valori dei contatori delle prestazioni inclusi nell'intervallo specificato.  Per limitare l'analisi a un periodo di tempo compreso tra due contrassegni particolari, selezionare i contrassegni, fare clic con il pulsante destro del mouse, quindi scegliere **Aggiungi filtro** \-\>  **contrassegni** dal menu di scelta rapida.  
  
 **Requisiti**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Le funzioni di sicurezza avanzate di Windows 8 e Windows Server 2012 hanno richiesto modifiche significative riguardo alla modalità di raccolta dei dati su queste piattaforme da parte del profiler di Visual Studio.  Le applicazioni Windows Store richiedono nuove tecniche di raccolta.  Vedere [Profilatura delle applicazioni Windows 8 e Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### Per raccogliere i dati dei contatori Windows  
  
1.  In Esplorazione prestazioni, fare clic con il pulsante destro del mouse sulla sessione per la quale si desidera configurare i contatori di Windows e scegliere **Proprietà**.  
  
2.  In **Pagine delle proprietà** fare clic su **Contatori Windows**.  
  
3.  Selezionare la casella di controllo **Raccogliere contatori Windows** .  
  
4.  Nella casella di testo **Intervallo di raccolta \(msecs\)** digitare un intervallo di tempo.  
  
5.  Selezionare una categoria dall'elenco a discesa **Categoria contatori** .  
  
6.  Selezionare un'istanza dall'elenco a discesa **Istanza** .  
  
7.  Selezionare i contatori che si desidera utilizzare quando si profila l'applicazione.  
  
8.  Fare clic su **Applica**.  
  
## Vedere anche  
 [Configurazione di sessioni di prestazioni](../profiling/configuring-performance-sessions.md)   
 [Proprietà della sessione di prestazioni](../profiling/performance-session-properties.md)   
 [Contatori CPU e Windows](../profiling/cpu-and-windows-counters.md)