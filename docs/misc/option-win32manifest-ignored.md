---
title: "Opzione /win32manifest ignorata | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc2034"
  - "bc2034"
helpviewer_keywords: 
  - "BC2034"
ms.assetid: 8009553a-f6ba-4d2b-8ddd-8a9357bc928e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Opzione /win32manifest ignorata
Opzione \/win32manifest ignorata. Può essere specificata solo quando la destinazione è un assembly.  
  
 Al compilatore Visual Basic è stata passata l'opzione `/win32manifest` del compilatore quando l'opzione `/target` è impostata su `module`.  
  
 **ID errore:** BC2034  
  
### Per correggere l'errore  
  
1.  Rimuovere l'opzione `/win32manifest` del compilatore o impostare l'opzione `/target` su `exe`, `winexe` o `library`.  
  
## Vedere anche  
 [\/target](/dotnet/visual-basic/reference/command-line-compiler/target)   
 [\/win32manifest](/dotnet/visual-basic/reference/command-line-compiler/win32manifest)   
 [Visual Basic Command\-Line Compiler](/dotnet/visual-basic/reference/command-line-compiler/index)