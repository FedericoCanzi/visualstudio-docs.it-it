---
title: "&#39;&lt;nomevariabile&gt;&#39; &#232; di tipo ambiguo perch&#233; i limiti del ciclo e la clausola step non eseguono la conversione nello stesso tipo | Microsoft Docs"
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
  - "vbc30983"
  - "bc30983"
helpviewer_keywords: 
  - "BC30983"
ms.assetid: 6b97153c-dee3-4429-b92a-2e5a212c864b
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nomevariabile&gt;&#39; &#232; di tipo ambiguo perch&#233; i limiti del ciclo e la clausola step non eseguono la conversione nello stesso tipo
Il codice contiene un ciclo `For...Next` nel quale il compilatore non è in grado di dedurre un tipo di dati per la variabile di controllo del ciclo perché si verificano le condizioni seguenti:  
  
-   Il tipo di dati della variabile di controllo del ciclo non è specificato con una clausola `As`.  
  
-   I limiti del ciclo e la clausola step contengono almeno due tipi di dati.  
  
-   Esistono più possibili conversioni tra i tipi di dati.  
  
-   Non esiste un tipo migliore fra i candidati, pertanto la scelta del tipo per la variabile di controllo del ciclo è ambigua.  
  
 Ad esempio, il ciclo seguente contiene un limite del ciclo di tipo `Integer` e un limite del ciclo di tipo `UInteger`:  
  
```vb#  
Dim m As Integer = 1 Dim n As UInteger = 10 ' Not valid. ' For i = m To n ' Loop processing. ' Next  
```  
  
 C'è una possibile conversione tra `Integer` e `UInteger` e una possibile conversione tra `UInteger` e `Integer`, ma sono entrambe conversioni verso un tipo di dati più piccolo, pertanto nessuna di esse è la migliore scelta.  
  
 Nel prossimo esempio viene aggiunta una terza variabile di tipo `Double`.`Integer` e `UInteger` hanno conversioni standard verso il tipo di dati più grande `Double`, il che rende la conversione a `Double` la migliore scelta. L'inferenza del tipo assegna alla variabile di controllo del ciclo `i` il tipo di dati `Double`.  
  
```vb#  
Dim stepVar As Double = 1 ' Valid. For i = m To n Step stepVar ' Loop processing. Next  
```  
  
 **ID errore:** BC30983  
  
### Per correggere l'errore  
  
-   Convertire esplicitamente una delle variabili in un tipo per cui le altre variabili hanno una conversione verso un tipo di dati più grande, ad esempio:  
  
    ```  
    For i = m To CLng(n)  
    ```  
  
-   Usare una clausola `As` per specificare il tipo della variabile di controllo:  
  
    ```  
    For i As Double = m To n   
    ```  
  
## Vedere anche  
 [Istruzione For...Next](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [Implicit and Explicit Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions)   
 [Local Type Inference](/dotnet/visual-basic/programming-guide/language-features/variables/local-type-inference)   
 [Option Infer Statement](/dotnet/visual-basic/language-reference/statements/option-infer-statement)   
 [Widening and Narrowing Conversions](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions)