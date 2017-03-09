---
title: "La creazione di rami all&#39;esterno di &#39;Finally&#39; non &#232; valida | Microsoft Docs"
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
  - "bc30101"
  - "vbc30101"
helpviewer_keywords: 
  - "BC30101"
ms.assetid: 16a0dc29-3657-4373-b77f-38f3cb80e6c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La creazione di rami all&#39;esterno di &#39;Finally&#39; non &#232; valida
Un'istruzione `GoTo` all'interno di un blocco `Finally` crea rami all'esterno del blocco. La creazione di rami all'interno o all'esterno di un blocco `Catch` o `Finally` non è consentita.  
  
 **ID errore:** BC30101  
  
### Per correggere l'errore  
  
-   Rimuovere l'istruzione `GoTo` e provare a implementare la logica di programma con strutture di controllo del ciclo o delle decisioni.  
  
## Vedere anche  
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)   
 [GoTo Statement](/dotnet/visual-basic/language-reference/statements/goto-statement)   
 [Control Flow](/dotnet/visual-basic/programming-guide/language-features/control-flow/index)