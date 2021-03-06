---
title: "Procedura: instrumentare un&#39;applicazione Web ASP.NET compilata dinamicamente e raccogliere dati di intervallo dettagliati con il profiler tramite la riga di comando | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c140ae2-ecdd-48c7-bd89-3dc1b88e19b0
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Procedura: instrumentare un&#39;applicazione Web ASP.NET compilata dinamicamente e raccogliere dati di intervallo dettagliati con il profiler tramite la riga di comando
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

In questo argomento viene illustrato come utilizzare gli strumenti da riga di comando disponibili negli strumenti di profilatura di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] per raccogliere dati di intervallo dettagliati per un'applicazione [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] compilata in modo dinamico tramite il metodo di strumentazione del profiler.  
  
> [!NOTE]
>  Gli strumenti da riga di comando degli strumenti di profilatura sono contenuti nella sottodirectory \\Team Tools\\Performance Tools della directory di installazione di [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  Nei computer a 64 bit gli strumenti sono disponibili nelle versioni a 32 e 64 bit.  Per utilizzare gli strumenti da riga di comando del profiler, è necessario aggiungere il percorso degli strumenti alla variabile di ambiente PATH della finestra Prompt dei comandi oppure aggiungerlo al comando stesso.  Per ulteriori informazioni, vedere [Specifica del percorso degli strumenti da riga di comando](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
  
 Per raccogliere i dati di prestazioni da un'applicazione Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], modificare il file web.config dell'applicazione di destinazione per abilitare lo strumento [VSInstr.exe](../profiling/vsinstr.md) per instrumentare i file dell'applicazione compilata in modo dinamico.  Utilizzare lo strumento [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) per impostare le variabili di ambiente appropriate nel server Web per abilitare il profilo, quindi riavviare il computer.  
  
 Avviare il profiler, quindi eseguire l'applicazione di destinazione.  Quando il profiler è connesso all'applicazione, è possibile sospendere e riprendere la raccolta dei dati.  Al termine della profilatura, chiudere l'applicazione, chiudere il processo di lavoro di Internet Information Services \(IIS\), quindi arrestare il profiler.  Dopo avere completato l'attività di profilo, ripristinare gli stati originali del file web.config e del server Web.  
  
## Configurazione dell'applicazione Web ASP.NET e del server Web  
  
#### Per configurare l'applicazione Web ASP.NET e il server Web  
  
1.  Modificare il file web.config dell'applicazione di destinazione.  Vedere [Procedura: modificare file Web.Config per instrumentare e profilare applicazioni Web ASP.NET compilate dinamicamente](../profiling/how-to-modify-web-config-files-to-instrument-and-profile-dynamically-compiled-aspnet-web-applications.md).  
  
2.  Aprire una finestra del prompt dei comandi.  
  
3.  Inizializzare le variabili di ambiente di profilo.  Tipo:  
  
     **VSPerfClrEnv \/globaltraceon**  
  
    -   **\/globaltraceon** abilita il profilo tramite il metodo di strumentazione.  
  
4.  Riavviare il computer.  
  
## Esecuzione della sessione di profilo  
  
#### Per eseguire il profilo dell'applicazione Web  
  
1.  Aprire una finestra del prompt dei comandi.  
  
2.  Avviare il profiler.  Tipo:  
  
     **VSPerfCmd**  [\/start](../profiling/start.md) **:trace**  [\/output](../profiling/output.md) **:** `OutputFile` \[`Options`\]  
  
    -   L'opzione **\/start:trace** consente di inizializzare il profiler.  
  
    -   L'opzione **\/output:**`OutputFile` è obbligatoria con **\/start**.  `OutputFile` specifica il nome e il percorso del file dei dati di profilo \(vsp\).  
  
     È possibile utilizzare qualsiasi opzione riportata di seguito con l'opzione **\/start:trace**.  
  
    > [!NOTE]
    >  Le opzioni **\/user** e **\/crosssession** sono in genere obbligatorie per le applicazioni ASP.NET.  
  
    |Opzione|Descrizione|  
    |-------------|-----------------|  
    |[\/user](../profiling/user-vsperfcmd.md) **:**\[`Domain`**\\**\]`UserName`|Specifica il dominio e il nome utente dell'account proprietario del processo di lavoro ASP.NET.  Questa opzione è obbligatoria se il processo è in esecuzione come un utente diverso dall'utente connesso.  Il proprietario del processo è elencato nella colonna Nome utente della scheda Processi di Gestione attività di Windows.|  
    |[\/crosssession](../profiling/crosssession.md)|Abilita il profilo dei processi in altre sessioni di accesso.  Questa opzione è obbligatoria se l'applicazione ASP.NET è in esecuzione in una sessione diversa.  L'identificatore di sessione è elencato nella colonna ID sessione della scheda Processi di Gestione attività di Windows.  È possibile specificare **\/CS** come abbreviazione per **\/crosssession**.|  
    |[\/globaloff](../profiling/globalon-and-globaloff.md)|Avvia il profiler con la raccolta dei dati in pausa.  Utilizzare [\/globalon](../profiling/globalon-and-globaloff.md) per riprendere il profilo.|  
    |[\/counter](../profiling/counter.md) **:** `Config`|Raccoglie informazioni dal contatore delle prestazioni del processore specificato in `Config`.  Le informazioni del contatore vengono aggiunte ai dati raccolti a ogni evento di profilatura.|  
    |[\/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Specifica un contatore delle prestazioni Windows di cui raccogliere i dati durante il profilo.|  
    |[\/automark](../profiling/automark.md) **:** `Interval`|Utilizzare unicamente con **\/wincounter**.  Specifica il numero di millisecondi tra gli eventi di raccolta dati del contatore delle prestazioni Windows.  Il valore predefinito è 500 ms.|  
    |[\/events](../profiling/events-vsperfcmd.md) **:** `Config`|Specifica un evento Traccia eventi per Windows \(ETW\) di cui raccogliere i dati durante il profilo.  Gli eventi ETW vengono raccolti in un file separato con estensione etl.|  
  
3.  Avviare l'applicazione Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] nel modo usuale.  
  
## Controllo della raccolta di dati  
 Quando l'applicazione di destinazione è in esecuzione, è possibile controllare la raccolta dei dati avviando e interrompendo la scrittura dei dati nel file dei dati del profiler tramite le opzioni di **VSPerfCmd.exe**.  Controllando la raccolta dei dati, è possibile raccogliere dati per una parte specifica dell'esecuzione del programma, ad esempio l'avvio o l'arresto dell'applicazione.  
  
#### Per avviare e interrompere la raccolta dei dati  
  
-   Le coppie di opzioni seguenti avviano e interrompono la raccolta dei dati.  Specificare ogni opzione in una riga di comando separata.  È possibile attivare e disattivare più volte la raccolta dei dati.  
  
    |Opzione|Descrizione|  
    |-------------|-----------------|  
    |[\/globalon \/globaloff](../profiling/globalon-and-globaloff.md)|Avvia \(**\/globalon**\) o interrompe \(**\/globaloff**\) la raccolta dei dati per tutti i processi.|  
    |[\/processon](../profiling/processon-and-processoff.md) **:** `PID` [\/processoff](../profiling/processon-and-processoff.md)**:**`PID`|Avvia \(**\/processon**\) o interrompe \(**\/processoff**\) la raccolta dei dati per il processo specificato dall'ID processo \(`PID`\).|  
    |[\/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [\/threadoff](../profiling/threadon-and-threadoff.md)**:**`TID`|Avvia \(**\/threadon**\) o interrompe \(**\/threadoff**\) la raccolta dei dati per il thread specificato dall'ID thread \(`TID`\).|  
  
-   È inoltre possibile utilizzare l'opzione **VSPerfCmd.exe** [\/mark](../profiling/mark.md) per inserire un contrassegno di profilo nel file di dati.  Il comando **\/mark** aggiunge un identificatore, un timestamp e una stringa di testo facoltativa definita dall'utente.  I contrassegni possono essere utilizzati per filtrare i dati nelle visualizzazioni dati e nei rapporti del profiler.  
  
## Fine della sessione di profilo  
 Per terminare una sessione di profilo, chiudere l'applicazione Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] di destinazione, reimpostare IIS per interrompere il processo profilato, quindi arrestare il profiler.  
  
#### Per terminare una sessione di profilo  
  
1.  Chiudere l'applicazione Web [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)].  
  
2.  Chiudere il processo di lavoro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] reimpostando Internet Information Services \(IIS\).  Tipo:  
  
     **IISReset \/stop**  
  
3.  Arrestare il profiler.  Tipo:  
  
     **VSPerfCmd**  [\/shutdown](../profiling/shutdown.md)  
  
4.  Riavviare IIS.  Tipo:  
  
     **IISReset \/start**  
  
## Ripristino della configurazione dell'applicazione e del computer  
 Dopo avere completato l'attività di profilo, sostituire il file web.config, cancellare le variabili di ambiente di profilo e riavviare il computer per ripristinare gli stati antecedenti il profilo del server e dell'applicazione.  
  
#### Per ripristinare la configurazione dell'applicazione e del computer  
  
1.  Sostituire il file web.config con una copia del file originale.  
  
2.  Cancellare le variabili di ambiente di profilo.  Tipo:  
  
     **VSPerfCmd \/globaloff**  
  
3.  Riavviare il computer.  
  
## Vedere anche  
 [Profilatura di applicazioni Web ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Visualizzazioni dei dati del metodo di strumentazione](../profiling/instrumentation-method-data-views.md)