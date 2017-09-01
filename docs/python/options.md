---
title: Opzioni di Python in Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 7/13/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c714867-7a64-4b1e-aca8-09d956192279
f1_keywords:
- VS.ToolsOptionsPages.Python_Tools
- VS.ToolsOptionsPages.Python_Tools.General
- VS.ToolsOptionsPages.Python_Tools.Debugging
- VS.ToolsOptionsPages.Python_Tools.Interactive_Windows
- VS.ToolsOptionsPages.Text_Editor.Python.Advanced
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6d25db4639f2c8391c1e32542701ea359f560178
ms.openlocfilehash: a71d076e85e1e7ae070014e83186c0011ca9e58f
ms.contentlocale: it-it
ms.lasthandoff: 07/18/2017

---

# <a name="options-for-python-in-visual-studio"></a>Opzioni di Python in Visual Studio

Per visualizzare le opzioni di Python, usare il comando di menu **Strumenti > Opzioni**, assicurarsi che sia selezionata l'opzione **Mostra tutte le impostazioni**, quindi passare a **Strumenti Python**:

![Finestra di dialogo Opzioni di Python, scheda Generale](media/options-general.png)

Nella scheda **Editor di testo > Python > Avanzate** sono presenti anche altre opzioni specifiche di Python.

Le opzioni specifiche sono descritte nelle sezioni seguenti:

