---
title: Novità di Microsoft Threat Protection
description: Elenca le nuove caratteristiche e funzionalità di Microsoft Threat Protection
keywords: Novità di Microsoft Threat Protection, GA, generalmente disponibile, funzionalità, disponibile, nuovo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 670b020e3c15ac99b06bc8615b2693ba73497b8a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412035"
---
# <a name="whats-new-in-microsoft-threat-protection"></a>Novità di Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Le caratteristiche seguenti sono generalmente disponibili (GA) nella versione più recente di Microsoft Threat Protection.

Feed RSS: ricevere una notifica quando questa pagina viene aggiornata copiando e incollando l'URL seguente nel lettore di feed:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+Threat+Protection%22&locale=en-us
```
## <a name="september-2020"></a>Settembre 2020
- [Tabella IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Individuare gli eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD). Questa tabella dello schema di [caccia avanzata](advanced-hunting-overview.md) copre una serie di eventi correlati all'identità e di eventi di sistema nel controller di dominio.
- [Funzione AssignedIPAddresses ()](advanced-hunting-assignedipaddresses-function.md) <br> Utilizzare questa funzione nelle query di caccia avanzate per ottenere rapidamente gli indirizzi IP più recenti assegnati a un dispositivo o gli indirizzi IP più recenti da un determinato periodo di tempo.

## <a name="july-2020"></a>Luglio 2020
- [Funzione fileprofile ()](advanced-hunting-fileprofile-function.md) <br> Utilizzare questa funzione nelle query di caccia avanzate per arricchire i risultati con informazioni complete sui file.
- [Tabelle di identità e app](advanced-hunting-schema-tables.md)<br> Ottenere visibilità negli eventi di autenticazione, nelle query di Active Directory e nell'attività correlata all'applicazione con le tabelle [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) nello schema di caccia avanzato.
- [Iniziare la ricerca](advanced-hunting-go-hunt.md)<br> Rapidamente pivot dall'indagine di un incidente per esaminare un evento specifico, un utente, un dispositivo o altri tipi di entità per la ricerca avanzata.

## <a name="june-2020"></a>Giugno 2020
- Feed Twitter <br> Ottenere le ultime ricerche sulla sicurezza, la tecnologia di minacce, le novità del prodotto e altro ancora, direttamente all'interno del dashboard.
- [Tabella dello schema di EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Includere informazioni sulle azioni di post-recapito eseguite nei messaggi di posta elettronica nelle query di caccia avanzate.
- [Ispezionare i record nella ricerca avanzata](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Esaminare rapidamente i record nei risultati della query con il nuovo riquadro dei dettagli.

## <a name="may-2020"></a>Maggio 2020
- [Rilevamenti personalizzati](custom-detections-overview.md) <br> Utilizzare le query di ricerca avanzate per creare regole di rilevamento personalizzate che monitorano e rispondano automaticamente agli eventi di sicurezza e agli Stati del sistema.

## <a name="february-2020"></a>Febbraio 2020
- [Eventi imprevisti](incidents-overview.md) <br> Sapere esattamente dove è stato avviato un attacco e altri dettagli che consentono di visualizzare l'entità dell'attacco.
- [Analisi e risposta automatizzate](mtp-autoir.md) <br> L'AIR consente al team delle operazioni di sicurezza di aumentare notevolmente la capacità dell'organizzazione di gestire avvisi e incidenti di sicurezza.
- [Miglioramenti alla ricerca avanzata](advanced-hunting-overview.md) <br> Cercare in modo proattivo le minacce nell'area di lavoro moderna con il linguaggio di query di Kusto e uno schema ottimizzato per la sicurezza.

## <a name="march-2019"></a>Marzo 2019
- Ricerca avanzata <br> Landing page to varie funzionalità di caccia che consentono di trovare in modo proattivo minacce che interessano la posta elettronica e i dati, i dispositivi e le identità.
- [Microsoft Secure Score](microsoft-secure-score.md) <br> Misura della posizione di sicurezza di un'organizzazione, con un numero superiore che indica altre azioni di miglioramento eseguite. Dopo i consigli sui punteggi di sicurezza è possibile proteggere l'organizzazione dalle minacce. 
- [Report](monitoring-and-reporting.md) <br>  Include una miriade di schede che coprono una serie di aree in cui gli analisti di sicurezza e gli amministratori rientrano nell'ambito delle operazioni quotidiane.
