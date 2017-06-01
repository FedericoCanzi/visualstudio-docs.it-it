---
title: "Procedura dettagliata: Importazione di un&#39;area del modulo progettata in Outlook"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "importazione di aree del modulo"
  - "aree del modulo [sviluppo per Office in Visual Studio], importazione"
ms.assetid: 86b0ef1a-6d7e-4ea5-b90e-458ffe4e1d10
caps.latest.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 31
---
# Procedura dettagliata: Importazione di un&#39;area del modulo progettata in Outlook
  Questa procedura dettagliata illustra come progettare un'area del modulo in Microsoft Office Outlook e come importare l'area del modulo in un progetto di componente aggiuntivo VSTO di Outlook con la procedura guidata **Nuova area modulo**. Progettando l'area del modulo in Outlook è possibile aggiungere i controlli nativi di Outlook all'area del modulo associata ai dati di Outlook. Dopo avere importato l'area del modulo, è possibile gestire gli eventi di ogni controllo.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Questa procedura dettagliata illustra le attività seguenti:  
  
-   Progettazione di un'area del modulo usando Progettazione aree di form in Outlook.  
  
-   Importazione di un'area del modulo in un progetto di componente aggiuntivo VSTO per Outlook.  
  
-   Gestione degli eventi dei controlli dell'area del modulo.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)] o [!INCLUDE[Outlook_14_short](../vsto/includes/outlook-14-short-md.md)].  
  
> [!NOTE]  
>  Nomi o percorsi visualizzati per alcuni elementi dell'interfaccia utente di Visual Studio nelle istruzioni seguenti potrebbero essere diversi nel computer in uso. La versione di Visual Studio in uso e le impostazioni configurate determinano questi elementi. Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/it-it/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 ![Collegamento a video](../vsto/media/playvideo.png "Collegamento a video")Per una dimostrazione video correlata, vedere la [procedura di creazione di aree del modulo Outlook usando Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=130305).  
  
## Progettazione di un'area del modulo usando Progettazione aree di form in Outlook  
 In questo passaggio si progetterà un'area del modulo in Outlook. L'area del modulo verrà quindi salvata in un percorso facilmente accessibile e successivamente importata in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
 Quest'area del modulo di esempio sostituisce completamente il normale modulo Attività. Fornisce una modalità per registrare lo stato di avanzamento di tutte le attività che devono essere completate prima che l'attività principale possa essere eseguita \(attività essenziali\). L'area del modulo visualizza un elenco delle attività essenziali e mostra lo stato di completamento di ogni attività nell'elenco. Gli utenti possono aggiungere attività all'elenco e rimuoverle, oltre ad aggiornare lo stato di completamento di ogni attività.  
  
#### Per progettare un'area del modulo usando Progettazione aree di form in Outlook  
  
1.  Avviare Microsoft Office Outlook.  
  
