---
title: "Errore del compilatore CS0145 | Microsoft Docs"
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
  - "CS0145"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0145"
ms.assetid: e5f9a90f-1700-4e6a-8f82-23d0c0287b85
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0145
È necessario specificare un valore nel campo const  
  
 È necessario inizializzare una variabile [const](/dotnet/csharp/language-reference/keywords/const). Per altre informazioni, vedere [Costanti](/dotnet/csharp/programming-guide/classes-and-structs/constants).  
  
 L'esempio seguente genera l'errore CS0145:  
  
```  
// CS0145.cs class MyClass { const int i;   // CS0145 // try the following line instead // const int i = 0; public static void Main() { } }  
```