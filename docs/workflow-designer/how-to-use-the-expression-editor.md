---
title: 'Procedura: utilizzare l''Editor espressioni | Documenti Microsoft'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.View.ExpressionTextBox.UI
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: be43ad439c8868064fc7e0bab79e051abb991e0d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-use-the-expression-editor"></a>Procedura: utilizzare l'editor espressioni
L'Editor espressioni è un controllo di progettazione del flusso di lavoro di Windows che viene utilizzato in molte attività di flusso di lavoro come mezzo per immettere e valutare queste espressioni. L'editor espressioni fornisce un'esperienza di modifica IDE completa che include, tra le altre funzionalità, IntelliSense, colorazione, ParamInfo, controllo errori di ortografia durante la digitazione. Il compilatore convalida l'espressione dopo che è stata immessa. Se l'espressione non è valida, viene visualizzata un'icona di errore. È possibile aprire l'editor anche come un **Editor espressioni** la finestra di dialogo.

 Le espressioni sono valori letterali o codice [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] associati ad argomenti o proprietà. Contengono elementi valore, ad esempio variabili, costanti, valori letterali, proprietà, che vengono combinati con le operazioni per produrre un nuovo valore. Le espressioni vengono scritte usando la sintassi VB.NET, anche se l'applicazione si trova in un programma che usa C#. Ciò significa che l'uso delle maiuscole non è rilevante, il confronto viene eseguito utilizzando uguale a un singolo segno ("=") anziché ("= ="), gli operatori booleani sono le parole "e" e "or" anziché i simboli "& &" e "&#124;&#124;", e **Nothing**  viene usata invece di **null**. Per ulteriori informazioni sulle espressioni e operatori in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] e per alcuni esempi, vedere [operatori ed espressioni in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=186818).

 Il **Editor espressioni** si comporta come segue:

-   Se lo stato attivo non è sull'editor espressioni, si presenta come un controllo TextBlock normale.

-   Quando lo stato attivo è sull'editor espressioni, si presenta e si comporta come un controllo dell'editor espressioni. Dopo aver perso lo stato attivo, si presenta nuovamente come un normale controllo TextBlock.

-   Se si imposta lo stato attivo sull'editor espressioni in un oggetto progettazione flussi di lavoro riallocato, si comporta come oggetto TextBox. Quando nell'oggetto progettazione flussi di lavoro riallocato si perde lo stato attivo, l'editor espressioni si presenta nuovamente come un normale oggetto TextBlock.

> [!NOTE]
> IntelliSense per l'editor espressioni e disponibile solo in [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]. Sia in [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] che nel caso di scenari di riallocazione, il compilatore convalida l'espressione dopo che è stata immessa e nell'editor espressioni viene visualizzata un'icona di errore se l'espressione non è valida.

### <a name="using-the-expression-editor"></a>Uso dell’editor espressioni

1.  In [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] aprire un progetto flusso di lavoro nuovo o esistente.

2.  Aggiungere, ad esempio, l'attività <xref:System.Activities.Statements.Assign> al flusso di lavoro.

    > [!NOTE]
    > Più attività del flusso di lavoro presentano editor espressioni. Gli oggetti TextBlock vengono inoltre visualizzati nella finestra di progettazione variabili, nella finestra di progettazione argomenti e nella finestra di progettazione argomenti dinamici. L'attività <xref:System.Activities.Statements.Assign> viene usata come esempio.

3.  Fare clic sull'editor espressioni sinistro nell'ActivityDesigner per l'attività <xref:System.Activities.Statements.Assign>.

     Le stringhe con filigrana di colore grigio  **\<per >** e  **\<immettere un'espressione VB >** è l'impostazione predefinita, le stringhe di testo per gli editor di espressioni nel <xref:System.Activities.Statements.Assign> attività.

4.  Immettere l'espressione. Se si immette una stringa, assicurarsi di inserire la stringa tra virgolette. Se si sceglie di associare l'argomento dell'espressione a una variabile, non usare le virgolette.

     Al termine, selezionare un'area esterna all'editor espressioni per trasferire lo stato attivo in un'altra parte della finestra di progettazione. In questo modo il compilatore convalida l'espressione, come descritto precedentemente.

     Una modalità alternativa per immettere/modificare un'espressione consiste nel fare clic sul pulsante con i puntini sospensivi accanto al nome della proprietà nella griglia delle proprietà. Verrà aperta la **Editor espressioni** come finestra di dialogo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Presentation.View.ExpressionTextBox>