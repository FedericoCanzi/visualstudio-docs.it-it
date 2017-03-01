---
title: 'Nuova generazione progetto: Dietro le quinte, parte&2; | Documenti di Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 73ce91d8-0ab1-4a1f-bf12-4d3c49c01e13
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: c5f214774a5cf0aeb3896004632f8a2076782b14
ms.lasthandoff: 02/22/2017

---
# <a name="new-project-generation-under-the-hood-part-two"></a>Nuova generazione progetto: Dietro le quinte, parte&2;
In [nuova generazione progetto: dietro le quinte:, parte&1;](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) abbiamo visto come il **nuovo progetto** inserite nella finestra di dialogo. Si supponga di aver selezionato un **applicazione Windows di Visual c#**, compilati il **nome** e **percorso** caselle di testo e fare clic su OK.  
  
## <a name="generating-the-solution-files"></a>Generazione dei file di soluzione  
 Scelta di un modello di applicazione indirizza [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] per decomprimere e aprire il file. vstemplate corrispondente e per avviare un modello per interpretare i comandi XML in questo file. Questi comandi creano progetti ed elementi del progetto nella soluzione nuova o esistente.  
  
 Il modello decomprime il file di origine, denominato modelli di elemento, dalla stessa cartella con estensione zip che contiene il file. vstemplate. Il modello consente di copiare questi file al nuovo progetto, la personalizzazione di conseguenza. Per una panoramica dei modelli di progetto e di elemento, vedere [NIB: modelli di Visual Studio](http://msdn.microsoft.com/en-us/141fccaa-d68f-4155-822b-27f35dd94041).  
  
### <a name="template-parameter-replacement"></a>Sostituzione dei parametri di modello  
 Quando il modello di copia di un modello di elemento a un nuovo progetto, i parametri di modello viene sostituito con le stringhe per personalizzare il file. Un parametro di modello è un token speciale che è preceduto e seguito da un segno di dollaro, ad esempio, $ $date.  
  
 Esaminiamo un modello di elemento di progetto tipico. Estrarre ed esaminare Program.cs nella cartella 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip Program Files\Microsoft Visual Studio.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace $safeprojectname$  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 Se si crea un nuovo progetto applicazione Windows denominato semplice, il modello sostituisce il `$safeprojectname$` parametro con il nome del progetto.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace Simple  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 Per un elenco completo dei parametri di modello, vedere [parametri di modello](../../ide/template-parameters.md).  
  
## <a name="a-look-inside-a-vstemplate-file"></a>Uno sguardo all'interno di una. File VSTemplate  
 Questo formato è un file. vstemplate di base  
  
```  
<VSTemplate Version="2.0.0"     xmlns="http://schemas.microsoft.com/developer/vstemplate/2005"     Type="Project">  
    <TemplateData>  
    </TemplateData>  
    <TemplateContent>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 Abbiamo visto la \<TemplateData > sezione la [nuova generazione progetto: dietro le quinte:, parte&1;](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md). Il tag in questa sezione vengono utilizzati per controllare l'aspetto del **nuovo progetto** la finestra di dialogo.  
  
 I tag di \<TemplateContent > sezione controllo la generazione di nuovi progetti ed elementi del progetto. Ecco il \<TemplateContent > sezione nel file cswindowsapplication.vstemplate nella cartella \Programmi\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip.  
  
```  
<TemplateContent>  
  <Project File="WindowsApplication.csproj" ReplaceParameters="true">  
    <ProjectItem ReplaceParameters="true"  
      TargetFileName="Properties\AssemblyInfo.cs">  
      AssemblyInfo.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Resources.resx">  
      Resources.resx  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Resources.Designer.cs">  
      Resources.Designer.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Settings.settings">  
      Settings.settings  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Settings.Designer.cs">  
      Settings.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true" OpenInEditor="true">  
      Form1.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Form1.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Program.cs  
    </ProjectItem>  
  </Project>  
</TemplateContent>  
```  
  
 Il \<progetto > tag controlla la generazione di un progetto e \<ProjectItem > tag controlla la generazione di un elemento di progetto. Se il parametro ReplaceParameters è true, il modello verrà personalizzare tutti i parametri di modello nel file di progetto o elemento. In questo caso, tutti gli elementi di progetto personalizzati, ad eccezione di Settings. Settings.  
  
 Il parametro TargetFileName specifica il nome e percorso relativo del file di progetto risultante o dell'elemento. Ciò consente di creare una struttura di cartelle per il progetto. Se non si specifica questo argomento, l'elemento di progetto avrà lo stesso nome di modello di elemento di progetto.  
  
 La struttura di cartelle dell'applicazione di Windows risulta è simile al seguente:  
  
 ![SimpleSolution](../../extensibility/internals/media/simplesolution.png "SimpleSolution")  
  
 Il primo e unico \<progetto > tag in legge il modello:  
  
```  
<Project File="WindowsApplication.csproj" ReplaceParameters="true">  
```  
  
 In questo modo il modello nuovo progetto per creare il file di progetto Simple.csproj copiando e personalizzazione di windowsapplication.csproj di elemento di modello.  
  
### <a name="designers-and-references"></a>Finestre di progettazione e riferimenti  
 È possibile vedere in Esplora soluzioni che la cartella di proprietà è presente e contiene i file previsti. Ma cosa succede progetto fa riferimento e dipendenze di file della finestra di progettazione, ad esempio Resources.Designer.cs in Resources. resx e Form1. Designer.cs per Form1. cs?  Questi vengono impostati nel file Simple.csproj quando viene generato.  
  
 Ecco il \<ItemGroup > da Simple.csproj che crea i riferimenti al progetto:  
  
```  
<ItemGroup>  
    <Reference Include="System" />  
    <Reference Include="System.Data" />  
    <Reference Include="System.Deployment" />  
    <Reference Include="System.Drawing" />  
    <Reference Include="System.Windows.Forms" />  
    <Reference Include="System.Xml" />  
</ItemGroup>  
```  
  
 È possibile vedere che questi sono i riferimenti al sei progetto visualizzati in Esplora soluzioni. Ecco una sezione da un altro \<ItemGroup >. Numero di righe di codice è stati eliminati per maggiore chiarezza. In questa sezione viene Settings.Designer.cs dipende Settings:  
  
```  
<ItemGroup>  
    <Compile Include="Properties\Settings.Designer.cs">  
        <DependentUpon>Settings.settings</DependentUpon>  
    </Compile>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Nuova generazione progetto: Dietro le quinte, parte&1;](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)  
 [MSBuild](../../msbuild/msbuild1.md)
