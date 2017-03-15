---
title: "Lo spazio dei nomi radice &lt;nomespaziodeinomi&gt; non &#232; conforme a CLS | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40038"
  - "vbc40038"
helpviewer_keywords: 
  - "BC40038"
ms.assetid: ec850295-b2fe-4f19-b808-d22fe0aaa32d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Lo spazio dei nomi radice &lt;nomespaziodeinomi&gt; non &#232; conforme a CLS
Un assembly è contrassegnato come `<CLSCompliant(True)>`, ma il nome dello spazio dei nomi radice inizia con un carattere di sottolineatura \(`_`\).  
  
 Un elemento di programmazione può contenere uno o più caratteri di sottolineatura, ma per la conformità con [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) non può iniziare con un segno di sottolineatura. Vedere [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names).  
  
 Quando <xref:System.CLSCompliantAttribute> viene applicato a un elemento di programmazione, il parametro `isCompliant` dell'attributo viene impostato su `True` o `False` per indicare la conformità o la non conformità. L'impostazione predefinita per questo parametro non è disponibile, quindi è necessario specificare un valore.  
  
 Se a un elemento non viene applicato <xref:System.CLSCompliantAttribute>, l'elemento non sarà considerato conforme.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configurazione degli avvisi in Visual Basic](../ide/configuring-warnings-in-visual-basic.md).  
  
 **ID errore:** BC40038  
  
### Per correggere l'errore  
  
-   Per la conformità con CLS, modificare il nome dello spazio dei nomi radice in modo che non inizi con un carattere di sottolineatura.  
  
-   Se è necessario lasciare invariato il nome dello spazio dei nomi radice, rimuovere <xref:System.CLSCompliantAttribute> dall'assembly o contrassegnarlo come `<CLSCompliant(False)>`.  
  
## Vedere anche  
 [Namespace Statement](/dotnet/visual-basic/language-reference/statements/namespace-statement)   
 [Spazi dei nomi in Visual Basic](/dotnet/visual-basic/programming-guide/program-structure/namespaces)   
 [\/rootnamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace)   
 [NIB: Procedura: Cambiare lo spazio dei nomi per un'applicazione \(Visual Basic\)](http://msdn.microsoft.com/it-it/029d85c0-e173-4f7a-afba-a29f3aaf6ebf)   
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)   
 [Visual Basic Naming Conventions](/dotnet/visual-basic/programming-guide/program-structure/naming-conventions)   
 [\<PAVE OVER\> Scrittura di codice conforme a CLS](http://msdn.microsoft.com/it-it/4c705105-69a2-4e5e-b24e-0633bc32c7f3)