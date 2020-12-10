---
title: Sicurezza di Office 365, Microsoft Defender per Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Sicurezza in Office 365, da EOP a Defender per Office 365 piani 1 e 2, configurazioni di sicurezza standard e rigorose e altro ancora. Informazioni su ciò che si ha e su come proteggere le proprietà.
ms.openlocfilehash: 84d7dcfc68ce78bfde92f3d7096cd4104355ce94
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616249"
---
# <a name="office-365-security-overview"></a>Panoramica della sicurezza di Office 365

In questo articolo vengono presentate le nuove proprietà di sicurezza nel cloud. Se si è parte di un centro operazioni di sicurezza, si è un amministratore della sicurezza nuovo nello spazio o si desidera un aggiornamento, è possibile iniziare.

> [!CAUTION]
> Se si utilizza **Outlook.com**, **Microsoft 365 Family** o **Microsoft 365 Personal** e sono necessari *collegamenti sicuri* o informazioni sugli *allegati sicuri* , ***fare clic su questo collegamento** _: [Advanced Outlook.com Security per i sottoscrittori di Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Sicurezza di Office 365 dispitata

Ogni abbonamento a Office 365 è dotato di funzionalità di sicurezza. Gli obiettivi e le azioni che è possibile intraprendere dipendono dallo stato attivo di questi diversi abbonamenti. Nella sicurezza di Office 365, esistono tre servizi di sicurezza principali (o prodotti) associati al tipo di sottoscrizione:

1. Exchange Online Protection (EOP)
1. Microsoft Defender per Office 365 piano 1 (Defender per Office P1)
1. Microsoft Defender per Office 365 piano 2 (Defender per Office P2)

> [!NOTE]
> Se l'abbonamento è stato acquistato e è necessario implementare le funzionalità di sicurezza _right ora *, passare alla procedura descritta nell'articolo [Protect Against Threats](protect-against-threats.md) . Se si è nuovi nell'abbonamento e si desidera conoscere la propria licenza prima di iniziare, consultare fatturazione > i prodotti nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

La sicurezza di Office 365 si basa sulle protezioni di base offerte da EOP. EOP è presente in tutti gli abbonamenti in cui è possibile trovare le cassette postali di Exchange Online (ricorda, tutti i prodotti di sicurezza descritti in questo articolo sono basati su cloud).

È possibile che si sia abituati a vedere questi tre componenti descritti in questo modo:

|EOP|Microsoft Defender per Office 365 P1|Microsoft Defender per Office 365 P2|
|---|---|---|
|Impedisce attacchi noti di ampie dimensioni, basati su volume.|Protegge la posta elettronica e la collaborazione dal compromesso di posta elettronica di malware, phishing e business di zero-day.|Aggiunge indagini, attività di ricerca e risposta successive alla violazione, nonché automazione e simulazione (per la formazione).|
|

Tuttavia, in termini di architettura, è possibile iniziare a pensare a ciascun brano come livelli cumulativi di sicurezza, ognuno con enfasi sulla sicurezza. Altre informazioni, ad esempio:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP e Microsoft Defender per Office 365 e le loro relazioni tra loro con enfasi sul servizio, inclusa una nota per l'autenticazione della posta elettronica.":::

Anche se ognuno di questi servizi enfatizza un obiettivo tra la protezione, il rilevamento, l'analisi e la risposta, ***tutti** i servizi possono svolgere gli obiettivi della protezione, del rilevamento _*_, dell'analisi_*_ e della risposta.

La sicurezza di Office 365 è la protezione di EOP. Microsoft Defender per Office 365 P1 contiene EOP. Il difensore per Office 365 P2 contiene P1 e EOP. La struttura è cumulativa. Per questo motivo, quando si configura questo prodotto, è consigliabile iniziare con EOP e collaborare con Defender per Office 365.

Anche se la configurazione di autenticazione della posta elettronica avviene in DNS pubblico, è importante configurare questa funzionalità per contribuire a difendersi dallo spoofing. _Se si dispone di EOP, * ***è necessario [configurare l'autenticazione della posta elettronica](email-validation-and-authentication.md)**_.

Se si dispone di un Office 365 E3 o di seguito, si dispone di EOP, ma con l'opzione di acquistare Defender autonomo per Office 365 P1 tramite l'aggiornamento. Se si dispone di Office 365 E5, si dispone già del difensore per Office 365 P2.

> [!TIP]
> Se l'abbonamento non è Office 365 E3 o E5, è comunque possibile controllare se si ha la possibilità di eseguire l'aggiornamento a Microsoft Defender per Office 365 P1. Se si è interessati, [Questa pagina Web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) elenca gli abbonamenti idonei per l'aggiornamento a Microsoft Defender per Office 365 P1 (verificare la fine della pagina per la stampa in fine).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>La scala di sicurezza di Office 365 da EOP a Microsoft Defender per Office 365

![EOP e Microsoft Defender per Office 365 e la loro enfasi sulla sicurezza, che vanno da proteggere e rilevare per indagare e rispondere. La configurazione di autenticazione della posta elettronica (almeno DKIM e DMARC) deve essere configurata per EOP e verso l'alto.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Informazioni dettagliate su queste pagine: [Exchange Online Protection](exchange-online-protection-overview.md)e [Defender per Office 365](office-365-atp.md).

Ciò che rende l'aggiunta di Microsoft Defender per Office 365 prevede un vantaggio per la gestione delle minacce di EOP pura può essere difficile da distinguere a prima vista. Per facilitare l'ordinamento se un percorso di aggiornamento è appropriato per la propria organizzazione, esaminare le funzionalità di ogni prodotto quando si tratta di:

- prevenzione e rilevamento di minacce
- indagando
- risponde

a partire da _ * Exchange Online Protection * *:
<p>

|Impedisci/rileva|Investigare|Risposta|
|---|---|---|
|Le tecnologie includono:<ul><li>posta indesiderata</li><li>phishing</li><li>malware</li><li>posta in blocco</li><li>Intelligence contraffatta</li><li>rilevamento della rappresentazione</li><li>Quarantena dell'amministratore</li><li>Invii di amministratori e utenti di falsi positivi e falsi negativi</li><li>Consenti/blocca per URL e file</li><li>Report</li></u1>|<li>Ricerca dei log di controllo</li><li>Traccia dei messaggi</li>|<li>Zero-hour auto-Purge (ZAP)</li><li>Perfezionamento e verifica degli elenchi Consenti e blocca</li>|
|

Se si vuole scavare in EOP, **[passare a questo articolo](exchange-online-protection-overview.md)**.

Poiché questi prodotti sono cumulativi, se si valuta Microsoft Defender per Office 365 P1 e si decide di sottoscriverlo, verranno aggiunte queste abilità.

Guadagni con il **difensore per Office 365, piano 1** (fino a oggi):
<p>

|Impedisci/rileva|Investigare|Risposta|
|---|---|---|
|Le tecnologie includono tutto in EOP Plus:<u1><li>Allegati sicuri</li><li>Collegamenti sicuri<li>Microsoft Defender per Office 365 protezione dei carichi di lavoro (es. SharePoint Online, teams, OneDrive for business)</li><li>Protezione del tempo di clic nei messaggi di posta elettronica, nei client di Office e nei team</li><li>anti-phishing in Defender per Office 365</li><li>Protezione della rappresentazione dell'utente e del dominio</li><li>Avvisi e API di integrazione di SIEM per gli avvisi</li>|<li>API di integrazione di SIEM per i rilevamenti</li><li>**Strumento di rilevamento in tempo reale**</li><li>Traccia URL</li>|<li>Stesso</li></u1>

In questo modo, Microsoft Defender per Office 365 P1 si espande sul fianco **_Prevention_* _ della casa e aggiunge ulteriori forme di _*_rilevamento_*_.

Microsoft Defender per Office 365 P1 aggiunge anche _ *rilevamenti in tempo reale** per le indagini. Il nome di questo strumento di ricerca di minacce è in grassetto perché è chiaro che è possibile *conoscere* il difensore per Office 365 P1. Non viene visualizzato in Defender per Office 365 P2.

Guadagni con **Defender per Office 365, piano 2** (fino a oggi):
<p>

|Impedisci/rileva|Investigare|Risposta|
|---|---|---|
|Le tecnologie includono tutto in EOP e Microsoft Defender per Office 365 P1 Plus:<u1><li>Stesso</li>|<li>**Esplora minacce**</li><li>Tracker delle minacce</li><li>Visualizzazioni della campagna</li>|<li>Indagine automatizzata e risposta (aria)</li><li>ARIA da Esplora minacce</li><li>ARIA per utenti compromessi</li><li>API SIEM Integration per indagini automatizzate</li>

In questo modo, Microsoft Defender per Office 365 P2 si espande sul fianco **_Investigation e Response_* _ della casa e aggiunge una nuova forza di caccia. Automazione.

In Microsoft Defender per Office 365 P2, lo strumento di caccia principale è denominato _ *Threat Explorer** invece di rilevamenti in tempo reale. Se si visualizza Esplora minacce quando si accede al centro sicurezza, si è in Microsoft Defender per Office 365 P2.

Per accedere ai dettagli di Microsoft Defender per Office 365 P1 e P2, **[passare a questo articolo](office-365-atp.md)**.

> [!TIP]
> EOP e Microsoft Defender per Office 365 sono diversi anche quando si tratta di utenti finali. In EOP e Defender per Office 365 P1, lo stato attivo è la *consapevolezza* e quindi questi due servizi includono il *componente aggiuntivo di Outlook messaggio di report in* modo che gli utenti possano segnalare messaggi di posta elettronica sospetti, per un'ulteriore analisi. <p> In Defender per Office 365 P2 (che contiene tutto in EOP e P1), lo stato attivo si sposta su un *ulteriore allenamento* per gli utenti finali e quindi il centro operazioni di sicurezza ha accesso a un potente strumento di *simulazione di minacce* e alle metriche degli utenti finali che fornisce.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender per Office 365 piano 1 vs piano 2 Cheat Sheet

Questo rapido riferimento consentirà di comprendere quali funzionalità vengono fornite con ogni sottoscrizione di Microsoft Defender per Office 365. In combinazione con la conoscenza delle funzionalità di EOP, può essere di aiuto ai decisori aziendali di determinare ciò che Microsoft Defender per Office 365 è migliore per le proprie esigenze.

|Difensore per Office 365 piano 1|Difensore per Office 365 piano 2|
|---|---|
|Funzionalità di configurazione, protezione e rilevamento: <ul><li>[Allegati sicuri](atp-safe-attachments.md)</li><li>[Collegamenti sicuri](atp-safe-links.md)</li><li>[ATP per SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protezione anti-phishing in Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Rilevamenti in tempo reale](threat-explorer.md)</li></ul>|Protezione per le funzionalità di Office 365 piano 1 <p> --- più --- <p> Funzionalità di automazione, analisi, correzione e formazione: <ul><li>[Tracker delle minacce](threat-trackers.md)</li><li>[Esplora minacce](threat-explorer.md)</li><li>[Analisi e risposta automatizzate](office-365-air.md)</li><li>[Simulatore di attacchi](attack-simulator.md)</li></ul>|
|

- Microsoft Defender per Office 365 piano 2 è incluso in Office 365 E5, Office 365 a5 e Microsoft 365 E5.

- Microsoft Defender per Office 365 piano 1 è incluso in Microsoft 365 Business Premium.

- Microsoft Defender per Office 365 piano 1 e Defender per Office 365 piano 2 sono disponibili come componente aggiuntivo per alcuni abbonamenti. Per ulteriori informazioni, vedere la disponibilità di un'altra funzionalità di collegamento [tra Microsoft Defender per Office 365 piani](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La funzionalità [documenti attendibili](safe-docs.md) è disponibile solo per gli utenti che dispongono delle licenze di sicurezza Microsoft 365 E5 o Microsoft 365 E5 (non incluse nei piani Microsoft Defender per Office 365).

- Se l'abbonamento corrente non include Microsoft Defender per Office 365 e lo si desidera, [contattare Sales per avviare una versione di valutazione](https://go.microsoft.com/fwlink/p/?LinkId=518644)e scoprire in che modo Microsoft Defender per Office 365 può funzionare nell'organizzazione.

> [!TIP]
> ***Suggerimento di insider** _. È possibile utilizzare il sommario di docs.microsoft.com per informazioni su EOP e Microsoft Defender per Office 365. Tornare a questa pagina, [Office 365 Security Overview](https://docs.microsoft.com/microsoft-365/security/office-365-security)e si noterà che l'organizzazione Sommario nella barra laterale. Inizia con la distribuzione (inclusa la migrazione) e quindi continua con la prevenzione, il rilevamento, l'analisi e la risposta. <p> Questa struttura è divisa in modo che gli argomenti _ *Security Administration** siano seguiti da argomenti relativi alle **operazioni di sicurezza** . Se si è un nuovo membro di entrambi i ruoli del processo, utilizzare il collegamento in questo suggerimento e la conoscenza del sommario per facilitare l'apprendimento dello spazio. Ricordarsi di usare i *collegamenti di feedback* e *gli articoli rate* Man mano che si passa. I commenti e suggerimenti ci aiutano a migliorare ciò che offriamo.

## <a name="where-to-go-next"></a>Dove andare dopo

Se si è un amministratore della sicurezza, potrebbe essere necessario configurare DKIM o DMARC per la posta elettronica. È possibile che si desideri eseguire il rollforward dei preset di sicurezza ' strict ' per gli utenti prioritari o per individuare le novità del prodotto. In alternativa, se si dispone di operazioni di sicurezza, è possibile utilizzare i rilevamenti in tempo reale o l'esploratore delle minacce per esaminare e rispondere oppure per eseguire il rilevamento degli utenti finali con simulatore di attacco. In entrambi i casi, ecco alcuni suggerimenti aggiuntivi su cosa guardare al prossimo.

[Autenticazione della posta elettronica, inclusi SPF, DKIM e DMARC (con collegamenti all'installazione di tutti e tre)](email-validation-and-authentication.md)

[Per configurare i criteri di sicurezza in modo rapido](preset-security-policies.md) , [vedere il file di configurazione ' Golden ' consigliato](recommended-settings-for-eop-and-office365-atp.md) e utilizzare le impostazioni predefinite consigliate.

Recuperare le [novità di Microsoft Defender per Office 365 (inclusi gli sviluppi di EOP)](whats-new-in-office-365-atp.md)

[Utilizzare Esplora minacce o rilevamenti in tempo reale](threat-explorer.md)

Usare [simulatore di attacco in Microsoft Defender per Office 365](attack-simulator.md)
