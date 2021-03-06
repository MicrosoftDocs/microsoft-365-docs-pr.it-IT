---
title: Microsoft Defender per Endpoint in Microsoft 365 Defender
description: Informazioni sulle modifiche apportate dall'Microsoft Defender Security Center a Microsoft 365 Defender
keywords: Introduzione a Microsoft 365 Defender, Microsoft Defender per Office 365, Microsoft Defender for Endpoint, MDO, MDE, portale di sicurezza, portale di sicurezza defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: b43b7c99c6585e8610d34f3c4e5b372fb1c829a2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842627"
---
# <a name="microsoft-defender-for-endpoint-in-microsoft-365-defender"></a>Microsoft Defender per Endpoint in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="quick-reference"></a>Riferimento rapido

L'immagine e la tabella seguente elencano le modifiche nello spostamento tra Microsoft Defender Security Center e Microsoft 365 Defender.

> [!div class="mx-imgBorder"]
> ![Immagine di ciò che è stato spostato nel punto in cui è stato spostato](../../media/mde-m3d-security-center.png)

| Microsoft Defender Security Center | Microsoft 365 Defender |
|---------|---------|
| Dashboard <ul><li>Operazioni di sicurezza</li><li>Analisi delle minacce</li></ul>  |Home <ul><li>Analisi delle minacce</li></ul>   |
| Eventi imprevisti | Eventi imprevisti & avvisi |
| Inventario dei dispositivi | Inventario dei dispositivi |
| Coda di avvisi | Eventi imprevisti & avvisi |
| Indagini automatizzate | Centro notifiche |
| Rilevazione avanzata | Ricerca |
| Report | Report |
| Partner & API | Partner & API |
| Gestione delle & delle minacce | Gestione delle vulnerabilità |
| Valutazione ed esercitazioni | Esercitazioni & valutazione |
| Gestione della configurazione | Gestione della configurazione |
| Impostazioni | Impostazioni | 

