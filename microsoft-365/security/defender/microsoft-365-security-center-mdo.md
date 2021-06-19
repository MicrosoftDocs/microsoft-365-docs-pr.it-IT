---
title: Microsoft Defender per Office 365 in Microsoft 365 Defender
description: Informazioni sulle modifiche apportate dal Centro sicurezza Office 365 conformità a Microsoft 365 Defender.
keywords: Microsoft 365 sicurezza, Introduzione a Microsoft 365 Defender, Microsoft Defender per Office 365, Microsoft Defender for Endpoint, MDO, MDE, riquadro singolo di vetro, nuovo portale di sicurezza, nuovo portale di sicurezza defender
ms.date: 02/21/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.prod: m365-security
ms.technology: m365d
ms.openlocfilehash: 15b1b152966c9c09bf77bea15b9b651f739c3566
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028956"
---
# <a name="microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft Defender per Office 365 in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>Riferimento rapido

Nella tabella seguente sono elencate le modifiche apportate all'esplorazione tra Office 365 Centro sicurezza & conformità e Microsoft 365 Defender.

<br>

****

|[Office 365 Conformità & sicurezza](https://protection.office.com)|[Microsoft 365 Defender](https://security.microsoft.com)|[Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)|[Interfaccia di amministrazione di Exchange](https://admin.exchange.microsoft.com/#/)|
|---|---|---|---|
|Avvisi|<ul><li>[Criteri di avviso](https://security.microsoft.com/alertpolicies)</li><li>[Eventi imprevisti & avvisi](https://security.microsoft.com/alerts)</li></ul>|[Pagina Avvisi](https://compliance.microsoft.com/homepage)||
|Classificazione||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|Prevenzione della perdita dei dati||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|Gestione dei record||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|Governance delle informazioni||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|Gestione dei rischi|[Collaborazione & posta elettronica](https://security.microsoft.com/homepage)|||
|Autorizzazioni|[Autorizzazioni & ruoli](https://security.microsoft.com/emailandcollabpermissions)|Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|Flusso di posta|||Vedere [Exchange di amministrazione](https://admin.exchange.microsoft.com/#/)|
|Privacy dei dati||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|Ricerca|[Audit](https://security.microsoft.com/auditlogsearch?viewid=Async%20Search)|Ricerca (ricerca contenuto)||
|Report|[Report](https://security.microsoft.com/emailandcollabreport)|||
|Garanzia del servizio||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|Supervisione||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||
|eDiscovery||Vedere [Centro conformità Microsoft 365](https://compliance.microsoft.com/homepage)||

[Microsoft 365 Defender](./overview-security-center.md) in combina le funzionalità di sicurezza dei portali di sicurezza Microsoft esistenti, incluso il Centro sicurezza <https://security.microsoft.com> Office 365 & conformità. Questo centro implementato aiuta i team di sicurezza a proteggere l'organizzazione dalle minacce in modo più efficace.

Se si ha familiarità con il portale Office 365 sicurezza e conformità (protection.office.com), in questo articolo vengono descritte alcune delle modifiche e dei miglioramenti apportati a Microsoft 365 Defender.

Ulteriori informazioni sui vantaggi: [Panoramica di Microsoft 365 Defender](overview-security-center.md)

Se si cercano elementi correlati alla conformità [, visitare il Centro conformità di Microsoft 365](https://compliance.microsoft.com/homepage).

## <a name="new-and-improved-capabilities"></a>Funzionalità nuove e migliorate

La barra di spostamento sinistro, o barra di avvio veloce, ha un aspetto familiare. Tuttavia, sono presenti alcuni elementi nuovi e aggiornati in questo Centro sicurezza.

Con la soluzione Microsoft 365 Defender unificata, è possibile unire i segnali di minaccia e determinare l'ambito completo e l'impatto della minaccia e il modo in cui attualmente influisce sull'organizzazione.

:::image type="content" source="../../media/M365-defender-converge-experience.png" alt-text="Immagine dell Microsoft 365 Defender'esperienza convergente":::

Defender for Office 365 protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione.

:::image type="content" source="../../media/Defender-for-O365.png" alt-text="Immagine di Defender per Office 365":::

### <a name="incidents-and-alerts"></a>Eventi imprevisti e avvisi

Raggruppa la gestione degli eventi imprevisti e degli avvisi in tutta la posta elettronica, i dispositivi e le identità. Gli avvisi sono ora disponibili nel nodo Indagini e offrono una visione generale di un attacco. La pagina di avviso fornisce contesto completo all'avviso, combinando i segnali dell'attacco per realizzare un’indagine dettagliata. In precedenza, gli avvisi erano specifici per diversi carichi di lavoro. Una nuova esperienza unificata ora riunisce una visualizzazione coerente degli avvisi nei diversi carichi di lavoro. È possibile analizzare, investigare e intervenire rapidamente.

- [Altre informazioni sulle indagini](incidents-overview.md)
-  [Altre informazioni sulla gestione degli avvisi](/windows/security/threat-protection/microsoft-defender-atp/review-alerts).

![Barra di avvio veloce Avvisi e azioni](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Ricerca

Cercare proattivamente minacce, software dannosi e attività dannose in endpoint, cassette postali di Office 365 e altro ancora usando [query di ricerca avanzata ](advanced-hunting-overview.md). Queste potenti query possono essere usate per  individuare ed esaminare indicatori di minacce ed entità per le minacce note e potenziali.

[Le regole di rilevamento](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules) personalizzate possono essere create da query di ricerca avanzate che consentono di osservare in modo proattivo gli eventi che potrebbero essere indicativi dell'attività di violazione e dei dispositivi non configurati correttamente.

Ecco un [esempio di ricerca avanzata](advanced-hunting-example.md) in Microsoft Defender per Office 365.  

### <a name="action-center"></a>Centro notifiche

Il centro notifiche mostra le indagini create da funzionalità automatizzate di indagine e risposta. Questo strumento automatizzato e self-healing di Microsoft 365 Defender può aiutare i team addetti alla sicurezza a rispondere automaticamente a eventi specifici.

Altre informazioni sul [Centro notifiche](m365d-action-center.md).

#### <a name="threat-analytics"></a>Analisi delle minacce

Ottenere analisi delle minacce da esperti ricercatori Microsoft in materia di sicurezza. Analisi delle minacce aiuta i team addetti alla sicurezza a essere più efficienti di fronte alle minacce emergenti. Analisi delle minacce comprende:

- Rilevamenti e mitigazioni correlati alla posta elettronica da Microsoft Defender per Office 365. Questa opzione si aggiunge ai dati dell’endpoint già disponibili da Microsoft Defender per endpoint.
- Visualizzazione degli incidenti relativi alle minacce.
- Esperienza migliorata per identificare e usare rapidamente le informazioni interattive nei report.

È possibile accedere all'analisi delle minacce dalla barra di spostamento in alto a sinistra in Microsoft 365 Defender o da una scheda del dashboard dedicata che mostra le minacce principali per l'organizzazione.

Ulteriori informazioni su come tenere [traccia e rispondere alle minacce emergenti con l'analisi delle minacce.](./threat-analytics.md)

### <a name="email--collaboration"></a>Posta elettronica e collaborazione

Tenere traccia delle minacce alla posta elettronica degli utenti e investigare su tali minacce, tenere traccia delle campagne e altro ancora. Se si è usato il Centro sicurezza e conformità di Office 365, questa operazione risulterà familiare.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Il menu di avvio veloce per & collab (o MSDO), a sinistra di Microsoft 365 Defender.":::

#### <a name="email-entity-page"></a>Pagina Entità posta elettronica 

La [pagina entità Posta elettronica](../office-365-security/mdo-email-entity-page.md) *unifica* le informazioni di posta elettronica che erano state sparse in pagine o visualizzazioni diverse in passato. L’analisi delle minacce e delle tendenze nella posta elettronica è *centralizzata*. Le informazioni relative all’intestazione e l'anteprima dei messaggi di posta elettronica sono accessibili tramite la stessa pagina di posta elettronica, insieme ad altre informazioni utili correlate alla posta elettronica. Analogamente, lo stato di detonazione degli URL o degli allegati ai file dannosi è disponibile in una scheda della stessa pagina. La pagina dell'entità E-mail consente ai team di amministratori e ai team addetti alle operazioni di sicurezza di comprendere rapidamente una minaccia per la posta elettronica e il suo stato e quindi di agire rapidamente per determinarne la gestione.

### <a name="access-and-reports"></a>Access e report

Consente di visualizzare report, modificare le impostazioni e i ruoli utente.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Il menu di avvio veloce per Microsoft 365 Defender autorizzazioni e report, sul lato sinistro del Centro sicurezza.":::

> [!NOTE]
> DomainKeys Identified Mail (DKIM) garantisce che i sistemi di posta elettronica di destinazione considera attendibili i messaggi inviati in uscita dal dominio personalizzato.
> Per Defender per Office 365 utenti, ora  è possibile gestire e ruotare le chiavi DKIM tramite Microsoft 365 Defender: o passare a Criteri & Criteri criteri <https://security.microsoft.com/threatpolicy>  \>  \> **DKIM**.
> 
> Per ulteriori informazioni, vedere [Use DKIM to validate outbound email sent from your custom domain](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email).

## <a name="whats-changed"></a>Modifiche

Questa tabella è un riferimento **&** rapido alla gestione delle minacce in cui si sono verificate modifiche tra il Centro sicurezza e conformità e il **portale Microsoft 365 Defender** sicurezza. Fare clic sui collegamenti per altre informazioni su queste aree.

<br>

****

|Area|Descrizione della modifica|
|---|---|
|[Indagine](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-microsoft-365-defender-portal)|Raggruppa le funzionalità AIR in [Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) e [Defender per Endpoint](../defender-endpoint/automated-investigations.md). Con questi aggiornamenti e migliorie, il team addetto alle operazioni di sicurezza potrà visualizzare dettagli sulle indagini automatizzate e le azioni di correzione per tutta la posta elettronica, i contenuti della collaborazione, gli account utente e i dispositivi, il tutto in un'unica posizione.|
|[Coda avvisi](../../compliance/alert-policies.md)|Il **riquadro a comparsa** Visualizza avvisi nel centro sicurezza e conformità Office ora include collegamenti a Microsoft 365 Defender. Fai clic sul **collegamento Apri pagina avviso** e Microsoft 365 Defender apertura. È possibile accedere alla pagina **Visualizza avvisi** facendo clic su qualsiasi avviso di Office 365 nella coda Avvisi.|
|[Formazione sulla simulazione degli attacchi](../office-365-security/attack-simulation-training-insights.md)|Usare la formazione sulla simulazione degli attacchi per scenari di attacchi realistici nell'organizzazione. Questi attacchi simulati possono aiutare a formare il personale prima che un attacco reale sia rivolto all'organizzazione. La formazione sulla simulazione degli attacchi include più opzioni, report avanzati e flussi di formazione migliorati, per semplificare la distribuzione e la gestione degli scenari di simulazione degli attacchi e di formazione.|
|

Nessuna modifica a queste aree:

- [Explorer](../office-365-security/threat-explorer.md)
- [Criteri e regole](../../compliance/alert-policies.md)
- [Campagna](../office-365-security/campaigns.md)
- [Invii ](../office-365-security/admin-submission.md)
- [Verifica](./m365d-action-center.md)
- [Registro minacce](../office-365-security/threat-trackers.md)

Vedere anche la sezione **Informazioni correlate** in fondo all'articolo.

> [!IMPORTANT]
> Il portale Microsoft 365 Defender ( <https://security.microsoft.com> ) combina le funzionalità di sicurezza in , e <https://securitycenter.windows.com> <https://protection.office.com> . Tuttavia, i dati visualizzati dipendono dall'abbonamento. Se si ha Solo Microsoft Defender per Office 365 piano 1 o 2 come abbonamenti autonomi, ad esempio, le funzionalità relative alla sicurezza per gli endpoint e a Defender per i clienti di Office piano 1 non saranno disponibili per elementi come Threat Analytics.

> [!TIP]
> Tutte Exchange Online Protection (EOP) verranno incluse in Microsoft 365 Defender, poiché EOP è un elemento di base di Defender per Office 365.

## <a name="microsoft-365-defender-home-page"></a>Microsoft 365 Defender Home page

La home page del portale contiene importanti informazioni di riepilogo sullo stato di sicurezza dell'Microsoft 365 ambiente.

Con la **Presentazione guidata** è possibile visitare rapidamente le pagine di Endpoint o quelle di posta elettronica e collaborazione. Si noti che ciò che viene visualizzato qui dipenderà dalla licenza di Defender per Office 365 e/o Defender per Endpoint.

È incluso anche un collegamento al **Centro sicurezza e conformità di Office 365** per confronto. L'ultimo collegamento è alla pagina **Novità** che descrive gli aggiornamenti recenti.

## <a name="related-information"></a>Informazioni correlate

- [Reindirizzamento del Centro sicurezza e conformità di Office 365 a Microsoft 365 Defender](microsoft-365-security-mdo-redirection.md)
- [Centro operativo](./m365d-action-center.md)
- [Avvisi posta elettronica e collaborazione](../../compliance/alert-policies.md#default-alert-policies)
- [Regole di rilevamento personalizzate](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Creare una simulazione di attacco di phishing](../office-365-security/attack-simulation-training.md) e [creare un payload per la formazione degli utenti](../office-365-security/attack-simulation-training-payloads.md)
