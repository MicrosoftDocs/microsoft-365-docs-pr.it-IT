---
title: Sicurezza di Office 365, Microsoft Defender per Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Sicurezza in Office 365, da EOP a Defender per Office 365 Piani 1 e 2, standard e rigide configurazioni di sicurezza e altro ancora. Comprendere cosa si ha e come proteggere le proprietà.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711941"
---
# <a name="office-365-security-overview"></a>Panoramica della sicurezza di Office 365

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)


Questo articolo ti introdurrà alle nuove proprietà di sicurezza nel cloud. Sia che si fa parte di un Centro operativo per la sicurezza, che si sia un amministratore della sicurezza nuovo nello spazio o che si desideri un aggiornamento, è possibile iniziare.

> [!CAUTION]
> Se si usa **Outlook.com,** Microsoft **365 Family** o Microsoft **365 Personal** e  sono necessarie informazioni su Collegamenti sicuri o Allegati sicuri, fare clic su questo ***collegamento:*** Sicurezza avanzata Outlook.com per gli abbonati [a Microsoft 365.](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2) 

## <a name="office-365-security-spelled-out"></a>Sicurezza di Office 365

Ogni abbonamento a Office 365 include funzionalità di sicurezza. Gli obiettivi e le azioni che è possibile intraprendere dipendono dall'attenzione di queste diverse sottoscrizioni. Nella sicurezza di Office 365 sono disponibili tre principali servizi di sicurezza (o prodotti) legati al tipo di abbonamento:

1. Exchange Online Protection (EOP)
1. Microsoft Defender per Office 365 Piano 1 (Defender per Office P1)
1. Microsoft Defender per Office 365 Piano 2 (Defender per Office P2)

> [!NOTE]
> Se l'abbonamento è stato acquistato ed è necessario implementare le funzionalità di sicurezza in questo *momento,* passare alla procedura descritta nell'articolo [Protezione dalle](protect-against-threats.md) minacce. Se non si ha una nuova sottoscrizione e si vuole conoscere la licenza prima di iniziare, consultare Fatturazione > Prodotti nell'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/AdminPortal/#/homepage)

La sicurezza di Office 365 si basa sulle protezioni principali offerte da EOP. EOP è presente in qualsiasi sottoscrizione in cui è possibile trovare le cassette postali di Exchange Online (tenere presente che tutti i prodotti di sicurezza qui descritti sono basati sul cloud).

Potresti essere abituato a vedere questi tre componenti descritti in questo modo:

|EOP|Microsoft Defender per Office 365 P1|Microsoft Defender per Office 365 P2|
|---|---|---|
|Impedisce attacchi noti ampi, basati su volume.|Protegge la posta elettronica e la collaborazione da malware zero-day, phish e compromissione della posta elettronica aziendale.|Aggiunge analisi, ricerca e risposta post-violazione, nonché automazione e simulazione (per la formazione).|
|

Tuttavia, in termini di architettura, iniziamo a pensare a ogni elemento come a livelli cumulativi di sicurezza, ognuno con un'attenzione particolare alla sicurezza. Più simile al seguente:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP e Microsoft Defender per Office 365 e le loro relazioni tra loro con particolare attenzione al servizio, inclusa una nota per l'autenticazione della posta elettronica.":::

Anche se ognuno di questi servizi sottolinea l'obiettivo di proteggere, rilevare, analizzare e rispondere, ***tutti** _ i servizi possono realizzare *___* qualsiasi * degli obiettivi di protezione, rilevamento, analisi e risposta.

La base della sicurezza di Office 365 è la protezione EOP. Microsoft Defender per Office 365 P1 contiene EOP. Defender per Office 365 P2 contiene P1 ed EOP. La struttura è cumulativa. Ecco perché, quando si configura questo prodotto, è consigliabile iniziare con EOP e lavorare a Defender per Office 365.

Anche se la configurazione dell'autenticazione della posta elettronica avviene nel DNS pubblico, è importante configurare questa funzionalità per la protezione contro lo spoofing. *Se si dispone di EOP, è* ***necessario configurare [l'autenticazione della posta elettronica.](email-validation-and-authentication.md)***

If you have an Office 365 E3, or below, you have EOP, but with the option to buy standalone Defender for Office 365 P1 through upgrade. Se si dispone di Office 365 E5, si dispone già di Defender per Office 365 P2.

> [!TIP]
> Se l'abbonamento non è office 365 E3 o E5, è comunque possibile verificare se si ha la possibilità di eseguire l'aggiornamento a Microsoft Defender per Office 365 P1. Se si è [interessati,](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) questa pagina Web elenca gli abbonamenti idonei per l'aggiornamento Microsoft Defender per Office 365 P1 (controllare la fine della pagina per la stampa fine).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>La sicurezza di Office 365 da EOP a Microsoft Defender per Office 365

