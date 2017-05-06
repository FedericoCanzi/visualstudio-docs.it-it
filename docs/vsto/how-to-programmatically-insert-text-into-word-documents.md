---
title: "Procedura: inserire testo nei documenti di Word a livello di codice"
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
  - "intervalli, inserimento di testo in documenti"
  - "testo [Sviluppo per Office in Visual Studio], inserimento in documenti"
  - "intervalli, sostituzione di testo in documenti"
  - "documenti [Sviluppo per Office in Visual Studio], inserimento di testo"
  - "testo [Sviluppo per Office in Visual Studio], sostituzione"
ms.assetid: 405d7442-8ba3-4fcc-b17e-7b289ffd3967
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 40
---
# Procedura: inserire testo nei documenti di Word a livello di codice
  Esistono tre modi principali per inserire il testo nei documenti di Microsoft Office Word:  
  
-   Inserire il testo in un intervallo.  
  
-   Sostituire il testo in un intervallo con il nuovo testo.  
  
-   Usare il metodo <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> di un oggetto <xref:Microsoft.Office.Interop.Word.Selection> per inserire il testo in corrispondenza del cursore o della selezione.  
  
> [!NOTE]  
>  È anche possibile inserire il testo nei controlli contenuto e nei segnalibri. Per altre informazioni, vedere [Controlli del contenuto](../vsto/content-controls.md) e [Controllo Bookmark](../vsto/bookmark-control.md).  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## Inserimento di testo in un intervallo  
 Usare la proprietà <xref:Microsoft.Office.Interop.Word.Range.Text%2A> di un oggetto <xref:Microsoft.Office.Interop.Word.Range> per inserire il testo in un documento.  
  
#### Per inserire il testo in un intervallo  
  
1.  Specificare un intervallo all'inizio di un documento e inserire il testo **New Text**.  
  
     L'esempio di codice seguente può essere usato in una personalizzazione a livello di documento.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#51](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#51)]
     [!code-vb[Trin_VstcoreWordAutomation#51](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#51)]  
  
     L'esempio di codice seguente può essere usato in un componente aggiuntivo VSTO. Questo codice usa il documento attivo.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#51](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#51)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#51](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#51)]  
  
2.  Selezionare l'oggetto <xref:Microsoft.Office.Interop.Word.Range>, che è stato espanso da un carattere alla lunghezza del testo inserito.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#52](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#52)]
     [!code-vb[Trin_VstcoreWordAutomation#52](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#52)]  
  
## Sostituzione di testo in un intervallo  
 Se l'intervallo specificato contiene testo, tutto il testo dell'intervallo viene sostituito con il testo inserito.  
  
#### Per sostituire il testo in un intervallo  
  
1.  Creare un oggetto <xref:Microsoft.Office.Interop.Word.Range> costituito dai primi 12 caratteri nel documento.  
  
     L'esempio di codice seguente può essere usato in una personalizzazione a livello di documento.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#53](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#53)]
     [!code-vb[Trin_VstcoreWordAutomation#53](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#53)]  
  
     L'esempio di codice seguente può essere usato in un componente aggiuntivo VSTO. Questo codice usa il documento attivo.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#53](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#53)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#53](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#53)]  
  
2.  Sostituire questi caratteri con la stringa **New Text**.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#54](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#54)]
     [!code-vb[Trin_VstcoreWordAutomation#54](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#54)]  
  
3.  Selezionare l'intervallo.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#55](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#55)]
     [!code-vb[Trin_VstcoreWordAutomation#55](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#55)]  
  
## Inserimento di testo con TypeText  
 Il metodo <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> inserisce il testo in corrispondenza della selezione.<xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A> si comporta in modo diverso a seconda delle opzioni impostate nel computer dell'utente. Il codice nella procedura seguente dichiara una variabile dell'oggetto <xref:Microsoft.Office.Interop.Word.Selection> e disattiva l'opzione **Overtype**, se attivata. Se l'opzione **Overtype** è attivata, l'eventuale testo accanto al cursore viene sovrascritto.  
  
#### Per inserire il testo usando il metodo TypeText  
  
1.  Dichiarare una variabile dell'oggetto <xref:Microsoft.Office.Interop.Word.Selection>.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#57](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#57)]
     [!code-vb[Trin_VstcoreWordAutomation#57](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#57)]  
  
2.  Disattivare l'opzione **Overtype** se attivata.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#58](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#58)]
     [!code-vb[Trin_VstcoreWordAutomation#58](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#58)]  
  
3.  Verificare se la selezione corrente si trova in corrispondenza del punto di inserimento.  
  
     In questo caso, il codice inserisce una frase usando <xref:Microsoft.Office.Interop.Word.Selection.TypeText%2A>, quindi un segno di paragrafo usando il metodo <xref:Microsoft.Office.Interop.Word.Selection.TypeParagraph%2A>.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#59](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#59)]
     [!code-vb[Trin_VstcoreWordAutomation#59](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#59)]  
  
4.  Il codice nel blocco **ElseIf** verifica che la selezione sia una selezione normale. In questo caso, un altro blocco **If** verifica che l'opzione **ReplaceSelection** sia attivata. In questo caso, il codice usa il metodo <xref:Microsoft.Office.Interop.Word.Selection.Collapse%2A> della selezione per comprimere la selezione in un punto di inserimento all'inizio del blocco di testo selezionato. Inserire il testo e un segno di paragrafo.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#60](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#60)]
     [!code-vb[Trin_VstcoreWordAutomation#60](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#60)]  
  
5.  Se la selezione non è un punto di inserimento o un blocco di testo selezionato, il codice nel blocco **Else** non esegue alcuna operazione.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#61](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#61)]
     [!code-vb[Trin_VstcoreWordAutomation#61](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#61)]  
  
 È anche possibile usare il metodo <xref:Microsoft.Office.Interop.Word.Selection.TypeBackspace%2A> dell'oggetto <xref:Microsoft.Office.Interop.Word.Selection> che riproduce la funzionalità del tasto BACKSPACE sulla tastiera. Tuttavia, per l'inserimento e la modifica del testo, l'oggetto <xref:Microsoft.Office.Interop.Word.Range> offre un maggiore controllo.  
  
 L'esempio seguente mostra il codice completo. Per usare questo esempio, eseguire il codice dalla classe `ThisDocument` o `ThisAddIn` nel progetto.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#56](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#56)]
 [!code-vb[Trin_VstcoreWordAutomation#56](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#56)]  
  
## Vedere anche  
 [Procedura: Formattare il testo nei documenti a livello di codice](../vsto/how-to-programmatically-format-text-in-documents.md)   
 [Procedura: definire e selezionare intervalli nei documenti a livello di codice](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Procedura: Estendere gli intervalli nei documenti a livello di codice](../vsto/how-to-programmatically-extend-ranges-in-documents.md)  
  
  