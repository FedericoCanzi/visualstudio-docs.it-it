---
title: "Errore del compilatore CS1611 | Microsoft Docs"
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
  - "CS1611"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1611"
ms.assetid: 48bfba77-6be2-4242-b1d2-98bf471b6d1e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS1611
Non è possibile dichiarare il parametro params come ref o out  
  
 Le parole chiave [ref](/dotnet/csharp/language-reference/keywords/ref) o [out](/dotnet/csharp/language-reference/keywords/out) non possono essere usate con la parola chiave [params](/dotnet/csharp/language-reference/keywords/params).  
  
 L'esempio seguente genera l'errore CS1611:  
  
```  
// CS1611.cs public class MyClass { public static void Test(params ref int[] a)   // CS1611, remove ref { } public static void Main() { Test(1); } }  
```