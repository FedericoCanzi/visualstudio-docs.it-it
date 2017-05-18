---
title: Conversione, migrazione e aggiornamento dei progetti di Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 04/28/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Win8ExpressDesktopBlock
- w8trefactor
- VS.ReviewProjectAndSolutionChangesDialog.UpgradeRetarget
- ProjectCompatibilityDlgHelpTopic
- VS.ReviewProjectAndSolutionChangesDialog.Upgrade
helpviewer_keywords:
- conversion, projects
- asset compatibility
- projects, conversion
ms.assetid: bee759bd-6ff5-4c2e-913a-ea7d3c906c29
author: kraigb
ms.author: kraigb
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
ms.sourcegitcommit: 1512a12a163e38aaa1b1d02dab1c2b99f5c9b344
ms.openlocfilehash: ce24abc3837047025497ccf7a58f768f90607079
ms.contentlocale: it-it
ms.lasthandoff: 04/28/2017

---
# <a name="port-migrate-and-upgrade-visual-studio-projects"></a>Conversione, migrazione e aggiornamento dei progetti di Visual Studio

Ogni nuova versione di Visual Studio in genere supporta la maggior parte dei tipi di progetti, file e altre risorse supportati in precedenza. Per lavorare con questi elementi come si è sempre fatto, purché non si dipenda da funzionalità più recenti, Visual Studio garantisce la compatibilità con le versioni precedenti come Visual Studio 2015, Visual Studio 2013 e Visual Studio 2012. Vedere le [note sulla versione](https://www.visualstudio.com/vs/release-notes/) per le funzionalità specifiche di ogni versione. Il supporto per alcuni tipi tuttavia cambia periodicamente. Una versione più recente di Visual Studio può non supportare più alcuni tipi o richiedere che vengano migrati e aggiornati in modo da non essere più compatibili con le versioni precedenti. In questo argomento vengono illustrati in dettaglio i tipi di progetto interessati in Visual Studio 2017. Un elenco dei tipi supportati per Visual Studio 2017 è disponibile nell'argomento [Selezione della piattaforma e compatibilità di Visual Studio 2017](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs).

> [!Note]
> L'apertura di determinati tipi di progetto richiederà l'aggiunta al carico di lavoro appropriato usando il programma di installazione di Visual Studio.


## <a name="projects"></a>Progetti

L'elenco che segue descrive il supporto di Visual Studio 2017 per i progetti creati nelle versioni precedenti. Se nell'elenco non appare un tipo di progetto o di file che dovrebbe apparire, consultare la [versione per Visual Studio 2015 di questo argomento](https://msdn.microsoft.com/library/hh266747.aspx) e creare una nota nei commenti riportati di seguito.

| Tipo di progetto | Supporto |
| --- | --- |
| Progetti .NET Core (XPROJ) | I progetti creati con Visual Studio 2015 utilizzavano strumenti di anteprima che includono un file di progetto XPROJ. Quando si apre un file XPROJ con Visual Studio 2017 viene chiesto di eseguire la migrazione del file in formato CSPROJ (viene eseguito un backup del file XPROJ). Questo formato CSPROJ per i progetti .NET Core non è supportato in VS2015 e versioni precedenti.  Il formato XPROJ non è supportato in Visual Studio 2017 tranne che per la migrazione a CSPROJ. Per altre informazioni, vedere [Migrazione di progetti .NET Core nel formato di file con estensione csproj](https://docs.microsoft.com/dotnet/articles/core/migration/#visual-studio-2017).|
| Applicazione Web ASP.NET e applicazione Web ASP.NET Core con Application Insights abilitato | Per ogni utente di Visual Studio, le informazioni sulle risorse sono memorizzate nel Registro di sistema per ogni istanza utente. Le informazioni vengono usate quando l'utente non ha un progetto aperto e vuole eseguire una ricerca nei dati di Azure Application Insights. Visual Studio 2015 usa un percorso del Registro di sistema diverso da quello di Visual Studio 2017 e non è in conflitto.<br/><br/>Quando un utente crea un'applicazione Web ASP.NET o un'applicazione Web ASP.NET Core, la risorsa viene archiviata nel file SUO. L'utente può aprire il progetto in Visual Studio 2015 o 2017 e le informazioni sulle risorse vengono usate per entrambi purché Visual Studio supporti i progetti e le soluzioni in uso in entrambe le versioni. Gli utenti dovranno eseguire l'autenticazione una sola volta per ogni prodotto. Ad esempio, se un progetto viene creato con Visual Studio 2015 e aperto in Visual Studio 2017, l'utente dovrà eseguire l'autenticazione in Visual Studio 2017. |
| Windows Form o Webform in C#/Visual Basic | È possibile aprire il progetto in Visual Studio 2017 e Visual Studio 2015. |
| Progetti di unit test del database (CSPROJ, VBPROJ)    | I progetti di unit test di dati meno recenti verranno caricati in Visual Studio 2017 ma useranno la versione GAC delle dipendenze. Per aggiornare il progetto di unit test in modo da usare le dipendenze più recenti, fare clic con il pulsante destro sul progetto in Esplora soluzioni e selezionare **Converti nel progetto di unit test di SQL Server...** . |
| F# | Visual Studio 2017 è in grado di aprire i progetti creati in Visual Studio 2013 e 2015. Per abilitare le funzionalità di Visual Studio 2017 in questi progetti, aprire le proprietà dei progetti e modificare la destinazione fsharp.core in F# 4.1. |
| Programma di installazione<br/>MSI InstallShield | I progetti di programma di installazione creati in Visual Studio 2010 possono essere aperti in versioni successive con il supporto dell'[estensione per i progetti di programma di installazione di Visual Studio](https://marketplace.visualstudio.com/items?itemName=UnniRavindranathan-MSFT.MicrosoftVisualStudio2013InstallerProjects). È anche possibile gestire tali progetti con [InstallShield Limited Edition](https://blogs.msdn.microsoft.com/visualstudio/2013/08/15/whats-new-in-visual-studio-2013-and-installshield-limited-edition/). |
| LightSwitch | LightSwitch non è più supportato in Visual Studio 2017. I progetti creati con Visual Studio 2012 e aperti in precedenza in Visual Studio 2013 o Visual Studio 2015 verranno aggiornati e in seguito possono essere aperti solo in Visual Studio 2013 o Visual Studio 2015. |
| Strumenti di Microsoft Azure per Visual Studio | Per aprire questi tipi di progetti, installare innanzitutto [Azure SDK per .NET](http://azure.microsoft.com/downloads/), quindi aprire il progetto. Se necessario, il progetto verrà aggiornato. |
| Framework ASP.NET MVC (Model-View-Controller) | Supporto per le versioni MVC e Visual Studio:<ul><li>Visual Studio 2010 SP1 supporta MVC 2 e MVC 3; il supporto MVC 4 viene aggiunto attraverso il [download di ASP.NET 4 MVC 4 per Visual Studio 2010 SP1](https://www.microsoft.com/download/details.aspx?id=30683)</li><li>Visual Studio 2012 supporta solo MVC 3 e MVC 4</li><li>Visual Studio 2013 supporta solo MVC 4 e MVC 5</li><li>Visual Studio 2017 e Visual Studio 2015 supportano MVC 4 (è possibile aprire i progetti esistenti ma non crearne uno nuovo) e MVC 5</li></ul><br/><br/>Aggiornamento delle versioni MVC:<ul><li>Per informazioni su come eseguire automaticamente l'aggiornamento da MVC 2 a MCV 3, vedere [ASP.NET MVC 3 Application Upgrader](http://go.microsoft.com/fwlink/?LinkID=238178).</li><li>Per informazioni su come eseguire manualmente l'aggiornamento da MVC 2 a MVC 3, vedere l'articolo sugli [strumenti di aggiornamento da un progetto ASP.NET MVC 2 ad ASP.NET MVC 3](http://go.microsoft.com/fwlink/?linkid=238178).</li><li>Per informazioni su come eseguire manualmente l'aggiornamento da MVC 3 a MVC 4, vedere l'articolo sull' [aggiornamento da un progetto ASP.NET MVC 3 ad ASP.NET MVC 4](http://www.asp.net/whitepapers/mvc4-release-notes). Se il progetto è destinato a .NET Framework 3.5 SP1, è necessario modificare la destinazione per usare .NET Framework 4.</li><li>Per informazioni su come eseguire manualmente l'aggiornamento da MVC 4 a MVC 5, vedere l'articolo sull'[aggiornamento da un progetto ASP.NET MVC 4 e API Web ad ASP.NET MVC 5 e API Web 2](https://www.asp.net/mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2)</li></ul> |
| Modellazione | Se si consente a Visual Studio di aggiornare automaticamente il progetto, è possibile aprirlo in Visual Studio 2015, Visual Studio 2013 o Visual Studio 2012.<br/><br/>Il formato del progetto di modellazione non è stato modificato tra Visual Studio 2015 e Visual Studio 2017 e il progetto può essere aperto e modificato in entrambe le versioni. Tuttavia, esistono differenze di comportamento in Visual Studio 2017:<ul><li>I progetti di modellazione ora sono denominati progetti di "convalida delle dipendenze" nei menu e nei modelli.</li><li>I diagrammi UML non sono più supportati in Visual Studio 2017. I file UML sono elencati in Esplora soluzioni come prima, ma verranno aperti come file XML. Usare Visual Studio 2015 per visualizzare, creare o modificare i diagrammi UML.</li><li>In Visual Studio 2017 la convalida delle dipendenze dell'architettura non viene più eseguita quando viene compilato il progetto di modellazione. La convalida viene invece eseguita quando si compila ogni progetto di codice. Questa modifica non influisce sul progetto di modellazione, ma richiede modifiche dei progetti di codice da convalidare. Visual Studio 2017 può apportare automaticamente le modifiche necessarie ai progetti di codice ([altre informazioni](http://go.microsoft.com/fwlink/?LinkId=827800)).</li></ul> |
| Programma di installazione MSI (vdproj) | Vedere le informazioni precedenti sui progetti InstallShield. | 
| Office 2007 VSTO | Richiede un aggiornamento unidirezionale per Visual Studio 2017. |
| Office 2010 VSTO | Se il progetto è destinato a .NET Framework 4, è possibile aprirlo in Visual Studio 2010 SP1 e versioni successive. Tutti gli altri progetti richiedono un aggiornamento unidirezionale. |
| SharePoint 2010 | Quando si apre un progetto di soluzione SharePoint con Visual Studio 2017, il progetto verrà aggiornato a SharePoint 2013 o SharePoint 2016. Il carico di lavoro "Sviluppo per desktop .NET" deve essere installato in Visual Studio 2017 per l'aggiornamento.<br/><br/>Per altre informazioni su come aggiornare i progetti SharePoint, vedere [Eseguire l'aggiornamento a SharePoint 2013](https://technet.microsoft.com/library/cc303420.aspx), [Update Workflow in SharePoint Server 2013](https://technet.microsoft.com/library/dn133867.aspx) (Flusso di lavoro di aggiornamento in SharePoint Server 2013) e [Creare la farm di SharePoint 2013 per un aggiornamento basato sul collegamento di database](https://technet.microsoft.com/library/cc263026(v=office.16).aspx). |
| SharePoint 2016 | I progetti Componente aggiuntivo per SharePoint creati in Office Developer Tools Preview 2 non possono essere aperti in Visual Studio 2017. Per risolvere il problema, sarà necessario aggiornare `MinimumVisualStudioVersion` alla versione 12.0 e `MinimumOfficeToolsVersion` alla versione 12.2 nel file `.csproj` o `.vbproj`. |
| Silverlight | I progetti Silverlight non sono supportati in Visual Studio 2017. Per gestire le applicazioni Silverlight, continuare a usare Visual Studio 2015. |
| SQL Server Reporting Services, SQL Server Analysis Services (SSDT, SSAS, MSAS, SSDT) | Il supporto per questi tipi di progetto è disponibile tramite due estensioni in Visual Studio Gallery: [progetti di modellazione di Microsoft Analysis Services](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects) e [progetti di report Microsoft per Visual Studio](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio). |
| Visual C++ | È possibile usare Visual Studio 2017 per aprire soluzioni e progetti creati in Visual Studio 2015 così come sono, ma i progetti creati in versioni precedenti di Visual Studio possono richiedere l'aggiornamento del progetto o il passaggio a un set di strumenti più recenti per compilare con Visual Studio 2017. Per altre informazioni, vedere [Guida al porting e aggiornamento in Visual C++](https://docs.microsoft.com/cpp/porting/visual-cpp-porting-and-upgrading-guide). |
| Strumenti di estendibilità in Visual Studio/VSIX | I progetti con MinimumVersion 14.0 o inferiore verranno aggiornati in modo da dichiarare MinimumVersion 15.0, il che impedisce l'apertura del progetto in versioni precedenti di Visual Studio. Per consentire l'apertura di un progetto nelle versioni precedenti, impostare MinimumVersion su `$(VisualStudioVersion)`. Vedere anche [Procedura: Eseguire la migrazione di progetti di estendibilità in Visual Studio 2017](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md). |
| Visual Studio Lab Management | È possibile usare Microsoft Test Manager o Visual Studio 2010 SP1 e versioni successive per aprire gli ambienti creati in una di queste versioni. Tuttavia, per Visual Studio 2010 SP1 è necessario che la versione di Microsoft Test Manager corrisponda alla versione di Team Foundation Server per poter creare gli ambienti. |
| Strumenti di Visual Studio per Apache Cordova |Questo progetto può essere aperto in Visual Studio 2017, ma non è compatibile con le versioni precedenti. All'apertura di un progetto da Visual Studio 2015, verrà richiesto di consentire la modifica del progetto. Ciò consente di aggiornare il progetto per l'uso dei set di strumenti anziché di un file `taco.json` per gestire il controllo delle versioni della libreria Cordova, di piattaforme e plug-in, nonché delle relative dipendenze nodo/npm. Per altre informazioni, vedere la [guida alla migrazione](http://taco.visualstudio.com/docs/vs-taco-2017-migration/). |
| Windows Communication Foundation, Windows Workflow Foundation | È possibile aprire il progetto in Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 e Visual Studio 2012 |
| Windows Presentation Foundation | È possibile aprire il progetto in Visual Studio 2013, Visual Studio 2012 e Visual Studio 2010 SP1. |
| App di Windows Store/Phone | I progetti per Windows Store 8.1 e 8.0, Windows Phone 8.1 e 8.0 non sono supportati in Visual Studio 2017. Per gestire queste app, continuare a usare Visual Studio 2015. Per gestire i progetti di Windows Phone 7.x, usare Visual Studio 2012. |

