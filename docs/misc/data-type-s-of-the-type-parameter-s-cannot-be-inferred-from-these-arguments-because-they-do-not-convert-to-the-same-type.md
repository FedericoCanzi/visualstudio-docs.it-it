---
title: "Non &#232; possibile dedurre da questi argomenti i tipi di dati dei parametri di tipo perch&#233; non vengono convertiti nello stesso tipo | Microsoft Docs"
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
  - "vbc36659"
  - "bc36659"
  - "vbc36656"
  - "bc36656"
helpviewer_keywords: 
  - "BC36659"
  - "BC36656"
ms.assetid: 0aa809da-3b44-4d78-b3c5-0a148bdf7ce8
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Non &#232; possibile dedurre da questi argomenti i tipi di dati dei parametri di tipo perch&#233; non vengono convertiti nello stesso tipo
Non è possibile dedurre da questi argomenti i tipi di dati dei parametri di tipo perché non vengono convertiti nello stesso tipo. Per correggere l'errore, provare a specificare i tipi di dati in modo esplicito.  
  
 Questo errore si verifica quando la risoluzione dell'overload non riesce. Viene visualizzato come messaggio subordinato che indica perché un determinato candidato di overload è stato eliminato. L'errore spiega che il compilatore non può usare l'inferenza del tipo per trovare tipi di dati per i parametri di tipo che siano compatibili con gli argomenti.  
  
> [!NOTE]
>  Quando non è possibile specificare gli argomenti \(ad esempio per gli operatori di query nelle espressioni di query\), il messaggio di errore visualizzato non contiene la seconda frase.  
  
 Per altre informazioni ed esempi, vedere [Non è possibile dedurre da questi argomenti i tipi di dati dei parametri di tipo nel metodo '\<nomemetodo\>' perché non vengono convertiti nello stesso tipo](../Topic/Data%20type\(s\)%20of%20the%20type%20parameter\(s\)%20in%20method%20'%3Cmethodname%3E'%20cannot%20be%20inferred%20from%20these%20arguments%20because%20they%20do%20not%20convert%20to%20the%20same%20type.md).  
  
 **ID errore:** BC36659 e BC36656  
  
## Vedere anche  
 [Relaxed Delegate Conversion](/dotnet/visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)   
 [Overload Resolution](/dotnet/visual-basic/programming-guide/language-features/procedures/overload-resolution)