---
title: "Previsto &#39;%=&#39; all&#39;inizio di un&#39;espressione incorporata | Microsoft Docs"
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
  - "vbc31179"
  - "bc31179"
helpviewer_keywords: 
  - "BC31179"
ms.assetid: 20b0382e-1744-47e4-84e1-7fc926cbc4df
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Previsto &#39;%=&#39; all&#39;inizio di un&#39;espressione incorporata
L'identificatore iniziale per un'espressione incorporata, `<%=`, non è stato codificato correttamente. Si noti che non è possibile usare un carattere percentuale \(%\) nel nome di un valore letterale elemento XML.  
  
 **ID errore:** BC31179  
  
### Per correggere l'errore  
  
-   Verificare che l'identificatore iniziale per l'espressione incorporata sia codificato come `<%=`.  
  
## Vedere anche  
 [Embedded Expressions in XML](/dotnet/visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml)   
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)