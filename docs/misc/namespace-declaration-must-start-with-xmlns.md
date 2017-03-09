---
title: "La dichiarazione dello spazio dei nomi deve iniziare con &#39;xmlns&#39; | Microsoft Docs"
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
  - "bc31187"
  - "vbc31187"
helpviewer_keywords: 
  - "BC31187"
ms.assetid: 64c6a033-7cdc-48a0-bff0-bdd045cb13ad
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La dichiarazione dello spazio dei nomi deve iniziare con &#39;xmlns&#39;
Un spazio dei nomi XML è stato specificato senza l'identificatore `xmlns` obbligatorio. L'identificatore `xmlns` deve contenere solo caratteri minuscoli.  
  
 **ID errore:** BC31187  
  
### Per correggere l'errore  
  
-   Usare l'identificatore `xmlns` quando si dichiara uno spazio dei nomi XML. Di seguito è riportato un esempio:  
  
    ```vb#  
    Imports <xmlns:ns="http://SampleNamespace">  
    ```  
  
## Vedere anche  
 [Imports Statement \(XML Namespace\)](/dotnet/visual-basic/language-reference/statements/imports-statement-xml-namespace)   
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)