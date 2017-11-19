---
title: 'Procedura: aprire il file di testo come cartelle di lavoro | Documenti Microsoft'
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
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
ms.assetid: 056ae3d0-7fe7-4c28-a2a5-5a948baee0e6
caps.latest.revision: "47"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b4148a9a8a8de627ed56f5e1abc6da3469399330
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>Procedura: aprire file di testo come cartelle di lavoro a livello di codice
  È possibile aprire un file di testo come una cartella di lavoro. È necessario passare il nome del file di testo che si desidera aprire. È possibile specificare diversi parametri facoltativi, ad esempio il numero di riga per iniziare l'analisi e il formato della colonna di dati nel file.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>Esempio  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 In questo esempio richiede i seguenti componenti:  
  
-   Un file di testo delimitato da virgole denominato `Test.txt` che contiene almeno tre righe di testo.  
  
-   Il file di testo `Test.txt` siano archiviati nell'unità C.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di cartelle di lavoro](../vsto/working-with-workbooks.md)   
 [Procedura: aprire cartelle di lavoro](../vsto/how-to-programmatically-open-workbooks.md)   
 [Procedura: creare nuove cartelle di lavoro](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [Procedura: salvare a livello di codice le cartelle di lavoro](../vsto/how-to-programmatically-save-workbooks.md)   
 [Procedura: chiudere a livello di codice le cartelle di lavoro](../vsto/how-to-programmatically-close-workbooks.md)   
 [Parametri facoltativi nelle soluzioni Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  