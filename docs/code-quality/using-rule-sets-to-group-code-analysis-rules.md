---
title: "Utilizzo di set di regole per raggruppare regole di analisi del codice | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.rulesets.learnmore"
helpviewer_keywords: 
  - "analisi codice, set di regole"
ms.assetid: ed0f3a2a-1516-42e2-92de-b8986dc75d42
caps.latest.revision: 36
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 36
---
# Utilizzo di set di regole per raggruppare regole di analisi del codice
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Quando si configura l'analisi del codice in [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], o [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], è possibile scegliere da un elenco di *set di regole*incorporate Microsoft.  Un set di regole è un raggruppamento logico di regole dell'analisi del codice che identificano problemi di destinazione e condizioni specifiche.  Ad esempio, è possibile applicare un set di regole progettato per analizzare il codice per le API disponibili, oppure è possibile applicare un set di regole che includa solo le regole minime consigliate.  È inoltre possibile applicare un set di regole che includa tutte le regole.  
  
 È possibile personalizzare un set di regole aggiungendo o eliminando regole oppure modificando le regole in modo che vengano visualizzate nella finestra **Elenco errori** come avvisi o errori.  I set di regole personalizzati possono soddisfare le esigenze di un determinato ambiente di sviluppo.  Quando si personalizza un set di regole, nella relativa pagina vengono forniti strumenti di ricerca e filtro che agevolano il processo.  
  
## Attività comuni  
  
|Task|Contenuto correlato|  
|----------|-------------------------|  
|**Fare pratica:** utilizzare gli strumenti di analisi codice per specificare un set di regole personalizzate e individuare e correggere problemi in una semplice applicazione .NET Framework.|-   [Procedura dettagliata: Configurazione e uso di un set di regole personalizzate](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)|  
|**Configurare l'analisi codice per un progetto:** scegliere un set di regole esistente per un progetto, un sito Web o una soluzione.|-   [Procedura: Configurare l'analisi codice per un progetto di codice gestito](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)<br />-   [Utilizzo di set di regole per specificare le regole C\+\+ da eseguire](../code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run.md)<br />-   [Procedura: configurare l'analisi del codice per un'applicazione Web ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)<br />-   [Procedura: specificare set di regole per più progetti in una soluzione](../code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)|  
|**Personalizzare un set di regole:** specificare le regole da applicare al progetto.|-   [Creazione di set di regole personalizzate](../code-quality/creating-custom-code-analysis-rule-sets.md)|  
|**Capire i set di regole standard:** visualizzare le regole di analisi codice che costituiscono i set di regole incorporati.|-   [Tabella di riferimento del set di regole di analisi del codice](../code-quality/code-analysis-rule-set-reference.md)|  
|**Integrare l'analisi codice con Team Foundation Server:**i criteri di archiviazione di[!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)] consentono ai team di sviluppo di assicurarsi che tutte le archiviazioni di codice soddisfino un set comune di standard di analisi codice.|-   [Procedura: sincronizzare i set di regole del progetto di codice con i criteri di archiviazione del progetto team](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)|