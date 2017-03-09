---
title: "Errore del compilatore CS0227 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0227"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0227"
ms.assetid: b595a1c9-8204-4ff7-a1d0-258b0b1d6ff7
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Errore del compilatore CS0227
Il codice di tipo unsafe è ammesso solo se si compila con \/unsafe  
  
 Se il codice sorgente contiene la parola chiave [unsafe](/dotnet/csharp/language-reference/keywords/unsafe), è necessario usare anche l'opzione del compilatore [\/unsafe](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option). Per altre informazioni, vedere [Codice unsafe e puntatori](/dotnet/csharp/programming-guide/unsafe-code-pointers/index).  
  
 Per impostare l'opzione unsafe in [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)], fare clic su **Progetto** nel menu principale, selezionare il riquadro **Compilazione** e quindi selezionare la casella "Consenti codice di tipo unsafe".  
  
 L'esempio seguente, quando viene compilato senza **\/unsafe**, genera l'errore CS0227:  
  
```  
// CS0227.cs public class MyClass { unsafe public static void Main()   // CS0227 { } }  
```  
  
## Vedere anche  
 [C\# Compiler Errors](/dotnet/csharp/language-reference/compiler-messages/index)