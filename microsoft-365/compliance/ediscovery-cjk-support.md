---
title: Supporto di CJK/Double byte per Advanced eDiscovery
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
description: Informazioni su come Advanced eDiscovery in Microsoft 365 supporta lingue cinesi, giapponesi e coreane (CJK), che utilizzano un set di caratteri a doppio byte.
ms.openlocfilehash: cef91001f48512545ce528d6f43de97c28c4c495
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626936"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>Supporto per la lingua CJK per Advanced eDiscovery

Advanced eDiscovery supporta le lingue con set di caratteri a doppio byte, tra cui il cinese semplificato, il cinese tradizionale, il giapponese e il coreano, noti collettivamente come lingue *CJK* , per i seguenti scenari avanzati in un set di riesame:

- Quando si [esegue la query dei dati in un set di revisione](review-set-search.md).

- Quando si [contrassegnano i documenti in un set di revisione](tagging-documents.md).

- Quando si [analizzano i dati del caso in un set di revisione](analyzing-data-in-review-set.md) , è possibile utilizzare la funzionalità di rilevamento duplicati, Threading di posta elettronica e analisi dei temi

## <a name="frequently-asked-questions"></a>Domande frequenti

**Come creare una ricerca per raccogliere gli elementi che contengono caratteri CJK.**

È possibile utilizzare i caratteri CJK per le [ricerche di parole chiave](building-search-queries.md#keyword-searches), [le query con parole chiave e le condizioni di ricerca](keyword-queries-and-search-conditions.md) durante la ricerca di contenuto in Advanced eDiscovery. La ricerca di caratteri CJK è supportata anche durante la ricerca di contenuto in eDiscovery di base e ricerca contenuto.

Viene fornito il supporto CJK per tutti [gli operatori di ricerca](keyword-queries-and-search-conditions.md#search-operators) e le [condizioni di ricerca](keyword-queries-and-search-conditions.md#search-conditions), compresi gli operatori booleani **e**, **o**, **non**e **vicino**.

Se si è certi che i percorsi o gli elementi di contenuto contengano caratteri CJK, ma le ricerche non restituiscono alcun risultato, fare clic sull'icona lingua query-paese/area geografica ![Lingua query-icona paese/area geografica nella ricerca contenuto](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) e seleziona il valore del codice corrispondente alla lingua per la ricerca. La lingua/area geografica predefinita è neutrale.

**È possibile eseguire la ricerca di più lingue contemporaneamente?**

Dipende dallo scenario di ricerca.

- Quando si [esegue una query di dati in un set di revisione](review-set-search.md) in Advanced eDiscovery, è possibile eseguire la ricerca di più lingue.

- Quando si [Crea una ricerca per raccogliere dati](create-search-to-collect-data.md), creare una ricerca distinta per ogni lingua che si desidera utilizzare. Ad esempio, se si esegue la ricerca di un documento contenente sia cinese che coreano, selezionare cinese per la prima query e selezionare coreano per la seconda query.

**Non viene visualizzata l'icona lingua query-paese/area geografica per selezionare una lingua per le query in un set di revisione. In che modo è possibile specificare una lingua di query in una ricerca set di Revisione?**

Per le query dei set di revisione, non è necessario specificare una lingua del documento. Advanced eDiscovery rileva automaticamente le lingue del documento quando si aggiunge contenuto a un set di revisione. In questo modo è possibile ottimizzare i risultati delle query in un set di revisione.

**È possibile visualizzare le lingue rilevate nei [metadati dei file](view-documents-in-review-set.md#file-metadata)?**

No, non è possibile visualizzare le lingue rilevate nei metadati dei file.

È **possibile filtrare in base alle lingue dei documenti in un set di revisione**?

No, non è possibile filtrare, ordinare o cercare in base alle lingue dei documenti in un set di revisione.

**La versione CJK per gli scenari del set di revisione influirà sulle ricerche e sui set di revisione esistenti?**

No, non verranno modificate le ricerche esistenti e i set di revisione. Non è necessario reindicizzare i dati esistenti e i risultati della ricerca per il testo in inglese saranno gli stessi.

**Come si modifica la lingua di visualizzazione in cinese, giapponese o coreano?**

Per informazioni su come modificare la lingua e il fuso orario di visualizzazione, vedere [How to set Language and Region Settings for Office 365](https://docs.microsoft.com/office365/troubleshoot/access-management/set-language-and-region).

## <a name="known-issues"></a>Problemi noti

- OCR non supporta i caratteri CJK dai file di immagine

- I file di posta elettronica (ad esempio, *. eml e *. msg) in [Visualizzazione annotazioni](view-documents-in-review-set.md#annotate-view) non sono supportati per le lingue CJK.

- La ricerca hit highlighting nella [visualizzazione testo](view-documents-in-review-set.md#text-view) non è supportata per le lingue CJK.

- Il [modulo di pertinenza](using-relevance.md) utilizzato per l'analisi dei dati non supporta le lingue CJK.

- Le [esenzioni basate su query](managing-holds.md#manage-non-custodial-holds) non sono supportate per le lingue CJK. 
