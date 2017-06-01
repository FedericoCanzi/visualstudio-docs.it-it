---
title: "Metodo ubound (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "ubound"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "ubound (metodo)"
ms.assetid: 761811c5-9a3d-4cb3-bfe0-0a8749f34496
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# Metodo ubound (VBArray) (JavaScript)
Restituisce il valore di indice più elevato usato nella dimensione specificata dell'oggetto VBArray.  
  
## Sintassi  
  
```  
  
safeArray.ubound(dimension)  
```  
  
## Parametri  
 *safeArray*  
 Obbligatorio. Un oggetto VBArray.  
  
 `dimension`  
 Facoltativo. La dimensione dell'oggetto VBArray per il quale si desidera recuperare l'indice più elevato. Se omesso, `ubound` si comporta come se venisse passato il valore 1.  
  
## Note  
 Se l'oggetto VBArray è vuoto, il metodo `ubound` restituisce non definito. Se `dim` è maggiore del numero di dimensioni dell'oggetto VBArray o è negativo, il metodo genera un errore del tipo "Indice non incluso nell'intervallo".  
  
## Esempio  
 L'esempio seguente si compone di tre parti: La prima parte è il codice VBScript per creare una matrice protetta di Visual Basic. La seconda parte è il codice [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] che determina il numero di dimensioni della matrice protetta e il limite superiore di ogni dimensione. Entrambe queste parti vanno inserite nella sezione \<HEAD\> di una pagina HTML. La terza parte è il codice [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] che va inserito nella sezione \<BODY\> per eseguire le altre due parti.  
  
```javascript  
<head>  
<script type="text/vbscript">  
<!--  
Function CreateVBArray()  
   Dim i, j, k  
   Dim a(2, 2)  
   k = 1  
   For i = 0 To 2  
      For j = 0 To 2  
         a(j, i) = k  
         k = k + 1  
      Next  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vba)  
{  
   var i;  
   var a = new VBArray(vba);  
   var s = "";  
   for (i = 1; i <= a.dimensions(); i++)  
   {  
      s += "The upper bound of dimension ";  
      s += i + " is ";  
      s += a.ubound(i);  
      s += ".<br />";  
   }  
   return (s);  
}  
-->  
</script>  
</head>  
  
<body>  
<script type="text/javascript">  
   document.write(VBArrayTest(CreateVBArray()));  
</script>  
</body>  
```  
  
## Requisiti  
 Supportato nelle modalità documento seguenti: Quirks, standard di Internet Explorer 6, standard di Internet Explorer 7, standard di Internet Explorer 8, standard di Internet Explorer 9 e standard di Internet Explorer 10. Non supportato in applicazioni [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)]. Vedere [Informazioni sulla versione](../../javascript/reference/javascript-version-information.md).  
  
 **Si applica a**: [Oggetto VBArray](../../javascript/reference/vbarray-object-javascript.md)  
  
## Vedere anche  
 [Metodo dimensions \(VBArray\)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [Metodo getItem \(VBArray\)](../../javascript/reference/getitem-method-vbarray-javascript.md)   
 [Metodo lbound \(VBArray\)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [Metodo toArray \(VBArray\)](../../javascript/reference/toarray-method-vbarray-javascript.md)