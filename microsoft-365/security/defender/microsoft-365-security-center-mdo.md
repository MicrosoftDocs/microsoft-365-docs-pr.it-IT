---
title: Microsoft Defender per Office 365 nel Centro sicurezza Microsoft 365
description: Informazioni sulle modifiche dal Centro sicurezza Office 365 o il Centro sicurezza e conformità di Office 365.
keywords: Microsoft 365 sicurezza, Introduzione al centro sicurezza Microsoft 365, Microsoft Defender per Office 365, Microsoft Defender for Endpoint, MDO, MDE, riquadro singolo di vetro, nuovo portale di sicurezza, nuovo portale di sicurezza defender
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
ms.openlocfilehash: ec5d22caa52ffaa061637cb8c510a0efaf566b6a
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782898"
---
# <a name="microsoft-defender-for-office-365-in-the-microsoft-365-security-center"></a>Microsoft Defender per Office 365 nel Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

## <a name="quick-reference"></a>Riferimento rapido

L'immagine e la tabella seguente elencano le modifiche nello spostamento tra Office 365 Centro sicurezza & conformità e il Centro sicurezza Microsoft 365 sicurezza.

> [!div class="mx-imgBorder"]
> ![Immagine di ciò che è stato spostato nel punto in cui è stato spostato](../../media/mdo-m3d-security-center.png)

<br>

****

