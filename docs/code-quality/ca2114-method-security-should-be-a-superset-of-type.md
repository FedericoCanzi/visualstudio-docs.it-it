---
title: 'CA2114: Sicurezza del metodo deve essere un superset del tipo | Documenti Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9784ae650a411ef4fe5086ae8bf756147fd2365
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2017
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: La sicurezza del metodo deve essere un superset del tipo
|||  
|-|-|  
|TypeName|MethodSecurityShouldBeASupersetOfType|  
|CheckId|CA2114|  
|Categoria|Microsoft.Security|  
|Breaking Change|Interruzione|  
  
## <a name="cause"></a>Causa  
 Un tipo ha la sicurezza dichiarativa e uno dei relativi metodi ha la sicurezza dichiarativa per la stessa azione di sicurezza e l'azione di sicurezza non è [le richieste di collegamento](/dotnet/framework/misc/link-demands) o [richieste di ereditarietà](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)e le autorizzazioni selezionata per il tipo non sono un sottoinsieme delle autorizzazioni controllato dal metodo.  
  
## <a name="rule-description"></a>Descrizione della regola  
 Un metodo non può presentare sia una sicurezza dichiarativa a livello di metodo e a livello di tipo per la stessa azione. I due controlli non sono stati combinati; viene applicata solo la richiesta a livello di metodo. Ad esempio, se un tipo richiede l'autorizzazione `X`, e uno dei relativi metodi richiede l'autorizzazione `Y`, codice non è necessario disporre dell'autorizzazione `X` per eseguire il metodo.  
  
## <a name="how-to-fix-violations"></a>Come correggere le violazioni  
 Esaminare il codice per assicurarsi che entrambe le azioni sono obbligatori. Se sono necessarie entrambe le azioni, assicurarsi che l'azione a livello di metodo include la sicurezza specificata a livello di tipo. Ad esempio, se il tipo richiede l'autorizzazione `X`, e il relativo metodo deve anche richiedere l'autorizzazione `Y`, il metodo deve richiedere in modo esplicito `X` e `Y`.  
  
## <a name="when-to-suppress-warnings"></a>Esclusione di avvisi  
 È possibile eliminare un avviso da questa regola se il metodo non richiede la sicurezza specificata dal tipo. Tuttavia, questo non è uno scenario comune e potrebbe indicare la necessità di una revisione della progettazione di attenzione.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa le autorizzazioni di ambiente per illustrare i rischi di violazione di questa regola. In questo esempio, il codice dell'applicazione crea un'istanza del tipo protetto prima di negare l'autorizzazione necessaria per il tipo. In uno scenario reale di rischio, l'applicazione potrebbe richiedere un altro modo per ottenere un'istanza dell'oggetto.  
  
 Nell'esempio seguente, la libreria richiede l'autorizzazione per un tipo di scrittura e autorizzazioni di lettura per un metodo.  
  
 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]  
  
## <a name="example"></a>Esempio  
 Il codice di applicazione seguente illustra la vulnerabilità della libreria chiamando il metodo, anche se non soddisfa il requisito di sicurezza a livello di tipo.  
  
 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]  
  
 Questo esempio produce il seguente output:  
  
 **[Tutte le autorizzazioni] Le informazioni personali: 16/6/1964 12:00:00 AM**  
**[Nessuna autorizzazione di scrittura (obbligatorie per tipo)] Le informazioni personali: 16/6/1964 12:00:00 AM**  
**[Nessuna autorizzazione di lettura (richiesta dal metodo)] Impossibile accedere alle informazioni personali: richiesta non riuscita.**   
## <a name="see-also"></a>Vedere anche  
 [Linee guida di codice sicuro](/dotnet/standard/security/secure-coding-guidelines)   
 [Richieste di ereditarietà](http://msdn.microsoft.com/en-us/28b9adbb-8f08-4f10-b856-dbf59eb932d9)   
 [Richieste di collegamento](/dotnet/framework/misc/link-demands)   
 [Dati e modellazione](/dotnet/framework/data/index)