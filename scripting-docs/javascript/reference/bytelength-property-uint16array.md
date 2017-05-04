---
title: "Propriet&#224; byteLength (Uint16Array) | Microsoft Docs"
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
ms.assetid: a8c9229b-8ee3-4af9-9b6e-7728260c7faf
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Propriet&#224; byteLength (Uint16Array)
Solo lettura.  Lunghezza della matrice dall'inizio del relativo ArrayBuffer, espressa in byte, fissata in fase di costruzione.  
  
## Sintassi  
  
```javascript  
var arrayByteLength = uint16Array.byteLength;  
```  
  
## Esempio  
 Nell'esempio seguente viene illustrato come ottenere la lunghezza della matrice.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint16Array(buffer.byteLength / 2);  
            alert(intArr.byteLength);  
        }  
    }  
  
```  
  
## Requisiti  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]