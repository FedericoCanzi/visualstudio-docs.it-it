---
title: 'Procedura: recuperare i caratteri iniziale e finale negli intervalli a livello di codice | Documenti Microsoft'
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, retrieving start and end characters
- end characters
- start characters
- documents [Office development in Visual Studio], retrieving ranges
ms.assetid: 734c630c-abc9-491d-94b6-429d1fc7a4cc
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e0cec972c731c823bb8c41f133ac721233a1b028
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-retrieve-start-and-end-characters-in-ranges"></a>Procedura: Recuperare i caratteri iniziale e finale negli intervalli a livello di codice
  Questo esempio illustra come recuperare le posizioni del carattere delle posizioni iniziale e finale di un intervallo.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-in-a-document-level-customization"></a>Per recuperare i caratteri iniziale e finale di un intervallo in una personalizzazione a livello di documento  
  
1.  Ottenere i valori delle proprietà <xref:Microsoft.Office.Interop.Word.Range.Start%2A> e <xref:Microsoft.Office.Interop.Word.Range.End%2A> dell'oggetto <xref:Microsoft.Office.Interop.Word.Range> . L'esempio di codice seguente ottiene la posizione iniziale e finale della seconda frase nel documento. Per usare questo esempio di codice, eseguirlo dalla classe `ThisDocument` nel progetto.  
  
     [!code-vb[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#25)]  
  
### <a name="to-retrieve-start-and-end-characters-of-a-range-by-using-an-vsto-add-in"></a>Per recuperare i caratteri iniziale e finale di un intervallo usando un componente aggiuntivo VSTO  
  
1.  Ottenere i valori delle proprietà <xref:Microsoft.Office.Interop.Word.Range.Start%2A> e <xref:Microsoft.Office.Interop.Word.Range.End%2A> dell'oggetto <xref:Microsoft.Office.Interop.Word.Range> . L'esempio di codice seguente ottiene la posizione iniziale e finale della seconda frase nel documento attivo. Per usare questo esempio di codice, eseguirlo dalla classe `ThisAddIn` nel progetto.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#25)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#25](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#25)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: definire a livello di codice e selezionare intervalli nei documenti](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Procedura: estendere gli intervalli nei documenti](../vsto/how-to-programmatically-extend-ranges-in-documents.md)   
 [Procedura: documenti di reimpostare gli intervalli in Word a livello di codice](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md)   
 [Procedura: a livello di programmazione comprimere intervalli o selezioni in documenti](../vsto/how-to-programmatically-collapse-ranges-or-selections-in-documents.md)   
 [Procedura: escludere a livello di codice i segni di paragrafo durante la creazione di intervalli](../vsto/how-to-programmatically-exclude-paragraph-marks-when-creating-ranges.md)   
 [Procedura: Conteggiare i caratteri nei documenti a livello di codice](../vsto/how-to-programmatically-count-characters-in-documents.md)  
  
  