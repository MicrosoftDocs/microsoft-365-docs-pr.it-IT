---
title: Sicurezza di Office 365
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
- microsoft-365-docs-pr
description: Sicurezza in Office 365, da EOP a ATP piani 1 e 2, configurazioni di sicurezza standard e rigorose e altro ancora, in modo da poter capire cosa si ha e come proteggere le proprietà.
ms.openlocfilehash: 680066f58850f59523ae6fb8a8168459dd813fc1
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304847"
---
# <a name="office-365-security-outline"></a>Struttura di protezione di Office 365

In questo articolo vengono presentate le nuove proprietà di sicurezza nel cloud. Se si è parte di un centro operazioni di sicurezza, si è un amministratore della sicurezza nuovo nello spazio o si desidera un aggiornamento, è possibile iniziare.

> [!CAUTION]
> Hi. Se si utilizza **Outlook.com**, **Microsoft 365 Family**o **Microsoft 365 Personal**e sono necessari *collegamenti sicuri* o informazioni sugli *allegati sicuri* , ***fare clic su questo collegamento***: [Advanced Outlook.com Security for Microsoft 365 subscribers](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2). Ringrazia!

## <a name="office-365-security-spelled-out"></a>Sicurezza di Office 365 dispitata

Ogni abbonamento a Office 365 è dotato di funzionalità di sicurezza. Gli obiettivi e le azioni che è possibile intraprendere dipendono dallo stato attivo di questi diversi abbonamenti. Nella sicurezza di Office 365, esistono tre servizi di sicurezza principali (o prodotti) associati al tipo di sottoscrizione:

1. Exchange Online Protection (EOP)
1. Protezione avanzata dalle minacce, piano 1 (ATP P1)
1. Protezione avanzata dalle minacce, piano 2 (ATP P2)

> [!NOTE]
> Se l'abbonamento è stato acquistato e è necessario implementare le funzionalità di sicurezza in *questo momento*, passare alla procedura descritta nell'articolo [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide) . Se si è nuovi nell'abbonamento e si desidera conoscere la propria licenza prima di iniziare, consultare fatturazione > i prodotti nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

La sicurezza di Office 365 si basa sulle protezioni di base offerte da EOP. EOP è presente in tutti gli abbonamenti in cui è possibile trovare le cassette postali di Exchange Online (ricorda, tutti i prodotti di sicurezza descritti in questo articolo sono basati su cloud).

È possibile che si sia abituati a vedere questi tre componenti descritti in questo modo:

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|Impedisce attacchi noti di ampie dimensioni, basati su volume.    |  Protegge la posta elettronica e la collaborazione dal compromesso di posta elettronica di malware, phishing e business di zero-day.       | Aggiunge indagini, attività di ricerca e risposta successive alla violazione, nonché automazione e simulazione (per la formazione).         |

Tuttavia, in termini di architettura, è possibile iniziare a pensare a ciascun brano come livelli cumulativi di sicurezza, ognuno con enfasi sulla sicurezza. Altre informazioni, ad esempio:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_EOPandATPGraphic.png" alt-text="Placeholder graphic":::

Anche se ognuno di questi servizi enfatizza un obiettivo specifico tra la protezione, il rilevamento, l'analisi e la risposta, ***tutti*** i servizi possono svolgere gli obiettivi della protezione, del rilevamento ***, dell'analisi*** e della risposta.

La sicurezza di Office 365 è la protezione di EOP. ATP P1 contiene EOP. ATP P2 contiene P1 e EOP. La struttura è cumulativa. Questo è il motivo per cui, quando si configura ATP, è consigliabile iniziare con EOP e lavorare con i layer.

