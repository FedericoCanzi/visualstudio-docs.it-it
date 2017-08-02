---
title: "Procedura: Ridimensionare i controlli ListObject"
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
  - "controlli [sviluppo per Office in Visual Studio], ridimensionamento"
  - "ListObject (controllo), ridimensionamento"
ms.assetid: a4c7dceb-7b55-447e-9b88-c3596a2fc361
caps.latest.revision: 50
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# Procedura: Ridimensionare i controlli ListObject
  Impostare la dimensione di un controllo <xref:Microsoft.Office.Tools.Excel.ListObject> quando lo si aggiunge a una cartella di lavoro di Microsoft Office Excel; tuttavia, potrebbe essere necessario ridimensionarlo in seguito. Ad esempio, potrebbe essere necessario cambiare un elenco a due colonne in uno a tre colonne.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 È possibile ridimensionare controlli <xref:Microsoft.Office.Tools.Excel.ListObject> in fase di progettazione oppure in fase di esecuzione in progetti a livello di documento. È possibile ridimensionare controlli <xref:Microsoft.Office.Tools.Excel.ListObject> in fase di esecuzione in un progetto di componente aggiuntivo VSTO.  
  
 Questo argomento descrive le attività seguenti:  
  
-   [Ridimensionamento di controlli ListObject in fase di progettazione](#designtime)  
  
-   [Ridimensionamento di controlli ListObject in fase di esecuzione in un progetto a livello di documento](#runtimedoclevel)  
  
-   [Ridimensionamento di controlli ListObject in fase di esecuzione in un progetto di componente aggiuntivo VSTO](#runtimeaddin)  
  
 Per altre informazioni sui controlli <xref:Microsoft.Office.Tools.Excel.ListObject>, vedere [Controllo ListObject](../vsto/listobject-control.md).  
  
 ![Collegamento a video](~/data-tools/media/playvideo.gif "Collegamento a video") Per una dimostrazione video correlata, vedere la [procedura di aggiunta di colonne a un oggetto elenco associato ai dati in fase di esecuzione](http://go.microsoft.com/fwlink/?LinkID=130318).  
  
##  <a name="designtime"></a> Ridimensionamento di un controllo ListObject in fase di progettazione  
 Per ridimensionare un elenco, è possibile selezionare e trascinare uno dei punti di controllo oppure è possibile ridefinirne la dimensione nella finestra di dialogo **Ridimensiona elenco**.  
  
#### Per ridimensionare un elenco usando la finestra di dialogo Ridimensiona elenco  
  
1.  Fare clic con il pulsante destro del mouse su un controllo <xref:Microsoft.Office.Tools.Excel.ListObject>.  
  
2.  Puntare su **Elenco**  e poi selezionare **Ridimensiona elenco** sul menu di scelta rapida.  
  
3.  Selezionare le celle che si vogliono usare per definire la dimensione dell'elenco.  
  
4.  Fare clic su **OK**.  
  
##  <a name="runtimedoclevel"></a> Ridimensionamento di un controllo ListObject in fase di esecuzione in un progetto a livello di documento  
 È possibile ridimensionare un controllo <xref:Microsoft.Office.Tools.Excel.ListObject> in fase di esecuzione usando il metodo <xref:Microsoft.Office.Tools.Excel.ListObject.Resize%2A>. Non è possibile usare questo metodo per spostare il controllo <xref:Microsoft.Office.Tools.Excel.ListObject> in una nuova posizione nel foglio di lavoro. Le intestazioni devono rimanere nella stessa riga e il controllo <xref:Microsoft.Office.Tools.Excel.ListObject> ridimensionato deve sovrapporsi all'oggetto elenco originale. Il controllo <xref:Microsoft.Office.Tools.Excel.ListObject> ridimensionato deve contenere una riga di intestazione e almeno una riga di dati.  
  
#### Per ridimensionare un oggetto elenco a livello di codice  
  
1.  Creare un controllo <xref:Microsoft.Office.Tools.Excel.ListObject> che si estende dalla cella **A1** a quella **B3** in `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#6](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreHostControlsExcel#6](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#6)]  
  
2.  Ridimensionare l'elenco in modo da includere le celle da **A1** a **C5**.  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/CS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreHostControlsExcel#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreHostControlsExcel/VB/Sheet1.vb#7)]  
  
##  <a name="runtimeaddin"></a> Ridimensionamento di un controllo ListObject in fase di esecuzione in un progetto di componente aggiuntivo VSTO  
 È possibile ridimensionare un controllo <xref:Microsoft.Office.Tools.Excel.ListObject> in qualsiasi foglio di lavoro aperto in fase di esecuzione. Per altre informazioni su come aggiungere un controllo <xref:Microsoft.Office.Tools.Excel.ListObject> a un foglio di lavoro usando un componente aggiuntivo VSTO, vedere [Procedura: Aggiungere controlli ListObject a fogli di lavoro](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
#### Per ridimensionare un oggetto elenco a livello di codice  
  
1.  Creare un controllo <xref:Microsoft.Office.Tools.Excel.ListObject> che si estende dalla cella **A1** a quella **B3** in `Sheet1`.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/ThisAddIn.cs#12)]
     [!code-vb[Trin_Excel_Dynamic_Controls#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/ThisAddIn.vb#12)]  
  
2.  Ridimensionare l'elenco in modo da includere le celle da **A1** a **C5**.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/CS/ThisAddIn.cs#13)]
     [!code-vb[Trin_Excel_Dynamic_Controls#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Excel_Dynamic_Controls/VB/ThisAddIn.vb#13)]  
  
## Vedere anche  
 [Estensione in fase di esecuzione di documenti di Word e di cartelle di lavoro di Excel in componenti aggiuntivi VSTO](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Controlli nei documenti di Office](../vsto/controls-on-office-documents.md)   
 [Aggiunta di controlli ai documenti di Office in fase di esecuzione](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Panoramica degli elementi e dei controlli host](../vsto/host-items-and-host-controls-overview.md)   
 [Automazione di Excel usando oggetti estesi](../vsto/automating-excel-by-using-extended-objects.md)   
 [Controllo ListObject](../vsto/listobject-control.md)   
 [Procedura: Aggiungere controlli ListObject a fogli di lavoro](../vsto/how-to-add-listobject-controls-to-worksheets.md)   
 [Procedura: Ridimensionare i controlli Bookmark](../vsto/how-to-resize-bookmark-controls.md)   
 [Procedura: Ridimensionare i controlli NamedRange](../vsto/how-to-resize-namedrange-controls.md)  
  
  