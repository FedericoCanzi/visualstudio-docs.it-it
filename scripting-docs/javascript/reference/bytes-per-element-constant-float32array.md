---
title: "Costante BYTES_PER_ELEMENT (Float32Array) | Microsoft Docs"
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
ms.assetid: faaae7ad-fea5-420e-b8af-cc051cd9b06d
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# Costante BYTES_PER_ELEMENT (Float32Array)
Dimensione in byte di ciascun elemento nella matrice.  
  
## Sintassi  
  
```javascript  
var arraySize = int8Array.BYTES_PER_ELEMENT;  
```  
  
## Esempio  
 Nell'esempio seguente viene illustrato come ottenere la dimensione degli elementi della matrice.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            alert(floatArr.BYTES_PER_ELEMENT);  
        }  
    }  
  
```  
  
## Requisiti  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]