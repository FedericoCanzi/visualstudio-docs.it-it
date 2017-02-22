---
title: "IDebugModule3::IsUserCode | Microsoft Docs"
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
  - "IDebugModule3::IsUserCode"
helpviewer_keywords: 
  - "IDebugModule3::IsUserCode"
ms.assetid: 77022946-bb8b-4114-aa81-614df6e54b13
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugModule3::IsUserCode
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Recupera le informazioni su se il modulo rappresenta il codice utente o meno.  
  
## Sintassi  
  
```cpp#  
HRESULT IsUserCode(  
   BOOL* pfUser  
);  
```  
  
```c#  
int IsUserCode(  
   out int pfUser  
);  
```  
  
#### Parametri  
 `pfUser`  
 \[out\]  Diverso da zero \(`TRUE`\) se il modulo rappresenta il codice utente, zero \(`FALSE`\) in caso contrario.  
  
## Valore restituito  
 Se l'operazione riesce, restituisce `S_OK`; in caso contrario, codice di errore restituito.  
  
## Vedere anche  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)