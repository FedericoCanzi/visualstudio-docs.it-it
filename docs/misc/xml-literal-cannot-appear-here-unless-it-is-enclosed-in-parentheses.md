---
title: "Il valore letterale XML non pu&#242; trovarsi in questa posizione a meno che non sia racchiuso tra parentesi | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31198"
  - "vbc31198"
helpviewer_keywords: 
  - "BC31198"
ms.assetid: 97b16076-39ff-430a-9c65-073d01bcb08e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Il valore letterale XML non pu&#242; trovarsi in questa posizione a meno che non sia racchiuso tra parentesi
Una dichiarazione di valore letterale XML viene usata in un'espressione in una posizione ambigua per il compilatore [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. In altri termini, il compilatore [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] non riesce a determinare se il segno di minore \(\<\) deve essere considerato come operatore di confronto o inizio di un valore letterale XML. Nel codice seguente ne viene illustrato un esempio:  
  
 \[Visual Basic\]  
  
```  
' Generates an error. Dim queryResult = From element In elements _ Where <sample>Value</sample> = "Value" _ Select element  
```  
  
 **ID errore:** BC31198  
  
### Per correggere l'errore  
  
-   Racchiudere la dichiarazione di valore letterale XML tra parentesi, come mostrato nell'esempio seguente:  
  
    ```vb#  
    Dim queryResult = From element In elements _ Where (<sample> Value</sample>) = "Value" _ Select element  
    ```  
  
-   Modificare il codice per fare riferimento a un valore letterale XML esistente, come mostrato nell'esempio seguente:  
  
    ```vb#  
    Dim queryResult = From element In elements _ Where e.<sample>.Value = "Value" _ Select element  
    ```  
  
## Vedere anche  
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML Axis Properties](/dotnet/visual-basic/language-reference/xml-axis/xml-axis-properties)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)