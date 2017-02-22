---
title: "IDebugDocumentTextEvents2::onDestroy | Microsoft Docs"
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
  - "IDebugDocumentTextEvents2::OnDestroy"
helpviewer_keywords: 
  - "IDebugDocumentTextEvents2::onDestroy"
ms.assetid: 60e4689c-c899-4c14-9d18-96393b741e1f
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentTextEvents2::onDestroy
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

Indica che l'intero documento è stato eliminato.  
  
## Sintassi  
  
```cpp#  
HRESULT onDestroy(   
   void   
);  
```  
  
```c#  
int onDestroy();  
```  
  
## Valore restituito  
 Se l'operazione riesce, restituisce `S_OK`; in caso contrario, restituisce un codice di errore.  
  
## Vedere anche  
 [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)