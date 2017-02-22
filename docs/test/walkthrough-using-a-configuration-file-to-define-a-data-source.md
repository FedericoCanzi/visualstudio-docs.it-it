---
title: "Procedura dettagliata: utilizzo di un file di configurazione per definire un&#39;origine dati | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "file di configurazione [Visual Studio ALM], definizione di origini dati"
  - "origini dati, definizione con file di configurazione"
  - "unit test, procedura dettagliata"
ms.assetid: 95fa5214-b12e-4e1f-84e5-cc4c2d86b0d7
caps.latest.revision: 32
caps.handback.revision: 32
ms.author: "mlearned"
manager: "douge"
---
# Procedura dettagliata: utilizzo di un file di configurazione per definire un&#39;origine dati
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Questa procedura dettagliata illustra come usare un'origine dati definita in un file app.config per gli unit test.  Viene mostrato come creare un file app.config che definisce un'origine dati che può essere usata dalla classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute>.  Le attività incluse nella procedura dettagliata sono le seguenti:  
  
-   Creazione di un file app.config.  
  
-   Definizione di una sezione di configurazione personalizzata.  
  
-   Definizione di stringhe di connessione.  
  
-   Definizione di origini dati.  
  
-   Accesso alle origini dati tramite la classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute>.  
  
## Prerequisiti  
 Per completare questa procedura dettagliata, è necessario disporre di:  
  
-   Visual Studio Enterprise  
  
-   Microsoft Access o Microsoft Excel per fornire dati per almeno uno dei metodi di test.  
  
-   Soluzione Visual Studio contenente un progetto di test.  
  
## Creare il file app.config  
  
#### Per aggiungere un file app.config al progetto  
  
