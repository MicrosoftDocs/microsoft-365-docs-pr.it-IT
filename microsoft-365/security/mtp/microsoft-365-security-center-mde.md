---
title: Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365
description: Informazioni sulle modifiche dal Centro sicurezza Microsoft Defender al Centro sicurezza Microsoft 365
keywords: Introduzione al Centro sicurezza Microsoft 365, OATP, MDATP, MDO, MDE, riquadro singolo di vetro, portale convergente, portale di sicurezza, portale di sicurezza, portale di sicurezza defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 03b73901512522edec7fdbc579eaf4073eed5d48
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167466"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a>Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Si applica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender per Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

Il Centro sicurezza [Microsoft 365](overview-security-center.md) migliorato combina funzionalità di sicurezza che proteggono, rilevano, analizzano e rispondono alle minacce di posta [https://security.microsoft.com](https://security.microsoft.com) elettronica, collaborazione, identità e dispositivi. Questo centro sicurezza riunisce le funzionalità dei portali di sicurezza Microsoft esistenti, tra cui Microsoft Defender Security Center e il Centro sicurezza & conformità di Office 365.

Se si ha familiarità con Microsoft Defender Security Center, questo articolo illustra alcune delle modifiche e dei miglioramenti apportati al Centro sicurezza Microsoft 365 migliorato. Tuttavia, esistono alcuni elementi nuovi e aggiornati di cui tenere conto.

Da sempre, [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) è stato la sede di Microsoft Defender per Endpoint. I team di sicurezza aziendali lo hanno usato per monitorare e rispondere agli avvisi di potenziali attività avanzate di minacce persistenti o violazioni dei dati. Per ridurre il numero di portali, il Centro sicurezza Microsoft 365 sarà la sede per il monitoraggio e la gestione della sicurezza tra identità, dati, dispositivi, app e infrastruttura Microsoft.

> [!IMPORTANT]
> Ciò che viene visualizzato nel Centro sicurezza Microsoft 365 dipende dagli abbonamenti correnti. Ad esempio, se non si dispone di una licenza per Microsoft Defender per Office 365, la sezione E-mail & Collaboration non verrà visualizzata.

Dai un'occhiata al Centro sicurezza Microsoft 365 migliorato: [https://security.microsoft.com](https://security.microsoft.com) .

Ulteriori informazioni sui vantaggi: Panoramica del Centro sicurezza [Microsoft 365](overview-security-center.md)

## <a name="whats-changed"></a>Modifiche

Questa tabella è un riferimento rapido alle modifiche tra Microsoft Defender Security Center e il Centro sicurezza Microsoft 365.

### <a name="alerts-and-actions"></a>Avvisi e azioni

|**Area**  |**Descrizione della modifica**  |
|---------|---------|
| [Eventi imprevisti & avvisi](incidents-overview.md)  | Nel Centro sicurezza Microsoft 365 è possibile gestire eventi imprevisti e avvisi in tutti gli endpoint, la posta elettronica e le identità. L'esperienza è stata convergente per aiutarti a trovare più facilmente gli eventi correlati. Per ulteriori informazioni, vedere [Panoramica degli eventi imprevisti.](incidents-overview.md)   |
| [Ricerca](advanced-hunting-overview.md)  |  La modifica delle regole di rilevamento personalizzate create in Microsoft Defender for Endpoint per includere le tabelle di identità e di posta elettronica le sposta automaticamente in Microsoft 365 Defender. Gli avvisi corrispondenti verranno visualizzati anche in Microsoft 365 Defender. Per ulteriori informazioni su queste modifiche, vedere Eseguire [la migrazione di regole di rilevamento personalizzate.](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules) La `DeviceAlertEvents` tabella per la ricerca avanzata non è disponibile in Microsoft 365 Defender. Per eseguire query sulle informazioni sugli avvisi specifici del dispositivo in Microsoft 365 Defender, è possibile utilizzare le tabelle e le tabelle per contenere ulteriori informazioni provenienti da un `AlertInfo` `AlertEvidence` set di origini diverse. Crea la query correlata al dispositivo successiva seguendo [query di scrittura senza DeviceAlertEvents.](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)|
|[Centro notifiche](mtp-action-center.md)    | Elenca le azioni in sospeso e completate eseguite in seguito a indagini automatizzate e azioni di correzione. In precedenza, il centro notifiche nel Microsoft Defender Security Center ha elencato le azioni in sospeso e completate per le azioni di correzione eseguite solo sui dispositivi, mentre le indagini automatizzate hanno elencato avvisi e stato. Nel centro sicurezza Microsoft 365 migliorato, il centro notifiche riunisce le azioni di correzione e le indagini su posta elettronica, dispositivi e utenti, il tutto in un'unica posizione.  |
| [Analisi delle minacce](threat-analytics.md) |  Spostato nella parte superiore della barra di spostamento per semplificarne l'individuazione e l'utilizzo. Ora include informazioni sulle minacce sia per gli endpoint che per la posta elettronica e la collaborazione.    |

### <a name="endpoints"></a>Endpoint

|**Area**  |**Descrizione della modifica**  |
|---------|---------|
|Ricerca   |  Invece di essere nell'intestazione, la barra di ricerca di Microsoft Defender for Endpoint si sposta sotto la sezione Endpoint. È possibile continuare a cercare dispositivi, file, utenti, URL, INDIRIZZI IP, vulnerabilità, software e suggerimenti.  |
|[Dashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Questo è il dashboard delle operazioni di sicurezza. Vedi una panoramica del numero di avvisi attivi attivati, dei dispositivi a rischio, degli utenti a rischio e del livello di gravità per avvisi, dispositivi e utenti. Puoi anche vedere se alcuni dispositivi hanno problemi con i sensori, l'integrità complessiva del servizio e come sono stati rilevati eventuali avvisi non risolti. |
|Inventario dei dispositivi | Nessuna modifica. |
|[Gestione delle vulnerabilità](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    Il nome è stato abbreviato per adattarsi al riquadro di spostamento. È la stessa della sezione di gestione delle minacce e delle vulnerabilità, con tutte le pagine sottostanti.     |
| Partner e API | Nessuna modifica. |
| Valutazioni & esercitazioni    |     Nuove funzionalità di test e apprendimento.     |
| Gestione della configurazione   |  Nessuna modifica.  |

> [!NOTE]
> **L'analisi e la correzione automatiche** sono ora parte degli incidenti. È possibile visualizzare gli eventi di analisi e correzione automatizzati nella **scheda Incident > Investigation.**

### <a name="access-and-reporting"></a>Accesso e creazione di report

|**Area**  |**Descrizione della modifica**  |
|---------|---------|
| Report  | Vedere i report per gli endpoint e la collaborazione & posta elettronica, tra cui protezione dalle minacce, integrità e conformità dei dispositivi e dispositivi vulnerabili. |
| Sanità  |  Attualmente si collega alla pagina "Integrità dei servizi" nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/) |
| Impostazioni |  Gestire le impostazioni per il Centro sicurezza Microsoft 365, Microsoft 365 Defender, endpoint, collaborazione & posta elettronica, identità e individuazione dei dispositivi.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Funzionalità e spostamento per la sicurezza di Microsoft 365

Lo spostamento a sinistra, o barra di avvio veloce, avrà un aspetto familiare. Tuttavia, in questo Centro sicurezza sono presenti alcuni elementi nuovi e aggiornati.

### <a name="incidents-and-alerts"></a>Eventi imprevisti e avvisi

Riunisce la gestione degli eventi imprevisti e degli avvisi nella posta elettronica, nei dispositivi e nelle identità. La pagina di avviso fornisce il contesto completo dell'avviso combinando i segnali di attacco per creare una storia dettagliata. Una nuova esperienza unificata ora riunisce una visualizzazione coerente degli avvisi tra i carichi di lavoro. È possibile esaminare, analizzare e intraprendere rapidamente un'azione efficace.

- [Altre informazioni sugli incidenti](incidents-overview.md)
- [Ulteriori informazioni sulla gestione degli avvisi](investigate-alerts.md)

![Barra di avvio veloce Avvisi e azioni](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Ricerca

Cercare in modo proattivo minacce, malware e attività dannose tra gli endpoint, le cassette postali di Office 365 e altro ancora utilizzando [query di ricerca avanzata.](advanced-hunting-overview.md) Queste query potenti possono essere utilizzate per individuare ed esaminare gli indicatori di minaccia e le entità per le minacce note e potenziali.

[Le regole di rilevamento](custom-detection-rules.md) personalizzate possono essere create da query di ricerca avanzata che consentono di controllare in modo proattivo gli eventi che potrebbero essere indicativi dell'attività di violazione e dei dispositivi non configurati correttamente.


### <a name="action-center"></a>Centro notifiche

Il centro notifiche mostra le indagini create dalle funzionalità di analisi e risposta automatizzate. Questa riparazione automatica in Microsoft 365 Defender può aiutare i team di sicurezza rispondendo automaticamente a eventi specifici.

[Altre informazioni sul centro notifiche](mtp-action-center.md)

### <a name="threat-analytics"></a>Threat Analytics

Ottenere informazioni sulle minacce da esperti ricercatori di sicurezza Microsoft. Threat Analytics consente ai team di sicurezza di essere più efficienti quando affrontano le minacce emergenti. Threat Analytics include:

- Rilevamenti e mitigazioni correlati alla posta elettronica da Microsoft Defender per Office 365. Questo si aggiunge ai dati dell'endpoint già disponibili da Microsoft Defender per Endpoint.
- Visualizzazione degli eventi imprevisti correlata alle minacce.
- Esperienza migliorata per l'identificazione rapida e l'utilizzo di informazioni utilizzabili nei report.

È possibile accedere all'analisi delle minacce dalla barra di spostamento in alto a sinistra nel Centro sicurezza Microsoft 365 o da una scheda del dashboard dedicata che mostra le principali minacce per l'organizzazione.

Ulteriori informazioni su come tenere traccia [e rispondere alle minacce emergenti con l'analisi delle minacce](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)

### <a name="endpoints-section"></a>Sezione Endpoint

Visualizzare e gestire la sicurezza degli endpoint nell'organizzazione. Se hai usato Microsoft Defender Security Center, avrà un aspetto familiare.

![Barra di avvio veloce endpoint](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Access e report

Visualizzare i report, modificare le impostazioni e modificare i ruoli utente.

![Barra di avvio veloce di Access e creazione di report](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>Connessioni API SIEM

Se usi [l'API Defender for Endpoint SIEM,](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)puoi continuare a farlo. Sono stati aggiunti nuovi collegamenti nel payload dell'API che puntano alla pagina di avviso o alla pagina degli eventi imprevisti nel portale di sicurezza di Microsoft 365. I nuovi campi API includono LinkToMTP e IncidentLinkToMTP. Per altre informazioni, vedere [Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)

### <a name="email-alerts"></a>Avvisi tramite posta elettronica

Puoi continuare a usare gli avvisi di posta elettronica per Defender per Endpoint. Abbiamo aggiunto nuovi collegamenti nei messaggi di posta elettronica che puntano alla pagina di avviso o alla pagina degli eventi imprevisti nel Centro sicurezza Microsoft 365. Per altre informazioni, vedere [Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)

## <a name="related-information"></a>Informazioni correlate

- [Centro sicurezza Microsoft 365](overview-security-center.md)
- [Microsoft Defender per Endpoint nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mde.md)
- [Reindirizzamento degli account da Microsoft Defender per Endpoint al Centro sicurezza Microsoft 365](microsoft-365-security-mde-redirection.md)
