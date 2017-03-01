---
title: "Generazione di file con l&quot;utilità TextTransform | Documenti di Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
ms.assetid: 06a48235-fe02-403e-a1cf-2ae70b4db62f
caps.latest.revision: 41
author: alancameronwills
ms.author: awills
manager: douge
translation.priority.ht:
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
ms.openlocfilehash: 7d54fba9b16b87122b78ec6157abdbf2a8aface1
ms.lasthandoff: 02/22/2017

---
# <a name="generating-files-with-the-texttransform-utility"></a>Generazione di file con l'utilità TextTransform
TextTransform.exe è uno strumento da riga di comando che è possibile utilizzare per trasformare un modello di testo. Quando si chiama TextTransform.exe, specificare il nome di un file di modello di testo come argomento. TextTransform.exe chiama il motore di trasformazione di testo ed elabora il modello di testo. TextTransform.exe viene in genere chiamato dagli script. Tuttavia, non è in genere necessaria, poiché è possibile eseguire trasformazione del testo in Visual Studio o nel processo di compilazione.  
  
> [!NOTE]
>  Se si desidera eseguire la trasformazione di testo come parte di un processo di compilazione, è consigliabile utilizzare l'attività di trasformazione testo MSBuild. Per ulteriori informazioni, vedere [generazione di codice in un processo di compilazione](../modeling/code-generation-in-a-build-process.md). In un computer nel quale [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] è installato, è anche possibile scrivere un'applicazione o [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] estensione in grado di trasformare i modelli di testo. Per ulteriori informazioni, vedere [l'elaborazione di modelli di testo tramite un Host personalizzato](../modeling/processing-text-templates-by-using-a-custom-host.md).  
  
 TextTransform.exe si trova nella directory seguente:  
  
 **\Programmi\File comuni\Microsoft Shared\TextTemplating\11.0**  
  
## <a name="syntax"></a>Sintassi  
  
```  
TextTransform [<options>] <templateName>  
```  
  
#### <a name="parameters"></a>Parametri  
  
|**Argomento**|**Descrizione**|  
|------------------|---------------------|  
|`templateName`|Identifica il nome del file di modello che si desidera trasformare.|  
  
|**Opzione**|**Descrizione**|  
|----------------|---------------------|  
|**-out** \<filename >|Il file in cui viene scritto l'output della trasformazione.|  
|**-r** \<assembly >|Un assembly utilizzato per compilare ed eseguire il modello di testo.|  
|**-u** \<dello spazio dei nomi >|Uno spazio dei nomi utilizzato per la compilazione del modello.|  
|**-I** \<includedirectory >|Una directory che contiene i modelli di testo inclusi nel modello di testo specificato.|  
|**-P** \<referencepath >|Una directory per cercare gli assembly specificati all'interno del modello di testo o per l'utilizzo di **- r** (opzione).<br /><br /> Ad esempio, per includere gli assembly utilizzati per l'API di Visual Studio, usare<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|  
|**-punto di distribuzione** \<processorName >!\< className >! \<assemblyName | codeBase >|Il nome, nome completo del tipo e assembly di un processore di direttiva che può essere utilizzato per elaborare direttive personalizzate all'interno del modello di testo.|  
|**-** [processorName]. [ directiveName]! \<parameterName >! \<parameterValue >|Specificare un valore di parametro per un processore di direttiva. Se si specifica solo il nome del parametro e il valore, il parametro sarà disponibile a tutti i processori di direttiva. Se si specifica un processore di direttiva, il parametro è disponibile solo per il processore specificato. Se si specifica un nome di una direttiva, il parametro è disponibile solo quando viene elaborata la direttiva specificata.<br /><br /> Per accedere ai valori di parametro da un processore di direttiva o di un modello di testo, utilizzare <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost.ResolveParameterValue%2A>.</xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost.ResolveParameterValue%2A> In un modello di testo, includere `hostspecific` nella direttiva del modello e richiamare il messaggio su `this.Host`. Ad esempio:<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`.<br /><br /> Digitare sempre il '!' contrassegnato, anche se si omette il processore facoltativo e nomi di direttiva. Ad esempio:<br /><br /> `-a !!param!value`|  
|**-h**|Fornisce la Guida.|  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Attività|Argomento|  
|----------|-----------|  
|Generare file in una soluzione di [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|[Generazione di codice in fase di progettazione tramite modelli di testo T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|  
|Scrivere processori di direttive per trasformare le origini dati.|[Personalizzazione della trasformazione del testo T4](../modeling/customizing-t4-text-transformation.md)|  
|Scrivere un host del modello di testo che consente di richiamare i modelli di testo dalla propria applicazione.|[Elaborazione di modelli di testo tramite un host personalizzato](../modeling/processing-text-templates-by-using-a-custom-host.md)|
