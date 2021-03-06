---
title: 'CA1063: Implementare IDisposable correttamente | Documenti Microsoft'
ms.custom: 
ms.date: 02/12/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.topic: article
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 29a2fbb82fd2795c675bfa249e213488913745a9
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2018
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: Implementare IDisposable correttamente

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|Category|Microsoft.Design|
|Modifica importante|Non sostanziale|

## <a name="cause"></a>Causa

`IDisposable` non è implementato correttamente. Tra le cause di questo problema sono elencate di seguito:

- IDisposable è nuovamente implementato nella classe.

- Finalizzare viene nuovamente eseguito l'override.

- Viene eseguito l'override di Dispose.

- Dispose () non è pubblico, sealed o denominato Dispose.

- Dispose (bool) non protetti, virtuali o non sealed.

- In tipi non sealed, Dispose devono chiamare Dispose (true).

- Per i tipi non sealed, l'implementazione di Finalize non chiama Dispose (bool) o il finalizzatore della classe base.

Violazione di uno di questi modelli genererà l'avviso.

Ogni tipo non sealed che dichiara e implementa l'interfaccia IDisposable è necessario fornire il relativo metodo Dispose (bool) void virtuale protetto. Dispose devono chiamare Dispose (true) e Finalize deve chiamare Dispose (false). Se si sta creando un tipo non sealed che dichiara e implementa l'interfaccia IDisposable, è necessario definire Dispose (bool) e chiamarlo. Per ulteriori informazioni, vedere [pulizia delle risorse non gestite](/dotnet/standard/garbage-collection/unmanaged) nel [indicazioni per la progettazione di .NET Framework](/dotnet/standard/design-guidelines/index).

## <a name="rule-description"></a>Descrizione della regola

È necessario che tutti i tipi IDisposable implementino correttamente il modello Dispose.

## <a name="how-to-fix-violations"></a>Come correggere le violazioni

Esaminare il codice e determinare quale delle soluzioni seguenti per correggere questa violazione.

- Rimuovere IDisposable dall'elenco di interfacce implementate da {0} ed eseguire l'override dell'implementazione di Dispose della classe di base.

- Rimuovere il finalizzatore dal tipo di {0}, eseguire l'override di Dispose (bool disposing) e inserire la logica di finalizzazione nel percorso di codice dove 'disposing' è false.

- Rimuovere {0}, eseguire l'override di Dispose (bool disposing) e inserire la logica di dispose nel percorso di codice dove 'disposing' è true.

- Verificare che {0} sia dichiarato public e sealed.

- Rinominare {0} in 'Dispose' e assicurarsi che sia dichiarato public e sealed.

- Verificare che tale {0} sia dichiarato come protected, virtual e non sealed.

- Modificare {0} in modo che chiama Dispose (true), quindi chiama GC. SuppressFinalize nell'istanza dell'oggetto corrente ('this' o 'Me' in [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]), quindi restituisce.

- Modificare {0} in modo che chiami Dispose (false) e quindi restituisce.

- Se si sta creando un tipo non sealed che dichiara e implementa l'interfaccia IDisposable, assicurarsi che l'implementazione di IDisposable segua il modello descritto in precedenza in questa sezione.

## <a name="when-to-suppress-warnings"></a>Esclusione di avvisi

Non escludere un avviso da questa regola.

## <a name="pseudo-code-example"></a>Esempio di pseudocodice

Lo pseudocodice seguente fornisce un esempio generale delle modalità di implementazione Dispose (bool) in una classe che utilizza gestita e le risorse native.

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources itself, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```