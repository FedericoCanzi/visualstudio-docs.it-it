---
title: "Debug in modalità mista per Python in Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 4/10/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ca86a87-e254-4ab7-b3ba-a0ab99c1da93
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 9328c347d548a03a536cea16bd5851817c03d5a2
ms.openlocfilehash: bdc621831893f907beba7ec5ad503fe4d96c0042
ms.lasthandoff: 04/10/2017

---

# <a name="debugging-python-and-c-together"></a>Debug di codice Python e C++ in contemporanea

La maggior parte dei normali debugger Python supporta solo il debug di codice Python. Nella pratica, tuttavia, Python viene usato in combinazione con C o C++ quando sono richieste prestazioni elevate o la possibilità di richiamare direttamente le API della piattaforma. Per un esempio, vedere [Creating a C++ Extension for Python](cpp-and-python.md) (Creazione di un'estensione C++ per Python). Visual Studio (usato con Python Tools for Visual Studio 2.0 e versioni successive) include funzionalità di debug in modalità mista integrate e simultanee per Python e i linguaggi nativi C/C++, con stack di chiamate combinate, la possibilità di passare tra codice Python e codice nativo, punti di interruzione per entrambi i tipi di codice e la possibilità di visualizzare rappresentazioni Python degli oggetti nei frame nativi e viceversa:

![Debug in modalità mista](media/mixed-mode-debugging.png) 

Per un'introduzione a compilazione, test e debug dei moduli C nativi con Visual Studio, vedere [Deep Dive: Creating Native Modules](https://youtu.be/D9RlT06a1EI) (Approfondimento: creazione di moduli nativi) (youtube.com, 9m9s).

> [!VIDEO https://www.youtube.com/embed/D9RlT06a1EI]

## <a name="enabling-mixed-mode-debugging"></a>Abilitazione del debug in modalità mista

1. Fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, scegliere **Proprietà**, selezionare la scheda **Debug** e quindi attivare l'opzione **Attiva il debug di codice nativo**. Verrà così abilitata la modalità mista per tutte le sessioni di debug.

    ![Abilitazione del debug di codice nativo](media/mixed-mode-debugging-enable-native.png)

    > [!Tip]    
    > Quando si abilita il debug del codice nativo, è possibile che la finestra di output di Python venga chiusa immediatamente al completamento del programma senza visualizzare il messaggio "Premere un tasto qualsiasi per continuare". Per specificare una pausa, aggiungere l'opzione `-i` al campo **Esegui > Argomenti dell'interprete** della scheda **Debug** quando si abilita il debug del codice nativo. In questo modo l'interprete di Python passa in modalità interattiva al termine del codice e attende che vengano premuti CTRL+Z, INVIO per uscire.

1. Quando si collega il debugger in modalità mista a un processo esistente (**Debug > Connetti a processo**), selezionare il pulsante **Seleziona** per aprire la finestra di dialogo **Seleziona tipo di codice**, impostare l'opzione **Esegui il debug di questi tipi di codice** e selezionare sia **Nativo** che **Python** nell'elenco:

    ![Selezione dei tipi di codice nativo e Python](media/mixed-mode-debugging-code-type.png)

    Le impostazioni del tipo di codice sono persistenti, quindi se si vuole disabilitare il debug in modalità mista quando ci si collega a un altro processo in un secondo momento, sarà necessario ripetere questa procedura e deselezionare il tipo di codice Python.

    È possibile selezionare altri tipi di codice in aggiunta, o in sostituzione del tipo **Nativo**. Ad esempio, se un'applicazione gestita ospita CPython, che a sua volta usa moduli di estensione nativi e si vuole eseguire il debug di tutti e tre, è possibile selezionare **Python**, **Nativo** e Gestito** insieme per un'esperienza di debug unificata, inclusi stack di chiamate combinati e la possibilità di passare tra tutti e tre i runtime.

1. Quando si avvia il debug in modalità mista per la prima volta, è possibile che venga visualizzata una finestra di dialogo **Simboli Python necessari**. Per altri dettagli, vedere [Simboli per il debug in modalità mista](debugging-symbols-for-mixed-mode.md). È necessario installare i simboli una sola volta per qualsiasi ambiente Python specificato. Si noti che se si installa il supporto di Python tramite il programma di installazione di Visual Studio 2017, i simboli vengono inclusi automaticamente.

1. È anche possibile avere a disposizione il codice sorgente Python. Il codice Python standard è disponibile in [https://www.python.org/downloads/source/](https://www.python.org/downloads/source/). Scaricare l'archivio appropriato per la versione e decomprimerlo in una cartella. Sarà possibile puntare Visual Studio a file specifici nella cartella ogni volta che verrà richiesto.

## <a name="mixed-mode-specific-features"></a>Funzionalità specifiche della modalità mista

- [Stack di chiamate combinato](#combined-call-stack)
- [Passaggio tra codice Python e codice nativo](#stepping-between-python-and-native-code)
- [Visualizzazione di valori PyObject nel codice nativo](#pyobject-values-view-in-native-code)
- [Visualizzazione di valori nativi nel codice Python](#native-values-view-in-python-code)

### <a name="combined-call-stack"></a>Stack di chiamate combinato

La finestra Stack di chiamate mostra sia gli stack frame nativi che di Python con interleave, con le transizioni contrassegnate tra i due:

![Stack di chiamate combinato](media/mixed-mode-debugging-call-stack.png)

> [!Note]
> Le transizioni vengono visualizzate come "[Codice esterno]", senza specificare la direzione della transizione, se è impostata l'opzione **Strumenti > Opzioni > Debug > Generale > Abilita Just My Code**.

È possibile fare doppio clic su qualsiasi frame di chiamata per attivarlo e per aprire il codice sorgente appropriato, se possibile. Se il codice sorgente non è disponibile, il frame viene comunque attivato ed è possibile controllare le variabili locali.

### <a name="stepping-between-python-and-native-code"></a>Passaggio tra codice Python e codice nativo

Quando si usano i comandi Esegui istruzione (F11) o Esci da istruzione/routine (MAIUSC+F11), il debugger in modalità mista gestisce correttamente le modifiche tra i tipi di codice. Ad esempio, quando Python chiama un metodo di un tipo implementato in C, l'esecuzione di istruzioni in una chiamata a tale metodo si interrompe all'inizio della funzione nativa che implementa il metodo. Analogamente, quando il codice nativo chiama una funzione API Python, ciò causa la chiamata del codice Python. Ad esempio, l'esecuzione di `PyObject_CallObject` per un valore di funzione originariamente definito in Python si interrompe all'inizio della funzione Python. Il passaggio da codice Python a codice nativo è supportato anche per le funzioni native richiamate da Python tramite [ctypes](http://docs.python.org/3/library/ctypes.html).

### <a name="pyobject-values-view-in-native-code"></a>Visualizzazione di valori PyObject nel codice nativo

Quando è attivo un frame nativo (C o C++), le relative variabili locali vengono visualizzate nella finestra Variabili locali del debugger. Nei moduli di estensione Python nativi, molte di queste sono di tipo `PyObject` (ovvero un typedef per `_object`) o di alcuni altri tipi di Python fondamentali (vedere l'elenco riportato di seguito). Nel debug in modalità mista, per questi valori esiste un nodo figlio aggiuntivo denominato "visualizzazione Python". Quando viene espanso, questo nodo mostra la rappresentazione Python della variabile, identica a quella che si vedrebbe se in un frame Python fosse presente una variabile locale che fa riferimento allo stesso oggetto. Gli elementi figlio di questo nodo sono modificabili.

![Python View (Visualizzazione Python)](media/mixed-mode-debugging-python-view.png)

Per disabilitare questa funzionalità, fare clic con il pulsante destro del mouse in qualsiasi punto della finestra Variabili locali e disattivare l'opzione di menu **Python > Show Python View Nodes** (Mostra nodi visualizzazione Python):

![Abilitazione del nodo Python View (Visualizzazione Python)](media/mixed-mode-debugging-enable-python-view.png)

Tipi C che mostrano i nodi "[Python View]" (Visualizzazione Python), se abilitati:

- `PyObject `
- `PyVarObject`
- `PyTypeObject`
- `PyByteArrayObject`
- `PyBytesObject`
- `PyTupleObject`
- `PyListObject`
- `PyDictObject`
- `PySetObject`
- `PyIntObject`
- `PyLongObject`
- `PyFloatObject`
- `PyStringObject`
- `PyUnicodeObject`

Il nodo "[Python View]"(Visualizzazione Python) non viene visualizzato automaticamente per i tipi creati dall'utente. Quando si creano estensioni per Python 3. x, non si tratta in genere di un problema perché qualsiasi oggetto ha fondamentalmente un campo `ob_base` di uno dei tipi indicati in precedenza e quindi il nodo "[Python View]"(Visualizzazione Python) viene visualizzato. 

Per Python 2. x, tuttavia, ogni tipo di oggetto dichiara in genere l'intestazione come raccolta di campi inline e non esiste alcuna associazione tra i tipi personalizzati creati e `PyObject` a livello del sistema dei tipi nel codice C/C++. Per abilitare i nodi "[Python View]"(Visualizzazione Python) per questi tipi personalizzati, modificare `PythonDkm.natvis` nella [directory di installazione di Python Tools](installation.md#install-locations) e aggiungere semplicemente un altro elemento nel codice XML per lo struct C o la classe C++.

Un'opzione alternativa (e migliore) consiste nel seguire la proposta [PEP 3123](http://www.python.org/dev/peps/pep-3123/) e usare un campo `PyObject ob_base;` esplicito invece di `PyObject_HEAD`, sebbene ciò non sia sempre possibile per motivi di compatibilità con le versioni precedenti.


### <a name="native-values-view-in-python-code"></a>Visualizzazione di valori nativi nel codice Python

In modo simile a quanto descritto nella sezione precedente, è possibile abilitare un nodo "[C++ View]" (Visualizzazione C++) per i valori nativi nella finestra Variabili locali quando è attivo un frame Python. Questa funzionalità non è abilitata per impostazione predefinita, quindi per attivarla è necessario fare clic con il pulsante destro del mouse nella finestra Variabili locali e attivare l'opzione di menu **Python > Show C++ View Nodes** (Mostra nodi visualizzazione C++).

![Abilitazione del nodo C++ View (Visualizzazione C++)](media/mixed-mode-debugging-enable-cpp-view.png)

Il nodo "[C++ View]" (Visualizzazione C++) offre una rappresentazione della struttura C/C++ sottostante per un valore, identica a quella che verrebbe visualizzata in un frame nativo. Ad esempio, mostra un'istanza di `_longobject` (per cui `PyLongObject` è un typedef) per un valore long integer Python e tenterà di dedurre i tipi per le classi native create dall'utente. Gli elementi figlio di questo nodo sono modificabili.

![C++ View (Visualizzazione C++)](media/mixed-mode-debugging-cpp-view.png)

Se un campo figlio di un oggetto è di tipo `PyObject` o di uno degli altri tipi supportati, avrà un nodo per la rappresentazione "[Python View]" (Visualizzazione Python), se abilitato, in modo che sia possibile esplorare gli oggetti grafici quando i collegamenti non sono esposti direttamente per Python.

Diversamente dai nodi "[Python View]" (Visualizzazione Python) che usano i metadati degli oggetti Python per determinare il tipo dell'oggetto, non esiste un meccanismo affidabile simile per i nodi "[C++ View]" (Visualizzazione C++). In termini generali, dato un valore Python, ovvero un riferimento a `PyObject`, non è possibile determinare in modo affidabile la struttura C/C++ sottostante. Il debugger in modalità mista tenta di dedurre il tipo esaminando i vari campi del tipo dell'oggetto (ad esempio `PyTypeObject` a cui fa riferimento il campo `ob_type` corrispondente) che hanno tipi di puntatore a funzione. Se uno di questi puntatori a funzione fa riferimento a una funzione che può essere risolta e tale funzione ha un parametro `self` con un tipo più specifico di `PyObject*`, si presuppone che tale tipo sia il tipo sottostante. Ad esempio, se `ob_type->tp_init` di un oggetto specificato fa riferimento alla funzione seguente:

```c
static int FobObject_init(FobObject* self, PyObject* args, PyObject* kwds) {
    return 0;
}
```

il debugger può dedurre correttamente che il tipo C dell'oggetto sia `FobObject`. Se non è possibile determinare un tipo più preciso da `tp_init`, il debugger passa ad altri campi. Se non è in grado di dedurre il tipo da uno qualsiasi di tali campi, il nodo "[C++ View]" (Visualizzazione C++) presenta l'oggetto come istanza di `PyObject`.

Per ottenere sempre una rappresentazione utile per i tipi personalizzati creati, è consigliabile registrare almeno una funzione speciale quando si registra il tipo e usare un parametro `self` fortemente tipizzato. La maggior parte dei tipi soddisfa questo requisito naturalmente. In caso contrario, `tp_init` è in genere la voce più comoda da usare per questo scopo. Un'implementazione fittizia di `tp_init` per un tipo che è presente unicamente per abilitare l'inferenza del tipo per il debugger può semplicemente restituire zero immediatamente, come nell'esempio di codice riportato sopra.

## <a name="differences-from-standard-python-debugging"></a>Differenze rispetto al debug Python standard

Il debugger in modalità mista è diverso dal [debugger Python standard](debugging.md) in quanto introduce alcune funzionalità aggiuntive, ma non include alcune funzionalità relative a Python:

- Funzionalità non supportate: punti di interruzione condizionali, finestra interattiva di debug e debug remoto multipiattaforma.
- Finestra di controllo immediato: è disponibile ma con un sottoinsieme limitato di funzionalità, tra cui tutte le limitazioni qui elencate.
- Versioni di Python supportate: solo CPython 2.7 e versioni successive alla 3.3.
- Visual Studio Shell: quando si usa Python con Visual Studio Shell, ad esempio se è stato installato con il programma di installazione integrato, Visual Studio non è in grado di aprire i progetti C++ e l'esperienza di modifica per i file di C++ è limitata a un semplice editor di testo. Il debug di C/C++ e il debug in modalità mista sono tuttavia supporti completamente nella shell con il codice sorgente, l'esecuzione istruzione per istruzione del codice nativo e la valutazione delle espressioni C++ nelle finestre del debugger.
- Visualizzazione ed espansione degli oggetti: durante la visualizzazione di oggetti Python nelle finestre del debugger Variabili locali ed Espressioni di controllo, il debugger in modalità mista mostra solo la struttura degli oggetti. Non valuta automaticamente le proprietà, né mostra gli attributi calcolati. Per le raccolte, mostra solo gli elementi per i tipi di raccolta predefiniti (`tuple`, `list`, `dict`, `set`). I tipi di raccolta personalizzati non vengono visualizzati come raccolte, a meno che non siano ereditati da un tipo di raccolta predefinito.
- Valutazione delle espressioni: vedere di seguito.

### <a name="expression-evaluation"></a>Valutazione delle espressioni

Il debugger Python standard consente la valutazione di espressioni arbitrarie di Python nelle finestre Espressioni di controllo e Controllo immediato quando il processo di debug viene sospeso in qualsiasi punto nel codice, a condizione che non sia bloccato in un'operazione di I/O o in altre chiamate di sistema simili. Nel debug in modalità mista, le espressioni arbitrarie possono essere valutate solo in caso di arresto nel codice Python, dopo un punto di interruzione o l'esecuzione istruzione per istruzione del codice, e le espressioni possono essere valutate solo nel thread in cui si verifica il punto di interruzione o l'operazione di esecuzione istruzione per istruzione.

In caso di arresto nel codice nativo, o nel codice Python quando non sono applicabili le condizioni sopra riportate (ad esempio, dopo un'operazione di uscita dall'istruzione o in un thread diverso), la valutazione delle espressioni si limita all'accesso alle variabili locali e globali nell'ambito del frame selezionato, all'accesso ai relativi campi e all'indicizzazione dei tipi di raccolta predefiniti con valori letterali. L'espressione seguente, ad esempio, può essere valutata in qualsiasi contesto, a condizione che tutti gli identificatori facciano riferimento a variabili e campi esistenti con tipi appropriati:

```python
foo.bar[0].baz['key']
```

Il debugger in modalità mista risolve anche queste espressioni in modo diverso. Tutte le operazioni di accesso ai membri cercano solo i campi che fanno parte direttamente dell'oggetto (come una voce in `__dict__` o `__slots__` oppure un campo di uno struct nativo esposto in Python tramite `tp_members`) e ignorano `__getattr__`, `__getattribute__` o logica di descrittore. In modo analogo, tutte le operazioni di indicizzazione ignorano `__getitem__` e accedono direttamente alle strutture dei dati interne delle raccolte.

Per mantenere la coerenza, questo schema di risoluzione dei nomi viene usato per tutte le espressioni che corrispondono ai vincoli per la valutazione delle espressioni limitate, indipendentemente dal fatto che le espressioni arbitrarie siano consentite o meno in corrispondenza del punto di interruzione corrente. Per forzare la semantica di Python appropriata quando è disponibile un analizzatore completo, racchiudere l'espressione tra parentesi:

```python
(foo.bar[0].baz['key'])
```
