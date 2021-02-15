---
title: Supporto CJK/Double Byte per Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come Advanced eDiscovery in Microsoft 365 supporta le lingue cinese, giapponese e coreano (CJK), che utilizzano un set di caratteri a byte doppio.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626936"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Supporto del linguaggio CJK per Advanced eDiscovery

Advanced eDiscovery supporta le lingue dei set di caratteri a byte doppio (tra cui cinese semplificato, cinese tradizionale, giapponese e coreano, note collettivamente come lingue *CJK)* per i seguenti scenari avanzati in un insieme da rivedere:

- Quando si [esegue una query sui dati in un insieme da rivedere.](review-set-search.md)

- Quando si [contrassegnano i documenti in un insieme da rivedere.](tagging-documents.md)

- Quando si [analizzano i dati del caso in un insieme da rivedere](analyzing-data-in-review-set.md) usando il rilevamento quasi duplicato, il threading della posta elettronica e l'analisi dei temi.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Come si crea una ricerca per raccogliere elementi che contengono caratteri CJK?**

È possibile utilizzare i caratteri CJK per [le](building-search-queries.md#keyword-searches)ricerche tramite parole chiave, le query con [parole chiave](keyword-queries-and-search-conditions.md) e le condizioni di ricerca durante la ricerca di contenuto in Advanced eDiscovery. La ricerca di caratteri CJK è supportata anche quando si cerca contenuto in Core eDiscovery e Ricerca contenuto.

Viene fornito il supporto [](keyword-queries-and-search-conditions.md#search-operators) CJK per tutti gli operatori di ricerca e le condizioni di [ricerca,](keyword-queries-and-search-conditions.md#search-conditions)inclusi gli operatori **booleani AND**, **OR**, **NOT** e **NEAR.**

Se si è certi che i percorsi di contenuto o gli elementi contengano caratteri CJK, ma le ricerche non restituiscono risultati, fare clic sull'icona lingua-paese/area geografica della query ![Icona lingua-paese/area geografica della query in Ricerca contenuto](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selezionare il valore del codice lingua-paese corrispondente per la ricerca. La lingua/area geografica predefinita è neutrale.

**È possibile cercare più lingue contemporaneamente?**

Dipende dallo scenario di ricerca.

- Quando si [e interrogano i dati in un insieme](review-set-search.md) di recensioni in Advanced eDiscovery, è possibile cercare più lingue.

- Quando [crei una ricerca per raccogliere dati,](create-search-to-collect-data.md)crea una ricerca separata per ogni lingua di destinazione. Se ad esempio si sta cercando un documento contenente sia il cinese che il coreano, selezionare il cinese per la prima query e il coreano per la seconda query.

**Non viene visualizzata l'icona lingua-paese/area geografica della query per selezionare una lingua per le query in un insieme da rivedere. Come è possibile specificare una lingua di query in una ricerca di set di recensioni?**

Per le query di revisione impostate, non è necessario specificare una lingua del documento. Advanced eDiscovery rileva automaticamente le lingue dei documenti quando si aggiunge contenuto a un insieme da rivedere. Ciò consente di ottimizzare i risultati delle query in un insieme da rivedere.

**È possibile visualizzare le lingue rilevate nei [metadati dei file?](view-documents-in-review-set.md#file-metadata)**

No, non è possibile visualizzare le lingue rilevate nei metadati dei file.

**È possibile filtrare in base alle lingue dei documenti in un insieme da rivedere?**

No, non è possibile filtrare, ordinare o cercare in base alle lingue dei documenti in un insieme di revisioni.

**Questa versione di CJK per gli scenari impostati per la revisione influirà su una delle ricerche e dei set di revisioni esistenti?**

No, nessuna delle ricerche e dei set di revisioni esistenti cambierà. Non è necessario reindicizzare i dati esistenti e i risultati della ricerca per il testo in inglese saranno gli stessi.

**Come modificare la lingua di visualizzazione in cinese, giapponese o coreano**

Per informazioni su come modificare la lingua di visualizzazione e il fuso orario, vedere Come impostare le impostazioni di lingua [e area geografica per Office 365.](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region)

## <a name="known-issues"></a>Problemi noti

- L'OCR non supporta i caratteri CJK dai file di immagine

- I file di posta elettronica (ad esempio *.eml e *.msg) nella visualizzazione [Annotate](view-documents-in-review-set.md#annotate-view) non sono supportati per i linguaggi CJK.

- L'evidenziazione dei risultati della ricerca [nella](view-documents-in-review-set.md#text-view) visualizzazione Testo non è supportata per i linguaggi CJK.

- Il [modulo Pertinenza](using-relevance.md) utilizzato per analizzare i dati non supporta i linguaggi CJK.

- [Le esenzioni basate su](managing-holds.md#manage-non-custodial-holds) query non sono supportate per i linguaggi CJK. 
