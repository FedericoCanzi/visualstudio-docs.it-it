---
title: "&#200; previsto &#39;Into&#39; | Microsoft Docs"
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
  - "bc36615"
  - "vbc36615"
helpviewer_keywords: 
  - "BC36615"
ms.assetid: 24062dd9-a973-43b6-88d3-c11adc5a3736
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#200; previsto &#39;Into&#39;
Una clausola `Aggregate`, `Group By` o `Group Join` è stata specificata senza un operatore `Into`. Usare l'operatore `Into` per identificare le funzioni di aggregazione da applicare al risultato della query e per identificare il membro del tipo di risultato della query per contenere i risultati raggruppati \(usando la funzione di aggregazione `Group`\).  
  
 **ID errore:** BC36615  
  
### Per correggere l'errore  
  
1.  Aggiungere l'operatore `Into` per la clausola `Aggregate`, `Group By` o `Group Join`. Di seguito è riportato un esempio:  
  
    ```vb#  
    Dim orders = From order In orderList _ Order By order.OrderDate _ Group By OrderDate = order.OrderDate _ Into OrdersByDate = Group  
    ```  
  
## Vedere anche  
 [Aggregate Clause](/dotnet/visual-basic/language-reference/queries/aggregate-clause)   
 [Clausola Group By](/dotnet/visual-basic/language-reference/queries/group-by-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)