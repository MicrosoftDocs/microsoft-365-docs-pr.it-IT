---
title: Novità di Microsoft 365 Defender
description: Elenca le nuove caratteristiche e funzionalità in Microsoft 365 Defender
keywords: novità di Microsoft 365 Defender, ga, generalmente disponibili, funzionalità, disponibili, nuove
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
ms.openlocfilehash: af5efb669b1f73b4008ac2c3fae251a4d08511dd
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53340985"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novità di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Vuoi provare Microsoft 365 Defender? Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).
>

Le funzionalità seguenti sono generalmente disponibili nella versione più recente di Microsoft 365 Defender.

Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="july-2021"></a>Luglio 2021
- [Professional dei servizi di distribuzione](https://sip.security.microsoft.com/interoperability/professional_services)<br>Migliorare le funzionalità di rilevamento, analisi e intelligence delle minacce della piattaforma con connessioni partner supportate.
    

## <a name="may-2021"></a>Maggio 2021

- [Nuova pagina di avviso nel portale Microsoft 365 Defender messaggi](https://techcommunity.microsoft.com/t5/microsoft-365-defender/easily-find-anomalies-in-incidents-and-alerts/ba-p/2339243) <br> Fornisce informazioni avanzate per il contesto in un attacco. È possibile vedere quale altro avviso attivato ha causato l'avviso corrente e tutte le entità e le attività interessate coinvolte nell'attacco, inclusi file, utenti e cassette postali. Per [ulteriori informazioni, vedere Analizzare](/microsoft-365/security/defender/investigate-alerts) gli avvisi.
- [Grafico delle tendenze per eventi imprevisti e avvisi nel portale Microsoft 365 Defender dati](https://techcommunity.microsoft.com/t5/microsoft-365-defender/new-alert-page-for-microsoft-365-defender-incident-detections/ba-p/2350425) <br> Determinare se sono presenti diversi avvisi per un singolo evento imprevisto o se l'organizzazione è sotto attacco con diversi eventi imprevisti. Per [ulteriori informazioni, vedere Assegnare priorità](/microsoft-365/security/defender/incident-queue) agli eventi imprevisti.


## <a name="april-2021"></a>Aprile 2021
- Microsoft 365 Defender<br> Il portale [Microsoft 365 Defender](https://security.microsoft.com) è ora disponibile. Questa nuova esperienza riunisce Defender for Endpoint, Defender for Office 365, Defender for Identity e altro ancora in un unico portale. Questa è la nuova sede per gestire i controlli di sicurezza. [Informazioni sulle novità](./overview-security-center.md).

- [Microsoft 365 Defender di analisi delle minacce](threat-analytics.md)<br>
 L'analisi delle minacce consente di rispondere e ridurre al minimo l'impatto degli attacchi attivi. Sono inoltre disponibili informazioni sui tentativi di attacco bloccati dalle soluzioni Microsoft 365 Defender ed eseguire azioni preventive che attenuano il rischio di ulteriore esposizione e aumentano la resilienza. Come parte dell'esperienza di sicurezza unificata, l'analisi delle minacce è ora disponibile per Microsoft Defender per Endpoint e Microsoft Defender per i titolari della licenza Office E5.

## <a name="march-2021"></a>Marzo 2021
- [Tabella CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Informazioni sugli eventi in varie app e servizi cloud coperti da Microsoft Cloud App Security. Questa tabella include anche informazioni precedentemente disponibili in `AppFileEvents` .
## <a name="february-2021"></a>Febbraio 2021
- (Anteprima) Il Centro sicurezza [Microsoft 365 avanzata https://security.microsoft.com) (](https://security.microsoft.com) è ora disponibile in anteprima pubblica. Questa nuova esperienza porta Defender per Endpoint e Defender per Office 365 centro. [Altre informazioni sulle novità](./overview-security-center.md).

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
- Rilevazione avanzata <br> Pagina di destinazione per varie funzionalità di ricerca che consentono di individuare in modo proattivo minacce che interessano posta elettronica, dati, dispositivi e identità.
- [Microsoft Secure Score](microsoft-secure-score.md) <br> Misurazione della posizione di sicurezza di un'organizzazione, con un numero maggiore che indica più azioni di miglioramento intraprese. Seguendo i consigli di Microsoft Secure Score è possibile proteggere l'organizzazione dalle minacce. 
- [Report](overview-security-center.md) <br>  Include una serie di schede che coprono un'ampia gamma di aree monitorate dagli analisti e dagli amministratori della sicurezza nell'ambito delle operazioni quotidiane.
