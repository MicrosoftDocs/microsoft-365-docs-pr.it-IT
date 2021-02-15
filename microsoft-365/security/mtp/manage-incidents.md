---
title: Gestire gli eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come assegnare, aggiornare lo stato,
keywords: evento imprevisto, eventi imprevisti, avvisi, avvisi correlati, assegnare, aggiornare, stato, gestire, classificazione, microsoft, 365, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 90d9d397b8baf0ffdb9844a0f068f142a5c7fd48
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930631"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Gestire gli eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



La gestione degli eventi è fondamentale per garantire il controllo e la soluzione delle minacce. In Microsoft 365 Defender, è possibile gestire gli eventi imprevisti su dispositivi, utenti e cassette postali. 


È possibile gestire gli eventi selezionandone uno dalla **Coda degli eventi imprevisti**. 

È possibile modificare il nome di un evento, risolverlo, impostarne la classificazione e la determinazione. Inoltre, è possibile assegnare l'evento a se stessi, aggiungere tag e commenti.

Se durante l'analisi si vogliono spostare gli avvisi da un evento all'altro è possibile eseguire l'operazione anche dalla scheda Avvisi, creando così un evento più grande oppure più piccolo che includa tutti gli avvisi pertinenti.

## <a name="edit-incident-name"></a>Modificare il nome di un evento imprevisto
Agli eventi imprevisti viene assegnato automaticamente un nome in base agli attributi degli avvisi, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie. Ciò consente di comprendere rapidamente l'ambito dell'incidente.

Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*

È possibile modificare il nome dell'evento per allinearlo alla convenzione di denominazione preferita.

> [!NOTE]
> Gli eventi imprevisti che si sono verificati prima dell'implementazione della funzionalità di denominazione automatica degli eventi imprevisti manterranno il nome.



## <a name="assign-incidents"></a>Assegnare gli eventi imprevisti
Se un evento non è stato ancora assegnato, è possibile selezionare **Assegna a me** per assegnare l'evento a se stessi. In questo modo si assume la proprietà non solo dell'evento, ma anche di tutti gli avvisi associati.

## <a name="set-status-and-classification"></a>Impostare lo stato e la classificazione
### <a name="incident-status"></a>Stato di un evento imprevisto
È possibile categorizzare gli eventi imprevisti, ad esempio **Attivo** oppure **Risolto**, modificando lo stato durante il corso dell'analisi. Questo consente di organizzare e gestire il modo in cui il team può rispondere agli eventi imprevisti.

Ad esempio, l'analista SOC può esaminare gli eventi **Attivi** e urgenti del giorno e decidere di assegnarli a se stesso per l'analisi.

In alternativa, può impostare l'evento come **Risolto** se l'evento è stato corretto. La risoluzione di un evento imprevisto chiude automaticamente tutti gli avvisi ancora aperti che fanno parte dell'evento. 

### <a name="classification-and-determination"></a>Classificazione e determinazione
È possibile scegliere di non impostare una classificazione oppure decidere di specificare se un evento è vero o falso. Così facendo, il team può visualizzare i criteri e imparare a usarli. 

## <a name="add-comments"></a>Aggiungere commenti
È possibile aggiungere commenti e visualizzare gli eventi cronologici relativi a un imprevisto per visualizzare le precedenti modifiche apportate.

Ogni volta che viene apportata una modifica o aggiunto un commento a un avviso, l'evento viene registrato nella sezione Commenti e cronologia.

I commenti aggiunti vengono visualizzati istantaneamente nel pannello.

## <a name="add-incident-tags"></a>Aggiungere tag agli eventi
È possibile aggiungere tag personalizzati a un evento, ad esempio per contrassegnare un insieme di eventi imprevisti con caratteristiche comuni. In seguito è possibile filtrare la coda di tutti gli eventi imprevisti che contengono un tag specifico.
