---
title: Sincronizzazione di tipo e il nome file - Refactoring (c#) | Documenti Microsoft
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48172dd7-24a5-4884-8a73-f92497ad6a0d
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: CSharp
ms.openlocfilehash: ee37983575aa82abb764d57006cdabd094ea6497
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-c"></a>Sincronizzazione di un tipo in un nome di file o un nome di file a un tipo in c# #

<!-- VERSIONLESS -->
**Questa funzionalità è disponibile in Visual Studio 2017 e versioni successive.  Inoltre, i progetti .NET Standard non sono ancora supportati per questo refactoring.**

**Novità:** consente di rinominare un tipo in modo che corrisponda il nome del file, o un nome di file per corrispondere al tipo che contiene.

**Quando:** è stato rinominato un file o un tipo e non sono state ancora aggiornate il corrispondente file o un tipo in modo che corrispondano. 

**Motivo:** inserendo un tipo in un file con un nome diverso o viceversa, risulta difficile trovare ciò che sta cercando.  Per rinominare il tipo o file, codice diventa più leggibile e di passare facilmente.

**Procedura:**

1. Evidenziare o posizionare il cursore di testo all'interno del nome del tipo da sincronizzare:

   ![Codice evidenziato](media/synctype_highlight.png)

1. Successivamente, eseguire una delle operazioni seguenti:
   * **Tastiera**
     * Premere **Ctrl +.** Per attivare il **azioni rapide e refactoring** dal menu **Rinomina file *TypeName*. cs** nel popup di finestra di anteprima, in cui *TypeName* è il nome del tipo selezionato.
     * Premere **Ctrl +.** Per attivare il **azioni rapide e refactoring** dal menu **rinominare tipo in _Filename_**  nel popup di finestra di anteprima, in cui *Filename* è il nome del file corrente.
   * **Mouse**
     * Pulsante destro del mouse nel codice, selezionare il **azioni rapide e refactoring** dal menu **Rinomina file *TypeName*cs** dalla finestra popup di finestra di anteprima, in cui *TypeName* è il nome del tipo selezionato.
     * Pulsante destro del mouse nel codice, selezionare il **azioni rapide e refactoring** dal menu **rinominare tipo _Filename_**  nel popup di finestra di anteprima, in cui  *Nome del file* è il nome del file corrente.

   Verrà rinominate immediatamente il tipo o il file.  Nell'esempio seguente, il file **MyClass.cs** è stato rinominato in **MyNewClass.cs** corrisponda al nome di tipo.

   ![Risultato inline](media/synctype_result.png)

## <a name="see-also"></a>Vedere anche  
[Refactoring (C#)](../refactoring-csharp.md)
