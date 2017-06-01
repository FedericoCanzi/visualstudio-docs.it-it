---
title: "Istruzioni per commenti (JavaScript) | Microsoft Docs"
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
  - "Comment_JavaScript"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "comment (istruzioni)"
  - "commenti, esclusione"
ms.assetid: b604824f-ac17-49d3-bcdb-2a893ab5fff8
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Istruzioni per commenti (JavaScript)
Imposta i commenti che il parser [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] deve ignorare.  
  
## Sintassi  
  
```  
Single-line Comment:  
// comment   
```  
  
```  
Multiline Comment:  
/*  
comment  
*/  
```  
  
```  
Comments with conditional compilation:  
//@CondStatement   
  
/*@  
condStatement  
@*/  
```  
  
## Note  
 L'argomento `comment` è il testo di qualsiasi commento da includere nello script.  L'argomento `condStatement` deve essere usato se la compilazione condizionale è attivata.  Se si usano i commenti a riga singola, non è possibile inserire spazi tra i caratteri "\/ \/" e "@".  
  
 Usare i commenti per impedire la lettura di parti di uno script da parte del parser [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  È possibile usare i commenti per includere note esplicative in un programma.  
  
 Se si usano i commenti a riga singola, il parser ignora il testo compreso tra il marcatore di commento e la fine della riga.  Se si usano i commenti a più righe, il parser ignora il testo compreso tra i marcatori di inizio\/fine.  
  
 I commenti vengono usati per supportare la compilazione condizionale mantenendo la compatibilità con i browser che non supportano tale funzionalità.  Questi browser trattano rispettivamente queste forme di commenti come commenti a riga singola o su più righe.  
  
## Esempio  
 Nell'esempio seguente vengono illustrati gli usi più comuni dei commenti.  
  
```javascript  
/* This is a multiline comment that  
    can span as many lines as necessary.  */  
function myfunction(arg1, arg2){  
    var r;  
    // This is a single line comment.  
    r = arg1 + arg2  
    return(r);  
}  
```  
  
## Esempio  
 Nell'esempio seguente viene illustrato come usare la compilazione condizionale.  In questo esempio vengono usati delimitatori di commento speciali applicati solo se la compilazione condizionale viene attivata dall'istruzione `@cc_on`.  I motori di script che non supportano la compilazione condizionale vedono solo il messaggio che indica che la compilazione condizionale non è supportata.  
  
```javascript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
## Requisiti  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]