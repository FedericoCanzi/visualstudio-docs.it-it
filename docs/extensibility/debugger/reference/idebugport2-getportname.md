---
title: "IDebugPort2::GetPortName | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPort2::GetPortName"
helpviewer_keywords: 
  - "IDebugPort2::GetPortName"
ms.assetid: 4478b3d5-aa30-4105-8d05-e3bae2f8917a
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugPort2::GetPortName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Ottiene il nome della porta.  
  
## Sintassi  
  
```cpp#  
HRESULT GetPortName(   
   BSTR* pbstrName  
);  
```  
  
```c#  
int GetPortName(   
   out string pbstrName  
);  
```  
  
#### Parametri  
 `pbstrName`  
 \[out\]  Restituisce il nome della porta.  
  
## Valore restituito  
 Se l'operazione riesce, restituisce `S_OK`; in caso contrario, restituisce un codice di errore.  
  
## Vedere anche  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)