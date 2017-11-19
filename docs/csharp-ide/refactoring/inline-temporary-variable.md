---
title: Variabile temporanea inline - Refactoring (c#) | Documenti Microsoft
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0182179f-f74f-47a2-a1dc-b60c86f9abaf
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e6e9ed28a42aa3d7521a059b668eed8ae1d28b8e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="inline-a-temporary-variable-with-c"></a>Inline una variabile temporanea con c# #
**Novità:** consente di rimuovere l'utilizzo di una variabile temporanea e sostituirlo con il codice effettivo.

**Quando:** l'uso della variabile temporanea rende più difficile da comprendere il codice.  

**Motivo:** la rimozione di una variabile temporanea potrebbe rendere più facile da leggere in alcuni casi il codice

**Procedura:**

1. Evidenziare o posizionare il cursore di testo all'interno di variabile temporanea per l'espansione inline:

   ![Codice evidenziato](media/inline_highlight.png)

1. Successivamente, eseguire una delle operazioni seguenti:
   * **Tastiera**
     * Premere **Ctrl +.** Per attivare il **azioni rapide e refactoring** dal menu **variabile temporanea Inline** nel popup di finestra di anteprima.
   * **Mouse**
     * Pulsante destro del mouse nel codice, selezionare il **azioni rapide e refactoring** dal menu **variabile temporanea Inline** nel popup di finestra di anteprima.

   La variabile verrà rimossa e relativi utilizzi sostituito con il valore della variabile immediatamente.

   ![Risultato inline](media/inline_result.png)

## <a name="see-also"></a>Vedere anche  
[Refactoring (C#)](../refactoring-csharp.md)