---
title: "&#39;Group&#39; non consentito in questo contesto. &#200; previsto l&#39;identificatore | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36708"
  - "vbc36708"
helpviewer_keywords: 
  - "BC36708"
ms.assetid: ef6b453e-68e7-47c2-997c-9fd1ca074217
caps.latest.revision: 3
caps.handback.revision: 3
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Group&#39; non consentito in questo contesto. &#200; previsto l&#39;identificatore
La parola chiave `Group` è inclusa nella sezione `Into` sezione di una clausola `Aggregate`. La parola chiave `Group` è valida solo nelle clausole `Group By` o `Group Join`.  
  
 **ID errore:** BC36618  
  
### Per correggere l'errore  
  
-   Rimuovere la parola chiave `Group` dalla clausola `Aggregate`. È possibile aggiungere una clausola `Group By` alla query per raggruppare i risultati.  
  
## Vedere anche  
 [Aggregate Clause](/dotnet/visual-basic/language-reference/queries/aggregate-clause)   
 [Clausola Group By](/dotnet/visual-basic/language-reference/queries/group-by-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)