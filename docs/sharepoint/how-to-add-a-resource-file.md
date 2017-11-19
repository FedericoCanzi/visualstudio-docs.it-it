---
title: 'Procedura: aggiungere un File di risorse | Documenti Microsoft'
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
- VB
- CSharp
helpviewer_keywords:
- resource files [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, resource files
ms.assetid: 2b4ac232-992e-4070-8e98-6f11eb88e1a8
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7233bc1a739bd3bf6544aad879f898bf3848ee7b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-resource-file"></a>Procedura: aggiungere un file di risorse
  I comandi per l'aggiunta di file di risorse è il menu di scelta rapida del nodo della soluzione e i nodi di funzionalità in Esplora soluzioni. Per ulteriori informazioni, vedere [localizzazione di soluzioni SharePoint](../sharepoint/localizing-sharepoint-solutions.md).  
  
### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>Per aggiungere un file di risorse globale a una soluzione di SharePoint  
  
1.  In [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], aprire una soluzione di SharePoint.  
  
2.  In **Esplora**, scegliere un nodo di progetto SharePoint, quindi, nella barra dei menu, **progetto**, **Aggiungi nuovo elemento**.  
  
3.  Nel **Aggiungi nuovo elemento** finestra di dialogo scegliere il **File di risorse globali** modello, quindi scegliere il **Aggiungi** pulsante.  
  
    > [!NOTE]  
    >  Il modello di elemento di progetto di File di risorse globali viene visualizzata solo quando viene selezionato un elemento di progetto SharePoint.  
  
4.  Nel **Aggiungi risorsa** finestra di dialogo, scegliere una lingua per il file di risorse, ad esempio inglese (Stati Uniti).  
  
     Questo passaggio aggiunge un file di risorse globale per la soluzione nel formato di risorsa*x***.** *delle impostazioni cultura***.** RESX, ad esempio Resource1-US.  
  
5.  Quando il **Editor risorse** viene aperto in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], aggiungere risorse al file di risorse.  
  
### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>Per aggiungere un file di risorse di funzionalità a una funzionalità SharePoint  
  
1.  Se la soluzione di SharePoint non è già aperta in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], aprire la soluzione.  
  
2.  In **Esplora**, aprire il menu di scelta rapida per il nome di una funzionalità nel **funzionalità** nodo, quindi scegliere **Aggiungi risorsa funzionalità**.  
  
     Questo passaggio viene aggiunto un file di risorse per la funzionalità nel formato, *ResourceFileName***.** *delle impostazioni cultura***.** RESX, ad esempio Feature1-US.  
  
3.  Quando il **Editor risorse** viene aperto in [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], aggiungere risorse al file di risorse.  
  
## <a name="see-also"></a>Vedere anche  
 [Sviluppo di soluzioni SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  