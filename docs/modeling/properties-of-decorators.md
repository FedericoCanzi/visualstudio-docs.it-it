---
title: "Proprietà degli elementi Decorator | Documenti Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, decorators
ms.assetid: f6322fe5-dc08-4d32-a6b3-0bd18879136d
caps.latest.revision: "23"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 23288d1afe9b9c0a181a5d978b1956071b683218
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2017
---
# <a name="properties-of-decorators"></a>Proprietà degli elementi Decorator
Gli elementi Decorator sono virgolette acute di espansione/compressione che è possono visualizzare le forme o connettori nel diagramma, testo o icone. Le tabelle seguenti illustrano le proprietà per i tre tipi di elemento decorator. Alcune delle proprietà vengono visualizzati solo gli elementi Decorator forma o solo per gli elementi Decorator connettore.  
  
 Per ulteriori informazioni, vedere [come definire un linguaggio specifico di dominio](../modeling/how-to-define-a-domain-specific-language.md). Per ulteriori informazioni sull'utilizzo di queste proprietà, vedere [personalizzare ed estendere un linguaggio specifico di dominio](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
## <a name="expandcollapse-decorator"></a>Espandi/Comprimi elemento Decorator  
  
|Proprietà|Descrizione|Impostazione predefinita|  
|--------------|-----------------|-------------|  
|DisplayName|Il nome di decoratore che verrà visualizzato nella finestra di progettazione generato.|Espandere l'elemento Decorator Comprimi|  
|Nome|Il nome dell'elemento decorator.|ExpandCollapseDecorator|  
|Note|Note informale che sono associate a questo elemento decorator.|\<Nessuno >|  
|HorizontalOffset|L'offset orizzontale rispetto alla posizione predefinita di decorator, espressa in pollici. (In forme solo.)|0|  
|VerticalOffset|L'offset verticale, relativo alla posizione predefinita di decorator, espressa in pollici. (In forme solo.)|0|  
|OffsetFromLine|L'offset dell'elemento decorator dalla riga di relativo alla posizione predefinita, in pollici. (Sui connettori solo.)|0|  
|OffsetFromShape|L'offset dell'elemento decorator dalla forma, relativo alla posizione predefinita, in pollici. (Sui connettori solo.)|0|  
|Posizione|La posizione predefinita dell'elemento decorator.|SourceTop|  
  
## <a name="icon-decorator"></a>Icona Decorator  
  
|Proprietà|Descrizione|Impostazione predefinita|  
|--------------|-----------------|-------------|  
|DefaultIcon|Il percorso del file icona o di immagine da visualizzare.|\<Nessuno >|  
|DisplayName|Il nome di decorator da visualizzare nella finestra di progettazione generato.|Icona Decorator|  
|Nome|Il nome dell'elemento decorator.|IconDecorator|  
|Note|Note informale associati con l'elemento decorator.|\<Nessuno >|  
|HorizontalOffset|L'offset orizzontale rispetto alla posizione predefinita di decorator, espressa in pollici. (In forme solo.)|0|  
|VerticalOffset|L'offset verticale, relativo alla posizione predefinita di decorator, espressa in pollici. (In forme solo.)|0|  
|OffsetFromLine|L'offset dell'elemento decorator dalla riga di relativo alla posizione predefinita, in pollici. (Sui connettori solo.)|0|  
|OffsetFromShape|L'offset dell'elemento decorator dalla forma, relativo alla posizione predefinita, in pollici. (Sui connettori solo.)|0|  
|Posizione|La posizione predefinita dell'elemento decorator.|SourceTop|  
  
## <a name="textdecorator"></a>TextDecorator  
  
|Proprietà|Descrizione|Impostazione predefinita|  
|--------------|-----------------|-------------|  
|DefaultText|Il testo predefinito da visualizzare.|Label|  
|DisplayName|Il nome di decorator da visualizzare nella finestra di progettazione generato.|Label|  
|FontSize|Le dimensioni del carattere per il testo visualizzato nell'elemento decorator.|8|  
|FontStyle|Lo stile del carattere per il testo visualizzato nell'elemento decorator.|Regular|  
|Nome|Il nome dell'elemento decorator.|Label|  
|Note|Note informale associati con l'elemento decorator.|\<Nessuno >|  
|HorizontalOffset|L'offset orizzontale rispetto alla posizione predefinita di decorator, espressa in pollici. (In forme solo.)|0|  
|VerticalOffset|L'offset verticale, relativo alla posizione predefinita di decorator, espressa in pollici. (In forme solo.)|0|  
|OffsetFromLine|L'offset dell'elemento decorator dalla riga di relativo alla posizione predefinita, in pollici. (Sui connettori solo.)|0|  
|OffsetFromShape|L'offset dell'elemento decorator dalla forma, relativo alla posizione predefinita, in pollici. (Sui connettori solo.)|0|  
|Posizione|La posizione predefinita dell'elemento decorator.|TargetBottom|  
  
## <a name="see-also"></a>Vedere anche  
 [Glossario di strumenti di linguaggio specifico di dominio](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)