2.  In Outlook, nella scheda **Sviluppatore**, fare clic **Progetta modulo**. Per altre informazioni, vedere [Procedura: visualizzare la scheda Sviluppo nella barra multifunzione](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
3.  Nella finestra **Progetta modulo** scegliere **Attività**, quindi **Apri**.  
  
4.  Nella scheda **Sviluppatore** del gruppo **Progettazione** di Outlook, scegliere **Nuova area modulo**.  
  
     Verrà aperta una nuova area del modulo. Se la finestra **Selezione campi** non viene visualizzata, fare clic su **Selezione campi** nel gruppo **Strumenti**.  
  
5.  Trascinare i campi **Oggetto** e **% completato** dalla finestra **Selezione campi** all'area del modulo.  
  
6.  Nel gruppo **Strumenti** fare clic su **Strumenti di controllo** per aprire la **Casella degli strumenti**.  
  
7.  Trascinare un'etichetta dalla **Casella degli strumenti** nell'area del modulo. Posizionare l'etichetta sotto i campi **Oggetto** e **% completato**.  
  
8.  Fare clic con il pulsante destro del mouse sull'etichetta, quindi scegliere **Proprietà avanzate**.  
  
9. Nella finestra **Proprietà** impostare la proprietà **Caption** su **L'attività dipende dalle seguenti attività**, impostare la proprietà **Width** su **200**, quindi fare clic su **Applica**.  
  
10. Trascinare un controllo ListBox dalla **Casella degli strumenti** nell'area del modulo. Posizionare la casella di riepilogo sotto l'etichetta **L'attività dipende dalle seguenti attività**.  
  
11. Selezionare la casella di riepilogo appena aggiunta.  
  
12. Nella finestra **Proprietà** impostare **Width** su **300**, quindi fare clic su **Applica**.  
  
13. Trascinare un'etichetta dalla **Casella degli strumenti** nell'area del modulo. Posizionare l'etichetta sotto la casella di riepilogo.  
  
14. Selezionare l'etichetta appena aggiunta.  
  
15. Nella finestra **Proprietà** impostare la proprietà **Caption** su **Selezionare un'attività da aggiungere all'elenco delle attività dipendenti**, impostare la proprietà **Width** su **200**, quindi fare clic su **Applica**.  
  
16. Trascinare un controllo ComboBox dalla **Casella degli strumenti** nell'area del modulo. Posizionare la casella combinata sotto l'etichetta **Selezionare un'attività da aggiungere all'elenco di attività dipendenti**.  
  
17. Selezionare la casella combinata appena aggiunta.  
  
18. Nella finestra **Proprietà** impostare la proprietà **Width** su **300**, quindi fare clic su **Applica**.  
  
19. Trascinare un controllo CommandButton dalla **Casella degli strumenti** all'area del modulo. Posizionare il pulsante di comando accanto alla casella combinata.  
  
20. Selezionare il pulsante di comando appena aggiunto.  
  
21. Nella finestra **Proprietà** impostare la proprietà **Name** su **AddDependentTask**, impostare la proprietà **Caption** su **Aggiungere attività dipendente**, impostare **Width** su **100**, quindi fare clic su **Applica**.  
  
22. In **Selezione campi**, fare clic su **Nuovo**.  
  
23. Nel campo **Nome** della finestra di dialogo **Nuovo campo** digitare **hiddenField** e scegliere **OK**.  
  
24. Trascinare il campo **hiddenField** dalla finestra **Selezione campi** all'area del modulo.  
  
25. Nella finestra **Proprietà** impostare **Visible** su **0 \- False**, quindi fare clic su **Applica**.  
  
26. In Outlook, nella scheda **Sviluppatore**, nel gruppo **Progettazione**, fare clic sul pulsante **Salva** quindi fare clic **Salva area modulo come**.  
  
     Denominare l'area del modulo **TaskFormRegion** e salvarla in una directory locale del computer.  
  
     L'area del modulo viene salvata come un file ofs \(Outlook Form Storage\). L'area del modulo viene salvata con il nome TaskFormRegion.ofs.  
  
27. Uscire da Outlook.  
  
## Creazione di un nuovo progetto di componente aggiuntivo per Outlook  
 In questo passaggio, verrà creato un progetto di componente aggiuntivo VSTO per Outlook. Più avanti in questa procedura, si importerà l'area del modulo nel progetto.  
  
#### Per creare un nuovo progetto di componente aggiuntivo VSTO di Outlook  
  
1.  In [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] creare un progetto relativo al componente aggiuntivo VSTO per Outlook con il nome **TaskAddIn**.  
  
2.  Nella finestra di dialogo **Nuovo progetto** selezionare **Crea directory per soluzione**.  
  
3.  Salvare il progetto nella directory del progetto predefinita.  
  
     Per altre informazioni, vedere [Procedura: creare progetti di Office in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
## Importazione dell'area del modulo  
 Usare la procedura guidata **Nuova area del modulo di Outlook** per importare l'area del modulo progettata in Outlook nel progetto di componente aggiuntivo VSTO per Outlook.  
  
#### Per importare l'area del modulo in un progetto di componente aggiuntivo VSTO per Outlook  
  
1.  In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **TaskAddIn**, scegliere **Aggiungi**, quindi fare clic su **Nuovo elemento**.  
  
2.  Nel riquadro **Modelli** selezionare **area del modulo di Outlook**, assegnare al file il nome **TaskFormRegion** e fare clic su **Aggiungi**.  
  
     Viene avviata la procedura guidata **Nuovaarea del modulo di Outlook**.  
  
3.  Nella pagina **Selezionare la modalità di creazione dell'area del modulo**, scegliere **Importa un file OFS \(Outlook Form Storage\)**, quindi fare clic su **Sfoglia**.  
  
4.  Nella finestra di dialogo **Percorso del file di area del modulo di Outlook esistente** passare alla posizione di **TaskFormRegion.ofs**, selezionare **TaskFormRegion.ofs**, fare clic su **Apri**, quindi su **Avanti**.  
  
5.  Nella pagina **Selezionare il tipo di area del modulo da creare** selezionare **Sostituzione completa** e scegliere **Avanti**.  
  
     Un'area del modulo *sostituzione completa* sostituisce l'intero modulo di Outlook. Per altre informazioni sui tipi di area del modulo, vedere [Creazione di aree di modulo di Outlook](../vsto/creating-outlook-form-regions.md).  
  
6.  Nella pagina **Fornire un testo descrittivo e selezionare le preferenze di visualizzazione** fare clic su **Avanti**.  
  
7.  Nella pagina **Identificare le classi di messaggi per la visualizzazione dell'area del modulo** digitare **IPM.Task.TaskFormRegion** nel campo **Fornire le classi di messaggi per la visualizzazione dell'area del modulo** e fare clic su **Fine**.  
  
     Un file TaskFormRegion.cs o TaskFormRegion.vb viene aggiunto al progetto.  
  
## Gestione degli eventi dei controlli dell'area del modulo  
 Ora che l'area del modulo è nel progetto, è possibile aggiungere il codice che gestisce l'evento Microsoft.Office.Interop.Outlook.OlkCommandButton.Click del pulsante aggiunto all'area del modulo in Outlook.  
  
 Aggiungere quindi all'evento <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> il codice che aggiorna i controlli sull'area del modulo quando l'area del modulo viene visualizzata.  
  
#### Per gestire gli eventi dei controlli nell'area del modulo  
  
1.  In **Esplora soluzioni** fare clic con il pulsante destro del mouse su TaskFormRegion.cs o TaskFormRegion.vb, quindi scegliere **Visualizza codice**.  
  
     TaskFormRegion.cs o TaskFormRegion.vb viene aperto nell'editor di codice.  
  
2.  Aggiungere il codice seguente alla classe `TaskFormRegion`. Questo codice popola la casella combinata nell'area del modulo con la riga dell'oggetto di ogni attività dalla cartella delle attività di Outlook.  
  
     [!code-csharp[Trin_Outlook_FR_Import#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/CS/TaskFormRegion.cs#1)]
     [!code-vb[Trin_Outlook_FR_Import#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/VB/TaskFormRegion.vb#1)]  
  
3.  Aggiungere il codice seguente alla classe `TaskFormRegion`. Mediante il codice vengono effettuate le seguenti attività:  
  
    -   Ricerca di Microsoft.Office.Interop.Outlook.TaskItem nella cartella delle attività chiamando il metodo di supporto `FindTaskBySubjectName` e passando l'oggetto dell'attività desiderata. Nel prossimo passaggio verrà aggiunto il metodo di supporto `FindTaskBySubjectName`.  
  
    -   Aggiunta dei valori Microsoft.Office.Interop.Outlook.TaskItem.Subject e Microsoft.Office.Interop.Outlook.TaskItem.PercentComplete alla casella di riepilogo dell'attività dipendente.  
  
    -   Aggiunta dell'oggetto dell'attività al campo nascosto sull'area del modulo. Il campo nascosto archivia questi valori come parte dell'elemento Outlook.  
  
     [!code-csharp[Trin_Outlook_FR_Import#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/CS/TaskFormRegion.cs#2)]
     [!code-vb[Trin_Outlook_FR_Import#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/VB/TaskFormRegion.vb#2)]  
  
4.  Aggiungere il codice seguente alla classe `TaskFormRegion`. Questo codice fornisce il metodo di supporto `FindTaskBySubjectName` descritto nel passaggio precedente.  
  
     [!code-csharp[Trin_Outlook_FR_Import#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/CS/TaskFormRegion.cs#3)]
     [!code-vb[Trin_Outlook_FR_Import#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/VB/TaskFormRegion.vb#3)]  
  
5.  Aggiungere il codice seguente alla classe `TaskFormRegion`. Mediante il codice vengono effettuate le seguenti attività:  
  
    -   Aggiornamento della casella di riepilogo sull'area del modulo con lo stato di completamento corrente di ogni attività dipendente.  
  
    -   Analisi del campo di testo nascosto per ottenere l'oggetto di ogni attività dipendente. Ricerca di Microsoft.Office.Interop.Outlook.TaskItem nella cartella delle attività chiamando il metodo di supporto `FindTaskBySubjectName` e passando l'oggetto di ogni attività.  
  
    -   Aggiunta dei valori Microsoft.Office.Interop.Outlook.TaskItem.Subject e Microsoft.Office.Interop.Outlook.TaskItem.PercentComplete alla casella di riepilogo dell'attività dipendente.  
  
     [!code-csharp[Trin_Outlook_FR_Import#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/CS/TaskFormRegion.cs#4)]
     [!code-vb[Trin_Outlook_FR_Import#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/VB/TaskFormRegion.vb#4)]  
  
6.  Sostituire il gestore eventi `TaskFormRegion_FormRegionShowing` con il codice seguente. Mediante il codice vengono effettuate le seguenti attività:  
  
    -   Inserimento degli oggetti delle attività nella casella combinata sull'area del modulo quando l'area del modulo viene visualizzata.  
  
    -   Chiamata del metodo di supporto `RefreshTaskListBox` quando l'area del modulo viene visualizzata. Viene visualizzata qualsiasi attività dipendente che era stata aggiunta alla casella di riepilogo quando l'elemento è stato precedentemente aperto.  
  
     [!code-csharp[Trin_Outlook_FR_Import#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/CS/TaskFormRegion.cs#5)]
     [!code-vb[Trin_Outlook_FR_Import#5](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Import/VB/TaskFormRegion.vb#5)]  
  
## Test dell'area del modulo di Outlook  
 Per verificare l'area del modulo, aggiungere le attività all'elenco di attività essenziali sull'area del modulo. Aggiornare lo stato di completamento di un'attività essenziale e quindi visualizzare lo stato di completamento aggiornato dell'attività nell'elenco delle attività essenziali.  
  
#### Per verificare l'area del modulo  
  
1.  Premere F5 per eseguire il progetto.  
  
     Viene avviato Outlook.  
  
2.  In Outlook nella scheda **Pagina iniziale** scegliere **Nuovi elementi** e quindi scegliere **Attività**.  
  
3.  Nel modulo di attività digitare **Attività dipendente** nel campo **Oggetto**.  
  
4.  Nella scheda **Attività** della barra multifunzione, fare clic su **Salva e chiudi** nel gruppo **Azioni**.  
  
5.  In Outlook, nella scheda **Pagina iniziale**, scegliere **Nuovi elementi**, fare clic **Più elementi** quindi fare clic su **Scegli modulo**.  
  
6.  Nella finestra di dialogo **Scegli modulo**, fare clic su **TaskFormRegion** e quindi su **Apri**.  
  
     Viene visualizzata l'area del modulo **TaskFormRegion**. Questo modulo sostituisce l'intero modulo di attività. La casella combinata **Selezionare un'attività da aggiungere all'elenco di attività dipendenti** viene popolata con le altre attività nella cartella delle attività.  
  
7.  Nel modulo di attività, digitare **Attività principale** nel campo **Oggetto**.  
  
8.  Nella casella combinata **Selezionare un'attività da aggiungere all'elenco di attività dipendenti**, selezionare **Attività dipendente**, quindi fare clic su **Aggiungi attività dipendente**.  
  
     **0% completato \-\- Attività dipendente** viene visualizzato nella casella di riepilogo **L'attività dipende dalle seguenti attività**. L'evento Microsoft.Office.Interop.Outlook.OlkCommandButton.Click è stato quindi correttamente gestito.  
  
9. Salvare e chiudere l'elemento **Attività principale**.  
  
10. Riaprire l'elemento Attività dipendente in Outlook.  
  
11. Nel modulo Attività dipendente, impostare il campo **% completato** su **50%**.  
  
12. Nella scheda **Attività** della barra multifunzione di Attività dipendente, fare clic su **Salva e chiudi** nel gruppo **Azioni**.  
  
13. Riaprire l'elemento **Attività principale** in Outlook.  
  
     **50% completato \-\- Attività dipendente** viene visualizzato nella casella di riepilogo **L'attività dipende dalle seguenti attività**.  
  
## Passaggi successivi  
 È possibile trovare altre informazioni sulla personalizzazione dell'interfaccia utente di un'applicazione di Outlook negli argomenti seguenti:  
  
-   Per altre informazioni sulla progettazione dell'aspetto di un'area del modulo trascinando i controlli gestiti su una finestra di progettazione visiva, vedere [Procedura dettagliata: progettazione di un'area del modulo di Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md).  
  
-   Per altre informazioni sulla personalizzazione della barra multifunzione di un elemento Outlook, vedere [Personalizzazione di una barra multifunzione per Outlook](../vsto/customizing-a-ribbon-for-outlook.md).  
  
-   Per altre informazioni sull'aggiunta di un riquadro attività personalizzato a Outlook, vedere [Riquadri attività personalizzati](../vsto/custom-task-panes.md).  
  
## Vedere anche  
 [Accesso a un'area del modulo in fase di esecuzione](../vsto/accessing-a-form-region-at-run-time.md)   
 [Creazione di aree di modulo di Outlook](../vsto/creating-outlook-form-regions.md)   
 [Linee guida per la creazione delle aree di modulo di Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Procedura dettagliata: progettazione di un'area del modulo di Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Procedura: Aggiungere un'area del modulo a un progetto di componente aggiuntivo per Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [Associazione di un'area del modulo a una classe messaggio di Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md)   
 [Azioni personalizzate nelle aree di modulo di Outlook](../vsto/custom-actions-in-outlook-form-regions.md)   
 [Procedura: impedire la visualizzazione di un'area del modulo in Outlook](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)  
  
  