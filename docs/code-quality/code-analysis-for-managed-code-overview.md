---
title: Codice di analisi del codice gestito in Visual Studio | Documenti Microsoft
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 8209e17985ef7f9924fc677b91b5cfe539977cb9
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2018
---
# <a name="overview-of-code-analysis-for-managed-code"></a>Panoramica di analisi del codice per il codice gestito

Visual Studio 2017 analizza il codice gestito in due modi: con legacy *FxCop* analisi statica di assembly gestiti e con .NET Compiler Platform *analizzatori*. Questo argomento vengono illustrate l'analisi statica del codice FxCop. Per ulteriori informazioni sull'analisi del codice usando gli analizzatori di .NET Compiler Platform, vedere [Panoramica di Roslyn analizzatori](../code-quality/roslyn-analyzers-overview.md).

L'analisi del codice gestito analizza gli assembly gestiti e fornisce informazioni sugli assembly, ad esempio le violazioni delle regole di programmazione e progettazione definite nelle linee guida di progettazione di Microsoft .NET Framework.

Lo strumento di analisi rappresenta i controlli eseguiti durante un'analisi come messaggi di avviso. I messaggi di avviso identificano eventuali problemi di programmazione e progettazione e, se possibile, forniscono informazioni su come risolverli.

## <a name="ide-integrated-development-environment-integration"></a>Integrazione nell'IDE (integrated development environment)

È possibile eseguire l'analisi del codice del progetto manualmente o automaticamente.

Per eseguire l'analisi codice ogni volta che si compila un progetto, selezionare **Attiva analisi codice in fase di compilazione** nella pagina delle proprietà del progetto. Per ulteriori informazioni, vedere [procedura: abilitare e disabilitare analisi del codice automatica](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

Per eseguire manualmente l'analisi del codice in un progetto, dalla barra dei menu scegliere **Analizza** > **Esegui analisi del codice** > **Esegui analisi del codice su <project>** . Per ulteriori informazioni, vedere [procedura: abilitare e disabilitare analisi del codice automatica](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md).

## <a name="rule-sets"></a>Set di regole

Regole di analisi del codice per il codice gestito raggruppate in *set di regole*. È possibile utilizzare uno dei set di regole standard Microsoft oppure creare un set di regole personalizzato per soddisfare una specifica esigenza. Per ulteriori informazioni, vedere [utilizzando il set di regole per raggruppare regole di analisi codice](../code-quality/using-rule-sets-to-group-code-analysis-rules.md).

## <a name="suppress-warnings"></a>Esclusione di avvisi

È in genere utile indicare se un avviso non è applicabile. In questo modo lo sviluppatore e altri individui che potrebbero esaminare il codice in un secondo momento verranno informati del fatto che un avviso è stato sottoposto ad analisi, quindi è stato eliminato o ignorato.

L'eliminazione nell'origine degli avvisi viene implementata attraverso attributi personalizzati. Per non visualizzare un avviso, aggiungere l'attributo `SuppressMessage` al codice sorgente, come illustrato nell'esempio seguente:

```csharp
[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

Per ulteriori informazioni, vedere [esclusione di avvisi](../code-quality/in-source-suppression-overview.md).

> [!NOTE]
> Se si esegue la migrazione di un progetto di Visual Studio 2017, possono incontrare improvvisamente con un numero eccessivo di avvisi di analisi codice. Se non si è pronti per risolvere gli avvisi e disattivare temporaneamente l'analisi del codice, aprire pagine delle proprietà del progetto (**progetto** > ***progetto* Properties...** ) e passare al **analisi del codice** scheda. Deselezionare **Attiva analisi codice in fase di compilazione**e quindi ricompilare il progetto. In alternativa, è possibile selezionare un diversa, più piccolo set di regole per eseguire il codice. È necessario attivare l'analisi del codice in quando si è pronti per risolvere gli avvisi.

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>Eseguire l'analisi del codice come parte dei criteri di archiviazione

Le organizzazioni richiedono talvolta che tutte le archiviazioni soddisfino determinati criteri, tra cui, in particolare:

- Nel codice da archiviare non siano presenti errori di compilazione.

- Analisi del codice viene eseguito come parte della compilazione più recente.

A tale scopo, è utile quindi definire dei criteri specifici per l'archiviazione. Per ulteriori informazioni, vedere [miglioramento della qualità del codice con i criteri di archiviazione del progetto Team](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md).

## <a name="team-build-integration"></a>Integrazione di team build

È possibile utilizzare le funzionalità integrate del sistema di compilazione per eseguire lo strumento di analisi come parte del processo di compilazione. Per ulteriori informazioni, vedere [di compilazione e versione (VSTS)](/vsts/build-release/index).

## <a name="see-also"></a>Vedere anche

- [Panoramica di Roslyn analizzatori](../code-quality/roslyn-analyzers-overview.md)
- [Uso di set di regole per raggruppare regole di analisi del codice](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [Procedura: abilitare e disabilitare l'analisi automatica del codice](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
