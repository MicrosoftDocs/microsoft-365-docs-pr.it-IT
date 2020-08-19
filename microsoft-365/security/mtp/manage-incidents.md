---
title: Gestire gli eventi imprevisti in Microsoft Threat Protection
description: Informazioni su come assegnare, aggiornare lo stato,
keywords: evento imprevisto, eventi imprevisti, avvisi, avvisi correlati, assegnare, aggiornare, stato, gestire, classificazione, microsoft, 365, M365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 8880655ec24f20efd139b8334ab754f51146b496
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798211"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a>Gestire gli eventi imprevisti in Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection



La gestione degli eventi è fondamentale per garantire il controllo e la soluzione delle minacce. In Microsoft Threat Protection si dispone dell'accesso alla gestione degli eventi imprevisti su dispositivi, utenti e cassette postali. 


È possibile gestire gli eventi selezionandone uno dalla **Coda degli eventi imprevisti**. 

È possibile modificare il nome di un evento, risolverlo, impostarne la classificazione e la determinazione. Inoltre, è possibile assegnare l'evento a se stessi, aggiungere tag e commenti.

Se durante l'analisi si vogliono spostare gli avvisi da un evento all'altro è possibile eseguire l'operazione anche dalla scheda Avvisi, creando così un evento più grande oppure più piccolo che includa tutti gli avvisi pertinenti.

## <a name="edit-incident-name"></a>Modificare il nome di un evento imprevisto
Agli eventi non consentiti viene assegnato automaticamente un nome basato su attributi di avviso, ad esempio il numero di endpoint coinvolti, gli utenti coinvolti, le origini di rilevamento o le categorie. In questo modo è possibile comprendere rapidamente l'ambito dell'evento Incident.

Ad esempio: *eventi a più fasi su più endpoint segnalati da più origini.*

È possibile modificare il nome dell'evento per allinearlo alla convenzione di denominazione preferita.

> [!NOTE]
> Gli eventi non consentiti precedentemente all'implementazione della funzionalità di denominazione degli incidenti automatici manterranno il nome.



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