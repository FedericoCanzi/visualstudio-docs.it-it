---
title: "Metodo IEnumJsStackFrames::Next | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumJsStackFrames.Next
apilocation: jscript9diag.dll
ms.assetid: efceb3a1-9239-4f55-9cbb-94670679988b
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# Metodo IEnumJsStackFrames::Next
Ottiene il numero specificato di frame.  
  
## Sintassi  
  
```  
HRESULT Next(  
   ULONG cFrameCount,  
   JS_NATIVE_FRAME *pFrames,  
   ULONG *pcFetched  
);  
```  
  
#### Parametri  
 `cFrameCount`  
 \[in\] Numero di frame da ottenere.  
  
 `pFrames`  
 \[out\] Matrice in cui archiviare i frame.  
  
 `pcFetched`  
 \[out\] Numero di frame restituiti.  
  
## Valore restituito  
  
## Requisiti  
 **Intestazione:** jscript9diag.h  
  
## Vedere anche  
 [Interfaccia IEnumJsStackFrames](../../winscript/reference/ienumjsstackframes-interface.md)