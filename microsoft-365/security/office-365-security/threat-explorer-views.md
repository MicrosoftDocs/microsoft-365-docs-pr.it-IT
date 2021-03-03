---
title: Visualizzazioni in Esplora minacce e rilevamenti in tempo reale
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni su come usare Esplora minacce e il report sui rilevamenti in tempo reale per analizzare e rispondere alle minacce nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406481"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Visualizzazioni in Esplora minacce e rilevamenti in tempo reale

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


![Esplora minacce](../../media/ThreatExplorerFirstOpened.png)

[Esplora minacce](threat-explorer.md) (e il report sui rilevamenti in tempo reale) è uno strumento potente e quasi in tempo reale che consente ai team delle operazioni di sicurezza di analizzare e rispondere alle minacce nel Centro sicurezza & conformità. Explorer (e il report sui rilevamenti in tempo reale) visualizza informazioni su malware e phish sospetti nella posta elettronica e nei file in Office 365, oltre ad altre minacce e rischi per la sicurezza per l'organizzazione.

- Se si dispone [di Microsoft Defender per Office 365](office-365-atp.md) Piano 2, si dispone di Explorer.
- Se si dispone di Microsoft Defender per Office 365 Piano 1, si dispone di rilevamenti in tempo reale.

Quando si apre Explorer per la prima volta (o il report dei rilevamenti in tempo reale), la visualizzazione predefinita mostra i rilevamenti di malware di posta elettronica negli ultimi 7 giorni. Questo report può anche mostrare i rilevamenti di Microsoft Defender per Office 365, ad esempio URL dannosi rilevati da Collegamenti sicuri [e](atp-safe-links.md)file dannosi rilevati da [Allegati sicuri.](atp-safe-attachments.md) Questo report può essere modificato per visualizzare i dati degli ultimi 30 giorni (con un abbonamento a pagamento a Microsoft Defender per Office 365 P2). Le sottoscrizioni di valutazione includeranno solo i dati degli ultimi sette giorni.

****

|Abbonamento|Utilità|Giorni di dati|
|---|---|---|
|Versione di valutazione di Microsoft Defender per Office 365 P1|Rilevamenti in tempo reale|7 |
|Microsoft Defender per Office 365 P1 a pagamento|Rilevamenti in tempo reale|30|
|Test a pagamento di Microsoft Defender per Office 365 P1 defender per la versione di valutazione di Office 365 P2|Esplora minacce|7 |
|Versione di valutazione di Microsoft Defender per Office 365 P2|Esplora minacce|7 |
|Microsoft Defender per Office 365 P2 a pagamento|Esplora minacce|30|
|

> [!NOTE]
> We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days. Questa modifica viene monitorata come parte della roadmap n. 70544 ed è attualmente in fase di implementazione.

Utilizzare il menu **Visualizza** per modificare le informazioni visualizzate. Le descrizioni comandi consentono di determinare la visualizzazione da usare.

![Menu Visualizzazione Esplora minacce](../../media/ThreatExplorerViewMenu.png)

Dopo aver selezionato una visualizzazione, è possibile applicare filtri e impostare query per eseguire ulteriori analisi. Le sezioni seguenti forniscono una breve panoramica delle varie visualizzazioni disponibili in Esplora risorse (o rilevamenti in tempo reale).

## <a name="email--malware"></a>Malware > posta elettronica

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** malware \> **di posta** \> **elettronica.** Questa visualizzazione mostra informazioni sui messaggi di posta elettronica identificati come contenenti malware.

![Visualizzare i dati relativi ai messaggi di posta elettronica identificati come malware](../../media/ExplorerEmailMalwareMenu.png)

Fare **clic su Mittente** per aprire l'elenco delle opzioni di visualizzazione. Utilizzare questo elenco per visualizzare i dati per mittente, destinatari, dominio del mittente, oggetto, tecnologia di rilevamento, stato di protezione e altro ancora.

