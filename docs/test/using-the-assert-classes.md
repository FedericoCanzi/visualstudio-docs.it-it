---
title: Uso di classi Assert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.assetid: da1b7a0d-4f1d-4d50-a07e-7b3ff60053f9
caps.latest.revision: 27
ms.author: douge
manager: douge
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ab78b6b8eaa8156ed2c8a807b1d8a80e75afa84
ms.openlocfilehash: 5a4f1fd5bf35a6010c2d919194b8ef21073e9a18
ms.contentlocale: it-it
ms.lasthandoff: 05/19/2017

---
# <a name="using-the-assert-classes"></a>Utilizzo di classi Assert
Usare le classi Assert dello spazio dei nomi UnitTestingFramework per verificare funzionalità specifiche. Un metodo di unit test verifica il codice di un metodo nel codice di sviluppo, ma segnala la correttezza del comportamento del codice soltanto se sono state incluse istruzioni Assert.  
  
## <a name="kinds-of-asserts"></a>Tipi di asserzioni  
 Lo spazio dei nomi <xref:Microsoft.VisualStudio.TestTools.UnitTesting> rende disponibili diversi tipi di classi Assert:  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>  
  
 Nel metodo di test è possibile chiamare qualsiasi numero di metodi della classe Assert, ad esempio Assert.AreEqual(). La classe Assert offre numerosi metodi tra cui scegliere e molti di questi metodi presentano vari overload.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>  
  
 Usare la classe CollectionAssert per confrontare raccolte di oggetti e per verificare lo stato di una o più raccolte.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>  
  
 Usare la classe StringAssert per confrontare stringhe. Questa classe contiene numerosi metodi utili, ad esempio StringAssert.Contains, StringAssert.Matches e StringAssert.StartsWith.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>  
  
 L'eccezione AssertFailedException è generata ogni volta che un test non viene superato. Un test non viene superato se scade a causa di un timeout, genera un'eccezione imprevista o contiene un'istruzione Assert che produce un risultato Non superato.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>  
  
 L'eccezione AssertInconclusiveException è generata ogni volta che un test produce un risultato Senza risultati. In genere, un'istruzione Assert.Inconclusive viene aggiunta a un test su cui si sta lavorando per indicare che non è ancora pronto per l'esecuzione.  
  
> [!NOTE]
>  Una strategia alternativa sarebbe contrassegnare un test che non è pronto per l'esecuzione con l'attributo Ignore. Tuttavia, ciò comporta lo svantaggio che non è possibile generare facilmente un report sul numero di test rimasti da implementare.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>  
  
 Se si scrive una nuova classe di eccezione Assert, impostare tale classe in modo che erediti dalla classe di base UnitTestAssertException rende più semplice identificare l'eccezione come un errore di asserzione, anziché un'eccezione imprevista generata dal codice di test o di produzione.  
  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>  
  
 Decorare un metodo di test con l'attributo ExpectedExceptionAttribute quando si vuole che il metodo di test verifichi che un'eccezione di cui è prevista la generazione da parte di un metodo nel codice di sviluppo sia effettivamente generata nel metodo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>   
 [Creazione ed esecuzione di unit test per il codice esistente](http://msdn.microsoft.com/en-us/e8370b93-085b-41c9-8dec-655bd886f173)

