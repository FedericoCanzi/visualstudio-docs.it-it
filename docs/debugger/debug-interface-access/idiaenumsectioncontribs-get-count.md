---
title: "IDiaEnumSectionContribs::get_Count | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaEnumSectionContribs::get_Count (interfaccia)"
ms.assetid: 94f11de3-9393-4a5c-9814-2e6bdb597f70
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumSectionContribs::get_Count
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Recupera il numero dei contributi della sezione.  
  
## Sintassi  
  
```cpp#  
HRESULT get_Count (   
   LONG* pRetVal  
);  
```  
  
#### Parametri  
 `pRetVal`  
 \[out\]  Restituisce il numero dei contributi della sezione.  
  
## Valore restituito  
 Se l'operazione riesce, restituisce `S_OK`; in caso contrario, restituisce un codice di errore.  
  
## Vedere anche  
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [IDiaEnumSectionContribs::Item](../../debugger/debug-interface-access/idiaenumsectioncontribs-item.md)