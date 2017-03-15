---
title: "Errore del compilatore CS0199 | Microsoft Docs"
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
  - "CS0199"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0199"
ms.assetid: 9eede3f2-b55a-4b85-a05d-6bf177e1c602
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0199
Non è possibile passare un parametro ref o out a campi del campo statico di sola lettura 'name' \(tranne che in un costruttore statico\)  
  
 Una variabile [readonly](/dotnet/csharp/language-reference/keywords/readonly) deve avere lo stesso utilizzo [statico](/dotnet/csharp/language-reference/keywords/static) del costruttore in cui si vuole passarlo come parametro [ref](/dotnet/csharp/language-reference/keywords/ref) o [out](/dotnet/csharp/language-reference/keywords/out). Per altre informazioni, vedere [Passaggio di parametri](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters).  
  
## Esempio  
 L'esempio seguente genera l'errore CS0199:  
  
```  
// CS0199.cs class MyClass { public static readonly int TestInt = 6; static void TestMethod(ref int testInt) { testInt = 0; } MyClass() { TestMethod(ref TestInt);   // CS0199, TestInt is static } public static void Main() { } }  
```