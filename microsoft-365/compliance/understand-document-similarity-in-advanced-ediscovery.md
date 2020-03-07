---
title: Comprendere la somiglianza del documento in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Esaminare in che modo il valore di somiglianza del documento, il livello minimo di somiglianza per due file da considerare quasi duplicati, è compatibile con Office 365 Advanced eDiscovery. '
ms.openlocfilehash: e15eb119a569c7cd296f9d3546969848808652da
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557666"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a>Comprendere la somiglianza del documento in Advanced eDiscovery (Classic)

> [!NOTE]
> Per usare Advanced eDiscovery è necessario avere Office 365 E3 con il componente aggiuntivo Advanced Compliance o un abbonamento E5 dell'organizzazione. Se non si ha questo piano e si desidera provare Advanced eDiscovery, è possibile [richiedere una valutazione di Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
In Advanced eDiscovery, la somiglianza dei documenti è il livello minimo di somiglianza necessario per due documenti che devono essere considerati quasi duplicati.
  
> [!TIP]
> Per la maggior parte delle applicazioni aziendali, è consigliabile utilizzare un valore di somiglianza pari a 60%-75%. Per il materiale OCR (Optical Character Recognition) di qualità molto scadente, è possibile applicare valori di similitudine inferiori. 
  
> [!NOTE]
> Dopo che è stato impostato ed eseguito per un determinato caso, il valore di somiglianza non può essere modificato. 
  
All'interno di un insieme quasi duplicato, possono essere presenti documenti con un livello di somiglianza inferiore alla soglia di somiglianza. Affinché un documento venga unito a un set ND, è necessario che sia presente almeno un documento nel set ND con un livello di somiglianza superiore alla somiglianza. 
  
Si supponga, ad esempio, che la somiglianza sia impostata su 80%, che Document F1 sia simile al documento F2 al livello 85% e che il documento F2 sia analogo al documento F3 al livello del 90%. 
  
Tuttavia, il documento F1 può essere simile a quello F3 al livello di soli 70%, che è al di sotto della soglia. Tuttavia, in questo esempio, i documenti F1, F2 e F3 vengono visualizzati tutti nel set ND. Analogamente, se si utilizza un valore di somiglianza pari a 80%, è possibile che siano stati creati due insiemi, EquiSet-1 e EquiSet-2. EquiSet-1 contiene i documenti E1 ed E2. Equiset-2 contiene i documenti F1, F2 e F3. 
  
I livelli di somiglianza sono illustrati nel modo seguente:
  
![Somiglianza documento](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
Si supponga che un altro documento, x1, sia stato inserito. La somiglianza tra x1 e E3 è 87%. Analogamente, la somiglianza tra x1 e F1 è 92%. Di conseguenza, EquiSet-1, EquiSet-2 e X1 vengono ora combinati in un solo set ND.
  
![Somiglianza documento](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> Se i due documenti vengono assegnati a un set ND, rimarranno insieme nello stesso set ND, anche se sono stati aggiunti altri documenti al set o se i set sono Stati Uniti. 
  
Dopo la fusione dei set, il documento pivot può variare quando vengono aggiunti nuovi documenti a un set. 
  
## <a name="see-also"></a>Vedere anche

[Advanced eDiscovery (classica)](office-365-advanced-ediscovery.md)
  
[Impostazione delle opzioni di analisi](set-analyze-options-in-advanced-ediscovery.md)
  
[Impostazione Ignora testo](set-ignore-text-in-advanced-ediscovery.md)
  
[Impostazione analisi impostazioni avanzate](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Visualizzazione dei risultati dell'analisi](view-analyze-results-in-advanced-ediscovery.md)

