---
title: "&#39;Equals&#39; non pu&#242; confrontare un valore di tipo &#39;&lt;tipo1&gt;&#39; con un valore di tipo &#39;&lt;tipo2&gt;&#39; | Microsoft Docs"
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
  - "vbc36621"
  - "bc36621"
helpviewer_keywords: 
  - "BC36621"
ms.assetid: bd40bf57-3a12-407a-8622-7e428850c77c
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Equals&#39; non pu&#242; confrontare un valore di tipo &#39;&lt;tipo1&gt;&#39; con un valore di tipo &#39;&lt;tipo2&gt;&#39;
Un operatore `Equals` in una clausola `Join` o `Group Join` ha provato a confrontare un tipo di dati con un altro in una modalità non definita. Un esempio di questo caso è un confronto di un valore `Boolean` con un tipo `Date`.  
  
 **ID errore:** BC36621  
  
### Per correggere l'errore  
  
-   Verificare che i valori su ogni lato dell'operatore `Equals` possano essere convertiti in un tipo di dati comune. Alcune opzioni che consentono di eseguire questa operazione sono le seguenti:  
  
    -   Usare la funzione `CType` per convertire uno o più valori in un tipo specifico.  
  
    -   Usare la classe <xref:System.Convert> o i metodi di conversione per convertire uno o più valori in un tipo immutabile comune.  
  
    -   Convertire i valori in stringhe usando il metodo `ToString`.  
  
## Vedere anche  
 [Funzione CType](/dotnet/visual-basic/language-reference/functions/ctype-function)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)   
 [Join Clause](/dotnet/visual-basic/language-reference/queries/join-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)