---
title: "Estensione in fase di esecuzione di documenti di Word e di cartelle di lavoro di Excel in componenti aggiuntivi VSTO"
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
  - "GetVstoObject (metodo)"
  - "componenti aggiuntivi a livello di applicazione [sviluppo per Office in Visual Studio], aggiunta di controlli ai documenti"
  - "elementi host [sviluppo per Office in Visual Studio], creazione in fase di esecuzione nei componenti aggiuntivi"
  - "componenti aggiuntivi a livello di applicazione [sviluppo per Office in Visual Studio], estensione di documenti di Word"
  - "componenti aggiuntivi a livello di applicazione [sviluppo per Office in Visual Studio], estensione di cartelle di lavoro di Excel"
  - "controlli [sviluppo per Office in Visual Studio], aggiunta in fase di esecuzione"
  - "HasVstoObject (metodo)"
ms.assetid: c1607314-4cf8-439c-b4c5-709db8b71cff
caps.latest.revision: 61
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 60
---
# Estensione in fase di esecuzione di documenti di Word e di cartelle di lavoro di Excel in componenti aggiuntivi VSTO
  È possibile usare un componente aggiuntivo VSTO per personalizzare i documenti di Word e le cartelle di lavoro di Excel nei modi seguenti:  
  
-   Aggiungere controlli gestiti a qualsiasi foglio di lavoro o documento aperto.  
  
-   Convertire un oggetto elenco di un foglio di lavoro di Excel in un oggetto <xref:Microsoft.Office.Tools.Excel.ListObject> esteso che espone gli eventi e che può essere associato a dati mediante il modello di associazione dati di Windows Form.  
  
-   Eventi di accesso a livello di applicazione esposti da Word ed Excel per documenti, cartelle di lavoro e fogli di lavoro specifici.  
  
 Per usare questa funzionalità, è necessario creare un oggetto in fase di esecuzione che estenda il documento o la cartella di lavoro.  
  
 **Applicazione:** le informazioni fornite in questo argomento sono valide per i progetti di componente aggiuntivo VSTO relativi a Excel e Word. Per altre informazioni, vedere [Funzionalità disponibili in base ai tipi di progetto e applicazioni di Office](../vsto/features-available-by-office-application-and-project-type.md).  
  
