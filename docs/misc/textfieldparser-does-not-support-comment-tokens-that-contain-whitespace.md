---
title: "TextFieldParser non supporta token di commento che contengono spazi vuoti | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrTextFieldParser_WhitespaceInToken"
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# TextFieldParser non supporta token di commento che contengono spazi vuoti
È stato fornito un token di commento che contiene spazi vuoti.`TextFieldParser` non supporta i token di commento che contengono spazi vuoti a meno che lo spazio vuoto non sia presente all'inizio del token. Gli spazi vuoti all'inizio di un token vengono ignorati.  
  
### Per correggere l'errore  
  
-   Fornire un token di commento corretto.  
  
## Vedere anche  
 [Proprietà TextFieldParser.CommentTokens](http://msdn.microsoft.com/it-it/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)   
 [Parsing Text Files with the TextFieldParser Object](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object)   
 [TextFieldParser Object](/dotnet/visual-basic/language-reference/objects/textfieldparser-object)