---
title: IDiaSourceFile::get_compilands | Documenti Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSourceFile::get_compilands method
ms.assetid: 57deb50a-9c22-43ea-a80c-eab205997bc4
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b351419b3331c318c6ebc1522d4e5912adae0ce9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="idiasourcefilegetcompilands"></a>IDiaSourceFile::get_compilands
Recupera un enumeratore dei moduli contenenti i numeri di riga che fa riferimento questo file.  
  
## <a name="syntax"></a>Sintassi  
  
```C++  
HRESULT get_compilands (   
   IDiaEnumSymbols** ppRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppRetVal`  
 [out] Restituisce un [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) oggetto che contiene un elenco di tutti i moduli che hanno numeri di riga che fa riferimento questo file.  
  
## <a name="return-value"></a>Valore restituito  
 Se ha esito positivo, restituisce `S_OK`; in caso contrario, restituisce un codice di errore.  
  
## <a name="see-also"></a>Vedere anche  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)