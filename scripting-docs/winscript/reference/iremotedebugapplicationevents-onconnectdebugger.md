---
title: "IRemoteDebugApplicationEvents::OnConnectDebugger | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplicationEvents.OnConnectDebugger
apilocation: jscript.dll
helpviewer_keywords: 
  - "IRemoteDebugApplicationEvents::OnConnectDebugger"
ms.assetid: 8c9c19b8-5426-4643-83e6-b68803ff69c4
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplicationEvents::OnConnectDebugger
Gestisce un debugger connettono l'evento.  
  
## Sintassi  
  
```  
HRESULT OnConnectDebugger(  
   IApplicationDebugger*  pad  
);  
```  
  
#### Parametri  
 `pad`  
 \[in\] il debugger è collegato.  
  
## Valore restituito  
 Il metodo restituisce un tipo `HRESULT`.  I valori possibili sono, ma non sono limitati a, quelli nella tabella seguente.  
  
|Valore|Descrizione|  
|------------|-----------------|  
|`S_OK`|Il metodo è riuscito.|  
  
## Note  
 Questo metodo gestisce il debugger si connette l'evento.  
  
## Vedere anche  
 [Interfaccia IRemoteDebugApplicationEvents](../../winscript/reference/iremotedebugapplicationevents-interface.md)