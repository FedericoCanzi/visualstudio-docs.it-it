---
title: "Errore del compilatore CS0160 | Microsoft Docs"
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
  - "CS0160"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0160"
ms.assetid: 4ef07061-8ef5-42d9-b043-3f81307d569f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0160
Una clausola catch precedente rileva già tutte le eccezioni del tipo this o super \('type'\)  
  
 Una serie di istruzioni **catch** deve essere in ordine di derivazione decrescente. Ad esempio, gli oggetti più derivati devono essere visualizzati per prima.  
  
 Per altre informazioni, vedere [Istruzioni di gestione delle eccezioni](/dotnet/csharp/language-reference/keywords/exception-handling-statements) e [Eccezioni e gestione delle eccezioni](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling).  
  
 L'esempio seguente genera l'errore CS0160:  
  
```  
// CS0160.cs public class MyClass2 : System.Exception {} public class MyClass { public static void Main() { try {} catch(System.Exception) {}   // Second-most derived; should be second catch catch(MyClass2) {}   // CS0160  Most derived; should be first catch } }  
```