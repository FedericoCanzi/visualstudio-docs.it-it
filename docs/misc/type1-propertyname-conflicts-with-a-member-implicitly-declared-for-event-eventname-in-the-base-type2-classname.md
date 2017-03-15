---
title: "&lt;tipo1&gt; &#39;&lt;nomepropriet&#224;&gt;&#39; &#232; in conflitto con un membro dichiarato in modo implicito per l&#39;evento &lt;nomeevento&gt; nel &lt;tipo2&gt; &#39;&lt;nomeclasse&gt;&#39; di base | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40014"
  - "bc40014"
helpviewer_keywords: 
  - "BC40014"
ms.assetid: 100534b9-d533-4e94-a2a7-0ed26426965b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;tipo1&gt; &#39;&lt;nomepropriet&#224;&gt;&#39; &#232; in conflitto con un membro dichiarato in modo implicito per l&#39;evento &lt;nomeevento&gt; nel &lt;tipo2&gt; &#39;&lt;nomeclasse&gt;&#39; di base
Una proprietà è dichiarata con lo stesso nome di un membro implicito formato da un evento nella classe base. Se ad esempio la classe base definisce un evento denominato `Event1`, il compilatore genera le routine implicite `add_Event1` e `remove_Event1`. Se la proprietà della classe ha uno di questi nomi, dovrebbe nascondere il membro della classe base.  
  
 Si tratta di un messaggio di avviso. Per impostazione predefinita viene usato `Shadows`. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configurazione degli avvisi in Visual Basic](../ide/configuring-warnings-in-visual-basic.md).  
  
 **ID errore:** BC40014  
  
### Per correggere l'errore  
  
1.  Per nascondere il membro della classe base, aggiungere la parola chiave `Shadows` alla dichiarazione della proprietà.  
  
2.  Se non si intende nascondere il membro della classe base, cambiare il nome della proprietà.  
  
## Vedere anche  
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)