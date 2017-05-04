---
title: "Configurazione di un computer per sviluppare soluzioni Office | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "strumenti di sviluppo per Office in Visual Studio, strumenti di installazione"
ms.assetid: 0b481186-fd31-43bf-aa4a-591f94309555
caps.latest.revision: 97
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 96
---
# Configurazione di un computer per sviluppare soluzioni Office
  Per creare componenti aggiuntivi VSTO e personalizzazioni per Microsoft Office, installare una versione supportata di Visual Studio, .NET Framework e Microsoft Office.  
  
|Software|Versioni supportate|  
|--------------|-------------------------|  
|Visual Studio|-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)]<br />-   [!INCLUDE[vsPreShort](../vsto/includes/vspreshort-md.md)]<br />-   [!INCLUDE[vsUltShort](../vsto/includes/vsultshort-md.md)] **Important:**  Durante l'installazione è necessario selezionare la casella di controllo Microsoft Office Developer Tools.|  
|.NET Framework|-   .NET Framework 4 o versione successiva|  
|Microsoft Office|<ul><li>Qualsiasi edizione di Office incluso Office Professional Plus per Office 365.</li><li>Qualsiasi applicazione autonoma tra le seguenti:<br /><br /> <ul><li>Excel</li><li>InfoPath \(solo Office 2013 e Office 2010\)</li><li>Outlook</li><li>PowerPoint</li><li>Progetto</li><li>Visio</li><li>Word</li></ul></li></ul><br /> Visual Basic, Applications Edition \(VBA\) deve essere installato unitamente a Office. **Important:**  Le versioni A portata di clic delle applicazioni di Office 2010 non sono supportate.|  
  
 Per la procedura dettagliata di installazione, vedere [Procedura: configurare un computer per sviluppare soluzioni Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).  
  
## Se i modelli di progetto non vengono visualizzati o non funzionano in Visual Studio  
 Se si installa una versione supportata di Visual Studio, .NET Framework e Microsoft Office, ma i modelli di progetto di Office non vengono visualizzati nella finestra di dialogo **Nuovo progetto** di Visual Studio oppure viene visualizzato un errore quando si tenta di usarne uno, verificare quanto segue:  
  
-   Assicurarsi che nel computer siano installati gli strumenti di sviluppo di Microsoft Office.  
  
     Gli strumenti di sviluppo di Office sono un componente facoltativo di Visual Studio, ma in genere vengono installati automaticamente insieme a Visual Studio. Se si personalizza l'installazione di Visual Studio specificando i componenti da installare, selezionare **Microsoft Office Developer Tools** durante l'installazione per installare gli strumenti.  
  
     Per verificare che questi strumenti siano installati, avviare il programma di installazione di Visual Studio e scegliere il pulsante **Modifica**. Selezionare la casella di controllo **Microsoft Office Developer Tools**, quindi scegliere il pulsante **Aggiorna**.  
  
-   Assicurarsi che la versione di Office in esecuzione non sia una versione A portata di clic. Vedere [Procedura guidata: Verificare se Outlook è un'applicazione A portata di clic in un computer](http://msdn.microsoft.com/library/office/ff864733(v=office.14).aspx).  
  
-   Verificare che sia in esecuzione una sola versione di Microsoft Office.  
  
 Se i problemi persistono, vedere [Supporto aggiuntivo per gli errori nelle soluzioni Office](../vsto/additional-support-for-errors-in-office-solutions.md).  
  
## Vedere anche  
 [Guida introduttiva &#40;sviluppo per Office in Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Procedura: configurare un computer per sviluppare soluzioni Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)   
 [Procedura: installare il runtime ridistribuibile di Microsoft Visual Studio Tools per Office](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)   
 [Procedura: installare assembly di interoperabilità primari di Office](../vsto/how-to-install-office-primary-interop-assemblies.md)   
 [Funzionalità disponibili in base ai tipi di progetto e applicazioni di Office](../vsto/features-available-by-office-application-and-project-type.md)  
  
  