![EOP e Microsoft Defender per Office 365 e la loro attenzione alla sicurezza, andando da Protezione e rilevamento per analizzare e rispondere. La configurazione dell'autenticazione della posta elettronica (almeno DKIM e DMARC) deve essere impostata per EOP e la configurazione.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Informazioni dettagliate su queste pagine: [Exchange Online Protection](exchange-online-protection-overview.md)e Defender per Office [365.](office-365-atp.md)

Ciò che rende l'aggiunta di piani di Microsoft Defender per Office 365 un vantaggio per la gestione pura delle minacce EOP può essere difficile da capire a prima vista. Per determinare se un percorso di aggiornamento è corretto per l'organizzazione, diamo un'occhiata alle funzionalità di ogni prodotto quando si tratta di:

- prevenzione e rilevamento delle minacce
- analisi
- risposta

a partire **da Exchange Online Protection:**
<p>

|Impedisci/Rileva|Investigare|Risposta|
|---|---|---|
|Le tecnologie includono:<ul><li>posta indesiderata</li><li>phish</li><li>malware</li><li>posta inviata in blocco</li><li>spoof intelligence</li><li>rilevamento della rappresentazione</li><li>Quarantena dell'amministratore</li><li>Invii di falsi positivi e falsi negativi da parte di amministratori e utenti</li><li>Consenti/Blocca per URL e file</li><li>Report</li></u1>|<li>Ricerca dei log di controllo</li><li>Traccia dei messaggi</li>|<li>Zero-hour Auto-Purge (ZAP)</li><li>Perfezionamento e test degli elenchi Consenti e Blocca</li>|
|

Se si desidera accedere a EOP, **[passare a questo articolo.](exchange-online-protection-overview.md)**

Poiché questi prodotti sono cumulativi, se si valuta Microsoft Defender per Office 365 P1 e si decide di sottoscriverlo, si aggiungeranno queste funzionalità.

Vantaggi con **Defender per Office 365, Piano 1** (ad oggi):
<p>

|Impedisci/Rileva|Investigare|Risposta|
|---|---|---|
|Le tecnologie includono tutto in EOP e:<u1><li>Allegati sicuri</li><li>Collegamenti sicuri<li>Protezione di Microsoft Defender per Office 365 per i carichi di lavoro (ad esempio SharePoint Online, Teams, OneDrive for Business)</li><li>Protezione time-of-click nella posta elettronica, nei client di Office e in Teams</li><li>anti-phishing in Defender per Office 365</li><li>Protezione della rappresentazione di utenti e domini</li><li>Avvisi e API di integrazione SIEM per gli avvisi</li>|<li>API di integrazione SIEM per i rilevamenti</li><li>**Strumento di rilevamento in tempo reale**</li><li>Traccia URL</li>|<li>Stesso</li></u1>

Pertanto, Microsoft Defender per Office 365 P1 si espande sul lato ***prevenzione** _ della casa e aggiunge ulteriori forme di rilevamento __*_**.

Microsoft Defender per Office 365 P1 aggiunge anche rilevamenti in tempo **reale** per le indagini. Il nome di questo strumento di ricerca delle minacce  è in grassetto perché è chiaro il modo di sapere di avere Defender per Office 365 P1. Non viene visualizzato in Defender per Office 365 P2.

Vantaggi con **Defender per Office 365, Piano 2** (ad oggi):
<p>

|Impedisci/Rileva|Investigare|Risposta|
|---|---|---|
|Le tecnologie includono tutto in EOP e Microsoft Defender per Office 365 P1 plus:<u1><li>Stesso</li>|<li>**Esplora minacce**</li><li>Tracker delle minacce</li><li>Visualizzazioni campagna</li>|<li>Analisi e risposta automatizzate (AIR)</li><li>AIR da Threat Explorer</li><li>AIR per gli utenti compromessi</li><li>API di integrazione SIEM per le indagini automatizzate</li>

Pertanto, Microsoft Defender per Office 365  P2 si espande sul lato dell'indagine e della risposta della casa e aggiunge una nuova forza di ricerca. Automazione.

In Microsoft Defender per Office 365 P2, lo strumento di ricerca principale è denominato **Esplora** minacce anziché rilevamenti in tempo reale. Se viene visualizzato Esplora minacce quando si passa al Centro sicurezza, si è in Microsoft Defender per Office 365 P2.

Per informazioni dettagliate su Microsoft Defender per Office 365 P1 e P2, **[passare a questo articolo.](office-365-atp.md)**

> [!TIP]
> EOP e Microsoft Defender per Office 365 sono diversi anche per quanto riguarda gli utenti finali. In EOP e Defender per Office 365 P1, l'attenzione è la consapevolezza e quindi questi due servizi includono il componente aggiuntivo Segnala messaggio *di Outlook in* modo che gli utenti possano segnalare i messaggi di posta elettronica che trovano sospetti, per un'ulteriore analisi. <p> In Defender per Office 365 P2 (che contiene tutto in EOP e P1), lo stato attivo passa a un'ulteriore formazione per gli utenti finali e quindi il Centro operativo per la sicurezza ha accesso a un potente strumento *simulatore* di minacce e alle metriche dell'utente finale fornite. 

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender per Office 365 Piano 1 e foglio trucchi piano 2

Questa guida di riferimento rapido consente di comprendere quali funzionalità sono disponibili in ogni abbonamento a Microsoft Defender per Office 365. Se combinato con la conoscenza delle funzionalità di EOP, può aiutare i decisori aziendali a determinare quale Microsoft Defender per Office 365 è il migliore per le proprie esigenze.

|Defender per Office 365 Piano 1|Defender per Office 365 Piano 2|
|---|---|
|Funzionalità di configurazione, protezione e rilevamento: <ul><li>[Allegati sicuri](atp-safe-attachments.md)</li><li>[Collegamenti sicuri](atp-safe-links.md)</li><li>[Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Protezione anti-phishing in Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Rilevamenti in tempo reale](threat-explorer.md)</li></ul>|Funzionalità di Defender per Office 365 Piano 1 <p> --- più --- <p> Funzionalità di automazione, analisi, correzione e formazione: <ul><li>[Tracker delle minacce](threat-trackers.md)</li><li>[Esplora minacce](threat-explorer.md)</li><li>[Analisi e risposta automatizzate](office-365-air.md)</li><li>[Simulatore di attacchi](attack-simulator.md)</li></ul>|
|

- Microsoft Defender per Office 365 Piano 2 è incluso in Office 365 E5, Office 365 A5 e Microsoft 365 E5.

- Microsoft Defender per Office 365 Piano 1 è incluso in Microsoft 365 Business Premium.

- Microsoft Defender per Office 365 Piano 1 e Defender per Office 365 Piano 2 sono disponibili come componente aggiuntivo per determinati abbonamenti. Per altre informazioni, ecco un altro collegamento Disponibilità delle funzionalità [tra i piani di Microsoft Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- La caratteristica [Documenti sicuri](safe-docs.md) è disponibile solo per gli utenti che dispongono di licenze Microsoft 365 E5 o Microsoft 365 E5 Security (non incluse nei piani di Microsoft Defender per Office 365).

- Se l'abbonamento corrente non include Microsoft Defender per Office 365 e lo si [desidera,](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)contattare le vendite per avviare una versione di valutazione e scoprire come Microsoft Defender per Office 365 può funzionare nell'organizzazione.

> [!TIP]
> ***Suggerimento Insider** _. È possibile utilizzare il docs.microsoft.com sommario per informazioni su EOP e Microsoft Defender per Office 365. Tornare a questa pagina, Panoramica della sicurezza di [Office 365](index.md)e si noterà che l'organizzazione del sommario è nella barra laterale. Inizia con la distribuzione (inclusa la migrazione) e quindi continua con la prevenzione, il rilevamento, l'indagine e la risposta. <p> Questa struttura è suddivisa in modo che gli argomenti _ *Security Administration** siano seguiti dagli **argomenti relativi alle operazioni di** sicurezza. Se si è un nuovo membro di uno di questi ruoli, utilizzare il collegamento in questo suggerimento e conoscere il sommario per imparare a usare lo spazio. Ricordarsi di usare *i collegamenti di feedback* e valutare gli *articoli* mentre si va. Il feedback ci aiuta a migliorare ciò che ti offriamo.

## <a name="where-to-go-next"></a>Dove andare dopo

If you're a Security Admin, you may need to configure DKIM or DMARC for your mail. È possibile implementare preimpostazioni di sicurezza "Strict" per gli utenti con priorità o cercare le novità del prodotto. Oppure, se si usa Security Ops, è possibile sfruttare i rilevamenti in tempo reale o Esplora minacce per analizzare e rispondere oppure formare il rilevamento degli utenti finali con il simulatore di attacchi. In entrambi i casi, di seguito sono riportati alcuni suggerimenti aggiuntivi per gli elementi da esaminare successivamente.

[Autenticazione della posta elettronica, tra cui SPF, DKIM e DMARC (con collegamenti alla configurazione di tutti e tre)](email-validation-and-authentication.md)

[Vedere le specifiche impostazioni di configurazione di riferimento](recommended-settings-for-eop-and-office365-atp.md) consigliate e usare le impostazioni predefinite consigliate per configurare rapidamente i criteri di [sicurezza](preset-security-policies.md)

Informazioni sulle [novità di Microsoft Defender per Office 365 (inclusi gli sviluppi di EOP)](whats-new-in-office-365-atp.md)

[Usare Esplora minacce o rilevamenti in tempo reale](threat-explorer.md)

Usare [il simulatore di attacchi in Microsoft Defender per Office 365](attack-simulator.md)
