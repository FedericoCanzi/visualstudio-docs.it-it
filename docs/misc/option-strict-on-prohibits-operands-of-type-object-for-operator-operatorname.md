---
title: "Option Strict On non ammette operandi di tipo Object per l&#39;operatore &#39;&lt;nomeoperatore&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30038"
  - "vbc30038"
helpviewer_keywords: 
  - "BC30038"
ms.assetid: eb047d36-1fb4-460d-ae98-c76f31a89bed
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict On non ammette operandi di tipo Object per l&#39;operatore &#39;&lt;nomeoperatore&gt;&#39;
Gli unici operatori definiti per le variabili oggetto sono `Is` e `TypeOf...Is`. Quando `Option Strict` è `On`, tutti gli operandi devono essere di tipi di dati definiti per l'operatore specificato.  
  
 **ID errore:** BC30038  
  
### Per correggere l'errore  
  
-   Usare le funzioni di conversione dei tipi appropriate, ad esempio `CInt` o `CStr`, per convertire gli operandi in tipi di dati definiti per l'operatore.  
  
## Vedere anche  
 [Is Operator](/dotnet/visual-basic/language-reference/operators/is-operator)   
 [Comparison Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)   
 [Type Conversion Functions](/dotnet/visual-basic/language-reference/functions/type-conversion-functions)