---
title: "I tipi nullable non sono consentiti nelle espressioni di compilazione condizionale | Microsoft Docs"
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
  - "bc33111"
  - "vbc33111"
helpviewer_keywords: 
  - "BC33111"
ms.assetid: 2c2587e5-2179-4a31-bcf7-7004db6f2d73
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# I tipi nullable non sono consentiti nelle espressioni di compilazione condizionale
Un tipo nullable non può essere usato nell'espressione di una direttiva di compilazione condizionale. Il codice seguente, ad esempio, causa questo errore.  
  
```vb#  
'#Const triggerPoint = 0 '' Not valid. '#If CType(triggerpoint, Boolean?) = True Then '        ' Body of the conditional directive. '#End If  
```  
  
 **ID errore:** BC33111  
  
### Per correggere l'errore  
  
-   Rimuovere la designazione di tipo nullable.  
  
## Vedere anche  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)   
 [\#If...Then...\#Else Directives](/dotnet/visual-basic/language-reference/directives/if-then-else-directives)   
 [Conditional Compilation](/dotnet/visual-basic/programming-guide/program-structure/conditional-compilation)