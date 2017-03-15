---
title: "Impossibile trovare &#39;&lt;nomeroutine&gt;&#39; non generico accessibile | Microsoft Docs"
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
  - "vbc32117"
  - "bc32117"
helpviewer_keywords: 
  - "BC32117"
ms.assetid: a7bf8b67-8a0a-499e-9992-dc00e09b7ff4
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Impossibile trovare &#39;&lt;nomeroutine&gt;&#39; non generico accessibile
Un'istruzione consente di chiamare una routine con più di una versione di overload, ma dal momento che tutte le versioni sono generiche, la chiamata non fornisce argomenti di tipo.  
  
 In presenza di un'unica versione generica che è possibile chiamare senza argomenti di tipo, il compilatore potrà provare a eseguire un'*inferenza del tipo*. Per altre informazioni, vedere "Inferenza di tipi" in [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures). In presenza di più versioni generiche, tuttavia, il compilatore non riesce a effettuare una scelta se non vengono forniti gli argomenti di tipo. Se viene fornito un solo argomento di tipo, è necessario fornirne uno per ogni parametro di tipo definito da una delle versioni di overload.  
  
 **ID errore:** BC32117  
  
### Per correggere l'errore  
  
-   Chiamare la routine con un elenco di argomenti di tipo.  
  
## Vedere anche  
 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads)   
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)   
 [Tipi generici in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)