---
title: 'Procedura: aggiungere un metodo Finder specifico | Documenti Microsoft'
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
- Business Data Connectivity service [SharePoint development in Visual Studio], Specific Finder
- BDC [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], get an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], Specific Finder
- Business Data Connectivity service [SharePoint development in Visual Studio], get an entity
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6bf2c422efd005c8121ee49fed6dbc7329708b90
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-specific-finder-method"></a>Procedura: aggiungere un metodo Finder specifico
  È possibile restituire una sola istanza di entità mediante la creazione di un *Finder specifico* metodo. Il servizio di integrazione applicativa dei dati (BDC) esegue il metodo Finder specifico quando un utente sceglie un'entità in una web part dati business o un elenco esterno. Per ulteriori informazioni, vedere [progettazione di un modello di connettività dei dati di Business](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
### <a name="to-create-a-specific-finder-method"></a>Per creare un metodo Finder specifico  
  
1.  Nella finestra di progettazione di integrazione applicativa dei dati, scegliere un'entità.  
  
     Per informazioni su come aggiungere un'entità alla finestra di progettazione di integrazione applicativa dei dati in Visual Studio, vedere [procedura: aggiungere un'entità a un modello](../sharepoint/how-to-add-an-entity-to-a-model.md).  
  
2.  Nella barra dei menu, scegliere **vista**, **altre finestre**, **Dettagli metodo di integrazione applicativa dei dati**.  
  
     Il **Dettagli metodo di integrazione applicativa dei dati** verrà visualizzata la finestra. Per ulteriori informazioni su tale finestra, vedere [panoramica degli strumenti di progettazione del modello di integrazione applicativa dei dati](../sharepoint/bdc-model-design-tools-overview.md).  
  
3.  Nel **aggiungere un metodo** scegliere **Crea metodo Finder specifico**.  
  
     Visual Studio aggiunge i seguenti elementi al modello. Questi elementi vengono visualizzati nel **Dettagli metodo di integrazione applicativa dei dati** finestra.  
  
    -   Un metodo.  
  
    -   Un parametro di input per il metodo.  
  
    -   Un parametro restituito del metodo.  
  
    -   Un descrittore di tipo per ogni parametro.  
  
    -   Un'istanza del metodo per il metodo.  
  
     Per ulteriori informazioni, vedere [progettazione di un modello di connettività dei dati di Business](../sharepoint/designing-a-business-data-connectivity-model.md).  
  
4.  Aprire Visual Studio **proprietà** finestra.  
  
5.  Configurare il descrittore di tipo del parametro restituito come un descrittore di tipo di entità. Per informazioni su come creare un descrittore di tipo di entità, vedere [procedura: definire il descrittore di tipo di parametro](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).  
  
    > [!NOTE]  
    >  Non è necessario eseguire questo passaggio se è stato aggiunto un metodo Finder all'entità. Visual Studio utilizza il descrittore di tipo definito nel metodo di ricerca.  
  
    > [!NOTE]  
    >  Se il campo dell'identificatore del tipo di entità rappresenta un campo in una tabella di database che viene generato automaticamente, impostare il **Read-only** proprietà del campo dell'identificatore di **True**.  
  
6.  Nel **Dettagli metodo** finestra, scegliere l'istanza del metodo del metodo.  
  
7.  Nel **finestra proprietà**, impostare il **nome parametro restituito** proprietà sul nome del parametro restituito del metodo. Per ulteriori informazioni sulle proprietà di istanza di metodo, vedere [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).  
  
8.  In **Esplora**, aprire il menu di scelta rapida del servizio file di codice che è stato generato per l'entità e quindi scegliere **Visualizza codice**.  
  
     File di codice servizio dell'entità verrà aperto nell'Editor di codice. Per ulteriori informazioni sui file di codice servizio dell'entità, vedere [creazione di un modello di connettività dei dati di Business](../sharepoint/creating-a-business-data-connectivity-model.md).  
  
9. Aggiungere codice al metodo Finder specifico. Mediante il codice vengono effettuate le seguenti attività:  
  
    -   Recupera un record da un'origine dati.  
  
    -   Restituisce un'entità per il servizio di integrazione applicativa dei dati.  
  
     Nell'esempio seguente viene restituito un contatto dal database di esempio AdventureWorks per SQL Server.  
  
    > [!NOTE]  
    >  Sostituire il valore di `ServerName` campo con il nome del server.  
  
     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 [Progettazione di un modello di integrazione applicativa dei dati Business](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [Procedura: aggiungere un metodo Finder](../sharepoint/how-to-add-a-finder-method.md)   
 [Procedura: aggiungere un metodo Creator](../sharepoint/how-to-add-a-creator-method.md)   
 [Procedura: aggiungere un metodo Deleter](../sharepoint/how-to-add-a-deleter-method.md)   
 [Procedura: aggiungere un metodo Updater](../sharepoint/how-to-add-an-updater-method.md)   
 [Panoramica degli strumenti di progettazione del modello di integrazione applicativa dei dati](../sharepoint/bdc-model-design-tools-overview.md)   
 [Procedura: aggiungere un parametro a un metodo](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [Procedura: Definire un'istanza di metodo](../sharepoint/how-to-define-a-method-instance.md)  
  
  