1.  Se il progetto di test dispone già di un file app.config, passare a [Definire una sezione di configurazione personalizzata](#DefineCustomConfigurationSection).  
  
2.  Fare clic con il pulsante destro del mouse sul progetto di test in **Esplora soluzioni**, scegliere **Aggiungi** e quindi fare clic su **Nuovo elemento**.  
  
     Verrà visualizzata la finestra **Aggiungi nuovo elemento**.  
  
3.  Selezionare il modello **File di configurazione dell'applicazione** e fare clic su **Aggiungi**.  
  
##  <a name="DefineCustomConfigurationSection"></a> Definire una sezione di configurazione personalizzata  
 Esaminare il file app.config.  Il file contiene almeno la dichiarazione XML e un elemento radice.  
  
#### Per aggiungere la sezione di configurazione personalizzata nel file app. config  
  
1.  L'elemento radice di app.config deve essere l'elemento `configuration`.  Creare un elemento `configSections` all'interno dell'elemento `configuration`.  `configSections` deve essere il primo elemento nel file app.config.  
  
2.  Nell'elemento `configSections` creare un elemento `section`.  
  
3.  Nell'elemento `section`, aggiungere un attributo denominato `name` e assegnarli il valore `microsoft.visualstudio.testtools`.  Aggiungere un altro attributo denominato `type` e assegnargli il valore `Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a`  
  
 L'elemento `section` dovrebbe essere simile al seguente:  
  
```  
<section name="microsoft.visualstudio.testtools" type="Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>  
```  
  
> [!NOTE]
>  Il nome dell'assembly deve corrispondere alla build di Microsoft Visual Studio .NET Framework in uso.  Impostare la versione su 9.0.0.0 se si usa Visual Studio .NET Framework 3.5.  Se si usa Visual Studio .NET Framework 2.0, impostare la versione su 8.0.0.0.  
  
## Definire le stringhe di connessione  
 Le stringhe di connessione definiscono informazioni specifiche del provider per l'accesso alle origini dati.  Le stringhe di connessione definite nei file di configurazione forniscono informazioni sui provider di dati riutilizzabili nell'ambito di un'applicazione.  In questa sezione vengono create due stringhe di connessione che verranno usate dalle origini dati definite nella sezione di configurazione personalizzata.  
  
#### Per definire le stringhe di connessione  
  
1.  Dopo l'elemento `configSections`, creare un elemento `connectionStrings`.  
  
2.  Nell'elemento `connectionStrings`, creare due elementi `add`.  
  
3.  Nel primo elemento `add`, creare i seguenti attributi e valori per una connessione a un database di Microsoft Access:  
  
|Attributo|Valori|  
|---------------|------------|  
|`name`|`"MyJetConn"`|  
|`connectionString`|`"Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;"`|  
|`providerName`|`"System.Data.OleDb"`|  
  
 Nel secondo elemento `add`, creare i seguenti attributi e valori per una connessione a un foglio di calcolo di Microsoft Excel:  
  
|||  
|-|-|  
|`name`|`"MyExcelConn"`|  
|`connectionString`|`"Dsn=Excel Files;dbq=data.xlsx;defaultdir=.; driverid=790;maxbuffersize=2048;pagetimeout=5"`|  
|`providerName`|`"System.Data.Odbc"`|  
  
 L'elemento `connectionStrings` dovrebbe essere simile al seguente:  
  
```  
<connectionStrings>  
    <add name="MyJetConn" connectionString="Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;" providerName="System.Data.OleDb" />  
    <add name="MyExcelConn" connectionString="Dsn=Excel Files;dbq=data.xlsx;defaultdir=.; driverid=790;maxbuffersize=2048;pagetimeout=5" providerName="System.Data.Odbc" />  
</connectionStrings>  
```  
  
## Definire le origini dati  
 La sezione relativa alle origini dati contiene quattro attributi usati dal motore di test per recuperare i dati da un'origine dati.  
  
-   `name` definisce l'identità usata da <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> per specificare l'origine dati da usare.  
  
-   `connectionString` identifica la stringa di connessione creata nella sezione Definire le stringhe di connessione precedente.  
  
-   `dataTableName` definisce la tabella o il foglio contenente i dati da usare nel test.  
  
-   `dataAccessMethod` definisce la tecnica per l'accesso ai valori dei dati nell'origine dati.  
  
 In questa sezione vengono definite due origini dati da usare in uno unit test.  
  
#### Per definire le origini dati  
  
1.  Dopo l'elemento `connectionStrings`, creare un elemento `microsoft.visualstudio.testtools`.  Questa sezione è stata creata in Definire una sezione di configurazione personalizzata.  
  
2.  Nell'elemento `microsoft.visualstudio.testtools` creare un elemento `dataSources`.  
  
3.  Nell'elemento `dataSources`, creare due elementi `add`.  
  
4.  Nel primo elemento `add`, creare i seguenti attributi e valori per un'origine dati di Microsoft Access:  
  
|Attributo|Valori|  
|---------------|------------|  
|`name`|`"MyJetDataSource"`|  
|`connectionString`|`"MyJetConn"`|  
|`dataTableName`|`"MyDataTable"`|  
|`dataAccessMethod`|`"Sequential"`|  
  
 Nel secondo elemento `add`, creare i seguenti attributi e valori per un'origine dati di Microsoft Excel:  
  
|||  
|-|-|  
|`Name`|`"MyExcelDataSource"`|  
|`connectionString`|`"MyExcelConn"`|  
|`dataTableName`|`"Sheet1$"`|  
|`dataAccessMethod`|`"Sequential"`|  
  
 L'elemento `microsoft.visualstudio.testtools` dovrebbe essere simile al seguente:  
  
```  
<microsoft.visualstudio.testtools>  
    <dataSources>  
        <add name="MyJetDataSource" connectionString="MyJetConn" dataTableName="MyDataTable" dataAccessMethod="Sequential"/>  
        <add name="MyExcelDataSource" connectionString="MyExcelConn" dataTableName="Sheet1$" dataAccessMethod="Sequential"/>  
    </dataSources>  
</microsoft.visualstudio.testtools>  
```  
  
 Il file app.config finale dovrebbe essere simile al seguente:  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <configSections>  
        <section name="microsoft.visualstudio.testtools" type="Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection, Microsoft.VisualStudio.QualityTools.UnitTestFramework, Version=8.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"/>   
    </configSections>  
    <connectionStrings>  
        <add name="MyJetConn" connectionString="Provider=Microsoft.Jet.OLEDB.4.0; Data Source=C:\testdatasource.accdb; Persist Security Info=False;" providerName="System.Data.OleDb" />  
        <add name="MyExcelConn" connectionString="Dsn=Excel Files;dbq=data.xlsx;defaultdir=.; driverid=790;maxbuffersize=2048;pagetimeout=5" providerName="System.Data.Odbc" />  
    </connectionStrings>  
    <microsoft.visualstudio.testtools>  
        <dataSources>  
            <add name="MyJetDataSource" connectionString="MyJetConn" dataTableName="MyDataTable" dataAccessMethod="Sequential"/>  
            <add name="MyExcelDataSource" connectionString="MyExcelConn" dataTableName="Sheet1$" dataAccessMethod="Sequential"/>  
        </dataSources>  
    </microsoft.visualstudio.testtools>  
</configuration>  
```  
  
## Creare uno unit test usando le origini dati definite in app.config  
 Ora che è stato definito un file app.config, si creerà uno unit test che usa i dati che si trovano nelle origini dati definite nel file app. config.  In questa sezione verranno eseguite le operazioni seguenti:  
  
-   Creare le origini dati presenti nel file app.config.  
  
-   Usare le origini dati in due metodi di test che confrontano i valori in ciascuna origine dati.  
  
#### Per creare un'origine dati di Microsoft Access  
  
1.  Creare un database di Microsoft Access denominato `testdatasource.accdb`.  
  
2.  Creare una tabella e denominarla `MyDataTable` in `testdatasource.accdb`.  
  
3.  Creare due campi in `MyDataTable` denominati `Arg1` e `Arg2` usando il tipo di dati `Number`.  
  
4.  Aggiungere cinque entità a `MyDataTable` con i valori seguenti per `Arg1` e `Arg2`, rispettivamente: \(10,50\), \(3,2\), \(6,0\), \(0,8\) e \(12312,1000\).  
  
5.  Salvare e chiudere il database.  
  
6.  Cambiare la stringa di connessione in modo che punti al percorso del database.  Cambiare il valore di `Data Source` in modo da riflettere il percorso del database.  
  
#### Per creare un'origine dati di Microsoft Excel  
  
1.  Creare un foglio di calcolo di Microsoft Excel denominato `data.xlsx`.  
  
2.  Creare un foglio denominato `Sheet1` se non è già presente in `data.xlsx`.  
  
3.  Creare due intestazioni di colonna e assegnare loro i nomi `Val1` e `Val2` in `Sheet1`.  
  
4.  Aggiungere cinque entità a `Sheet1` con i valori seguenti per `Val1` e `Val2`, rispettivamente: \(1,1\), \(2,2\), \(3,3\), \(4,4\) e \(5,0\).  
  
5.  Salvare e chiudere il foglio di calcolo.  
  
6.  Cambiare la stringa di connessione in modo che punti al percorso del foglio di calcolo.  Cambiare il valore di `dbq` in modo da riflettere il percorso del foglio di calcolo.  
  
#### Per creare uno unit test usando le origini dati in app.config  
  
1.  Aggiungere uno unit test al progetto di test.  
  
     Per altre informazioni, vedere [Creating and Running Unit Tests for Existing Code](http://msdn.microsoft.com/it-it/e8370b93-085b-41c9-8dec-655bd886f173).  
  
2.  Sostituire il contenuto generato automaticamente dello unit test con il codice seguente:  
  
    ```  
    using System;  
    using Microsoft.VisualStudio.TestTools.UnitTesting;  
  
    namespace TestProject1  
    {  
         [TestClass]  
        public class UnitTest1  
        {  
            private TestContext context;  
  
            public TestContext TestContext  
            {  
                get { return context; }  
                set { context = value; }  
            }  
  
            [TestMethod()]  
            [DeploymentItem("MyTestProject\\testdatasource.accdb")]  
            [DataSource("MyJetDataSource")]  
            public void MyTestMethod()  
            {  
                int a = Int32.Parse(context.DataRow["Arg1"].ToString());  
                int b = Int32.Parse(context.DataRow["Arg2"].ToString());  
                Assert.AreNotEqual(a, b, "A value was equal.");  
            }  
  
            [TestMethod()]  
            [DeploymentItem("MyTestProject\\data.xlsx")]  
            [DataSource("MyExcelDataSource")]  
            public void MyTestMethod2()  
            {  
                Assert.AreEqual(context.DataRow["Val1"], context.DataRow["Val2"]);  
            }  
        }  
    }  
    ```  
  
3.  Esaminare gli attributi DataSource.  Notare i nomi delle impostazioni nel file app.config.  
  
4.  Compilare la soluzione ed eseguire i test MyTestMethod e MyTestMethod2.  
  
> [!IMPORTANT]
>  Distribuire gli elementi come origini dati in modo che siano accessibili al test nella directory di distribuzione.  
  
## Vedere anche  
 [Eseguire unit test del codice](../test/unit-test-your-code.md)   
 [Creating and Running Unit Tests for Existing Code](http://msdn.microsoft.com/it-it/e8370b93-085b-41c9-8dec-655bd886f173)   
 [Test dell'applicazione](/devops-test-docs/test/test-apps-early-and-often)   
 [Procedura: Creare uno unit test basato sui dati](../test/how-to-create-a-data-driven-unit-test.md)