---
title: Novità di Microsoft 365 Defender
description: Elenca le nuove funzionalità e funzionalità di Microsoft 365 Defender
keywords: novità di Microsoft Threat Protection, ga, generalmente disponibile, funzionalità, disponibili, nuove
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e75cfe445f62860f8bdb1480fcf9029daa8ac6ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068242"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novità di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Vuoi provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eseguire il progetto pilota in [produzione.](m365d-pilot.md?ocid=cx-evalpilot)
>

Le funzionalità seguenti sono generalmente disponibili nella versione più recente di Microsoft 365 Defender.

Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="march-2021"></a>Marzo 2021
- [Tabella CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Informazioni sugli eventi in varie app e servizi cloud trattati da Microsoft Cloud App Security. Questa tabella include anche informazioni precedentemente disponibili in `AppFileEvents` .
## <a name="february-2021"></a>Febbraio 2021
- (Anteprima) Il Centro sicurezza [Microsoft 365 avanzato ( https://security.microsoft.com) ](https://security.microsoft.com) è ora disponibile in anteprima pubblica. Questa nuova esperienza porta Defender per Endpoint e Defender per Office 365 al centro. [Altre informazioni sulle novità](./overview-security-center.md).

## <a name="september-2020"></a>Settembre 2020
- [Tabella IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Trovare eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD). Questa [tabella dello](advanced-hunting-overview.md) schema di ricerca avanzata copre una serie di eventi correlati all'identità ed eventi di sistema nel controller di dominio.
- [Funzione AssignedIPAddresses()](advanced-hunting-assignedipaddresses-function.md) <br> Utilizzare questa funzione nelle query di ricerca avanzate per ottenere rapidamente gli indirizzi IP più recenti assegnati a un dispositivo o gli indirizzi IP più recenti da un momento specifico.

## <a name="july-2020"></a>Luglio 2020
- [Funzione FileProfile()](advanced-hunting-fileprofile-function.md) <br> Utilizzare questa funzione nelle query di ricerca avanzate per arricchire i risultati con informazioni complete sui file.
- [Tabelle di identità e app](advanced-hunting-schema-tables.md)<br> Ottieni visibilità negli eventi di autenticazione, nelle query di Active Directory e nelle attività correlate alle app con le tabelle [IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) nello schema di ricerca avanzata.
- [Iniziare la ricerca](advanced-hunting-go-hunt.md)<br> Passare rapidamente dall'analisi di un evento imprevisto all'ispezione di un evento specifico, di un utente, di un dispositivo o di altri tipi di entità per la ricerca avanzata.

## <a name="june-2020"></a>Giugno 2020
- Feed di Twitter <br> Ottieni le più recenti ricerche sulla sicurezza, intelligence sulle minacce, notizie sui prodotti e altro ancora, direttamente all'interno del dashboard.
- [Tabella dello schema EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Incorporare informazioni sulle azioni post-recapito eseguite sui messaggi di posta elettronica nelle query di ricerca avanzate.
- [Esaminare i record nella ricerca avanzata](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Esaminare rapidamente i record nei risultati della query con il nuovo riquadro dei dettagli.

## <a name="may-2020"></a>Maggio 2020
- [Rilevamenti personalizzati](custom-detections-overview.md) <br> Utilizzare query di ricerca avanzate per creare regole di rilevamento personalizzate che monitorano e rispondono automaticamente agli eventi di sicurezza e agli stati di sistema.

## <a name="february-2020"></a>Febbraio 2020
- [Eventi imprevisti](incidents-overview.md) <br> Sapere esattamente dove è iniziato un attacco e altri dettagli per vedere la portata dell'attacco.
- [Analisi e risposta automatizzate](m365d-autoir.md) <br> L'AIR consente al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire avvisi e incidenti di sicurezza.
- [Miglioramenti avanzati per la ricerca](advanced-hunting-overview.md) <br> Ricerca proattiva delle minacce nell'area di lavoro moderna con Kusto Query Language e uno schema ottimizzato per la sicurezza.

## <a name="march-2019"></a>Marzo 2019
- Ricerca avanzata <br> Pagina di destinazione per varie funzionalità di ricerca che consentono di individuare in modo proattivo minacce che interessano posta elettronica, dati, dispositivi e identità.
- [Microsoft Secure Score](microsoft-secure-score.md) <br> Misurazione della posizione di sicurezza di un'organizzazione, con un numero maggiore che indica più azioni di miglioramento intraprese. Seguendo i consigli di Microsoft Secure Score è possibile proteggere l'organizzazione dalle minacce. 
- [Report](overview-security-center.md) <br>  Include una serie di schede che coprono un'ampia gamma di aree monitorate dagli analisti e dagli amministratori della sicurezza nell'ambito delle operazioni quotidiane.