Il miglioramento [Microsoft 365 Defender](overview-security-center.md) combina funzionalità di sicurezza che proteggono, rilevano, analizzano e rispondono alle minacce di posta [https://security.microsoft.com](https://security.microsoft.com) elettronica, collaborazione, identità e dispositivi. In questo modo vengono riunite le funzionalità dei portali di sicurezza Microsoft esistenti, tra cui Microsoft Defender Security Center e il Centro sicurezza Office 365 sicurezza & conformità.

Se hai familiarità con il Microsoft Defender Security Center, questo articolo illustra alcune delle modifiche e dei miglioramenti apportati a Microsoft 365 Defender. Esistono tuttavia alcuni elementi nuovi e aggiornati di cui tenere conto.

Storicamente, la [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) è stata la sede di Microsoft Defender per Endpoint. Enterprise team di sicurezza lo hanno usato per monitorare e contribuire a rispondere agli avvisi di potenziali attività avanzate di minacce persistenti o violazioni dei dati. Per ridurre il numero di portali, Microsoft 365 Defender sarà la sede per il monitoraggio e la gestione della sicurezza tra identità, dati, dispositivi, app e infrastruttura Microsoft.

Microsoft Defender for Endpoint in Microsoft 365 Defender supporta la concessione dell'accesso ai provider di servizi di sicurezza gestiti [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) nello stesso modo in cui viene concesso l'accesso nel Centro sicurezza [Microsoft Defender.](mssp-access.md)

> [!IMPORTANT]
> Ciò che vedi in Microsoft 365 Defender dipende dalle sottoscrizioni correnti. Ad esempio, se non hai una licenza per Microsoft Defender per Office 365, la sezione Email & Collaboration non verrà visualizzata.

> [!Note]
> Microsoft 365 Defender non è disponibile per:
>- Us Government Community Cloud (GCC)
>- Us Government Community Cloud High (GCC High)
>- US Department of Defense
>- Tutte le istituzioni governative statunitensi con licenze commerciali

Dai un'occhiata a Microsoft 365 Defender: [https://security.microsoft.com](https://security.microsoft.com) .

Altre informazioni sui vantaggi: [Panoramica di Microsoft 365 Defender](overview-security-center.md)

## <a name="whats-changed"></a>Modifiche

Questa tabella è un riferimento rapido alle modifiche tra Microsoft Defender Security Center e Microsoft 365 Defender.

### <a name="alerts-and-actions"></a>Avvisi e azioni

| Area | Descrizione della modifica |
|---------|---------|
| [Eventi imprevisti & avvisi](incidents-overview.md)  | In Microsoft 365 Defender puoi gestire eventi imprevisti e avvisi in tutti gli endpoint, i messaggi di posta elettronica e le identità. Abbiamo convergente l'esperienza per aiutarti a trovare più facilmente gli eventi correlati. Per ulteriori informazioni, vedere [Incidents Overview.](incidents-overview.md)   |
| [Ricerca](advanced-hunting-overview.md)  |  La modifica delle regole di rilevamento personalizzate create in Microsoft Defender for Endpoint per includere le tabelle di identità e posta elettronica le sposta automaticamente Microsoft 365 Defender. Gli avvisi corrispondenti verranno visualizzati anche in Microsoft 365 Defender. Per ulteriori informazioni su queste modifiche, vedere [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules). <br><br>La `DeviceAlertEvents` tabella per la ricerca avanzata non è disponibile in Microsoft 365 Defender. Per eseguire query sulle informazioni di avviso specifiche del dispositivo in Microsoft 365 Defender, puoi usare le tabelle e per includere ulteriori informazioni da un `AlertInfo` `AlertEvidence` set di origini diverse. Crea la query correlata al dispositivo successiva seguendo [Le query di scrittura senza DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).|
|[Centro notifiche](m365d-action-center.md)    | Elenca le azioni in sospeso e completate eseguite in seguito a indagini automatizzate e azioni di correzione. In precedenza, il centro notifiche nel Microsoft Defender Security Center elencate le azioni in sospeso e completate per le azioni di correzione eseguite solo sui dispositivi, mentre le indagini automatizzate hanno elencato gli avvisi e lo stato. Nella versione Microsoft 365 Defender, il centro notifiche riunisce le azioni di correzione e le indagini su posta elettronica, dispositivi e utenti, il tutto in un'unica posizione.  |
| [Analisi delle minacce](threat-analytics.md) |  Spostato nella parte superiore della barra di spostamento per semplificarne l'individuazione e l'utilizzo. Ora include informazioni sulle minacce sia per gli endpoint che per la posta elettronica e la collaborazione.    |

### <a name="endpoints"></a>Endpoint

| Area | Descrizione della modifica |
|---------|---------|
|Ricerca   |  Invece di essere nell'intestazione, la barra di ricerca di Microsoft Defender for Endpoint si sposta sotto la sezione Endpoint. È possibile continuare a cercare dispositivi, file, utenti, URL, IP, vulnerabilità, software e suggerimenti.  |
|[Dashboard](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  Questo è il dashboard delle operazioni di sicurezza. Vedi una panoramica del numero di avvisi attivi attivati, dei dispositivi a rischio, degli utenti a rischio e del livello di gravità per avvisi, dispositivi e utenti. Puoi anche vedere se i dispositivi hanno problemi con i sensori, l'integrità complessiva del servizio e il modo in cui sono stati rilevati eventuali avvisi non risolti. |
|Inventario dei dispositivi | Nessuna modifica. |
|[Gestione delle vulnerabilità](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    Il nome è stato abbreviato per adattarsi al riquadro di spostamento. Corrisponde alla sezione gestione di minacce e vulnerabilità, con tutte le pagine sottostanti.     |
| Partner e API | Nessuna modifica. |
| Valutazioni & esercitazioni    |     Nuove funzionalità di test e apprendimento.     |
| Gestione della configurazione   |  Nessuna modifica.  |

> [!NOTE]
> **L'analisi e la correzione automatiche** fanno ora parte degli incidenti. È possibile visualizzare gli eventi di analisi e correzione automatizzati nella **scheda Analisi** > eventi imprevisti.

> [!TIP]
> La ricerca dei dispositivi viene eseguita da Endpoint > Search.

### <a name="access-and-reporting"></a>Accesso e creazione di report

| Area | Descrizione della modifica |
|---------|---------|
| Report  | Vedi i report per gli endpoint e la & di posta elettronica, tra cui Protezione dalle minacce, Integrità e conformità dei dispositivi e Dispositivi vulnerabili. |
| Sanità  |  Attualmente si collega alla pagina "Integrità del servizio" [nell'Microsoft 365 di amministrazione.](https://admin.microsoft.com/) |
| Impostazioni |  Gestisci le impostazioni per Microsoft 365 Defender, Endpoint, Email & collaboration, Identities e Device discovery.   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a>Microsoft 365 navigazione e funzionalità di sicurezza

La barra di spostamento sinistro, o barra di avvio veloce, ha un aspetto familiare. Tuttavia, sono presenti alcuni elementi nuovi e aggiornati in questo Centro sicurezza.

### <a name="incidents-and-alerts"></a>Eventi imprevisti e avvisi

Raggruppa la gestione degli eventi imprevisti e degli avvisi in tutta la posta elettronica, i dispositivi e le identità. La pagina di avviso fornisce il contesto completo dell'avviso combinando i segnali di attacco per creare una storia dettagliata. Una nuova esperienza unificata ora riunisce una visualizzazione coerente degli avvisi nei diversi carichi di lavoro. È possibile analizzare, investigare e intervenire rapidamente.

- [Altre informazioni sugli incidenti](incidents-overview.md)
-  [Altre informazioni sulla gestione degli avvisi](investigate-alerts.md).

![Barra di avvio veloce Avvisi e azioni](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Ricerca

Cercare proattivamente minacce, software dannosi e attività dannose in endpoint, cassette postali di Office 365 e altro ancora usando [query di ricerca avanzata ](advanced-hunting-overview.md). Queste query potenti possono essere utilizzate per individuare ed esaminare gli indicatori di minaccia e le entità per le minacce note e potenziali.

[Le regole di rilevamento](custom-detection-rules.md) personalizzate possono essere create da query di ricerca avanzate che consentono di osservare in modo proattivo gli eventi che potrebbero essere indicativi dell'attività di violazione e dei dispositivi non configurati correttamente.


### <a name="action-center"></a>Centro notifiche

Il centro notifiche mostra le indagini create da funzionalità automatizzate di indagine e risposta. Questo strumento automatizzato e self-healing di Microsoft 365 Defender può aiutare i team addetti alla sicurezza a rispondere automaticamente a eventi specifici.

[Altre informazioni sul centro notifiche](m365d-action-center.md).

### <a name="threat-analytics"></a>Analisi delle minacce

Ottenere analisi delle minacce da esperti ricercatori Microsoft in materia di sicurezza. Analisi delle minacce aiuta i team addetti alla sicurezza a essere più efficienti di fronte alle minacce emergenti. Analisi delle minacce comprende:

- Rilevamenti e mitigazioni correlati alla posta elettronica da Microsoft Defender per Office 365. Questa opzione si aggiunge ai dati dell’endpoint già disponibili da Microsoft Defender per endpoint.
- Visualizzazione degli incidenti relativi alle minacce.
- Esperienza migliorata per identificare e usare rapidamente le informazioni interattive nei report.

È possibile accedere all'analisi delle minacce dalla barra di spostamento in alto a sinistra in Microsoft 365 Defender o da una scheda del dashboard dedicata che mostra le minacce principali per l'organizzazione.

Ulteriori informazioni su come tenere [traccia e rispondere alle minacce emergenti con l'analisi delle minacce.](./threat-analytics.md)

### <a name="endpoints-section"></a>Sezione Endpoint

Visualizzare e gestire la sicurezza degli endpoint nell'organizzazione. Se hai usato il Microsoft Defender Security Center, sarà familiare.

![Barra di avvio veloce Endpoints](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a>Accesso e report

Consente di visualizzare report, modificare le impostazioni e i ruoli utente.

![Barra di avvio rapido accesso e creazione di report](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a>Connessioni API SIEM

Se usi [l'API Defender for Endpoint SIEM,](../defender-endpoint/enable-siem-integration.md)puoi continuare a farlo. Nel payload dell'API sono stati aggiunti nuovi collegamenti che puntano alla pagina di avviso o alla pagina degli eventi imprevisti nel portale Microsoft 365 sicurezza. I nuovi campi API includono LinkToMTP e IncidentLinkToMTP. Per altre informazioni, vedi [Reindirizzamento degli account da Microsoft Defender per Endpoint a Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).

### <a name="email-alerts"></a>Avvisi tramite posta elettronica

Puoi continuare a usare gli avvisi di posta elettronica per Defender per Endpoint. Abbiamo aggiunto nuovi collegamenti nei messaggi di posta elettronica che puntano alla pagina di avviso o alla pagina dell'evento imprevisto in Microsoft 365 Defender. Per altre informazioni, vedi [Reindirizzamento degli account da Microsoft Defender per Endpoint a Microsoft 365 Defender](./microsoft-365-security-mde-redirection.md).

### <a name="managed-security-service-providers-mssp"></a>Provider di servizi di sicurezza gestiti (MSSP)

L'accesso a più tenant contemporaneamente nella stessa sessione di esplorazione non è attualmente supportato nel portale unificato. Puoi rifiutare esplicitamente il reindirizzamento automatico ripristinando l'ex [portale di Microsoft Defender for Endpoint](microsoft-365-security-mde-redirection.md#can-i-go-back-to-using-the-former-portal)per mantenere questa funzionalità fino a quando il problema non viene risolto.

## <a name="related-information"></a>Informazioni correlate

- [Microsoft 365 Defender](overview-security-center.md)
- [Microsoft Defender per Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Reindirizzamento degli account da Microsoft Defender per Endpoint a Microsoft 365 Defender](microsoft-365-security-mde-redirection.md)