## Creazione di oggetti estesi nei componenti aggiuntivi VSTO  
 Gli *oggetti estesi* rappresentano istanze di tipi forniti da Visual Studio Tools per Office Runtime e aggiungono funzionalità a oggetti che esistono in modo nativo nei modelli a oggetti di Word o Excel \(chiamati *oggetti nativi di Office*\). Per creare un oggetto esteso per un oggetto di Word o Excel, usare il metodo GetVstoObject. La prima volta che si chiama il metodo GetVstoObject per un oggetto specifico di Word o di Excel, viene restituito un nuovo oggetto che estende quello specificato. Tutte le altre volte in cui si chiama un metodo e si specifica lo stesso oggetto di Word o Excel, viene restituito lo stesso oggetto esteso.  
  
 Il tipo dell'oggetto esteso dispone dello stesso nome di quello dell'oggetto nativo di Office; tuttavia, il tipo è definito nello spazio dei nomi <xref:Microsoft.Office.Tools.Excel> o <xref:Microsoft.Office.Tools.Word>. Ad esempio, se si chiama il metodo GetVstoObject per estendere un oggetto <xref:Microsoft.Office.Interop.Word.Document>, il metodo restituisce un oggetto <xref:Microsoft.Office.Tools.Word.Document>.  
  
 l metodi GetVstoObject devono essere usati principalmente nei progetti di componente aggiuntivo VSTO. È inoltre possibile usare questi metodi nei progetti a livello di documento, ma si comportano in modo diverso e sono caratterizzati da minori possibilità di utilizzo.  
  
 Per determinare se un oggetto esteso sia stato già creato per un particolare oggetto nativo di Office, usare il metodo HasVstoObject. Per altre informazioni, vedere [Determinare se un oggetto di Office sia stato esteso](#HasVstoObject).  
  
### Creazione di elementi host  
 Quando si usa GetVstoObject per estendere un oggetto a livello di documento \(ovvero, un <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet> o <xref:Microsoft.Office.Interop.Word.Document>\), l'oggetto restituito viene denominato *elemento host*. Un elemento host è un tipo che può contenere altri oggetti, inclusi altri oggetti estesi e controlli. È simile al tipo corrispondente presente nell'assembly di interoperabilità primaria di Word o Excel, ma dispone di funzionalità aggiuntive. Per altre informazioni sugli elementi host, vedere [Panoramica degli elementi e dei controlli host](../vsto/host-items-and-host-controls-overview.md).  
  
 Dopo aver generato un elemento host, è possibile usarlo per aggiungere controlli gestiti al documento, alla cartella di lavoro o al foglio di lavoro. Per altre informazioni, vedere [Aggiunta di controlli gestiti a documenti e fogli di lavoro](#AddControls).  
  
##### Creare un elemento host per un documento di Word  
  
-   Nel seguente esempio di codice viene spiegato come creare un elemento host per il documento attivo.  
  
     [!code-csharp[Trin_WordAddInDynamicControls#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#8)]
     [!code-vb[Trin_WordAddInDynamicControls#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#8)]  
  
##### Creare un elemento host per una cartella di lavoro di Excel  
  
-   Nel seguente esempio di codice viene spiegato come creare un elemento host per la cartella di lavoro attiva.  
  
     [!code-csharp[Trin_ExcelAddInDynamicControls#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ExcelAddInDynamicControls/CS/ThisAddIn.cs#2)]
     [!code-vb[Trin_ExcelAddInDynamicControls#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ExcelAddInDynamicControls/VB/ThisAddIn.vb#2)]  
  
##### Creare un elemento host per un foglio di lavoro di Excel  
  
-   Nel seguente esempio di codice viene spiegato come creare un elemento host per il foglio di lavoro attivo.  
  
     [!code-csharp[Trin_ExcelAddInDynamicControls#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ExcelAddInDynamicControls/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_ExcelAddInDynamicControls#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ExcelAddInDynamicControls/VB/ThisAddIn.vb#1)]  
  
### Creazione di controlli host ListObject  
 Quando si usa il metodo GetVstoObject per estendere un <xref:Microsoft.Office.Interop.Excel.ListObject>, il metodo restituisce un <xref:Microsoft.Office.Tools.Excel.ListObject>. Il <xref:Microsoft.Office.Tools.Excel.ListObject> dispone di tutte le funzionalità del <xref:Microsoft.Office.Interop.Excel.ListObject> originale, ma non mancano quelle aggiuntive, ad esempio, la possibilità di essere associato ai dati tramite il modello di associazione dati di Windows Form. Per altre informazioni, vedere [Controllo ListObject](../vsto/listobject-control.md).  
  
##### Creare un controllo host per ListObject  
  
-   Nel seguente esempio di codice viene spiegato come creare un <xref:Microsoft.Office.Tools.Excel.ListObject> per il primo <xref:Microsoft.Office.Interop.Excel.ListObject> nel foglio di lavoro attivo di un progetto.  
  
     [!code-csharp[Trin_ExcelAddInDynamicControls#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ExcelAddInDynamicControls/CS/ThisAddIn.cs#3)]
     [!code-vb[Trin_ExcelAddInDynamicControls#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ExcelAddInDynamicControls/VB/ThisAddIn.vb#3)]  
  
##  <a name="AddControls"></a> Aggiunta di controlli gestiti a documenti e fogli di lavoro  
 Dopo aver generato un <xref:Microsoft.Office.Tools.Word.Document> o un <xref:Microsoft.Office.Tools.Excel.Worksheet>, è possibile aggiungere controlli al documento o al foglio di lavoro rappresentato da tali oggetti estesi. Per effettuare questa operazione, usare la proprietà Controls del <xref:Microsoft.Office.Tools.Word.Document> o del <xref:Microsoft.Office.Tools.Excel.Worksheet>. Per altre informazioni, vedere [Aggiunta di controlli ai documenti di Office in fase di esecuzione](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 È possibile aggiungere controlli Windows Form o *controlli host*. Un controllo host viene fornito dal [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] e che esegue il wrapping di un controllo corrispondente nell'assembly di interoperabilità primario di Word o di Excel. Un controllo host espone tutti i comportamenti dell'oggetto Office nativo sottostante; inoltre, genera eventi e può essere associato ai dati tramite il modello di data binding di Windows Form. Per altre informazioni, vedere [Panoramica degli elementi e dei controlli host](../vsto/host-items-and-host-controls-overview.md).  
  
> [!NOTE]  
>  Non è possibile aggiungere un controllo <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> a un foglio di lavoro, un controllo <xref:Microsoft.Office.Tools.Word.XMLNode> oppure <xref:Microsoft.Office.Tools.Word.XMLNodes> a un documento usando un componente aggiuntivo VSTO. Questi controlli host non possono essere aggiunti a livello di codice. Per altre informazioni, vedere [Limitazioni a livello di codice degli elementi e dei controlli host](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).  
  
### Persistenza e rimozione di controlli  
 Quando si aggiungono controlli gestiti a un documento oppure a un foglio di lavoro, tali controlli non vengono conservati al momento di salvataggio e chiusura del documento. Tutti i controlli host vengono rimossi; in questo modo, vengono conservati soltanto gli oggetti Office nativi. Ad esempio, un <xref:Microsoft.Office.Tools.Excel.ListObject> diventa un <xref:Microsoft.Office.Interop.Excel.ListObject>. Inoltre, vengono rimossi tutti i controlli Windows Form. Tuttavia, i wrapper ActiveX dei controlli vengono mantenuti nel documento. È necessario includere un codice nel componente aggiuntivo VSTO per pulire i controlli oppure per creare di nuovo i controlli alla successiva apertura del documento. Per altre informazioni, vedere [Persistenza dei controlli dinamici nei documenti di Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
## Accesso agli eventi a livello di applicazione su documenti e cartelle di lavoro  
 Alcuni eventi relativi a documenti, cartelle di lavoro e fogli di lavoro nei modelli a oggetti nativi di Word ed Excel vengono generati soltanto a livello di applicazione. Ad esempio, l'evento <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> viene generato quando si apre un documento di Word; tuttavia, tale evento viene definito nella classe <xref:Microsoft.Office.Interop.Word.Application> invece che nella classe <xref:Microsoft.Office.Interop.Word.Document>.  
  
 Quando si usano soltanto oggetti nativi di Office nel componente aggiuntivo VSTO, è necessario gestire tali eventi a livello di applicazione e scrivere codice aggiuntivo per determinare se il documento che ha creato l'evento è uno di quelli personalizzati. Gli elementi host forniscono questi eventi a livello di documento, in modo che sia più semplice gestire gli eventi per un documento specifico. È possibile creare un elemento host e gestire l'evento per quell'elemento host.  
  
### Esempio che usa oggetti nativi di Word  
 Nel seguente esempio di codice viene descritto come gestire un evento a livello di applicazione per i documenti di Word. Il metodo `CreateDocument` consente di creare un nuovo documento e di definire il gestore eventi <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> che impedisce di salvare il documento. Dal momento che si tratta di un evento a livello di applicazione creato per l'oggetto <xref:Microsoft.Office.Interop.Word.Application>, il gestore eventi deve confrontare il parametro `Doc` con l'oggetto `document1` per determinare se `document1` rappresenta il documento salvato.  
  
 [!code-csharp[Trin_WordAddInDynamicControls#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#12)]
 [!code-vb[Trin_WordAddInDynamicControls#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#12)]  
  
### Esempi in cui viene usato un elemento host  
 Negli esempi di codice seguenti, il processo viene semplificato gestendo l'evento <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> di un elemento host <xref:Microsoft.Office.Tools.Word.Document>. Il metodo `CreateDocument2` riportato in questi esempi consente di generare un <xref:Microsoft.Office.Tools.Word.Document> che estende l'oggetto `document2` e definisce un gestore eventi <xref:Microsoft.Office.Tools.Word.Document.BeforeSave> che impedisce di salvare il documento. Siccome questo gestore eventi viene chiamato soltanto quando si salva `document2`, il gestore eventi è in grado di annullare il salvataggio senza effettuare operazioni aggiuntive, al fine di stabilire quale documento è stato salvato.  
  
 Nell'esempio di codice seguente viene illustrata questa attività.  
  
 [!code-csharp[Trin_WordAddInDynamicControls#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/CS/ThisAddIn.cs#13)]
 [!code-vb[Trin_WordAddInDynamicControls#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_WordAddInDynamicControls/VB/ThisAddIn.vb#13)]  
  
##  <a name="HasVstoObject"></a> Determinare se un oggetto di Office sia stato esteso  
 Per determinare se un oggetto esteso sia stato già creato per un particolare oggetto nativo di Office, usare il metodo HasVstoObject. Questo metodo restituisce **true** se è stato già creato un oggetto esteso; in caso contrario, restituisce **false**.  
  
 Usare il metodo Globals.Factory.HasVstoMethod. Passare all'oggetto Word o Excel nativo \(ad esempio, un <xref:Microsoft.Office.Interop.Word.Document> o <xref:Microsoft.Office.Interop.Excel.Worksheet>\) che si desidera sottoporre a test per un oggetto esteso.  
  
 Il metodo HasVstoObject è utile se si desidera eseguire il codice nel caso in cui un oggetto di Office disponga di un oggetto esteso. Ad esempio, se è disponibile un componente aggiuntivo VSTO di Word che gestisce l'evento <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> per rimuovere i controlli gestiti da un documento prima che venga salvato, è possibile usare il metodo HasVstoObject per determinare se è stato esteso il documento. Se il documento non è stato esteso, non può includere controlli gestiti. Pertanto, il gestore eventi può soltanto essere restituito senza provare a pulire i controlli del documento.  
  
## Vedere anche  
 [Programmazione di componenti aggiuntivi VSTO](../vsto/programming-vsto-add-ins.md)   
 [Aggiunta di controlli ai documenti di Office in fase di esecuzione](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Panoramica degli elementi e dei controlli host](../vsto/host-items-and-host-controls-overview.md)   
 [Procedure dettagliate ed esempi di sviluppo di applicazioni per Microsoft Office](../vsto/office-development-samples-and-walkthroughs.md)  
  
  