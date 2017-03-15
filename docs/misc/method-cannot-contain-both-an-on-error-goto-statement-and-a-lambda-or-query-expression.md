---
title: "Il metodo non pu&#242; contenere un&#39;istruzione &#39;On Error GoTo&#39; insieme a un&#39;espressione lambda o di query | Microsoft Docs"
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
  - "bc36595"
  - "vbc36595"
helpviewer_keywords: 
  - "BC36595"
ms.assetid: 4e7cc11e-f53d-4481-afb4-653a81d54483
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Il metodo non pu&#242; contenere un&#39;istruzione &#39;On Error GoTo&#39; insieme a un&#39;espressione lambda o di query
Un metodo contiene sia un'istruzione `On Error Goto` che un'espressione lambda o una query LINQ. Non è possibile includere un'istruzione `On Error Goto` con un'espressione lambda o una query LINQ in un metodo.  
  
 **ID errore:** BC36595  
  
### Per correggere l'errore  
  
1.  Sostituire il codice di gestione delle eccezioni che usa l'istruzione `On Error Goto` con un'istruzione `Try...Catch`.  
  
## Vedere anche  
 [Introduzione alla gestione delle eccezioni \(Visual Basic\)](http://msdn.microsoft.com/it-it/9792f16a-0cd2-40bd-ace2-f7a4344c0e52)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [On Error Statement](/dotnet/visual-basic/language-reference/statements/on-error-statement)