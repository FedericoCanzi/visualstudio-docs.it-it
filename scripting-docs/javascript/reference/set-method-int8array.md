---
title: impostare il metodo (Int8Array) | Documenti Microsoft
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4beae82e-8556-48aa-86c6-18c8859d913e
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bfa9c319caf448e20888aeefa2f29aaade9aa364
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-int8array"></a>Metodo set (Int8Array)
Imposta un valore o una matrice di valori.  
  
## <a name="syntax"></a>Sintassi  
  
```JavaScript  
int8Array.set(index, value);  
int8Array.set(array, offset);  
  
```  
  
## <a name="parameters"></a>Parametri  
 `index`  
 Indice della posizione da impostare.  
  
 `value`  
 Valore da impostare.  
  
 `array`  
 Matrice tipizzata o non tipizzata di valori da impostare.  
  
 `offset`  
 Indice nella matrice corrente in base al quale devono essere scritti i valori.  
  
## <a name="remarks"></a>Note  
 Se la matrice di input è un oggetto TypedArray, le due matrici possono utilizzare lo stesso oggetto ArrayBuffer sottostante. In questa situazione, l'impostazione dei valori viene eseguita come se tutti i dati venissero prima copiati in un buffer temporaneo che non si sovrappone ad alcuna matrice e come se successivamente i dati presenti nel buffer temporaneo venissero copiati nella matrice corrente.  
  
 Se l'offset più la lunghezza della matrice specificata non è compreso nell'intervallo per l'oggetto TypedArray corrente, viene generata un'eccezione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come impostare il primo elemento della matrice.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int8Array(buffer.byteLength);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Requisiti  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]