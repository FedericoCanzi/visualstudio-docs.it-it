---
title: "Non &#232; possibile dedurre gli argomenti di tipo per il metodo &#39;&lt;nomeroutine&gt;&#39; dal delegato &#39;&lt;nomedelegato&gt;&#39; | Microsoft Docs"
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
  - "vbc30952"
  - "bc30952"
helpviewer_keywords: 
  - "BC30952"
ms.assetid: 5eb804ce-2e93-4668-b655-7fe00815e552
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Non &#232; possibile dedurre gli argomenti di tipo per il metodo &#39;&lt;nomeroutine&gt;&#39; dal delegato &#39;&lt;nomedelegato&gt;&#39;
Un'istruzione di assegnazione usa `AddressOf` per assegnare l'indirizzo di un oggetto generico a un delegato, ma non fornisce alcun argomento di tipo alla routine generica.  
  
 Di norma, quando si richiama un tipo generico, si fornisce un argomento di tipo per ogni parametro di tipo definito dal tipo generico. Se non si specifica alcun argomento di tipo, il compilatore prova a dedurre i tipi da passare ai parametri di tipo. Se il contesto non fornisce informazioni sufficienti per consentire al compilatore di dedurre i tipi, viene generato un errore.  
  
 **ID errore:** BC30952  
  
### Per correggere l'errore  
  
-   Specificare gli argomenti di tipo per la routine generica nell'espressione `AddressOf`.  
  
## Vedere anche  
 [Tipi generici in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [AddressOf Operator](/dotnet/visual-basic/language-reference/operators/addressof-operator)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)