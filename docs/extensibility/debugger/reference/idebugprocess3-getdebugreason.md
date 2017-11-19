---
title: IDebugProcess3::GetDebugReason | Documenti Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProcess3::GetDebugReason
helpviewer_keywords: IDebugProcess3::GetDebugReason
ms.assetid: f23fbabc-8b18-4278-bebf-4cdc7091513c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1c88282541c20e93f86c5d8369ade795ecb95387
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprocess3getdebugreason"></a>IDebugProcess3::GetDebugReason
Questo metodo restituisce il motivo che il processo è stato avviato per il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDebugReason(  
   DEBUG_REASON* pReason  
);  
```  
  
```csharp  
int GetDebugReason(  
   out enum_DEBUG_REASON pReason  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pReason`  
 [out] Restituisce un valore di [DEBUG_REASON](../../../extensibility/debugger/reference/debug-reason.md) enumerazione.  
  
## <a name="return-value"></a>Valore restituito  
 Se ha esito positivo, restituisce `S_OK`; in caso contrario, restituisce il codice di errore.  
  
## <a name="see-also"></a>Vedere anche  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [DEBUG_REASON](../../../extensibility/debugger/reference/debug-reason.md)