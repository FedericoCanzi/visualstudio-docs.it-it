---
title: 'Procedura: eseguire codice quando la distribuzione esecuzione dei passaggi | Documenti Microsoft'
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, extending deployment
ms.assetid: 6b0a52e5-e0ba-41bc-9e8a-1013e51fd3ba
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e1aed7e4fe7ee30450b3ec37ce36616648e830fa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-run-code-when-deployment-steps-are-executed"></a>Procedura: eseguire codice all'esecuzione dei passaggi di distribuzione
  Se si desidera eseguire attività aggiuntive per un passaggio di distribuzione in un progetto SharePoint, è possibile gestire gli eventi generati da elementi di progetto SharePoint prima e dopo ogni passaggio di distribuzione eseguiti in Visual Studio. Per ulteriori informazioni, vedere [estensione SharePoint e distribuzione di pacchetti](../sharepoint/extending-sharepoint-packaging-and-deployment.md).  
  
### <a name="to-run-code-when-deployment-steps-are-executed"></a>Per eseguire codice quando vengono eseguiti i passaggi di distribuzione  
  
1.  Creare un'estensione di elemento di progetto, un'estensione di progetto o una definizione di un nuovo tipo di elemento di progetto. Per altre informazioni, vedere i seguenti argomenti:  
  
    -   [Procedura: Creare un'estensione di elemento del progetto SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)  
  
    -   [Procedura: Creare un'estensione di progetto SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)  
  
    -   [Procedura: Definire un tipo di elemento di progetto SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)  
  
2.  Nell'estensione, gestire il <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> e <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> gli eventi di un <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> oggetto (in un'estensione di elemento di progetto o l'estensione di progetto) o un <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition> oggetto (in una definizione di un nuovo tipo di elemento di progetto).  
  
3.  Nei gestori eventi, utilizzare il <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepStartedEventArgs> e <xref:Microsoft.VisualStudio.SharePoint.DeploymentStepCompletedEventArgs> parametri per ottenere informazioni sul passaggio di distribuzione. Ad esempio, è possibile determinare il passaggio di distribuzione è in esecuzione e se la soluzione viene distribuita o ritratta.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come gestire il <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepStarted> e <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.DeploymentStepCompleted> gli eventi in un'estensione per l'elemento di progetto di istanza di elenco. Questa estensione scrive un messaggio aggiuntivo per il **Output** finestra quando Visual Studio viene riciclato il pool di applicazioni durante la distribuzione e chiudere la soluzione.  
  
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/handledeploymentstepevents.vb#4)]
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#4](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/handledeploymentstepevents.cs#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Questo esempio richiede riferimenti agli assembly seguenti:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Distribuzione dell'estensione  
 Per distribuire l'estensione, creare un [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) per l'assembly e altri file che si desiderano distribuire con l'estensione del pacchetto. Per ulteriori informazioni, vedere [distribuzione di estensioni per gli strumenti di SharePoint in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Distribuzione e l'estensione dei pacchetti di SharePoint](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [Procedura dettagliata: Creazione di un passaggio di distribuzione personalizzato per i progetti SharePoint](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)   
 [Procedura: Eseguire codice quando un progetto SharePoint viene distribuito o ritratto](../sharepoint/how-to-run-code-when-a-sharepoint-project-is-deployed-or-retracted.md)  
  
  