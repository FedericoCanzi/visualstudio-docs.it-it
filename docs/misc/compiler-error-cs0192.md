---
title: "Errore del compilatore CS0192 | Microsoft Docs"
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
  - "CS0192"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0192"
ms.assetid: d3fb6d18-dbf3-42c3-a280-afe55b97c2d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0192
Non è possibile passare un parametro ref o out a campi del campo statico di sola lettura 'name' \(tranne che in un costruttore statico\)  
  
 Un campo \(variabile\) contrassegnato con la parola chiave [readonly](/dotnet/csharp/language-reference/keywords/readonly) non può essere passato a un parametro [ref](/dotnet/csharp/language-reference/keywords/ref) o [out](/dotnet/csharp/language-reference/keywords/out) tranne che all'interno di un costruttore. Per altre informazioni, vedere [Campi](/dotnet/csharp/programming-guide/classes-and-structs/fields).  
  
 L'errore CS0192 viene generato anche se il campo `readonly` è [statico](/dotnet/csharp/language-reference/keywords/static) e il costruttore non è contrassegnato come `static`.  
  
## Esempio  
 L'esempio seguente genera l'errore CS0192.  
  
```  
// CS0192.cs class MyClass { public readonly int TestInt = 6; static void TestMethod(ref int testInt) { testInt = 0; } MyClass() { TestMethod(ref TestInt);   // OK } public void PassReadOnlyRef() { TestMethod(ref TestInt);   // CS0192 } public static void Main() { } }  
```