- [Opzioni generali](#general-options)
- [Opzioni di debug](#debugging-options)
- [Opzioni della finestra interattiva](#interactive-windows-options)
- [Opzioni avanzate dell'editor di Python](#advanced-python-editor-options)

## <a name="general-options"></a>Opzioni generali

| Opzione | Default | Descrizione |
| --- | --- | --- |
| Mostra la finestra di output durante la creazione degli ambienti virtuali| Attivato | Deselezionare per impedire che venga visualizzata la finestra di output. |
| Mostra la finestra di output durante l'installazione o la rimozione di pacchetti | Attivato |  Deselezionare per impedire che venga visualizzata la finestra di output. |
| Esegui sempre pip come amministratore | Disattivato | Eleva sempre le operazioni `pip install` per tutti gli ambienti. Durante l'installazione dei pacchetti, Visual Studio richiede i privilegi di amministratore se l'ambiente si trova in un'area protetta del file system, come `c:\Program Files`. In questo prompt è possibile scegliere di elevare sempre `pip install` per tale specifico ambiente. Vedere [Ambienti Python - Scheda pip](python-environments.md#pip-tab). |
| Genera automaticamente il database di completamento al primo uso | Attivato | Per fare in modo che i [completamenti IntelliSense](code-editing.md#intellisense) funzionino con una libreria, Visual Studio deve generare un database di completamento per tale libreria. La creazione del database viene eseguita in background quando viene installata una libreria, ma potrebbe non essere completa quando si avvia la scrittura del codice. Se è selezionata questa opzione, Visual Studio assegna la priorità del completamento del database a una libreria, quando si scrive un codice che ne fa uso. |
| Ignora variabili PYTHONPATH a livello di sistema | Attivato | PYTHONPATH viene ignorato per impostazione predefinita perché Visual Studio offre un mezzo più diretto per specificare i percorsi di ricerca negli ambienti e nei progetti. Vedere [Ambienti Python - Percorsi di ricerca](python-environments.md#search-paths) per informazioni dettagliate. |
| Aggiorna percorsi di ricerca quando vengono aggiunti file collegati | Attivato | Quando questa opzione è impostata, l'aggiunta di un [file collegato](python-projects.md#linked-files) a un progetto aggiorna i [percorsi di ricerca](python-environments.md#search-paths) in modo che IntelliSense possa includere il contenuto della cartella del file collegato nel relativo database di completamento. Deselezionare questa opzione per escludere tale contenuto dal database di completamento. |
| Avvisa quando non è possibile trovare il modulo importato | Attivato | Deselezionare questa opzione per non visualizzare gli avvisi quando si è certi che un modulo importato non è attualmente disponibile, ma non influisce comunque sul funzionamento del codice. |
| Segnala rientro incoerente come | Avvisi | Poiché l'interprete di Python dipende fortemente da un rientro corretto per determinare l'ambito, Visual Studio per impostazione predefinita genera dei messaggi di avviso quando rileva rientri incoerenti che potrebbero indicare errori di codifica. Per maggiore precisione, impostare su *Errori*, opzione che provoca la chiusura del programma in casi di questo tipo. Per disabilitare completamente questo comportamento, selezionare *No*. |
| Controlla disponibilità di sondaggi/novità | Una volta alla settimana | Imposta la frequenza con cui si consente a Visual Studio di aprire una finestra contenente una pagina web con sondaggi e notizie relativi a Python, qualora disponibili. Le opzioni sono *Mai*, *Una volta al giorno*, *Una volta alla settimana* e *Una volta al mese*. |
| Ripristina tutte le finestre di dialogo nascoste in modo permanente (pulsante) | n/d | Diverse finestre di dialogo presentano opzioni quali **Non visualizzare più questo messaggio**. Usare questo pulsante per cancellare tali opzioni e visualizzare nuovamente le finestre di dialogo. |

![Finestra di dialogo Opzioni di Python, scheda Generale](media/options-general.png)

## <a name="debugging-options"></a>Opzioni di debug

| Opzione | Default | Descrizione |
| --- | --- | --- |
| Chiedi conferma prima dell'esecuzione quando sono presenti errori | Attivato | Se impostato, viene chiesto di confermare che si desidera eseguire il codice contenente errori. Deselezionare questa opzione per disabilitare l'avviso. |
| Attendi input quando il processo viene chiuso in modo anomalo<br/><br/>Attendi input quando il processo viene chiuso normalmente | Attivato (per entrambi) | Un programma Python avviato da Visual Studio viene eseguito nella propria finestra della console. Per impostazione predefinita, la finestra attende che venga premuto un tasto prima di chiudere il programma, indipendentemente dalla modalità con cui viene chiuso il programma. Per rimuovere il prompt e chiudere la finestra automaticamente, deselezionare una o entrambe le opzioni. |
| Output del programma tee nella finestra di output del debug | Attivato | Visualizza l'output del programma in una finestra della console separata e nella finestra di output di Visual Studio. Deselezionare questa opzione per visualizzare l'output solo nella finestra della console separata. |
| Interrompi in caso di eccezione SystemExit con codice di uscita zero | Disattivato | Se l'opzione è selezionata, il debugger viene arrestato su questa eccezione. Se è deselezionata, il debugger viene chiuso senza interruzioni. |
| Abilita il debug della libreria standard Python | Disattivato | Consente di eseguire il codice sorgente della libreria standard durante il debug, ma aumenta il tempo necessario all'avvio del debugger.|

![Finestra di dialogo Opzioni di Python, scheda Debug](media/options-debugging.png)

## <a name="interactive-windows-options"></a>Opzioni della finestra interattiva

| Opzione | Default | Descrizione |
| --- | --- | --- |
| Script | n/d | Specifica una cartella generale per gli script di avvio valida per le finestre interattive per tutti gli ambienti. Vedere [Script di avvio](python-environments.md#startup-scripts). Si noti, tuttavia, che questa funzionalità non è attualmente supportata. |
| Spostarsi nella cronologia con le frecce su/giù | Attivato | Usare i tasti freccia per spostarsi nella cronologia, nella finestra interattiva. Deselezionare questa impostazione per usare i tasti freccia per spostarsi invece all'interno dell'output della finestra interattiva. |
| Modalità di completamento | Valutare unicamente le espressioni senza chiamate di funzione | Il processo di determinazione dei membri disponibili su un'espressione nella finestra interattiva può richiedere la valutazione dell'espressione incompleta corrente, con la conseguente chiamata ripetuta di effetti collaterali o funzioni. L'impostazione predefinita, *Valuta solo le espressioni senza chiamate di funzione* esclude le espressioni che sembrano chiamare una funzione, ma valuta altre espressioni. Ad esempio, valuta `a.b` ma non `a().b`.  *Non valutare mai le espressioni* evita tutti gli effetti collaterali e usa solo il motore di IntelliSense normale per i suggerimenti. *Valuta tutte le espressioni* valuta l'espressione completa per ottenere suggerimenti, indipendentemente dagli effetti collaterali. |
| Nascondi suggerimenti analisi statica | Disattivato | Se è impostata questa opzione, vengono visualizzati solo i suggerimenti ottenuti dalla valutazione dell'espressione. Se è associata alla modalità di completamento *Non valutare mai le espressioni*, non viene visualizzato alcun completamento utile nella finestra interattiva. |

![Finestra di dialogo delle opzioni di Python, scheda Finestre interattive](media/options-interactive-windows.png)

## <a name="advanced-python-editor-options"></a>Opzioni avanzate dell'editor di Python

### <a name="completion-results"></a>Risultati del completamento

| Opzione | Default | Descrizione |
| --- | --- | --- |
| Il completamento dei membri visualizza l'intersezione dei membri | Disattivato | Se l'opzione è impostata, vengono visualizzati solo i completamenti supportati da tutti i tipi possibili. |
| Elenco di filtri in base alla stringa di ricerca | Attivato | Applica il filtro dei suggerimenti di completamento durante la digitazione (l'opzione è selezionata per impostazione predefinita). |
| Visualizza automaticamente i completamenti per tutti gli identificatori | Attivato | Deselezionare questa opzione per disabilitare i completamenti sia nell'editor che nelle finestre interattive. |

### <a name="selection-in-completion-list"></a>Selezione negli elenchi di completamento

| Opzione | Default | Descrizione |
| --- | --- | --- |
| Commit alla digitazione dei caratteri seguenti | {}[]().,:;+-*/%&&#124;^~=<>#@\ | Questi caratteri seguono in genere un identificatore che può essere selezionato da un elenco di completamento, pertanto è consigliabile eseguire il commit del completamento semplicemente digitando un carattere. È possibile rimuovere o aggiungere caratteri specifici all'elenco in base alle esigenze.  |
| Immetti completamento corrente dei commit | Attivato | Se questa opzione è impostata, il tasto INVIO sceglie e applica il completamento attualmente selezionato in modo analogo ai caratteri riportati sopra (ma ovviamente, non esiste un carattere per il tasto Invio, pertanto non può entrare direttamente in tale elenco). |
| Aggiungi nuova riga quando si preme Invio alla fine della parola digitata | Disattivato | Per impostazione predefinita, se si digita la parola che viene visualizzata nella finestra popup di completamento e si preme INVIO, si esegue il commit di tale completamento. Impostando questa opzione, si esegue il commit dei completamenti quando si finisce di digitare l'identificatore, di conseguenza, premendo il tasto INVIO viene inserita una nuova riga. |

### <a name="miscellaneous-options"></a>Altre opzioni

| Opzione | Default | Descrizione |
| --- | --- | --- |
| Attiva modalità struttura all'apertura del file | Attivato | Attiva automaticamente la funzionalità di struttura nell'editor di Visual Studio all'apertura di un file di codice Python. |
| Paste removed REPL prompts (Incolla prompt REPL rimossi) | Attivato | Rimuove >>> e ... dal testo incollato, consentendo il trasferimento agevole del codice dalla finestra interattiva all'editor. Deselezionare questa opzione se è necessario conservare tali caratteri provenienti da altre origini. |
| Nomi dei colori in base ai tipi | Attivato | Abilita la colorazione della sintassi nel codice Python. |

![Finestra di dialogo delle opzioni dell'editor di Python, scheda avanzate](media/options-editor-advanced.png)
