---
title: "Elemento host Workbook | Microsoft Docs"
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
  - "cartelle di lavoro di Excel"
  - "Workbook (elementi host)"
  - "elementi host [sviluppo per Office in Visual Studio], Workbook"
  - "cartelle di lavoro, Excel"
  - "elementi host Workbook, eventi"
  - "cartelle di lavoro"
  - "Excel [sviluppo per Office in Visual Studio], cartelle di lavoro"
  - "cartelle di lavoro, eventi"
  - "eventi [sviluppo per Office in Visual Studio]"
ms.assetid: 54489d91-a799-4dc2-89b8-498cf17c2f57
caps.latest.revision: 42
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 41
---
# Elemento host Workbook
  L'elemento host <xref:Microsoft.Office.Tools.Excel.Workbook> è un tipo che estende il tipo <xref:Microsoft.Office.Interop.Excel.Workbook> dall'assembly di interoperabilità primario per Excel. L'elemento host <xref:Microsoft.Office.Tools.Excel.Workbook> fornisce non solo tutte le proprietà, i metodi e gli eventi di un oggetto <xref:Microsoft.Office.Interop.Excel.Workbook>, ma anche funzionalità aggiuntive.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 Nei progetti a livello di documento è presente un elemento host predefinito <xref:Microsoft.Office.Tools.Excel.Workbook> che rappresenta la cartella di lavoro nel progetto. Nei progetti di componente aggiuntivo VSTO è possibile generare elementi host <xref:Microsoft.Office.Tools.Excel.Workbook> in fase di esecuzione.  
  
## Informazioni sull'elemento host Workbook nei progetti a livello di documento  
 Per accedere alla cartella di lavoro nel progetto, usare la classe `ThisWorkbook`. La classe `ThisWorkbook` consente l'accesso ai membri dell'elemento host <xref:Microsoft.Office.Tools.Excel.Workbook> per eseguire attività di base nella personalizzazione, ad esempio eseguire codice quando la cartella di lavoro è aperta o chiusa. Per altre informazioni, vedere [Programmazione delle personalizzazioni a livello di documento](../vsto/programming-document-level-customizations.md).  
  
 La classe `ThisWorkbook` offre un punto di partenza per iniziare a scrivere codice nel progetto. Dal momento che la classe offre tutte le stesse proprietà, gli stessi metodi ed eventi dell'oggetto <xref:Microsoft.Office.Interop.Excel.Workbook> nell'assembly di interoperabilità primario per Excel, è possibile usare anche `ThisWorkbook` per accedere al modello a oggetti di Excel. Per altre informazioni, vedere [Cenni preliminari sul modello a oggetti di Excel](../vsto/excel-object-model-overview.md).  
  
 Fare doppio clic sul progetto **ThisWorkbook** in **Esplora soluzioni** per visualizzare la finestra di progettazione della cartella di lavoro e vedere le proprietà e gli eventi della cartella di lavoro nella finestra **Proprietà**.  
  
### Limitazioni dell'elemento host Workbook nei progetti a livello di documento  
 Un progetto a livello di documento può contenere solo un elemento host <xref:Microsoft.Office.Tools.Excel.Workbook> \(ossia, la classe `ThisWorkbook`\). Non è possibile aggiungere nuovi elementi host <xref:Microsoft.Office.Tools.Excel.Workbook> al progetto in fase di progettazione, né creare nuovi elementi host <xref:Microsoft.Office.Tools.Excel.Workbook> in fase di esecuzione da una personalizzazione a livello di documento.  
  
 Se si crea una nuova cartella di lavoro di Excel in fase di esecuzione, sarà di tipo <xref:Microsoft.Office.Interop.Excel.Workbook>. Dal momento che non si tratta di un elemento host, non può contenere alcun controllo host o controllo Windows Form. Per altre informazioni sulla creazione di cartelle di lavoro in fase di esecuzione, vedere [Procedura: creare nuove cartelle di lavoro a livello di codice](../vsto/how-to-programmatically-create-new-workbooks.md).  
  
 L'elemento host <xref:Microsoft.Office.Tools.Excel.Workbook> non funge da contenitore per i controlli host. Pertanto, alla cartella di lavoro non è possibile aggiungere controlli visibili, ma si possono inserire componenti, ad esempio <xref:System.Data.DataSet>, in modo che possano essere condivisi da tutte le cartelle di lavoro. In un progetto a livello di documento i componenti disponibili per la cartella di lavoro sono reperibili nelle schede **Componente**, **Dati** e **Tutti i Windows Form** della **Casella degli strumenti**.  
  
> [!NOTE]  
>  Gli strumenti di sviluppo di Office in Visual Studio non supportano le cartelle di lavoro condivise.  
  
## Informazioni sugli elementi host Workbook nei progetti di componente aggiuntivo VSTO  
 Nei progetti di componente aggiuntivo VSTO è possibile generare un elemento host <xref:Microsoft.Office.Tools.Excel.Workbook> in fase di esecuzione per qualsiasi cartella di lavoro aperta in Excel. Per generare un elemento host <xref:Microsoft.Office.Tools.Excel.Workbook>, usare il metodo GetVstoObject. Per altre informazioni, vedere [Estensione in fase di esecuzione di documenti di Word e di cartelle di lavoro di Excel in componenti aggiuntivi VSTO](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
## Vedere anche  
 [Procedure dettagliate ed esempi di sviluppo di applicazioni per Microsoft Office](../vsto/office-development-samples-and-walkthroughs.md)   
 [Estensione in fase di esecuzione di documenti di Word e di cartelle di lavoro di Excel in componenti aggiuntivi VSTO](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Panoramica degli elementi e dei controlli host](../vsto/host-items-and-host-controls-overview.md)   
 [Elemento host Worksheet](../vsto/worksheet-host-item.md)   
 [Automazione di Excel usando oggetti estesi](../vsto/automating-excel-by-using-extended-objects.md)   
 [Limitazioni a livello di codice degli elementi e dei controlli host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  