---
title: "&#39;&lt;propriet&#224;1&gt;&#39; e &#39;&lt;propriet&#224;2&gt;&#39; non possono essere in rapporto di overload perch&#233; solo uno &#232; dichiarato come &#39;Default&#39; | Microsoft Docs"
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
  - "bc30361"
  - "vbc30361"
helpviewer_keywords: 
  - "BC30361"
ms.assetid: bac85b32-1a1f-4c43-817c-76e209cfeb8c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;propriet&#224;1&gt;&#39; e &#39;&lt;propriet&#224;2&gt;&#39; non possono essere in rapporto di overload perch&#233; solo uno &#232; dichiarato come &#39;Default&#39;
Se una proprietà specifica `Default`, tutte le proprietà di overload nel nome devono specificare anche `Default`.  
  
 **ID errore:** BC30361  
  
### Per correggere l'errore  
  
-   Verificare che tutte le proprietà di overload siano dichiarate come `Default`.  
  
## Vedere anche  
 [Considerations in Overloading Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures)   
 [Default](/dotnet/visual-basic/language-reference/modifiers/default)