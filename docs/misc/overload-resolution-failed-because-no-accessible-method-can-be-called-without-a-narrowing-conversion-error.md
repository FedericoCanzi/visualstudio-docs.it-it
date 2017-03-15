---
title: "La risoluzione dell&#39;overload non &#232; riuscita perch&#233; nessun &#39;&lt;metodo&gt;&#39; accessibile pu&#242; essere chiamato senza una conversione verso un tipo di dati pi&#249; piccolo: &lt;errore&gt; | Microsoft Docs"
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
  - "vbc30519"
  - "bc30519"
helpviewer_keywords: 
  - "BC30519"
ms.assetid: 3b3e724d-6fad-4146-b47d-6525493b2fa8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La risoluzione dell&#39;overload non &#232; riuscita perch&#233; nessun &#39;&lt;metodo&gt;&#39; accessibile pu&#242; essere chiamato senza una conversione verso un tipo di dati pi&#249; piccolo: &lt;errore&gt;
È stata effettuata una chiamata a un metodo di overload, ma il compilatore non riesce a trovare un metodo che può essere chiamato senza una conversione verso un tipo di dati più piccolo. Una conversione verso un tipo di dati più piccolo imposta un valore su un tipo di dati che potrebbe non contenere esattamente alcuni dei possibili valori.  
  
 **ID errore:** BC30519  
  
### Per correggere l'errore  
  
-   Specificare `Option Strict Off`.  
  
## Vedere anche  
 [Overloaded Properties and Methods](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)