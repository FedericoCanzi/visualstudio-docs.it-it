---
title: "Propriet&#224; buffer (DataView) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: b69afc28-586e-4277-8cd6-b9d69a54fb55
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# Propriet&#224; buffer (DataView)
Sola lettura.  Ottiene l'oggetto ArrayBuffer a cui la visualizzazione fa riferimento.  
  
## Sintassi  
  
```javascript  
var arrayBuffer = dataView.buffer;  
```  
  
## Esempio  
 Nell'esempio seguente viene illustrato come ottenere la lunghezza di ArrayBuffer sottostante a DataView.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.buffer.byteLength)  
        }  
    }  
  
```  
  
## Requisiti  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]