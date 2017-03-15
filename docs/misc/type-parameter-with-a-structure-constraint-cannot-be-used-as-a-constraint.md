---
title: "Impossibile utilizzare come vincolo il parametro di tipo con un vincolo &#39;Structure&#39; | Microsoft Docs"
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
  - "vbc32114"
  - "bc32114"
helpviewer_keywords: 
  - "BC32114"
ms.assetid: 442b2048-9dc4-4223-bcfc-4d96bf8d14de
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Impossibile utilizzare come vincolo il parametro di tipo con un vincolo &#39;Structure&#39;
Un parametro di tipo con un vincolo `Structure` viene usato come vincolo per un altro parametro di tipo.  
  
 Il vincolo `Structure` richiede che l'argomento di tipo passato al parametro di tipo sia un tipo valore. Tuttavia, un tipo valore non può essere implementato o ereditato, quindi non è significativo usarlo come vincolo, che richiederebbe all'altro parametro di tipo di implementarlo o ereditarlo da esso.  
  
 L'unica interpretazione significativa di questa situazione è che entrambi gli argomenti di tipo devono essere esattamente dello stesso tipo. In tal caso, il tipo generico richiede un solo parametro di tipo.  
  
 L'istruzione seguente può generare questo errore.  
  
 `Class c1(Of t1 As Structure, t2 As t1)`  
  
 Il tipo passato a `t2` non può implementare o ereditare il tipo passato a `t1`, perché il tipo passato a `t1` deve essere un tipo valore.  
  
 **ID errore:** BC32114  
  
### Per correggere l'errore  
  
-   Rimuovere il parametro di tipo vincolato a `Structure` dall'elenco di vincoli sull'altro parametro di tipo.  
  
-   Se entrambi i parametri di tipo richiedono lo stesso tipo valore, definire il tipo generico con un solo parametro di tipo.  
  
## Vedere anche  
 [Tipi generici in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)   
 [Structure \(Visual Basic\)](http://msdn.microsoft.com/it-it/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [Value Types and Reference Types](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)