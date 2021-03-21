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
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926602"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Supporto del linguaggio CJK per Advanced eDiscovery

Advanced eDiscovery supporta le lingue dei set di caratteri a due byte (tra cui cinese semplificato, cinese tradizionale, giapponese e coreano, note collettivamente come lingue *CJK)* per i seguenti scenari avanzati in un set di recensioni:

- Quando si [esegue una query sui dati in un set di revisione](review-set-search.md).

- Quando [tagi documenti in un set di revisioni](tagging-documents.md).

- Quando [analizzi i dati del caso in un set di recensioni](analyzing-data-in-review-set.md) usando il rilevamento quasi duplicato, il threading della posta elettronica e l'analisi dei temi.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Come si crea una ricerca per raccogliere elementi che contengono caratteri CJK?**

È possibile utilizzare i caratteri CJK per [le](building-search-queries.md#keyword-searches)ricerche con parole chiave, le query con [parole chiave](keyword-queries-and-search-conditions.md) e le condizioni di ricerca durante la ricerca di contenuto in Advanced eDiscovery. La ricerca di caratteri CJK è supportata anche durante la ricerca di contenuto in Core eDiscovery e ricerca contenuto.

È disponibile il supporto CJK per tutti [gli](keyword-queries-and-search-conditions.md#search-operators) operatori di ricerca e le condizioni di [ricerca,](keyword-queries-and-search-conditions.md#search-conditions)inclusi gli operatori **booleani AND**, **OR**, **NOT** e **NEAR**.

Se si è certi che i percorsi di contenuto o gli elementi contengano caratteri CJK, ma le ricerche non restituiscono risultati, fare clic sull'icona lingua-paese/area geografica della query ![Icona lingua-paese/area geografica query in Ricerca contenuto](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e selezionare il valore del codice lingua-paese corrispondente per la ricerca. La lingua/area geografica predefinita è neutrale.

**È possibile cercare più lingue contemporaneamente?**

Dipende dallo scenario di ricerca.

- Quando si [esegue una query sui dati in un set di](review-set-search.md) revisione in Advanced eDiscovery, è possibile cercare più lingue.

- Quando [crei una ricerca per raccogliere dati,](create-search-to-collect-data.md)crea una ricerca separata per ogni lingua di destinazione. Ad esempio, se si sta cercando un documento contenente sia cinese che coreano, selezionare Cinese per la prima query e coreano per la seconda query.

**Non viene visualizzata l'icona lingua-paese/area geografica della query per selezionare una lingua per le query in un set di recensioni. Come è possibile specificare un linguaggio di query in una ricerca di set di recensioni?**

Per le query di set di revisione, non è necessario specificare una lingua del documento. Advanced eDiscovery rileva automaticamente le lingue dei documenti quando si aggiunge contenuto a un set di revisioni. In questo modo è possibile ottimizzare i risultati delle query in un set di revisioni.

**È possibile visualizzare le lingue rilevate nei [metadati dei file?](view-documents-in-review-set.md#file-metadata)**

No, non è possibile visualizzare le lingue rilevate nei metadati dei file.

**È possibile filtrare in base alle lingue dei documenti in un set di revisioni?**

No, non è possibile filtrare, ordinare o eseguire ricerche in base alle lingue dei documenti in un set di revisioni.

**Questa versione di CJK per gli scenari di set di revisione influirà su una delle ricerche e sui set di revisione esistenti?**

No, nessuna delle ricerche e dei set di revisioni esistenti verrà cambiata. Non è necessario reindicizzare i dati esistenti e i risultati della ricerca per il testo in inglese saranno gli stessi.

**Come si modifica la lingua di visualizzazione in cinese, giapponese o coreano?**

Per informazioni su come modificare la lingua di visualizzazione e il fuso orario, vedere Come impostare le impostazioni di lingua [e area geografica per Office 365.](/office365/troubleshoot/access-management/set-language-and-region)

## <a name="known-issues"></a>Problemi noti

- L'OCR non supporta i caratteri CJK dai file di immagine

- I file di posta elettronica (ad esempio *.eml e *.msg) nella visualizzazione [Annotazione](view-documents-in-review-set.md#annotate-view) non sono supportati per le lingue CJK.

- L'evidenziazione dei risultati della ricerca [nella](view-documents-in-review-set.md#text-view) visualizzazione Testo non è supportata per le lingue CJK.

- Il [modulo Pertinenza](using-relevance.md) utilizzato per analizzare i dati non supporta i linguaggi CJK.

- [I blocchi basati su query](managing-holds.md#manage-non-custodial-holds) non sono supportati per i linguaggi CJK.