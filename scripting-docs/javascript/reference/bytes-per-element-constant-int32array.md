---
title: "Costante BYTES_PER_ELEMENT (Int32Array) | Microsoft Docs"
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
ms.assetid: 95a84abb-c8d3-4fa9-8944-0fde9cfdb3df
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Costante BYTES_PER_ELEMENT (Int32Array)
Dimensione in byte di ciascun elemento nella matrice.  
  
## Sintassi  
  
```javascript  
var arraySize = int32Array.BYTES_PER_ELEMENT;  
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
            var intArr = new Int32Array(buffer.byteLength / 4);  
            alert(intArr.BYTES_PER_ELEMENT);  
        }  
    }  
  
```  
  
## Requisiti  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]