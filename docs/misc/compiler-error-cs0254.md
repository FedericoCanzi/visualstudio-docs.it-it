---
title: "Errore del compilatore CS0254 | Microsoft Docs"
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
  - "CS0254"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0254"
ms.assetid: 85b2ab1e-0011-4f1d-9181-76b9c9f3d914
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0254
La parte destra dell'assegnazione di un'istruzione fixed non può essere un'espressione cast  
  
 Il lato destro di un'espressione [fixed](/dotnet/csharp/language-reference/keywords/fixed-statement) non può usare un cast. Per altre informazioni, vedere [Codice unsafe e puntatori](/dotnet/csharp/programming-guide/unsafe-code-pointers/index).  
  
 L'esempio seguente genera l'errore CS0254:  
  
```  
// CS0254.cs // compile with: /unsafe class Point { public uint x, y; } class FixedTest { unsafe static void SquarePtrParam (int* p) { *p *= *p; } unsafe public static void Main() { Point pt = new Point(); pt.x = 5; pt.y = 6; fixed (int* p = (int*)&pt.x)   // CS0254 // try the following line instead // fixed (uint* p = &pt.x) { SquarePtrParam ((int*)p); } } }  
```