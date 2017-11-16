---
title: Uso delle espressioni regolari in Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vsregularexpressionhelp
- vs.regularexpressionhelp
- vs.wildcardsbuilder
- vs.netregularexpressionhelp
- vs.wildcards
helpviewer_keywords:
- regular expressions [Visual Studio]
- regular expressions
- Visual Studio, regular expressions
ms.assetid: 718a617d-0e05-47e1-a218-9746971527f4
caps.latest.revision: "53"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c01023649879c34838cbca3172aec6b5a053f4bd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="using-regular-expressions-in-visual-studio"></a>Utilizzo delle espressioni regolari in Visual Studio
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] usa espressioni regolari di .NET Framework per trovare e sostituire il testo. Per altre informazioni sulle espressioni regolari di .NET, vedere [Espressioni regolari di .NET Framework](/dotnet/standard/base-types/regular-expressions).  
  
 Prima di Visual Studio 2012, Visual Studio usava la sintassi personalizzata di espressione regolare nelle finestre Trova e sostituisci. Per una spiegazione su come convertire alcuni dei simboli di espressione regolare di uso più comune nelle versioni .NET, vedere le [conversioni delle espressioni regolari in Visual Studio](https://msdn.microsoft.com/en-us/library/2k3te2cs\(v=vs.110\).aspx).  
  
> [!TIP]
>  Nei sistemi operativi Windows la maggior parte delle righe termina con "\r\n" (un ritorno a capo seguito da una nuova riga). Questi caratteri non sono visibili, ma sono presenti nell'editor e passati al servizio delle espressioni regolari di.NET.  
  
> [!TIP]
>  Per informazioni sulle espressioni regolari usate nei criteri di sostituzione, vedere [Sostituzioni](/dotnet/standard/base-types/substitutions-in-regular-expressions). Per usare un gruppo Capture numerato, la sintassi è `$1` per specificare il gruppo numerato e `(x)` per specificare il gruppo in questione. Ad esempio, l'espressione regolare raggruppata `(\d)([a-z])` trova quattro corrispondenze nella stringa seguente: **1a 2b 3c 4d**. La stringa di sostituzione `z$1` converte tale stringa in **z1 z2 z3 z4**.  
  
## <a name="regular-expressions-in-visual-studio"></a>Uso delle espressioni regolari in Visual Studio  
 Ecco alcuni esempi.  
  
|Scopo|Espressione|Esempio|  
|-------------|----------------|-------------|  
|Trovare la corrispondenza con qualsiasi carattere singolo (tranne un'interruzione di riga)|.|`a.o` trova "aro" in "around" e "abo" in "about", ma non "acro" in "across".|  
|Trovare la corrispondenza con zero o più occorrenze dell'espressione precedente (trovare quanti più caratteri corrispondenti possibile)|*|`a*r` trova "r" in "rack", "ar" in "ark" e "aar" in "aardvark"|  
|Trovare la corrispondenza con qualsiasi carattere zero o più volte (carattere jolly *)|.*|c.*e trova "cke" in "racket", "comme" in "comment" e "code" in "code"|  
|Trovare la corrispondenza con una o più occorrenze dell'espressione precedente (trovare quanti più caratteri corrispondenti possibile)|+|`e.+e` trova "eede" in "feeder" ma non "ee".|  
|Trovare la corrispondenza con qualsiasi carattere una o più volte (carattere jolly ?)|.+|e.+e trova "eede" in "feeder" ma non "ee".|  
|Trovare la corrispondenza a zero o più occorrenze dell'espressione precedente (trovare quanti meno caratteri corrispondenti possibile)|*?|`e.*?e` trova "ee" in "feeder" ma non "eede".|  
|Trovare la corrispondenza a una o più occorrenze dell'espressione precedente (trovare quanti meno caratteri corrispondenti possibile)|+?|`e.+?e` trova "ente" e "erprise" in "enterprise", ma non l'intera parola "enterprise".|  
|Ancorare la stringa di corrispondenza all'inizio di una riga o stringa|^|`^car` trova la parola "car" solo quando viene visualizzata all'inizio di una riga.|  
|Ancorare la stringa di corrispondenza alla fine di una riga o stringa|\r?$|`End\r?$` trova "end" solo quando è visualizzato alla fine di una riga.|  
|Trovare la corrispondenza con qualsiasi carattere singolo in un set|[abc]|`b[abc]` trova "ba", "bb" e "bc".|  
|Trovare la corrispondenza con qualsiasi carattere in un intervallo di caratteri|[a-f]|`be[n-t]` trova "bet" in "between", "ben" in "beneath" e "bes" in "beside", ma non "below".|  
|Acquisire e numerare in modo implicito l'espressione racchiusa tra parentesi|()|`([a-z])X\1` trova "aXa" e "bXb", ma non "aXb". ". "\1" fa riferimento al primo gruppo di espressioni "[a-z]".|  
|Invalidare una corrispondenza|(?!abc)|`real (?!ity)` trova "real" in "realty" e "really", ma non in "reality". Trova anche il secondo "real" (ma non il primo "real") in "realityreal".|  
|Trovare la corrispondenza con qualsiasi carattere non presente in un determinato set di caratteri|[^abc]|`be[^n-t]` trova "bef" in "before", "beh" in "behind" e "bel" in "below", ma non "beneath".|  
|Trovare la corrispondenza dell'espressione prima o dopo il simbolo.|&#124;|`(sponge&#124;mud) bath` trova "sponge bath" e "mud bath".|  
|Includere il carattere che segue la barra rovesciata usando una sequenza di escape|\|`\^` trova il carattere ^.|  
|Specificare il numero di occorrenze del gruppo o del carattere precedente|{x}, dove x è il numero di occorrenze|`x(ab){2}x` trova "xababx" e `x(ab){2,3}x` trova "xababx" e "xabababx" ma non "xababababx".|  
|Trovare la corrispondenza con un testo in una classe di caratteri Unicode, dove "X" è il numero Unicode. Per altre informazioni sulle classi di caratteri Unicode, vedere<br /><br /> [Proprietà dei caratteri Unicode standard 5.2](http://www.unicode.org/versions/Unicode5.2.0/ch04.pdf).|\p{X}|`\p{Lu}` trova "T" e "D" in "Thomas Doe".|  
|Trovare la corrispondenza con un confine di parola|`\b` (all'esterno di una classe di caratteri \b specifica un confine di parola e all'interno di una classe di caratteri specifica un backspace).|`\bin` trova "in" in "inside" ma non "pinto".|  
|Trovare la corrispondenza con un'interruzione di riga (cioè un ritorno a capo seguito da una nuova riga).|\r?\n|`End\r?\nBegin` trova "End" e "Begin" solo quando "End" è l'ultima stringa in una riga e "Begin" è la prima stringa nella riga successiva.|  
|Trovare la corrispondenza con qualsiasi carattere alfanumerico|\w|`a\wd` trova "add" e "a1d", ma non "a d".|  
|Trovare la corrispondenza con qualsiasi spazio vuoto.|(?([^\r\n])\s)|`Public\sInterface` trova la frase "Public Interface".|  
|Trovare la corrispondenza con qualsiasi carattere numerico|\d|`\d` trova "3" in "3456", "2" in 23" e "1" in "1".|  
|Trovare la corrispondenza con un carattere Unicode|\uXXXX dove XXXX specifica il valore del carattere Unicode.|`\u0065` trova il carattere "e".|  
|Trovare la corrispondenza con un identificatore|\b(_\w+&#124;[\w-[0-9\_]]\w*)\b|Trova "type1" ma non &type1" o "#define".|  
|Trovare la corrispondenza con una stringa tra virgolette|((\\".+?\\")&#124;('.+?'))|Trova qualsiasi stringa racchiusa tra virgolette singole o doppie.|  
|Trovare la corrispondenza con un numero esadecimale|\b0[xX]([0-9a-fA-F]\)\b|Trova "0xc67f", ma non "0xc67fc67f".|  
|Trovare la corrispondenza con numeri interi e decimali|\b[0-9]*\\.\*[0-9]+\b|Trova "1.333".|  
  
## <a name="see-also"></a>Vedere anche  
 [Ricerca e sostituzione di testo](../ide/finding-and-replacing-text.md)