|Office 365 Conformità & sicurezza|Centro sicurezza Microsoft 365|Centro conformità Microsoft 365|Interfaccia di amministrazione di Exchange|
|---|---|---|---|
|Avvisi|Posta elettronica e collaborazione|||
|Classificazione||Vedere [centro Microsoft 365 conformità](https://compliance.microsoft.com/homepage)||
|Prevenzione della perdita dei dati||Vedere [centro Microsoft 365 conformità](https://compliance.microsoft.com/homepage)||
|Gestione dei record||Vedere [centro Microsoft 365 conformità](https://compliance.microsoft.com/homepage) ||
|Governance delle informazioni||Vedere [centro Microsoft 365 conformità](https://compliance.microsoft.com/homepage)||
|Gestione dei rischi|Posta elettronica e collaborazione|||
|Flusso di posta|||Vedere [Exchange di amministrazione](https://admin.exchange.microsoft.com/#/)|
|Privacy dei dati||Vedere [centro Microsoft 365 conformità](https://compliance.microsoft.com/homepage)||
|Ricerca|Ricerca|||
|Report|Report|||
|Garanzia del servizio|Impostazioni|||
|

Il centro sicurezza [Microsoft 365 ](./overview-security-center.md) <https://security.microsoft.com>implementato combina le funzionalità di sicurezza degli attuali portali di sicurezza Microsoft, tra cui Microsoft Defender Security Center e il Centro sicurezza e conformità di Office 365. Questo centro implementato aiuta i team di sicurezza a proteggere l'organizzazione dalle minacce in modo più efficace.

Se si ha familiarità con il portale per la sicurezza e la conformità di Office 365 (protection.office.com), questo articolo descrive alcune modifiche e migliorie apportate al Centro sicurezza e conformità di Microsoft 365.

Altre informazioni sui vantaggi: [Panoramica del Centro sicurezza Microsoft 365r](overview-security-center.md)

Se si cercano elementi correlati alla conformità [, visitare il Centro conformità di Microsoft 365](https://compliance.microsoft.com/homepage).

## <a name="whats-changed"></a>Modifiche

Questa tabella è un riferimento rapido alle aree E-mail e collaborazione in cui è stata apportata una modifica tra il **Centro sicurezza e conformità** e il portale **Sicurezza di Microsoft 365**. Fare clic sui collegamenti per altre informazioni su queste aree.

<br>

****

|Area|Descrizione della modifica|
|---|---|
|[Pagina Entità posta elettronica](../office-365-security/mdo-email-entity-page.md)|Questa pagina **unifica** le informazioni relative alla posta elettronica che in passato erano distribuite in pagine o visualizzazioni diverse. L’analisi delle minacce e delle tendenze nella posta elettronica è *centralizzata*. Le informazioni relative all’intestazione e l'anteprima dei messaggi di posta elettronica sono accessibili tramite la stessa pagina di posta elettronica, insieme ad altre informazioni utili correlate alla posta elettronica. Analogamente, lo stato di detonazione degli URL o degli allegati ai file dannosi è disponibile in una scheda della stessa pagina. La pagina dell'entità E-mail consente ai team di amministratori e ai team addetti alle operazioni di sicurezza di comprendere rapidamente una minaccia per la posta elettronica e il suo stato e quindi di agire rapidamente per determinarne la gestione.|
|[Indagine](../office-365-security/office-365-air.md#changes-are-coming-soon-in-your-security-center)|Raggruppa le funzionalità AIR in [Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) e [Defender per Endpoint](../defender-endpoint/automated-investigations.md). Con questi aggiornamenti e migliorie, il team addetto alle operazioni di sicurezza potrà visualizzare dettagli sulle indagini automatizzate e le azioni di correzione per tutta la posta elettronica, i contenuti della collaborazione, gli account utente e i dispositivi, il tutto in un'unica posizione.|
|[Visualizzazione avviso](../../compliance/alert-policies.md)|Il riquadro a comparsa **Visualizza avvisi** nel Centro sicurezza e conformità di Office ora include collegamenti al Centro sicurezza e conformità di Microsoft 365. Fare clic sul collegamento **Apri pagina avviso** per aprire il Centro sicurezza e conformità di Microsoft 365. È possibile accedere alla pagina **Visualizza avvisi** facendo clic su qualsiasi avviso di Office 365 nella coda Avvisi.|
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
> Il Microsoft 365 security portal ( <https://security.microsoft.com> ) combina le funzionalità di sicurezza in , e <https://securitycenter.windows.com> <https://protection.office.com> . Tuttavia, i dati visualizzati dipendono dall'abbonamento. Se si ha Solo Microsoft Defender per Office 365 piano 1 o 2 come abbonamenti autonomi, ad esempio, le funzionalità relative alla sicurezza per gli endpoint e a Defender per i clienti di Office piano 1 non saranno disponibili per elementi come Threat Analytics.

> [!TIP]
> Tutte Exchange Online Protection (EOP) verranno incluse nel Centro sicurezza Microsoft 365, poiché EOP è un elemento di base di Defender per Office 365.

## <a name="microsoft-365-security-center-home-page"></a>Home page Centro sicurezza Microsoft 365

Viene visualizzata la home page del portale:

- Ratings di Secure Score
- il numero di utenti e dispositivi a rischio
- coda eventi imprevisti attivi
- elenchi delle applicazioni OAuth privilegiate
- dati sull’integrità del dispositivo
- tweet di Microsoft dal feed twitter di Microsoft sull’intelligence sulla sicurezza
- e altre informazioni di riepilogo

Con la **Presentazione guidata** è possibile visitare rapidamente le pagine di Endpoint o quelle di posta elettronica e collaborazione. Si noti che ciò che viene visualizzato qui dipenderà dalla licenza di Defender per Office 365 e/o Defender per Endpoint.

È incluso anche un collegamento al **Centro sicurezza e conformità di Office 365** per confronto. L'ultimo collegamento è alla pagina **Novità** che descrive gli aggiornamenti recenti.

## <a name="improved-capabilities"></a>Funzionalità migliorate

La barra di spostamento sinistro, o barra di avvio veloce, ha un aspetto familiare. Tuttavia, sono presenti alcuni elementi nuovi e aggiornati in questo Centro sicurezza.

### <a name="incidents-and-alerts"></a>Eventi imprevisti e avvisi

Raggruppa la gestione degli eventi imprevisti e degli avvisi in tutta la posta elettronica, i dispositivi e le identità. Gli avvisi sono ora disponibili nel nodo Indagini e offrono una visione generale di un attacco. La pagina di avviso fornisce contesto completo all'avviso, combinando i segnali dell'attacco per realizzare un’indagine dettagliata. In precedenza, gli avvisi erano specifici per diversi carichi di lavoro. Una nuova esperienza unificata ora riunisce una visualizzazione coerente degli avvisi nei diversi carichi di lavoro. È possibile analizzare, investigare e intervenire rapidamente.

- [Altre informazioni sulle indagini](incidents-overview.md)
-  [Altre informazioni sulla gestione degli avvisi](/windows/security/threat-protection/microsoft-defender-atp/review-alerts).

![Barra di avvio veloce Avvisi e azioni](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a>Ricerca

Cercare proattivamente minacce, software dannosi e attività dannose in endpoint, cassette postali di Office 365 e altro ancora usando [query di ricerca avanzata ](advanced-hunting-overview.md). Queste potenti query possono essere usate per  individuare ed esaminare indicatori di minacce ed entità per le minacce note e potenziali.

[Regole di rilevamento personalizzate](/windows/security/threat-protection/microsoft-defender-atp/custom-detection-rules)  possono essere create con query di ricerca avanzate che consentono di controllare proattivamente gli eventi che potrebbero essere indicativi di attività di violazione e dispositivi non correttamente configurati.

### <a name="action-center"></a>Centro notifiche

Il centro notifiche mostra le indagini create da funzionalità automatizzate di indagine e risposta. Questo strumento automatizzato e self-healing di Microsoft 365 Defender può aiutare i team addetti alla sicurezza a rispondere automaticamente a eventi specifici.

[Altre informazioni sul Centro notifiche](m365d-action-center.md)

#### <a name="threat-analytics"></a>Analisi delle minacce

Ottenere analisi delle minacce da esperti ricercatori Microsoft in materia di sicurezza. Analisi delle minacce aiuta i team addetti alla sicurezza a essere più efficienti di fronte alle minacce emergenti. Analisi delle minacce comprende:

- Rilevamenti e mitigazioni correlati alla posta elettronica da Microsoft Defender per Office 365. Questa opzione si aggiunge ai dati dell’endpoint già disponibili da Microsoft Defender per endpoint.
- Visualizzazione degli incidenti relativi alle minacce.
- Esperienza migliorata per identificare e usare rapidamente le informazioni interattive nei report.
È possibile accedere ad Analisi delle minacce dalla barra di spostamento superiore sinistra del Centro sicurezza Microsoft 365 o da una scheda del dashboard dedicata che mostra le principali minacce per l'organizzazione.

Altre informazioni su come [tenere traccia e rispondere alle minacce emergenti con analisi delle minacce](./threat-analytics.md)

### <a name="email--collaboration"></a>Posta elettronica e collaborazione

Tenere traccia delle minacce alla posta elettronica degli utenti e investigare su tali minacce, tenere traccia delle campagne e altro ancora. Se si è usato il Centro sicurezza e conformità di Office 365, questa operazione risulterà familiare.

:::image type="content" source="../../media/converge-3-email-and-collab-new.png" alt-text="Menu di avvio veloce per posta elettronica e collaborazione (o MSDO), sul lato sinistro del Centro sicurezza e conformità di Microsoft 365.":::

### <a name="access-and-reports"></a>Access e report

Consente di visualizzare report, modificare le impostazioni e i ruoli utente.

:::image type="content" source="../../media/converge-4-access-and-reporting-new.png" alt-text="Menu avvio veloce per le autorizzazioni e la creazione di report del Centro sicurezza e protezione di Microsoft 365, sul lato sinistro del centro sicurezza.":::

> [!NOTE]
> Per Defender per gli utenti Office 365,  ora è possibile gestire e ruotare le chiavi DKIM (DomainKeys Identified Mail) tramite il Centro sicurezza Microsoft 365: oppure passare a Criteri & Regole <https://security.microsoft.com/threatpolicy>  \> **Criteri** \> **DKIM**.

## <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Esempio di rilevazione avanzata per Microsoft Defender per Office 365

Iniziare a cercare le minacce tramite posta elettronica con la ricerca avanzata? Provare quanto segue:

La [guida introduttiva](/microsoft-365/security/office-365-security/defender-for-office-365.md#getting-started) dell'articolo [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) include blocchi di configurazione iniziali logici simili ai seguenti:

1. Configura tutto con "Anti" nel nome.
   - Antimalware
   - Anti-phishing
   - Protezione da posta indesiderata
2. Configura tutto con "Sicuro" nel nome.
   - Collegamenti sicuri
   - Allegati sicuri
3. Difendere i carichi di lavoro (ad esempio SharePoint Online, OneDrive e Teams).
4. Proteggi con eliminazione automatica a zero ore.

Oltre a un [collegamento](../office-365-security/protect-against-threats.md) per iniziare subito a eseguire la configurazione il primo giorno.

L'ultimo passaggio in **guida introduttiva** consiste nella protezione degli utenti con la **Zero-Hour Auto Purge**, anche nota come ZAP. Sapere se i provvedimenti per rimuovere con ZAP un messaggio sospetto o pericoloso dopo il recapito hanno avuto successo è molto importante.

Il passaggio rapido al linguaggio di query Kusto per rilevare problemi è un vantaggio derivante dalla convergenza di questi due centri sicurezza. I team di sicurezza possono monitorare i mancati problemi zap facendo i loro passi successivi [qui,](https://security.microsoft.com/advanced-hunting)sotto **Ricerca** \> **avanzata**.

1. Nella pagina Rilevazione avanzata fare clic su Query.
1. Copiare la query seguente nella finestra Query.
1. Selezionare Esegui query.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="La pagina Ricerca avanzata (in Ricerca) con query selezionata nella parte superiore del pannello di query ed esecuzione di una query Kusto per acquisire le azioni ZAP negli ultimi 7 giorni.":::

I dati di questa query verranno visualizzati nel pannello Risultati sotto la query stessa. I risultati includono informazioni come 'DeviceName', 'AccountDisplayName' e 'ZapTime' in un set di risultati personalizzabile. È anche possibile esportare i risultati per i record. Se la query è di nuovo necessaria, selezionare **Salva** > **Salva con nome** e aggiungere la query all'elenco di query, condivise o della community.

## <a name="related-information"></a>Informazioni correlate

- [Defender per Office 365 nel Centro sicurezza Microsoft 365](microsoft-365-security-center-mdo.md)
- [Centro operativo](./m365d-action-center.md)
- [Avvisi posta elettronica e collaborazione](../../compliance/alert-policies.md#default-alert-policies)
- [Cercare minacce tra dispositivi, posta elettronica, app e identità](./advanced-hunting-query-emails-devices.md)
- [Regole di rilevamento personalizzate](/microsoft-365/security/defender-endpoint/custom-detection-rules)
- [Creare una simulazione di attacco di phishing](../office-365-security/attack-simulation-training.md) e [creare un payload per la formazione degli utenti](../office-365-security/attack-simulation-training-payloads.md)
