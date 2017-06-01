---
title: "Assembly nel runtime di Visual Studio Tools per Office"
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
  - "Strumenti di Visual Studio Tools per Office runtime, assembly"
ms.assetid: d2b7f8f4-0f41-4943-bca5-48c520748b7e
caps.latest.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# Assembly nel runtime di Visual Studio Tools per Office
  Quando si crea un progetto di Office, in Visual Studio vengono automaticamente aggiunti riferimenti agli assembly [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] usati per il tipo di progetto e .NET Framework di destinazione del progetto. Sono disponibili diversi assembly nelle estensioni di Office per .NET Framework 3.5, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] e [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Per altre informazioni sulle estensioni di Office, vedere [Panoramica di Visual Studio Tools per Office Runtime](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
## Assembly nelle estensioni di Office per .NET Framework 4 e [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]  
 Nella tabella seguente sono elencati gli assembly che vengono inclusi nelle estensioni di Office per [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] e [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]. Per la documentazione sugli spazi dei nomi e tipi in questi assembly, vedere [Riferimenti gestiti &#40;sviluppo per Office in Visual Studio&#41;](../vsto/managed-reference-office-development-in-visual-studio.md).  
  
|Nome assembly|Descrizione|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.dll|Fornisce i seguenti tipi:<br /><br /> -   Tipi per la creazione di personalizzazioni della barra multifunzione e smart tag. **Note:**      Gli smart tag sono deprecati in [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] e [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-   Tipi per la creazione di riquadri azioni nelle personalizzazioni a livello di documento e di riquadri attività personalizzati nei componenti aggiuntivi VSTO.|  
|Microsoft.Office.Tools.Excel.dll|Fornisce interfacce che rappresentano elementi host e controlli host per i progetti di Excel e tipi di supporto. Per altre informazioni, vedere [Automazione di Excel usando oggetti estesi](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.dll|Fornisce tipi che è possibile usare per creare aree del modulo personalizzate in componenti aggiuntivi VSTO di Outlook.|  
|Microsoft.Office.Tools.Word.dll|Fornisce interfacce che rappresentano elementi host e controlli host per i progetti di Word e tipi di supporto. Per altre informazioni, vedere [Automazione di Word usando oggetti estesi](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v4.0.Framework.dll|Fornisce i seguenti tipi:<br /><br /> -   Eccezioni che possono essere generate dal runtime di Visual Studio Tools per Office.<br />-   Attributi da usare durante la creazione di aree del modulo di Outlook.|  
|Microsoft.Office.Tools.dll|Fornisce i tipi che fanno parte dell'infrastruttura runtime di Visual Studio Tools per Office e che non è previsto vengano usati direttamente dal codice.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.dll|Fornisce i seguenti tipi:<br /><br /> -   L'attributo <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> e l'interfaccia <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType>, che si possono usare per memorizzare gli oggetti dati nella cache in una personalizzazione a livello di documento. Per altre informazioni, vedere [Memorizzazione di dati nella cache](../vsto/caching-data.md).<br />-   L'interfaccia <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction>, che è possibile implementare per eseguire ulteriori passaggi di installazione, come il passaggio finale del programma di installazione ClickOnce per una soluzione Office. Per altre informazioni, vedere [Distribuzione di una soluzione Office utilizzando ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md).<br />-   Eccezioni che possono essere generate dal runtime di Visual Studio Tools per Office.<br />-   Altri tipi che fanno parte dell'infrastruttura runtime di Visual Studio Tools per Office e che non è previsto vengano usati direttamente dal codice.|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll|Fornisce i seguenti tipi:<br /><br /> -   La classe <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>, che è possibile usare per collegare gli assembly di personalizzazione ai documenti e accedere ai dati dei documenti memorizzati nella cache. Per altre informazioni, vedere [Gestione dei documenti di un server utilizzando la classe ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-   Diverse classi che rappresentano la gerarchia dei dati memorizzati nella cache in una personalizzazione a livello di documento. Per altre informazioni, vedere [Accesso ai dati dei documenti sul server](../vsto/accessing-data-in-documents-on-the-server.md).|  
  
 I progetti destinati a [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] o [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] fanno riferimento agli assembly seguenti. Questi assembly non fanno parte del [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ridistribuibile. Sono invece gli assembly dipendenti che devono essere distribuiti con la soluzione. Per impostazione predefinita, vengono copiati nella cartella di output di compilazione del progetto \(la proprietà **Copia localmente** di questi assembly è impostata su **True**\). Se si distribuisce il progetto tramite ClickOnce, questi assembly vengono inclusi nel pacchetto generato.  
  
|Nome assembly|Descrizione|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v4.0.Utilities.dll|Fornisce le classi base per la classe `ThisAddIn` generata nei progetti di componente aggiuntivo VSTO e la classe Ribbon generata in tutti i progetti.|  
|Microsoft.Office.Tools.Excel.v4.0.Utilities.dll|Fornisce i seguenti tipi:<br /><br /> -   Classi di base le classi `ThisWorkbook` e `Sheet` generate nei progetti a livello di documento per Excel.<br />-   Controlli Windows Form che è possibile usare nei fogli di lavoro dei progetti di Excel.|  
|Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll|Fornisce le classi di base le classi `ThisAddIn` e le classi dell'area del modulo generate nei progetti di Outlook.|  
|Microsoft.Office.Tools.Word.v4.0.Utilities.dll|Fornisce i seguenti tipi:<br /><br /> -   Classi di base per la classe `ThisDocument` generata nei progetti a livello di documento per Word.<br />-   Controlli Windows Form che è possibile usare nei documenti dei progetti di Word.|  
  
## Assembly nelle estensioni di Office per .NET Framework 3.5  
 Nella tabella seguente sono elencati gli assembly che vengono inclusi nelle estensioni di Office per .NET Framework 3.5. Per la documentazione sugli spazi dei nomi e le classi in questi assembly, vedere la sezione di riferimento seguente nella documentazione di Visual Studio 2008: [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=160658](http://go.microsoft.com/fwlink/?LinkId=160658).  
  
|Nome assembly|Descrizione|  
|-------------------|-----------------|  
|Microsoft.Office.Tools.Common.v9.0.dll|Fornisce i seguenti tipi:<br /><br /> -   Classe base Microsoft.Office.Tools.AddIn per componenti aggiuntivi VSTO.<br />-   Classi per la creazione di personalizzazioni della barra multifunzione e smart tag. **Note:**      Gli smart tag sono deprecati in [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] e [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)].<br />-   Classi per la creazione di riquadri azioni nelle personalizzazioni a livello di documento e di riquadri attività personalizzati nei componenti aggiuntivi VSTO.|  
|Microsoft.Office.Tools.Excel.v9.0.dll|Fornisce gli elementi host e i controlli host per le soluzioni Excel. Per altre informazioni, vedere [Automazione di Excel usando oggetti estesi](../vsto/automating-excel-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.Outlook.v9.0.dll|Fornisce classi che è possibile usare per creare arre del modulo personalizzate in componenti aggiuntivi VSTO di Outlook.|  
|Microsoft.Office.Tools.Word.v9.0.dll|Fornisce gli elementi host e i controlli host per le soluzioni Word. Per altre informazioni, vedere [Automazione di Word usando oggetti estesi](../vsto/automating-word-by-using-extended-objects.md).|  
|Microsoft.Office.Tools.v9.0.dll|Fornisce i seguenti tipi:<br /><br /> -   La classe Microsoft.VisualStudio.Tools.Office.RemoteBindableComponent, che fornisce le funzionalità di associazione dati per i controlli host nelle personalizzazioni a livello di documento.<br />-   Altri tipi che fanno parte dell'infrastruttura runtime di Visual Studio Tools per Office e che non è previsto vengano usati direttamente dal codice.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v9.0.dll|Fornisce i seguenti tipi:<br /><br /> -   L'attributo Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute e l'interfaccia Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType, che si possono usare per memorizzare gli oggetti dati nella cache in una personalizzazione a livello di documento. Per altre informazioni, vedere [Memorizzazione di dati nella cache](../vsto/caching-data.md).<br />-   Eccezioni che possono essere generate dal runtime di Visual Studio Tools per Office.<br />-   Altri tipi che fanno parte dell'infrastruttura runtime di Visual Studio Tools per Office e che non è previsto vengano usati direttamente dal codice.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v10.0.dll|Fornisce l'interfaccia Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction, che è possibile implementare per eseguire ulteriori passaggi di installazione, come il passaggio finale del programma di installazione ClickOnce per una soluzione Office. Per altre informazioni, vedere [Distribuzione avanzata di soluzioni Office](http://msdn.microsoft.com/it-it/9147b6f6-849f-4cb1-b2c5-e22658d74b02).|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.v10.0.dll|Fornisce i seguenti tipi:<br /><br /> -   La classe Microsoft.VisualStudio.Tools.Applications.ServerDocument, che è possibile usare a livello di codice per collegare gli assembly di personalizzazione ai documenti e accedere ai dati dei documenti memorizzati nella cache. Per altre informazioni, vedere [Gestione dei documenti di un server utilizzando la classe ServerDocument](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md).<br />-   Diverse classi che rappresentano la gerarchia dei dati memorizzati nella cache in una personalizzazione a livello di documento. Per altre informazioni, vedere [Accesso ai dati dei documenti sul server](../vsto/accessing-data-in-documents-on-the-server.md).|  
|Microsoft.VisualStudio.Tools.Office.Runtime.v10.0.dll|Fornisce i seguenti tipi:<br /><br /> -   Le classi Microsoft.VisualStudio.Tools.Office.Runtime.Security.AddInSecurityEntry e Microsoft.VisualStudio.Tools.Office.Runtime.Security.UserInclusionList, che è possibile usare per creare le voci dell'elenco di inclusione dell'utente per concedere l'attendibilità alle soluzioni Office destinate a .NET Framework 3.5.<br />-   Altri tipi che fanno parte dell'infrastruttura runtime di Visual Studio Tools per Office e che non è previsto vengano usati direttamente dal codice.|  
  
## Vedere anche  
 [Panoramica di Visual Studio Tools per Office Runtime](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Scenari di installazione del runtime di Visual Studio Tools per Office](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)  
  
  