---
title: "IDiaInjectedSource::get_filename | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaInjectedSource::get_filename (metodo)"
ms.assetid: 20f4fc68-335a-4971-b3a6-76501f0e8b19
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaInjectedSource::get_filename
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

recupera il nome file per il database di origine.  
  
## Sintassi  
  
```cpp#  
HRESULT get_filename (   
   BSTR* pRetVal  
);  
```  
  
#### Parametri  
 pRetVal  
 \[out\]  restituisce il nome file per il database di origine.  
  
## Valore restituito  
 Se l'operazione riesce, restituisce `S_OK`.  Restituisce `S_FALSE` se questa proprietà non è supportata.  In caso contrario, restituisce un codice di errore.  
  
## Vedere anche  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)