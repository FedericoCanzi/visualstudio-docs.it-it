---
title: "Impossibile importare pi&#249; volte il tipo generico &#39;&lt;nometipogenerico&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BC32086"
  - "vbc32086"
helpviewer_keywords: 
  - "BC32086"
ms.assetid: d93bae4b-3224-4a6e-a072-8ce231084519
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Impossibile importare pi&#249; volte il tipo generico &#39;&lt;nometipogenerico&gt;&#39;
Un'[Imports Statement \(.NET Namespace and Type\)](/dotnet/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type) specifica un tipo generico già importato con una parametrizzazione di tipo diverso.  
  
 È possibile dichiarare più tipi costruiti da un tipo generico perché la dichiarazione di un tipo costruito non ridefinisce il tipo generico. Tuttavia, più importazioni di un tipo generico equivalgono a diverse definizioni.  
  
 **ID errore:** BC32086  
  
### Per correggere l'errore  
  
1.  Se il file di origine che contiene questa istruzione `Imports` include un'altra istruzione `Imports` che specifica lo stesso tipo generico, rimuoverne una.  
  
2.  Se è necessario importare lo stesso tipo generico con altre parametrizzazioni di tipo, usare più file di origine.  
  
## Vedere anche  
 [Tipi generici in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)