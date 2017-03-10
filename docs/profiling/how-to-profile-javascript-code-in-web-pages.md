---
title: 'Procedura: Profilare codice JavaScript nelle pagine Web | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript performance profiling
- Profiling Tools,JavaScript
- web site performance profiling
ms.assetid: 37d02aad-ca4d-4eb0-bf66-ca3ecef31fbe
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 6c394dfcf1c0df0cb7d006592b3dc386da328876
ms.openlocfilehash: 40c90059930b16e081d7d46a24c1b93bdc34f98a
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-profile-javascript-code-in-web-pages"></a>Procedura: Profilare codice JavaScript nelle pagine Web
Gli strumenti di profilatura di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] possono raccogliere dati sulle prestazioni per il codice JavaScript eseguito in un'applicazione Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], in una pagina Web arbitraria o in un'applicazione JavaScript usando il metodo di profilatura della strumentazione.  
  
 **Requirements**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
-   Internet Explorer 8 o versioni successive.  
  
> [!WARNING]
>  Per profilare il codice JavaScript nelle app di Windows Store, vedere [Memoria JavaScript](../profiling/javascript-memory.md). 
  
 È possibile usare la procedura guidata di profilatura per creare una sessione di prestazioni. Specificare il metodo di strumentazione, quindi specificare l'opzione di profilatura JavaScript nella pagina Strumentazione della finestra di dialogo delle proprietà per la sessione di prestazioni.  
  
 Quando si specifica la profilatura JavaScript, questa viene applicata sia al codice JavaScript eseguito nel browser che al codice [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] eseguito nel server.  
  
-   Per un'applicazione Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], la profilatura viene applicata sia al codice JavaScript eseguito nel browser che al codice [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] eseguito nel server.  
  
-   Per una pagina Web arbitraria, la profilatura viene applicata al codice JavaScript eseguito nel browser.  
  
### <a name="to-profile-javascript-in-an-aspnet-web-application-project"></a>Per eseguire la profilatura di JavaScript in un progetto dell'applicazione Web ASP.NET  
  
1.  In [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] aprire il progetto Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)].  
  
2.  Nel menu **Analizza** fare clic su **Avvia Creazione guidata sessione di prestazioni**.  
  
3.  Nella prima pagina della procedura guidata, specificare il metodo di profilatura **Strumentazione** , quindi fare clic su **Avanti**.  
  
4.  Nella seconda pagina della procedura guidata, assicurarsi che il progetto corrente sia selezionato nell'elenco delle destinazioni, quindi fare clic su **Avanti**.  
  
5.  Nella terza pagina della procedura guidata, selezionare la casella di controllo **Profilo JavaScript** , quindi fare clic su **Avanti**.  
  
6.  Nella quarta pagina della procedura guidata, fare clic su **Fine** per avviare l'applicazione Web nel browser.  
  
7.  Verificare la funzionalità di cui eseguire la profilatura.  
  
8.  Per terminare la sessione di profilatura, chiudere il browser.  
  
### <a name="to-profile-javascript-in-individual-web-pages-or-a-javascript-applications"></a>Per eseguire la profilatura del codice JavaScript in singole pagine Web o in applicazioni JavaScript  
  
1.  Aprire [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)].  
  
2.  Nel menu **Analizza** fare clic su **Avvia Creazione guidata sessione di prestazioni**.  
  
3.  Nella prima pagina della procedura guidata, specificare il metodo di profilatura **Strumentazione** , quindi fare clic su **Avanti**.  
  
4.  Nella seconda pagina della procedura guidata, fare clic su un'applicazione ASP.NET o JavaScript, quindi fare clic su **Avanti**.  
  
5.  Nella terza pagina della procedura guidata:  
  
    1.  Digitare l'URL della pagina nella casella **Specificare l'URL o il percorso che esegue l'applicazione Web** .  
  
    2.  Selezionare la casella di controllo **Profilo JavaScript** , quindi fare clic su **Avanti**.  
  
6.  Nella quarta pagina della procedura guidata, fare clic su **Fine** per avviare la pagina Web nel browser.  
  
7.  Verificare la funzionalità di cui eseguire la profilatura.  
  
8.  Per terminare la sessione di profilatura, chiudere il browser.
