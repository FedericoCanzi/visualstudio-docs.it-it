---
title: Come usare i frammenti di codice XML in Microsoft Visual Studio | Documenti Microsoft
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: article
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3e8e94b799db6572b3aafcbd6bacf826b4a22861
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-use-xml-snippets"></a>Procedura: utilizzare XML frammenti di codice

È possibile richiamare i frammenti XML usando i due comandi seguenti dal menu di scelta rapida dell'editor XML. Il **Inserisci frammento di codice** comando consente di inserire il frammento XML nella posizione del cursore. Il **Racchiudi** comando esegue il wrapping il frammento XML nel testo selezionato. Ogni frammento XML dispone di tipi di frammento designati. I tipi di frammento determinano se il frammento di codice è disponibile con il **Inserisci frammento di codice** comando, il **Racchiudi** o entrambi.

Dopo che il frammento XML è stato aggiunto all'editor, i campi modificabili nel frammento vengono evidenziati in giallo e il cursore viene posizionato nel primo campo modificabile.

## <a name="insert-snippet"></a>Inserisci frammento di codice

Le procedure seguenti descrivono come accedere il **Inserisci frammento di codice** comando.

> [!NOTE]
> Il **Inserisci frammento di codice** comando è anche disponibile tramite il tasto di scelta rapida (**Ctrl**+**K**, quindi **Ctrl** + **X**).

### <a name="to-insert-snippets-from-the-shortcut-menu"></a>Per inserire i frammenti dal menu di scelta rapida

1. Posizionare il cursore nel punto in cui si desidera inserire il frammento XML.

2. Mouse e scegliere **Inserisci frammento di codice**.

   Viene visualizzato un elenco dei frammenti XML disponibili.

3. Selezionare un frammento dall'elenco usando il mouse o digitando il nome del frammento di codice e premendo **scheda** o **invio**.

### <a name="to-insert-snippets-using-the-intellisense-menu"></a>Per inserire i frammenti dal menu IntelliSense

1. Posizionare il cursore nel punto in cui si desidera inserire il frammento XML.

2. Dal **modifica** dal menu **IntelliSense**, quindi selezionare **Inserisci frammento di codice**.

   Viene visualizzato un elenco dei frammenti XML disponibili.

3. Selezionare un frammento dall'elenco usando il mouse o digitando il nome del frammento di codice e premendo **scheda** o **invio**.

### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>Per inserire i frammenti dall'elenco Completa parola di IntelliSense

1. Posizionare il cursore nel punto in cui si desidera inserire il frammento XML.

2. Iniziare a digitare il frammento XML che si desidera aggiungere al file. Se il completamento automatico è attivato, viene visualizzato l'elenco Completa parola di IntelliSense. Se non è visualizzato, premere **Ctrl**+**spazio** per attivarlo.

3. Selezionare il frammento XML dall'elenco Completa parola.

4. Premere **scheda**, **scheda** per richiamare il frammento XML.

> [!NOTE]
> In alcuni casi è possibile che il frammento XML non venga richiamato. Ad esempio, se si tenta di inserire un elemento `xs:complexType` all'interno di un nodo `xs:element`, l'editor non genera alcun frammento XML. Quando un elemento `xs:complexType` viene usato all'interno di un nodo `xs:element`, non vengono rilevati attributi o sottoelementi obbligatori, pertanto l'editor non disporrà di alcun dato da inserire.

### <a name="to-insert-snippets-using-the-shortcut-name"></a>Per inserire i frammenti dal nome del collegamento

1. Posizionare il cursore nel punto in cui si desidera inserire il frammento XML.

2. Digitare `<` nel riquadro dell'editor.

3. Premere **Esc** per chiudere l'elenco completa parola di IntelliSense.

4. Digitare il nome del collegamento del frammento e premere **scheda** per richiamare il frammento XML.

## <a name="surround-with"></a>Racchiudi tra

Le procedure seguenti descrivono come accedere il **Racchiudi** comando.

> [!NOTE]
> Il **Racchiudi** comando è anche disponibile tramite il tasto di scelta rapida (**Ctrl**+**K**, quindi **Ctrl** + **S**).

### <a name="to-use-surround-with-from-the-context-menu"></a>Per usare il comando dal menu di scelta rapida

1. Selezionare il testo da racchiudere nell'editor XML.

2. Mouse e scegliere **Racchiudi**.

   Viene visualizzato un elenco delle scelte disponibili con i frammenti XML.

3. Selezionare un frammento dall'elenco usando il mouse o digitando il nome del frammento di codice e premendo **scheda** o **invio**.

### <a name="to-use-surround-with-from-the-intellisense-menu"></a>Per utilizzare dal menu di IntelliSense

1. Selezionare il testo da racchiudere nell'editor XML.

2. Dal **modifica** dal menu **IntelliSense**, quindi selezionare **Racchiudi**.

   Viene visualizzato un elenco delle scelte disponibili con i frammenti XML.

3. Selezionare un frammento dall'elenco usando il mouse o digitando il nome del frammento di codice e premendo **scheda** o **invio**.

## <a name="using-xml-snippets"></a>Utilizzo dei frammenti XML

Una volta scelto il frammento XML, il testo del frammento di codice viene inserito automaticamente nella posizione del cursore. I campi modificabili del frammento vengono evidenziati e il primo campo modificabile viene selezionato automaticamente. Il campo attualmente selezionato è di tipo boxed.

Quando si seleziona un campo, è possibile digitare un nuovo valore per tale campo. Premendo **scheda** scorre i campi modificabili del frammento di codice; premere **MAIUSC**+**scheda** scorrerli in ordine inverso. Se si fa clic su un campo il cursore viene posizionato all'interno del campo, se si fa doppio clic il campo viene selezionato. Quando un campo è evidenziato, potrebbe essere visualizzata la finestra con la descrizione del campo.

È modificabile solo la prima istanza di un determinato campo. Quando il campo è evidenziato, le altre istanze del campo sono tratteggiate. Quando si modifica il valore di un campo modificabile, il campo viene modificato ovunque venga usato nel frammento.

Premendo **invio** o **Esc** Annulla la modifica dei campi e restituisce l'editor Normal.

Colori predefiniti per i campi dei frammenti di codice modificabile possono essere modificati modificando l'impostazione del campo frammento di codice nel **tipi di carattere e colori** riquadro del **opzioni** la finestra di dialogo. Per ulteriori informazioni, vedere [procedura: modificare tipi di carattere e colori nell'Editor](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).

## <a name="see-also"></a>Vedere anche

- [Frammenti di codice XMLs](../xml-tools/xml-snippets.md)
- [Procedura: Generare un frammento XML da XML Schema](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)
- [Procedura: Creare frammenti XML](../xml-tools/how-to-create-xml-snippets.md)