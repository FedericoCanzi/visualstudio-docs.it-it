---
title: "Unit test per metodi generici | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "generics, e unit test"
  - "unit test, e generics"
ms.assetid: ffc89814-a7df-44fc-aef5-dd3dfeb28a9b
caps.latest.revision: 47
caps.handback.revision: 47
ms.author: "mlearned"
manager: "douge"
---
# Unit test per metodi generici
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

È possibile generare unit test per metodi generici procedendo esattamente come per altri metodi, come descritto in [How to: Create and Run a Unit Test](http://msdn.microsoft.com/it-it/5e0f43cf-5e51-48e2-9c98-0eb9324bdc48).  Le sezioni seguenti forniscono informazioni ed esempi relativi alla creazione di unit test per metodi generici.  
  
## Argomenti di tipo e vincoli di tipo  
 Quando [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] genera uno unit test per una classe generica, ad esempio `MyList<T>`, vengono generati due metodi: un helper generico e un metodo di test.  Se `MyList<T>` dispone di uno o più vincoli di tipo, l'argomento di tipo deve soddisfare tutti i vincoli.  Per assicurarsi che il codice generico sottoposto a test funzioni come previsto per tutti gli input consentiti, il metodo di test chiama il metodo helper generico con tutti i vincoli che si desidera testare.  
  
## Esempi  
 Gli esempi seguenti illustrano unit test per i metodi generici.  
  
-   [Modifica del codice di test generato](#EditingGeneratedTestCode).  Questo esempio include due sezioni, relative a codice di test generato e codice di test modificato.  Mostra come modificare il codice di test non elaborato generato da un metodo generico per creare un metodo di test utile.  
  
-   [Uso di un vincolo di tipo](#TypeConstraintNotSatisfied).  Questo esempio mostra uno unit test per un metodo generico che usa un vincolo di tipo.  In questo esempio il vincolo di tipo non viene soddisfatto.  
  
###  <a name="EditingGeneratedTestCode"></a> Esempio 1: Modifica del codice di test generato  
 Il codice di test in questa sezione consente di testare un metodo di codice sottoposto a test denominato `SizeOfLinkedList()`.  Questo metodo restituisce un numero intero che specifica il numero di nodi nell'elenco collegato.  
  
 Il primo esempio di codice, nella sezione relativa al codice di test generato, mostra il codice di test non modificato, così come è stato generato da Visual Studio Enterprise.  Il secondo esempio, nella sezione relativa al codice di test modificato, mostra come eseguire il test del funzionamento del metodo SizeOfLinkedList per due tipi di dati diversi, `int` e `char`.  
  
 Il codice illustra due metodi:  
  
-   Un metodo helper di test, `SizeOfLinkedListTestHelper<T>()`.  Per impostazione predefinita, un metodo helper di test contiene "TestHelper" nel nome.  
  
-   Un metodo di test, `SizeOfLinkedListTest()`.  Ogni metodo di test è contrassegnato con l'attributo TestMethod.  
  
#### Codice di test generato  
 Il codice di test seguente è stato generato dal metodo `SizeOfLinkedList()`.  Poiché si tratta del test generato non modificato, è necessario modificarlo per eseguire correttamente il test del metodo SizeOfLinkedList.  
  
```  
public void SizeOfLinkedListTestHelper<T>()  
{  
    T val = default(T); // TODO: Initialize to an appropriate value  
    MyLinkedList<T> target = new MyLinkedList<T>(val); // TODO: Initialize to an appropriate value  
    int expected = 0; // TODO: Initialize to an appropriate value  
    int actual;  
    actual = target.SizeOfLinkedList();  
    Assert.AreEqual(expected, actual);  
    Assert.Inconclusive("Verify the correctness of this test method.");  
}  
  
[TestMethod()]  
public void SizeOfLinkedListTest()  
{  
   SizeOfLinkedListTestHelper<GenericParameterHelper>();  
}  
```  
  
 Nel codice precedente il parametro di tipo generico è `GenericParameterHelper`.  Sebbene sia possibile modificarlo per fornire tipi di dati specifici, come illustrato nell'esempio seguente, è possibile eseguire il test senza modificare questa istruzione.  
  
#### Codice di test modificato  
 Nel codice seguente, il metodo di test e il metodo helper di test sono stati modificati per consentire la corretta esecuzione del test del metodo di codice sottoposto a test `SizeOfLinkedList()`.  
  
##### Metodo helper di test  
 Il metodo helper di test esegue i passaggi seguenti, che corrispondono alle righe nel codice indicate dal passaggio 1 al passaggio 5.  
  
1.  Creare un elenco collegato generico.  
  
2.  Aggiungere quattro nodi all'elenco collegato.  Il tipo di dati del contenuto di questi nodi è sconosciuto.  
  
3.  Assegnare la dimensione prevista dell'elenco collegato alla variabile `expected`.  
  
4.  Calcolare la dimensione effettiva dell'elenco collegato e assegnarla alla variabile `actual`.  
  
5.  Confrontare `actual` con `expected` in un'istruzione Assert.  Se la dimensione effettiva non è uguale a quella prevista, il test ha esito negativo.  
  
##### Metodo di test  
 Il metodo di test viene compilato nel codice che viene chiamato quando si esegue il test denominato SizeOfLinkedListTest.  Il metodo esegue i passaggi seguenti, che corrispondono alle righe nel codice indicate dai passaggi 6 e 7.  
  
1.  Specificare `<int>` quando si chiama il metodo helper di test per verificare che il test funzioni per le variabili `integer`.  
  
2.  Specificare `<char>` quando si chiama il metodo helper di test per verificare che il test funzioni per le variabili `char`.  
  
```  
  
public void SizeOfLinkedListTestHelper<T>()  
{  
    T val = default(T);   
    MyLinkedList<T> target = new MyLinkedList<T>(val); // step 1  
    for (int i = 0; i < 4; i++) // step 2  
    {  
        MyLinkedList<T> newNode = new MyLinkedList<T>(val);  
        target.Append(newNode);  
    }  
    int expected = 5; // step 3  
    int actual;  
    actual = target.SizeOfLinkedList(); // step 4  
    Assert.AreEqual(expected, actual); // step 5  
}  
  
[TestMethod()]  
public void SizeOfLinkedListTest()   
{  
    SizeOfLinkedListTestHelper<int>();  // step 6  
    SizeOfLinkedListTestHelper<char>(); // step 7  
}  
```  
  
> [!NOTE]
>  Ogni volta che viene eseguito il test SizeOfLinkedListTest, il relativo metodo TestHelper viene chiamato due volte.  L'istruzione Assert deve restituire true ogni volta affinché il test venga superato.  Se il test non viene superato, potrebbe non essere chiaro se l'esito negativo è dovuto alla chiamata che ha specificato `<int>` o alla chiamata che ha specificato `<char>`.  Per trovare la risposta, è possibile esaminare lo stack di chiamate oppure è possibile impostare punti di interruzione nel metodo di test e quindi eseguire il debug durante l'esecuzione del test.  Per altre informazioni, vedere [Procedura: eseguire il debug durante l'esecuzione di un test in una soluzione ASP.NET](../Topic/How%20to:%20Debug%20while%20Running%20a%20Test%20in%20an%20ASP.NET%20Solution.md).  
  
###  <a name="TypeConstraintNotSatisfied"></a> Esempio 2: Uso di un vincolo di tipo  
 Questo esempio mostra uno unit test per un metodo generico che usa un vincolo di tipo che non viene soddisfatto.  La prima sezione mostra il codice del progetto di codice sottoposto a test.  Il vincolo di tipo è evidenziato.  
  
 La seconda sezione mostra il codice del progetto di test.  
  
#### Progetto di codice sottoposto a test  
  
```  
using System;  
using System.Linq;  
using System.Collections.Generic;  
using System.Text;  
  
namespace ClassLibrary2  
{  
    public class Employee  
    {  
        public Employee(string s, int i)  
        {  
        }  
    }  
  
    public class GenericList<T> where T : Employee  
    {  
        private class Node  
        {  
            private T data;  
            public T Data  
            {  
                get { return data; }  
                set { data = value; }  
            }  
        }  
    }  
}  
```  
  
#### Progetto di test  
 Come con tutti gli unit test appena generati, è necessario aggiungere a questo unit test istruzioni Assert non senza risultati affinché vengano restituiti risultati utili.  Le istruzioni non vengono aggiunte al metodo contrassegnato con l'attributo TestMethod, ma al metodo "TestHelper", per il test denominato `DataTestHelper<T>()`.  
  
 In questo esempio il parametro di tipo generico `T`  contiene il vincolo `where T : Employee`.  Il vincolo non viene soddisfatto nel metodo di test.  Pertanto, il metodo `DataTest()` contiene un'istruzione Assert che avvisa della necessità di fornire il vincolo di tipo inserito in `T`.  Il messaggio di questa istruzione Assert è il seguente: `("No appropriate type parameter is found to satisfies the type constraint(s) of T. " + "Please call DataTestHelper<T>() with appropriate type parameters.");`  
  
 In altre parole, quando si chiama il metodo `DataTestHelper<T>()` dal metodo di test,  `DataTest()`, è necessario passare un parametro di tipo `Employee` o una classe derivata da `Employee`.  
  
 `using ClassLibrary2;`  
  
 `using Microsoft.VisualStudio.TestTools.UnitTesting;`  
  
 `namespace TestProject1`  
  
```  
{  
    [TestClass()]  
    public class GenericList_NodeTest  
    {  
  
        public void DataTestHelper<T>()  
            where T : Employee  
        {  
            GenericList_Shadow<T>.Node target = new GenericList_Shadow<T>.Node(); // TODO: Initialize to an appropriate value  
            T expected = default(T); // TODO: Initialize to an appropriate value  
            T actual;  
            target.Data = expected;  
            actual = target.Data;  
            Assert.AreEqual(expected, actual);  
            Assert.Inconclusive("Verify the correctness of this test method.");  
        }  
  
        [TestMethod()]  
        public void DataTest()  
        {  
            Assert.Inconclusive("No appropriate type parameter is found to satisfies the type constraint(s) of T. " +  
            "Please call DataTestHelper<T>() with appropriate type parameters.");  
        }  
    }  
}  
```  
  
## Vedere anche  
 [Anatomy of a Unit Test](http://msdn.microsoft.com/it-it/a03d1ee7-9999-4e7c-85df-7d9073976144)   
 [Eseguire unit test del codice](../test/unit-test-your-code.md)