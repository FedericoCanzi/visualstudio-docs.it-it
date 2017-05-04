---
title: "Propriet&#224; bufferOffset (Float64Array) | Microsoft Docs"
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
ms.assetid: 9b566ec9-97d1-4a54-96cd-c1608f0ed330
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# Propriet&#224; bufferOffset (Float64Array)
Sola lettura.  Offset della matrice dall'inizio di ArrayBuffer, in byte, corretto in fase di costruzione.  
  
## Sintassi  
  
```javascript  
var arrayOffset = float64Array.byteOffset;  
```  
  
## Esempio  
 Nell'esempio seguente viene illustrato come ottenere l'offset della matrice.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var floatArr = new Float64Array(buffer.byteLength / 8);  
            alert(floatArr.byteOffset);  
        }  
    }  
  
```  
  
## Requisiti  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]