Ad esempio, per vedere quali azioni sono state eseguite sui messaggi di posta elettronica rilevati, scegliere **Stato protezione** nell'elenco. Selezionare un'opzione e quindi fare clic sul pulsante Aggiorna per applicare il filtro al report.

![Opzioni relative allo stato di Protezione dalle minacce per Esplora minacce](../../media/ThreatExplorerProtectionStatusOptions.png)

Sotto il grafico, visualizzare ulteriori dettagli su messaggi specifici. Quando si seleziona un elemento nell'elenco, viene visualizzato un riquadro a comparsa in cui sono disponibili ulteriori informazioni sull'elemento selezionato.

![Esplora minacce con riquadro a comparsa aperto](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>Email > Phish

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** \>  \> **e-mail phish.** Questa visualizzazione mostra i messaggi di posta elettronica identificati come tentativi di phishing.

![Visualizzare i dati relativi ai messaggi di posta elettronica identificati come tentativi di phishing](../../media/ThreatExplorerEmailPhish.png)

Fare **clic su Mittente** per aprire l'elenco delle opzioni di visualizzazione. Utilizzare questo elenco per visualizzare i dati in base al mittente, ai destinatari, al dominio del mittente, all'IP del mittente, al dominio URL, al verdetto e altro ancora.

Ad esempio, per vedere quali azioni sono state eseguite quando gli utenti  hanno fatto clic su URL identificati come tentativi di phishing, scegliere Verdetto clic nell'elenco, selezionare una o più opzioni e quindi fare clic sul pulsante Aggiorna.

![Click verdict options for the Phish report](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Sotto il grafico, visualizzare ulteriori dettagli su messaggi specifici, clic su URL, URL e origine della posta elettronica.

![URL rilevati come phish nei messaggi di posta elettronica](../../media/ThreatExplorerEmailPhishURLs.png)

Quando si seleziona un elemento nell'elenco, ad esempio un URL rilevato, viene visualizzato un riquadro a comparsa in cui sono disponibili ulteriori informazioni sull'elemento selezionato.

![Dettagli su un URL rilevato](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>Invii di > posta elettronica

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza invii** \> **di posta** \> **elettronica.** Questa visualizzazione mostra la posta elettronica segnalata dagli utenti come posta indesiderata, non indesiderata o di phishing.

![Messaggi di posta elettronica segnalati dagli utenti](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Fare **clic su Mittente** per aprire l'elenco delle opzioni di visualizzazione. Utilizzare questo elenco per visualizzare le informazioni per mittente, destinatari, tipo di rapporto (la determinazione dell'utente che il messaggio di posta elettronica era indesiderato, non indesiderato o di phish) e altro ancora.

Ad esempio, per visualizzare informazioni sui messaggi di posta elettronica segnalati come tentativi di phishing, fare clic su **Tipo** di rapporto mittente, selezionare Phishing e quindi fare clic \> sul pulsante Aggiorna. 

![Phish selezionato per il filtro Tipo di rapporto](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Sotto il grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, l'indirizzo IP del mittente, l'utente che ha segnalato il messaggio come posta indesiderata, non indesiderata o di phish e altro ancora.

![Messaggi segnalati come tentativi di phishing](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Selezionare un elemento nell'elenco per visualizzare ulteriori dettagli.

## <a name="email--all-email"></a>Posta > tutti i messaggi di posta elettronica

Per visualizzare questo report,  in Esplora risorse scegliere Visualizza tutta \> **la posta** \> **elettronica.** Queste visualizzazioni mostrano una visualizzazione all-up dell'attività di posta elettronica, inclusa la posta elettronica identificata come dannosa a causa di phishing o malware, nonché tutta la posta non dannosa (posta elettronica normale, posta indesiderata e posta inviata in blocco).

> [!NOTE]
> Se viene visualizzato un errore che legge troppi dati da **visualizzare,** aggiungere un filtro e, se necessario, restringere l'intervallo di date visualizzato.

Per applicare un filtro, scegliere **Mittente,** selezionare un elemento nell'elenco e quindi fare clic sul pulsante Aggiorna. In questo esempio abbiamo usato la **tecnologia di rilevamento** come filtro (sono disponibili diverse opzioni). Visualizzare le informazioni in base al mittente, al dominio del mittente, ai destinatari, all'oggetto, al nome del file dell'allegato, alla famiglia di malware, allo stato di protezione (azioni intraprese dalle funzionalità e dai criteri di protezione dalle minacce in Office 365), alla tecnologia di rilevamento (come è stato rilevato il malware) e altro ancora.

![Visualizzare i dati sulla posta elettronica rilevata dalla tecnologia di rilevamento](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Sotto il grafico, visualizzare ulteriori dettagli su messaggi di posta elettronica specifici, ad esempio la riga dell'oggetto, il destinatario, il mittente, lo stato e così via.

## <a name="content--malware"></a>Malware > contenuto

Per visualizzare questo report, in Esplora risorse (o rilevamenti in tempo reale), scegliere **Visualizza** \> **malware** \> **contenuto.** Questa visualizzazione mostra i file identificati come dannosi da [Microsoft Defender per Office 365 in SharePoint Online, OneDrive for Business e Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Visualizzare le informazioni in base alla famiglia di malware, alla tecnologia di rilevamento (come è stato rilevato il malware) e al carico di lavoro (OneDrive, SharePoint o Teams).

![Visualizzare i dati sul malware rilevato](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Sotto il grafico, visualizzare ulteriori dettagli su file specifici, ad esempio nome file allegato, carico di lavoro, dimensioni del file, chi ha modificato il file per ultima e altro ancora.

## <a name="click-to-filter-capabilities"></a>Funzionalità di filtro a clic

Con Esplora risorse (e rilevamenti in tempo reale), puoi applicare un filtro in un clic. Fare clic su un elemento nella legenda e tale elemento diventa un filtro per il report. Si supponga, ad esempio, di guardare la visualizzazione Malware in Esplora risorse:

![Passare a Esplora gestione \> minacce](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Se **si fa clic su Detonazione ATP** in questo grafico, verrà restituita una visualizzazione simile alla seguente:

![Explorer filtrato per visualizzare solo i risultati della detonazione di Defender per Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

In questa visualizzazione sono ora in corso i dati per i file che sono stati detonati dagli [allegati sicuri.](atp-safe-attachments.md) Sotto il grafico è possibile visualizzare i dettagli relativi a messaggi di posta elettronica specifici con allegati rilevati da Allegati sicuri.

![Dettagli specifici sui messaggi di posta elettronica con allegati rilevati](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

La selezione di uno o più elementi attiva il **menu** Azioni, che offre diverse scelte tra cui scegliere per gli elementi selezionati.

![Se si seleziona un elemento, viene attivato il menu Azioni](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

La possibilità di filtrare con un clic e passare a dettagli specifici consente di risparmiare tempo nell'analisi delle minacce.

## <a name="queries-and-filters"></a>Query e filtri

Explorer (oltre al report sui rilevamenti in tempo reale) include diversi potenti filtri e funzionalità di query che consentono di eseguire il drill-down dei dettagli, ad esempio gli utenti di destinazione principali, le principali famiglie di malware, la tecnologia di rilevamento e altro ancora. Ogni tipo di report offre diversi modi per visualizzare ed esplorare i dati.

> [!IMPORTANT]
> Non utilizzare caratteri jolly, ad esempio un asterisco o un punto interrogativo, nella barra delle query per Esplora risorse (o rilevamenti in tempo reale). Quando si esegue  una ricerca nel campo Oggetto per i messaggi di posta elettronica, Explorer (o rilevamenti in tempo reale) esegue una corrispondenza parziale e restituisce risultati simili a una ricerca con caratteri jolly.
