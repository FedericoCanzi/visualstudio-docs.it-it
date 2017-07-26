---
title: Importa/Esporta impostazioni (comando) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
caps.latest.revision: 5
author: kempb
ms.author: kempb
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: dca11a81e650f0470c891cb79623f9cc088ea669
ms.contentlocale: it-it
ms.lasthandoff: 05/24/2017

---
# <a name="import-and-export-settings-command"></a>Importa/Esporta impostazioni (comando)
Consente di importare, esportare o reimpostare le impostazioni di [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]  
```  
  
## <a name="switches"></a>Opzioni  
 /export:`filename`  
 Parametro facoltativo. Esporta le impostazioni correnti nel file specificato.  
  
 /import:`filename`  
 Parametro facoltativo. Importa le impostazioni correnti nel file specificato.  
  
 /reset  
 Parametro facoltativo. Reimposta le impostazioni correnti.  
  
## <a name="remarks"></a>Note  
 Se si esegue questo comando senza opzioni viene visualizzata l'**Importazione/Esportazione guidata delle impostazioni**. Per altre informazioni, vedere [Procedura: Condividere le impostazioni tra computer o versioni di Visual Studio](http://msdn.microsoft.com/en-us/1131fb10-35c1-42da-9cd8-91aa3235b882).  
  
## <a name="example"></a>Esempio  
 Il comando seguente esporta le impostazioni correnti nel file `MyFile.vssettings`.  
  
```  
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Personalizzare l'IDE di Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)   
 [Comandi di Visual Studio](../../ide/reference/visual-studio-commands.md)
