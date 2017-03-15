---
title: "Modificatore &#39;Custom&#39; non valido negli eventi dichiarati nelle interfacce | Microsoft Docs"
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
  - "bc31121"
  - "vbc31121"
helpviewer_keywords: 
  - "BC31121"
ms.assetid: b5687034-a2b2-4961-88b7-0ba73023573e
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Modificatore &#39;Custom&#39; non valido negli eventi dichiarati nelle interfacce
Un evento personalizzato non può essere dichiarato in un'interfaccia perché un evento personalizzato deve fornire un'implementazione dei relativi metodi `AddHandler`, `RemoverHandler` e `RaiseEvent`.  
  
 La parola chiave `Custom` può essere usata in una classe derivata che implementa l'evento.  
  
 **ID errore:** BC31121  
  
### Per correggere l'errore  
  
-   Rimuovere la parola chiave `Custom` dalla dichiarazione di evento nell'interfaccia.  
  
## Esempio  
 Questo esempio illustra come implementare un evento dichiarato in un'interfaccia come evento personalizzato.  
  
 [!CODE [VbVbalrEventError#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#3)]  
  
## Vedere anche  
 [Custom \- eliminazione](http://msdn.microsoft.com/it-it/dc62be07-c896-4866-a533-982a661d143f)   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [Delegate Statement](/dotnet/visual-basic/language-reference/statements/delegate-statement)   
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)   
 [Interface Statement](/dotnet/visual-basic/language-reference/statements/interface-statement)   
 [Events](/dotnet/visual-basic/programming-guide/language-features/events/events)