Anche se la configurazione di autenticazione della posta elettronica avviene in DNS pubblico, è importante configurare questa funzionalità per contribuire a difendersi dallo spoofing. *Se si dispone di EOP,* ***è consigliabile [configurare l'autenticazione della posta elettronica](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication?view=o365-worldwide)***.

Se si dispone di un Office 365 E3 o di seguito, si dispone di EOP, ma con l'opzione di acquistare autonomo ATP P1 tramite l'aggiornamento. Se si dispone di Office 365 E5, si dispone già del trifosfato di adenosina P2.

> [!TIP]
> Se l'abbonamento non è Office 365 E3 o E5, è comunque possibile controllare se si ha la possibilità di eseguire l'aggiornamento a ATP P1. Se si è interessati, [Questa pagina Web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) elenca gli abbonamenti idonei per l'aggiornamento ATP P1 (verificare la fine della pagina per la stampa in fine).

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>Scala di sicurezza di Office 365 da EOP a ATP

:::image type="content" source="../../media/tp_EOPATPEmailAuth4.gif" alt-text="Placeholder graphic":::

> [!IMPORTANT]
> Informazioni dettagliate su queste pagine: [Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-worldwide)e [Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide).

Ciò che rende l'aggiunta di piani ATP un vantaggio alla gestione delle minacce EOP pura può essere difficile da distinguere a prima vista. Per facilitare l'ordinamento se un percorso di aggiornamento è appropriato per la propria organizzazione, esaminare le funzionalità di ogni prodotto quando si tratta di:

 - prevenzione e rilevamento di minacce
 - indagando
 - risponde

a partire da **Exchange Online Protection**:
<p>

|Impedisci/rileva  |Investigare  |Risposta  |
|---------|---------|---------|
| Le tecnologie includono:<ul><li>posta indesiderata</li><li>phishing</li><li>malware</li><li>posta in blocco</li><li>Intelligence contraffatta</li><li>rilevamento della rappresentazione</li><li>Quarantena dell'amministratore</li><li>Invii di amministratori e utenti di falsi positivi e falsi negativi</li><li>Consenti/blocca per URL e file</li><li>Report</li></u1>|<li>Ricerca dei log di controllo</li><li>Traccia dei messaggi</li>|<li>Zero-hour auto-Purge (ZAP)</li><li>Perfezionamento e verifica degli elenchi Consenti e blocca</li>|

Se si vuole scavare in EOP, **[passare a questo articolo](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)**.

Poiché questi prodotti sono cumulativi, se si valuta ATP P1 e si decide di sottoscriverlo, verranno aggiunte queste abilità.

Guadagni con **Advanced Threat Protection, piano 1** (fino a oggi):
<p>

|Impedisci/rileva  |Investigare  |Risposta  |
|---------|---------|---------|
| Le tecnologie includono tutto in EOP Plus:<u1><li>Allegati sicuri</li><li>Collegamenti sicuri<li>Protezione ATP per i carichi di lavoro (es. SharePoint Online, teams, OneDrive for business)</li><li>Protezione del tempo di clic nei messaggi di posta elettronica, nei client di Office e nei team</li><li>Anti-phishing ATP</li><li>Protezione della rappresentazione dell'utente e del dominio</li><li>Avvisi e API di integrazione di SIEM per gli avvisi</li>|<li>API di integrazione di SIEM per i rilevamenti</li><li>**Strumento di rilevamento in tempo reale**</li><li>Traccia URL</li>|<li>Stesso</li></u1>

In questo modo, il trifosfato di adenosina P1 si espande sul fianco di ***prevenzione*** della casa e aggiunge ulteriori forme di ***rilevamento***.

ATP P1 aggiunge anche **rilevamenti in tempo reale** per le indagini. Il nome di questo strumento di ricerca di minacce è in grassetto perché è chiaro che è possibile *sapere* di avere ATP P1. Non viene visualizzato in ATP P2.

Guadagni con **Advanced Threat Protection, piano 2** (fino a oggi):
<p>

|Impedisci/rileva  |Investigare  |Risposta  |
|---------|---------|---------|
| Le tecnologie includono tutto in EOP e ATP P1 Plus:<u1><li>Stesso</li>|<li>**Esplora minacce**</li><li>Tracker delle minacce</li><li>Visualizzazioni della campagna</li>|<li>Indagine automatizzata e risposta (aria)</li><li>ARIA da Esplora minacce</li><li>ARIA per utenti compromessi</li><li>API SIEM Integration per indagini automatizzate</li>

In questo modo, il trifosfato di adenosina P2 si espande sul fianco di ***indagine e risposta*** della casa e aggiunge una nuova forza di caccia. Automazione.

In ATP P2, lo strumento di caccia principale è denominato **Esplora minacce** anziché i rilevamenti in tempo reale. Se si visualizza Esplora minacce quando si accede al centro sicurezza, si è in ATP P2.

Per accedere ai dettagli di ATP P1 e P2, **[passare a questo articolo](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)**.

> [!TIP]
> EOP e ATP sono diversi anche quando si tratta di utenti finali. In EOP e ATP P1, lo stato attivo è la *consapevolezza*e quindi questi due servizi includono il *componente aggiuntivo di Outlook messaggio di report in* modo che gli utenti possano segnalare messaggi di posta elettronica sospetti, per un'ulteriore analisi. <p> In ATP P2 (che contiene tutto in EOP e P1), lo stato attivo si sposta su un *ulteriore allenamento* per gli utenti finali e quindi il centro operazioni di sicurezza ha accesso a un potente strumento di *simulazione di minacce* e alle metriche degli utenti finali che fornisce.

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP piano 1 vs piano 2 Cheat Sheet

Questo riferimento rapido consentirà di comprendere quali funzionalità vengono fornite con ogni sottoscrizione ATP. In combinazione con la conoscenza delle funzionalità di EOP, può essere utile per i decisori aziendali determinare cosa è meglio per le proprie esigenze.

|Office 365 ATP Piano 1|Office 365 ATP Piano 2|
|---|---|
|<br/>Funzionalità di configurazione, protezione e rilevamento: <ul><li>[Allegati sicuri](atp-safe-attachments.md)</li><li>[Collegamenti sicuri](atp-safe-links.md)</li><li>[ATP per SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protezione anti-phishing ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Rilevamenti in tempo reale](threat-explorer.md)</li></ul>|Funzionalità di Office 365 ATP Piano 1<br/>--- più ---<br/>Funzionalità di automazione, analisi, correzione e formazione:</li><li>[Tracker delle minacce](threat-trackers.md)</li><li>[Esplora minacce](threat-explorer.md)</li><li>[Analisi e risposta automatizzate](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Simulatore di attacchi](attack-simulator.md)</li></ul>|
|

- Office 365 ATP Piano 2 è incluso in Office 365 E5, Office 365 A5 e Microsoft 365 E5.

- Office 365 ATP Piano 1 è incluso in Microsoft 365 Business Premium.

- Office 365 ATP Piano 1 e Office 365 ATP Piano 2 sono disponibili come componenti aggiuntivi per alcuni abbonamenti. Per ulteriori informazioni, vedere la disponibilità di un altro collegamento [tra i piani ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La caratteristica [Documenti sicuri](safe-docs.md) è disponibile solo per gli utenti che dispongono di licenze Microsoft 365 E5 o Microsoft 365 E5 Security (non incluse nei piani di Office 365 ATP).

- Se l'abbonamento corrente non include Office 365 ATP e lo si desidera, [contattare Sales per avviare una versione di valutazione](https://go.microsoft.com/fwlink/p/?LinkId=518644)e scoprire in che modo è possibile utilizzare ATP nell'organizzazione.

> [!TIP]
> ***Suggerimento Insider***. È possibile utilizzare il sommario di docs.microsoft.com per informazioni su EOP e ATP. Accedere a articoli di [sicurezza di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap?view=o365-worldwide) e si noterà che l'organizzazione Sommario inizia con la valutazione e la distribuzione (inclusa la migrazione) e quindi continua con la prevenzione, il rilevamento, l'analisi e la risposta. <p> Questa struttura è divisa in modo che gli argomenti di **amministrazione della sicurezza** siano seguiti da argomenti relativi alle **operazioni di sicurezza** . Se si è un nuovo membro di entrambi i ruoli del processo, utilizzare il collegamento in questo suggerimento e la conoscenza del sommario per facilitare l'apprendimento dello spazio. Ricordarsi di usare i *collegamenti di feedback* e *gli articoli rate* Man mano che si passa. I commenti e suggerimenti ci aiutano a migliorare ciò che offriamo.
