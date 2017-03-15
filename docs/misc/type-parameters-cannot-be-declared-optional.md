---
title: "I parametri di &lt;tipo&gt; non possono essere dichiarati come &#39;Optional&#39; | Microsoft Docs"
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
  - "bc33010"
  - "vbc33010"
helpviewer_keywords: 
  - "BC33010"
ms.assetid: ec4023e7-9ba6-4532-a6b9-4ae6b4f9063a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# I parametri di &lt;tipo&gt; non possono essere dichiarati come &#39;Optional&#39;
Una definizione di un delegato, di un evento o di un operatore dichiara un parametro [Optional](/dotnet/visual-basic/language-reference/modifiers/optional).  
  
 I parametri `Optional` sono consentiti solo per i parametri `Declare`, `Function`, `Property` e `Sub`.  
  
 **ID errore:** BC33010  
  
### Per correggere l'errore  
  
-   Rimuovere la parola chiave `Optional` dall'elenco di parametri.  
  
-   Se si sta definendo un operatore, può essere possibile ottenere la funzionalità `Optional` con una serie di overload.  
  
-   Se si sta definendo un delegato o un evento, è necessario rielaborare la logica complessiva di questa parte di applicazione. Non è possibile usare i parametri `Optional` o [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray), oppure versioni di overload, per parametri del delegato o di evento.  
  
## Vedere anche  
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)