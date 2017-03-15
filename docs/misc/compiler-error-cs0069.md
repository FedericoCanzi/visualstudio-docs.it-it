---
title: "Errore del compilatore CS0069 | Microsoft Docs"
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
  - "CS0069"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0069"
ms.assetid: a1b32906-7773-47c6-8515-162a201a9be5
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0069
Un evento in un'interfaccia non può avere funzioni di accesso add o remove  
  
 Non è possibile definire le funzioni di accesso di un evento in un'[interfaccia](/dotnet/csharp/language-reference/keywords/interface). Per altre informazioni, vedere [Eventi](/dotnet/csharp/programming-guide/events/index) e [Interfacce](/dotnet/csharp/programming-guide/interfaces/index).  
  
 L'esempio seguente genera l'errore CS0069:  
  
```  
// CS0069.cs // compile with: /target:library public delegate void EventHandler(); public interface a { event EventHandler Click { remove {} }   // CS0069 event EventHandler Click2;   // OK }  
```