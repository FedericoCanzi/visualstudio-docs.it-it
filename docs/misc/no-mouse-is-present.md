---
title: "Mouse non presente | Microsoft Docs"
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
  - "vbrMouse_NoMouseIsPresent"
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Mouse non presente
È stata chiamata una delle proprietà dell'oggetto `My.Computer.Mouse`, ma nel computer non è installato alcun mouse o porta del mouse.  
  
### Per correggere l'errore  
  
-   Aggiungere un blocco `Try...Catch` nella chiamata alla proprietà dell'oggetto `My.Computer.Mouse`.  
  
     oppure  
  
-   Installare un mouse del computer.  
  
## Vedere anche  
 [My.Computer.Mouse Object](/dotnet/visual-basic/language-reference/objects/my-computer-mouse-object)   
 [Gestione di eccezioni ed errori in Visual Basic](http://msdn.microsoft.com/it-it/3e351e73-cf23-40ab-8b60-05794160529e)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)