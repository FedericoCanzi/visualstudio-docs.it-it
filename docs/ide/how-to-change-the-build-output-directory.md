---
title: 'Procedura: Modificare la directory di output della compilazione | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
caps.latest.revision: 14
author: kempb
ms.author: kempb
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
translationtype: Human Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 14be502abb42d6bb9637e7394ec8bf20b50c4231
ms.lasthandoff: 04/05/2017

---
# <a name="how-to-change-the-build-output-directory"></a>Procedura: modificare la directory dell'output compilato
Il percorso dell'output generato dal progetto può essere specificato a livello di singole configurazioni (per debug e/o rilascio).  
  
> [!NOTE]
>  Se si ha un progetto **Installazione** , vedere la nota alla fine di questo articolo.  
  
## <a name="changing-the-build-output-directory"></a>Modifica della directory dell'output di compilazione  
  
#### <a name="to-change-the-build-output-directory"></a>Per modificare la directory dell'output di compilazione  
  
1.  Nella barra dei menu scegliere **Progetto**, *NomeApp* **Proprietà**. In alternativa, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**.  
  
2.  Per i progetti Basic, selezionare la scheda **Compilazione** . Per i progetti Visual C#, selezionare la scheda **Compilazione** . Per un progetto C++ o JavaScript, selezionare la scheda **Generale** .  
  
3.  Nell'elenco a discesa della configurazione nella parte superiore, scegliere la configurazione per cui si vuole modificare il percorso di output (debug, rilascio o tutte).  
  
     Individuare la voce relativa al percorso di output (**Percorso dell'output di compilazione** in Visual Basic **Directory di output** in Visual C++, **Percorso di Output** in JavaScript e C#). Specificare una nuova directory dell'output di compilazione relativa alla directory del progetto.  
  
> [!NOTE]
>  In un progetto di installazione, la casella **Nome file di output** modifica solo il percorso del file Setup.exe file, non il percorso dei file di progetto. Per ulteriori informazioni, vedere **Compilazione, proprietà di configurazione, finestra di dialogo delle proprietà del progetto di distribuzione**.  
  
## <a name="see-also"></a>Vedere anche  
 [Build Page, Project Designer (C#)](../ide/reference/build-page-project-designer-csharp.md)  (Pagina Compilazione, Progettazione progetti (C#))  
 [General Property Page (Project)](/cpp/ide/general-property-page-project)  (Pagina delle proprietà Generale (Progetto))  
 [Compiling and Building](../ide/compiling-and-building-in-visual-studio.md) (Compilazione e creazione)
