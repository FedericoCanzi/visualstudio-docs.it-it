---
title: "L&#39;attributo XML &#39;attribute1&#39; deve essere specificato prima dell&#39;attributo XML &#39;attribute2&#39; | Microsoft Docs"
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
  - "bc31157"
  - "vbc31157"
helpviewer_keywords: 
  - "BC31157"
ms.assetid: d8d8769e-533d-454e-b145-99955ce45cc5
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# L&#39;attributo XML &#39;attribute1&#39; deve essere specificato prima dell&#39;attributo XML &#39;attribute2&#39;
Gli attributi in un valore letterale di documento XML sono specificati in un ordine non valido. L'ordine valido degli attributi per un valore letterale di documento XML è basato sulla specifica XML 1.0. Ad esempio, l'attributo `encoding` di un valore letterale di documento XML deve essere posto immediatamente dopo l'attributo `version`.  
  
 **ID errore:** BC31157  
  
### Per correggere l'errore  
  
-   Aggiornare l'ordine degli attributi per il valore letterale di documento XML usando le linee guida indicate nella specifica XML 1.0.  
  
## Vedere anche  
 [XML Literals and the XML 1.0 Specification](/dotnet/visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification)   
 [XML Document Literal](/dotnet/visual-basic/language-reference/xml-literals/xml-document-literal)   
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)