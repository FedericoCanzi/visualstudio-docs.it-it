---
title: "Errore del compilatore CS0107 | Microsoft Docs"
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
  - "CS0107"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0107"
ms.assetid: 505763c5-6d68-4c57-a8bd-7b03682da4c5
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0107
Sono presenti più modificatori di protezione  
  
 In un membro di classe è consentito solo un modificatore di accesso \([public](/dotnet/csharp/language-reference/keywords/public), [private](/dotnet/csharp/language-reference/keywords/private), [protected](/dotnet/csharp/language-reference/keywords/protected) o [internal](/dotnet/csharp/language-reference/keywords/internal)\), con l'eccezione di **internal protected**.  
  
 L'esempio seguente genera l'errore CS0107:  
  
```  
// CS0107.cs public class C { private internal void f()   // CS0107, delete private or internal { } public static int Main() { return 1; } }  
```