---
title: "Errore del compilatore CS0666 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0666"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0666"
ms.assetid: 44ad4574-b4a2-487b-8d05-0116762231ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0666
'member': in struct è stato dichiarato il nuovo membro protetto  
  
 Uno [struct](/dotnet/csharp/language-reference/keywords/struct) non può essere [abstract](/dotnet/csharp/language-reference/keywords/abstract) ed è sempre implicitamente [sealed](/dotnet/csharp/language-reference/keywords/sealed). Poiché gli struct non supportano l'ereditarietà, il concetto di un membro [protected](/dotnet/csharp/language-reference/keywords/protected) in uno struct non ha senso. Per altre informazioni, vedere [Ereditarietà](/dotnet/csharp/programming-guide/classes-and-structs/inheritance).  
  
## Esempio  
 L'esempio seguente genera l'errore CS0666:  
  
```  
// CS0666.cs class M { static void Main() { } } struct S { protected int x;   // CS0666 }  
```