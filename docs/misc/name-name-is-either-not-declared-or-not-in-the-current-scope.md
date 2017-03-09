---
title: "Il nome &#39;&lt;nome&gt;&#39; non &#232; dichiarato o non &#232; nell&#39;ambito corrente | Microsoft Docs"
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
  - "vbc36610"
  - "bc36610"
helpviewer_keywords: 
  - "BC36610"
ms.assetid: e66a4b8a-9252-42ae-a30d-341fad4f74be
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Il nome &#39;&lt;nome&gt;&#39; non &#232; dichiarato o non &#232; nell&#39;ambito corrente
Una query LINQ fa riferimento a un elemento di programmazione, ma il compilatore non trova un elemento con quel nome esatto.  
  
 **ID errore:** BC36610  
  
### Per correggere l'errore  
  
1.  Controllare l'ortografia del nome nell'istruzione di riferimento.[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] non fa distinzione tra maiuscole e minuscole, ma qualsiasi altra variazione nell'ortografia costituisce un nome diverso. Si noti che il carattere di sottolineatura \(`_`\) fa parte del nome e quindi dell'ortografia.  
  
2.  Verificare che l'elemento di programmazione sia nell'ambito. Se l'istruzione di riferimento è all'esterno dell'area di dichiarazione dell'elemento di programmazione, è necessario qualificare il nome dell'elemento. Per altre informazioni, vedere [Scope in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/scope).  
  
3.  Assicurarsi di avere l'operatore di accesso ai membri \(`.`\) tra un oggetto e il relativo membro. Ad esempio, se è presente un controllo <xref:System.Windows.Forms.TextBox> denominato `TextBox1`, per accedere alla relativa proprietà <xref:System.Windows.Forms.TextBoxBase.Text%2A> occorre digitare `TextBox1.Text`. Se invece si digita `TextBox1Text`, viene creato un nome diverso.  
  
## Vedere anche  
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [Visual Basic Naming Conventions](/dotnet/visual-basic/programming-guide/program-structure/naming-conventions)   
 [References to Declared Elements](/dotnet/visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements)