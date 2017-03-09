---
title: "Errore del compilatore CS0205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0205"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0205"
ms.assetid: 616d98cf-e7a5-4f8e-93da-fcd6e1e4de35
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0205
Impossibile chiamare un membro di base astratto: 'method'  
  
 Non è possibile chiamare un metodo [abstract](/dotnet/csharp/language-reference/keywords/abstract) perché non ha un corpo del metodo. Per altre informazioni, vedere [Classi e membri delle classi astratte e sealed](/dotnet/csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members).  
  
 L'esempio seguente genera l'errore CS0205:  
  
```  
// CS0205.cs abstract public class MyClass { abstract public void M(); } public class MyClass2 : MyClass { public override void M() { base.M();   // CS0205, delete this line } public static void Main() { } }  
```