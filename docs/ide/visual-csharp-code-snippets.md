---
title: Frammenti di codice Visual C# | Microsoft Docs
ms.custom: 
ms.date: 06/05/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- snippets [C#], default snippets
- snippets [C#], Code Snippet Inserter
- Code Snippet Inserter [J#]
- Code Snippet Inserter [C#]
- Visual C#, default snippets
ms.assetid: dbea3dd6-e650-4190-b874-c9f097d7de6e
caps.latest.revision: 33
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 5f996aff0c247db658f3b9f1fec666792751ae11
ms.openlocfilehash: 407ef81649de1c62d91d5a79535a8f9c67feb97c
ms.contentlocale: it-it
ms.lasthandoff: 06/06/2017

---
# <a name="visual-c-code-snippets"></a>Frammenti di codice Visual C#
I frammenti di codice sono piccole porzioni di codice pronte all'uso che si possono inserire rapidamente nel codice. Ad esempio, il frammento di codice `for` crea un ciclo `for` vuoto. Alcuni frammenti di codice sono frammenti racchiusi, che consentono di selezionare righe di codice e quindi scegliere un frammento di codice che incorpora le righe di codice selezionate. Ad esempio, quando si selezionano righe di codice e si attiva il frammento di codice `for`, viene creato un ciclo `for` con le righe di codice all'interno del blocco del ciclo. I frammenti di codice possono rendere la scrittura del codice dei programmi più veloce, più semplice e più affidabile.  

 È possibile inserire un frammento di codice nella posizione del cursore o un frammento di codice racchiuso intorno al codice attualmente selezionato. Lo strumento per l'inserimento dei frammenti di codice viene richiamato usando i comandi **Inserisci frammento di codice** o **Racchiudi tra** del menu **IntelliSense** o usando i tasti di scelta rapida CTRL+K e quindi X o CTRL+K e quindi S rispettivamente.  

 Lo strumento per l'inserimento dei frammenti di codice visualizza il nome del frammento di codice per tutti i frammenti di codice disponibili. Lo strumento include anche una finestra di dialogo di input in cui è possibile digitare il nome del frammento di codice o parte del nome del frammento di codice. Lo strumento per l'inserimento dei frammenti di codice evidenzia la corrispondenza più prossima al nome di un frammento di codice. Quando si preme TAB in qualsiasi momento lo strumento per l'inserimento dei frammenti di codice viene chiuso e viene inserito il frammento di codice attualmente selezionato. Se si preme ESC o si fa clic con il mouse nell'Editor di codice, lo strumento per l'inserimento dei frammenti di codice viene chiuso senza inserire un frammento di codice.  

## <a name="default-code-snippets"></a>Frammenti di codice predefiniti  
 Per impostazione predefinita in Visual Studio sono inclusi i frammenti di codice riportati di seguito.  

|Nome (o collegamento)|Descrizione|Percorsi validi per l'inserimento del frammento di codice|  
|--------------------------|-----------------|---------------------------------------|  
|#if|Crea una direttiva [#if](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-if) e una direttiva [#endif](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endif).|Ovunque.|  
|#region|Crea una direttiva [#region](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-region) e una direttiva [#endregion](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endregion).|Ovunque.|  
|~|Crea un distruttore per la classe contenitore.|All'interno di una classe.|  
|Attributo|Crea una dichiarazione per una classe che deriva da <xref:System.Attribute>.|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale), una classe o uno struct.|  
|checked|Crea un blocco [checked](/dotnet/csharp/language-reference/keywords/checked).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|classe|Crea una dichiarazione di classe.|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale), una classe o uno struct.|  
|ctor|Crea un costruttore per la classe contenitore.|All'interno di una classe.|  
|cw|Crea una chiamata a <xref:System.Console.WriteLine%2A>.|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|do|Crea un ciclo [do](/dotnet/csharp/language-reference/keywords/do) `while`.|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|else|Crea un blocco [else](/dotnet/csharp/language-reference/keywords/if-else).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|enum|Crea una dichiarazione [enum](/dotnet/csharp/language-reference/keywords/enum).|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale), una classe o uno struct.|  
|equals|Crea una dichiarazione di metodo che esegue l'override del metodo <xref:System.Object.Equals%2A> definito nella classe <xref:System.Object>.|All'interno di una classe o uno struct.|  
|exception|Crea una dichiarazione per una classe che deriva da un'eccezione (<xref:System.Exception> per impostazione predefinita).|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale), una classe o uno struct.|  
|for|Crea un ciclo [for](/dotnet/csharp/language-reference/keywords/for).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|foreach|Crea un ciclo [foreach](/dotnet/csharp/language-reference/keywords/foreach-in).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|forr|Crea un ciclo [for](/dotnet/csharp/language-reference/keywords/for) che decrementa la variabile di ciclo dopo ogni iterazione.|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|if|Crea un blocco [if](/dotnet/csharp/language-reference/keywords/if-else).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|indicizzatore|Crea una dichiarazione di indicizzatore.|All'interno di una classe o uno struct.|  
|interfaccia|Crea una dichiarazione [interface](/dotnet/csharp/language-reference/keywords/interface).|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale), una classe o uno struct.|  
|invoke|Crea un blocco che richiama in modo sicuro un evento.|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|iteratore|Crea un iteratore.|All'interno di una classe o uno struct.|  
|iterindex|Crea una coppia iteratore/indicizzatore "denominata" usando una classe annidata.|All'interno di una classe o uno struct.|  
|blocco|Crea un blocco [lock](/dotnet/csharp/language-reference/keywords/lock-statement).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|mbox|Crea una chiamata a <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>. Può essere necessario aggiungere un riferimento a System.Windows.Forms.dll.|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|namespace|Crea una dichiarazione [namespace](/dotnet/csharp/language-reference/keywords/namespace).|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale).|  
|prop|Crea una dichiarazione di [proprietà implementata automaticamente](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties).|All'interno di una classe o uno struct.|  
|propfull|Crea una dichiarazione di proprietà con le funzioni di accesso `get` e `set`.|All'interno di una classe o uno struct.|  
|propg|Crea una [proprietà implementata automaticamente](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties) di sola lettura con una funzione di accesso `set` privata.|All'interno di una classe o uno struct.|  
|sim|Crea una dichiarazione [static](/dotnet/csharp/language-reference/keywords/static) [int](/dotnet/csharp/language-reference/keywords/int) del metodo Main.|All'interno di una classe o uno struct.|  
|struct|Crea una dichiarazione [struct](/dotnet/csharp/language-reference/keywords/struct).|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale), una classe o uno struct.|  
|svm|Crea una dichiarazione [static](/dotnet/csharp/language-reference/keywords/static) [void](/dotnet/csharp/language-reference/keywords/void) del metodo Main.|All'interno di una classe o uno struct.|  
|switch|Crea un blocco [switch](/dotnet/csharp/language-reference/keywords/switch).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|try|Crea un blocco [try-catch](/dotnet/csharp/language-reference/keywords/try-catch).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|tryf|Crea un blocco [try-finally](/dotnet/csharp/language-reference/keywords/try-finally).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|unchecked|Crea un blocco [unchecked](/dotnet/csharp/language-reference/keywords/unchecked).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|unsafe|Crea un blocco [unsafe](/dotnet/csharp/language-reference/keywords/unsafe).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  
|utilizzo|Crea una direttiva [using](/dotnet/csharp/language-reference/keywords/using-directive).|All'interno di uno spazio dei nomi (incluso lo spazio dei nomi globale).|  
|while|Crea un ciclo [while](/dotnet/csharp/language-reference/keywords/while).|All'interno di un metodo, un indicizzatore, una funzione di accesso proprietà o una funzione di accesso eventi.|  

## <a name="see-also"></a>Vedere anche  
 [Funzioni dei frammenti di codice](../ide/code-snippet-functions.md)   
 [Frammenti di codice](../ide/code-snippets.md)   
 [Parametri di modello](../ide/template-parameters.md)   
 [Procedura: Usare frammenti di codice racchiusi](../ide/how-to-use-surround-with-code-snippets.md)   

