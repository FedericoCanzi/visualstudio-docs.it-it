---
title: MACHINE_INFO_FLAGS | Documenti Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MACHINE_INFO_FLAGS
helpviewer_keywords: MACHINE_INFO_FLAGS enumeration
ms.assetid: 1482095d-9a2e-4ef1-9e14-362c0b85194e
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b820c7290326c29ca7453e175b588af6832f6009
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="machineinfoflags"></a>MACHINE_INFO_FLAGS
Utilizzato per descrivere un computer.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
enum enum_MACHINE_INFO_FLAGS {   
   MCIFLAG_TERMINAL_SERVICES_AVAILABLE = 0x00000001  
};  
typedef DWORD MACHINE_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_MACHINE_INFO_FLAGS {   
   MCIFLAG_TERMINAL_SERVICES_AVAILABLE = 0x00000001  
};  
```  
  
## <a name="members"></a>Membri  
 MCIFLAG_TERMINAL_SERVICES_AVAILABLE  
 Indica che i servizi terminal sono disponibili.  
  
## <a name="remarks"></a>Note  
 Utilizzato come il `Flags` appartenente il [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) struttura.  
  
## <a name="requirements"></a>Requisiti  
 Intestazione: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)