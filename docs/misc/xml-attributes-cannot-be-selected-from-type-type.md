---
title: "Impossibile selezionare attributi XML dal tipo &#39;type&#39; | Microsoft Docs"
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
  - "bc36808"
  - "vbc36808"
helpviewer_keywords: 
  - "BC36808"
ms.assetid: 76b2605c-3d9b-4e56-ba3f-99c60c668290
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Impossibile selezionare attributi XML dal tipo &#39;type&#39;
È stato fatto riferimento a un attributo XML per un oggetto che non è di tipo <xref:System.Xml.Linq.XElement> o `IEnumerable(Of XElement)`. Per altre informazioni, vedere [XML Attribute Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-attribute-axis-property).  
  
```vb#  
' Generates an error. Dim var = "sample text".@attr  
```  
  
 **ID errore:** BC36808  
  
### Per correggere l'errore  
  
-   Se si fa riferimento a un attributo di un oggetto, quest'ultimo deve essere fortemente tipizzato come <xref:System.Xml.Linq.XElement> o `IEnumerable(Of XElement)`. Di seguito è riportato un esempio:  
  
    ```vb#  
    Dim elem As XElement = <root attr="value"/> Dim var = elem.@attr  
    ```  
  
## Vedere anche  
 [XML Attribute Axis Property](/dotnet/visual-basic/language-reference/xml-axis/xml-attribute-axis-property)   
 [XML Axis Properties](/dotnet/visual-basic/language-reference/xml-axis/xml-axis-properties)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)