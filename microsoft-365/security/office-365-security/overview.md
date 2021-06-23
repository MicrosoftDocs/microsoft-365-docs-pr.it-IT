---
title: Sicurezza di Office 365, Microsoft Defender per Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 06/11/2021
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Sicurezza in Office 365, da EOP a Defender per Office Piani 1 e 2 di Office 365, differenza tra configurazione della sicurezza standard e rigorosa e altro ancora. Comprendere ciò che si ha e come proteggere le proprie proprietà.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: db458f0a3a3ac2cc4a06d0827844e156798f6505
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083657"
---
# <a name="microsoft-defender-for-office-365-security-overview"></a>Panoramica di Microsoft Defender Office 365 sicurezza

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)

Questo articolo ti introdurrà al nuovo Microsoft Defender per le Office 365 sicurezza nel cloud. Se si fa parte di un centro operazioni per la sicurezza, si è un amministratore della sicurezza nuovo dell'argomento o si desidera fare un ripasso, questo è il posto giusto per iniziare.

> [!CAUTION]
> Se si usa **Outlook.com**, **Microsoft 365 Family** o **Microsoft 365 Personal** e si cercano informazioni sui *collegamenti sicuri* o gli *allegati sicuri* in Outlook, ***fare clic sul collegamento*** vedere [Sicurezza avanzata Outlook.com per gli abbonati a Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="what-is-defender-for-office-365-security"></a>Che cos'è Defender per Office 365 sicurezza

Ogni abbonamento a Office 365 include funzionalità di sicurezza. Gli obiettivi e le azioni che è possibile intraprendere dipendono dal focus di questi diversi abbonamenti. La sicurezza di Office 365 comprende tre servizi di sicurezza (o prodotti) principali, che sono associati al tipo di abbonamento:

1. Exchange Online Protection (EOP)
1. Microsoft Defender per Office 365 Piano 1 (Defender per Office P1)
1. Microsoft Defender per Office 365 Piano 2 (Defender per Office P2)

> [!NOTE]
> Se si è già acquistato l'abbonamento e occorre implementare *immediatamente* le funzionalità di sicurezza, passare alla procedura nell'articolo [Protezione dalle minacce](protect-against-threats.md). Se l'abbonamento è nuovo e si vogliono informazioni sulla licenza di cui si dispone prima di iniziare, passare a Fatturazione > I tuoi prodotti nell'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/AdminPortal/#/homepage).

La sicurezza di Office 365 si basa sulle misure di protezione di base offerte da EOP. EOP è presente in qualsiasi abbonamento in cui sono disponibili cassette postali di Exchange Online (tenere presente che tutti i prodotti per la sicurezza illustrati qui sono basati sul cloud).

Forse si è abituati a vedere questi tre componenti illustrati in questo modo:

|EOP|Microsoft Defender per Office 365 P1|Microsoft Defender per Office 365 P2|
|---|---|---|
|Previene attacchi noti estesi e basati su volume.|Protegge l'e-mail e la collaborazione da attacchi di malware zero-day, messaggi di phishing e compromissione della posta elettronica aziendale.|Aggiunge indagini post-violazione, rilevazione e risposta post-violazione, oltre ad automazione e simulazione (per la formazione).|
|

In termini di architettura, tuttavia, si può pensare ai vari elementi come a livelli di sicurezza cumulativi, ognuno con un'enfasi sulla sicurezza. Il concetto è più simile a questo:

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP e Microsoft Defender per Office 365 e le loro relazioni reciproche, con enfasi sul servizio, inclusa una nota per l'autenticazione della posta elettronica.":::

Anche se ognuno di questi servizi pone l'accento su un obiettivo tra Protezione, Rilevamento, Indagine e Risposta, ***tutti** _ i servizi possono svolgere _ *_qualsiasi_** attività di protezione, rilevamento, indagine e risposta.

Il nucleo della sicurezza di Office 365 è la protezione EOP. Microsoft Defender per Office 365 P1 contiene EOP. Defender per Office 365 P2 contiene P1 ed EOP. La struttura è cumulativa. Ecco perché, quando si configura questo prodotto, è consigliabile iniziare con EOP e arrivare a Defender per Office 365.

Anche se la configurazione dell'autenticazione della posta elettronica avviene nel DNS pubblico, è importante configurare questa funzionalità per difendersi dallo spoofing. *Se si ha EOP,* ***è consigliabile [configurare l'autenticazione della posta elettronica](email-validation-and-authentication.md)***.

Se si ha Office 365 E3 o versione inferiore, si ha anche EOP, ma con l'opzione di acquistare Defender per Office 365 P1 autonomo tramite un aggiornamento. Se si ha Office 365 E5, si ha già Defender per Office 365 P2.

> [!TIP]
> Se l'abbonamento non è né Office 365 E3, né Office 365 E5, si può comunque verificare se è disponibile l'opzione per eseguire l'aggiornamento a Microsoft Defender per Office 365 P1. Se si è interessati, [questa pagina Web](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) contiene un elenco degli abbonamenti idonei per l'aggiornamento Microsoft Defender per Office 365 P1 (cercare in fondo alla pagina).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Gerarchia della sicurezza di Office 365, da EOP a Microsoft Defender per Office 365

> [!IMPORTANT]
> Informazioni dettagliate sono disponibili a queste pagine: [Exchange Online Protection](exchange-online-protection-overview.md) e [Defender per Office 365](defender-for-office-365.md).

I vantaggi di aggiungere i piani di Microsoft Defender per Office 365 alla pura gestione delle minacce di EOP possono essere difficili da vedere a un primo sguardo. Per determinare se un percorso di aggiornamento è giusto per la propria organizzazione, esaminare le funzionalità di ogni prodotto in termini di:

- prevenzione e rilevamento delle minacce
- indagine
- risposta

a partire da **Exchange Online Protection**:
<p>

|Prevenzione/Rilevamento|Indagine|Risposta|
|---|---|---|
|Le tecnologie includono:<ul><li>Posta indesiderata</li><li>Messaggi di phishing</li><li>Malware</li><li>Posta inviata in massa</li><li>Spoof intelligence</li><li>Rilevamento delle imitazioni</li><li>Quarantena amministratore</li><li>Invii di falsi positivi e falsi negativi da parte di amministratori e utenti</li><li>Consenti/Blocca per URL e file</li><li>Report</li></u1>|<li>Ricerca nel log di audit</li><li>Traccia messaggio</li>|<li>Zero-hour Auto-Purge (ZAP)</li><li>Perfezionamento e test degli elenchi Consenti e Blocca</li>|
|

Per informazioni approfondite su EOP, passare a **[questo articolo](exchange-online-protection-overview.md)**.

Poiché questi prodotti sono cumulativi, se si valuta Microsoft Defender per Office 365 P1 e si decide di abbonarsi, si aggiungeranno queste capacità.

Vantaggi con **Defender per Office 365 Piano 1** (a oggi):
<p>

|Prevenzione/Rilevamento|Indagine|Risposta|
|---|---|---|
|Le tecnologie includono tutte le funzionalità di EOP, più:<u1><li>Allegati sicuri</li><li>Collegamenti sicuri<li>Protezione di Microsoft Defender per Office 365 per i carichi di lavoro (ad es. SharePoint Online, Teams, OneDrive for Business)</li><li>Protezione al momento del clic nella posta elettronica, nei client di Office e in Teams</li><li>Anti-phishing in Defender per Office 365</li><li>Protezione dall'imitazione di utenti e domini</li><li>Avvisi e API di integrazione SIEM per gli avvisi</li>|<li>API di integrazione SIEM per i rilevamenti</li><li>**Strumento Rilevamenti in tempo reale**</li><li>Traccia URL</li>|<li>Uguali</li></u1>

Quindi, Microsoft Defender per Office 365 P1 è più ricco sul lato ***prevenzione** e aggiunge altre forme di *_rilevamento_**.

Microsoft Defender per Office 365 P1 aggiunge anche **Rilevamenti in tempo reale** per le indagini. Il nome di questo strumento di rilevazione delle minacce è in grassetto perché la presenza dello strumento *indica chiaramente* che si dispone di Defender per Office 365 P1. Non compare in Defender per Office 365 P2.

Vantaggi con **Defender per Office 365 Piano 2** (a oggi):
<p>

|Prevenzione/Rilevamento|Indagine|Risposta|
|---|---|---|
|Le tecnologie includono tutte le funzionalità di EOP e Microsoft Defender per Office 365 P1, più:<u1><li>Uguali</li>|<li>**Esplora minacce**</li><li>Tracker delle minacce</li><li>Visualizzazioni campagna</li>|<li>Indagine e reazione automatizzati (AIR)</li><li>AIR di Esplora minacce</li><li>AIR per utenti compromessi</li><li>API di integrazione SIEM per indagini automatizzate</li>

Quindi Microsoft Defender per Office 365 P2 è più ricco sul lato ***indagine e risposta*** e aggiunge una nuova capacità di rilevazione. L'automazione.

In Microsoft Defender per Office 365 P2, lo strumento di rilevazione principale si chiama **Esplora minacce** e non Rilevamenti in tempo reale. Se vedi Threat Explorer quando accedi al portale Microsoft 365 Defender, sei in Microsoft Defender per Office 365 P2.

Per informazioni dettagliate su Microsoft Defender per Office 365 P1 e P2, passare a **[questo articolo](defender-for-office-365.md)**.

> [!TIP]
> EOP e Microsoft Defender per Office 365 sono diversi anche per quanto riguarda gli utenti finali. In EOP e Defender per Office 365 P1 l'accento è posto sulla *consapevolezza*. Per questo motivo, questi due servizi includono il *componente aggiuntivo di Outlook Segnala messaggio*, che consente agli utenti di segnalare i messaggi che trovano sospetti per un'ulteriore analisi. <p> In Defender per Office 365 P2 (che contiene tutte le funzionalità in EOP e P1), l'accento si sposta sulla *maggiore formazione* degli utenti finali, quindi il centro operazioni per la sicurezza ha accesso a un potente strumento di *simulazione delle minacce* e alle metriche per gli utenti finali che fornisce.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Scheda di riferimento rapido sulle differenze tra Microsoft Defender per Office 365 Piano 1 e Piano 2

Questo riferimento rapido è utile per comprendere quali funzionalità sono disponibili con ogni abbonamento a Microsoft Defender per Office 365. Se combinato con le proprie conoscenze sulle funzionalità di EOP, può aiutare i decision maker aziendali a individuare la soluzione Microsoft Defender per Office 365 più adatta alle proprie esigenze.

|Defender per Office 365 Piano 1|Defender per Office 365 Piano 2|
|---|---|
|Funzionalità di configurazione, protezione e rilevamento: <ul><li>[Allegati sicuri](safe-attachments.md)</li><li>[Collegamenti sicuri](safe-links.md)</li><li>[Allegati sicuri per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Protezione anti-phishing in Defender per Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Rilevamenti in tempo reale](threat-explorer.md)</li></ul>|Funzionalità di Defender per Office 365 Piano 1 <p> --- più --- <p> Funzionalità di automazione, analisi, correzione e formazione: <ul><li>[Tracker delle minacce](threat-trackers.md)</li><li>[Esplora minacce](threat-explorer.md)</li><li>[Analisi e risposta automatizzate](office-365-air.md)</li><li>[Formazione per la simulazione di attacchi](attack-simulation-training.md)</li></ul>|
|

- Microsoft Defender per Office 365 Piano 2 è incluso in Office 365 E5, Office 365 A5 e Microsoft 365 E5.

- Microsoft Defender per Office 365 Piano 1 è incluso in Microsoft 365 Business Premium.

- Microsoft Defender per Office 365 Piano 1 e Defender per Office 365 Piano 2 sono disponibili come componenti aggiuntivi per determinati abbonamenti. Per altre informazioni, vedere anche [Disponibilità delle funzionalità tra i piani di Microsoft Defender per Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- La caratteristica [Documenti sicuri](safe-docs.md) è disponibile solo per gli utenti che dispongono di licenze Microsoft 365 E5 o Microsoft 365 E5 Security (non incluse nei piani di Microsoft Defender per Office 365).

- Se l'abbonamento attuale non include Microsoft Defender per Office 365, [contattare il reparto vendite per avviare una versione di valutazione](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) e scoprire cosa può fare Microsoft Defender per Office 365 per la propria organizzazione.

> [!TIP]
> ***Suggerimento** _. È possibile usare il sommario alla pagina docs.microsoft.com per trovare altre informazioni su EOP e Microsoft Defender per Office 365. Tornare a questa pagina, [Panoramica sulla sicurezza di Office 365](index.yml) e notare l'organizzazione del sommario nella barra laterale. Inizia con una sezione sulla distribuzione, inclusa la migrazione, e quindi continua con le attività di prevenzione, rilevamento, indagine e risposta. <p> Questa struttura è suddivisa in modo che gli argomenti sull'*Amministrazione della sicurezza** siano seguiti da quelli sulle **Operazioni di sicurezza**. Se si è un nuovo membro di uno dei due ruoli, usare il collegamento in questo suggerimento e la guida del sommario per esplorare più facilmente lo spazio di proprio interesse. Ricordare di usare *collegamenti per il feedback* e di *valutare gli articoli* man mano che si procede. Il feedback ci aiuta a migliorare le informazioni offerte.

## <a name="where-to-go-next"></a>Passaggi successivi

Gli amministratori della sicurezza potrebbero dover configurare DKIM o DMARC per la posta elettronica. Potrebbero voler implementare set di impostazioni di sicurezza rigorose per gli utenti con priorità maggiore o cercare le novità del prodotto. I membri del team delle operazioni di sicurezza potrebbero voler usare Rilevamenti in tempo reale o Esplora minacce per indagare e rispondere oppure formare gli utenti finali al rilevamento con Simulatore di attacchi. In entrambi i casi, ecco alcuni altri consigli sui prossimi articoli da consultare.

[Autenticazione della posta elettronica, inclusi SPF, DKIM e DMARC (con collegamenti alla configurazione di tutti e tre i meccanismi)](email-validation-and-authentication.md)

[Vedere le specifiche configurazioni consigliate](recommended-settings-for-eop-and-office365.md) e [usare i set di impostazioni consigliate per configurare rapidamente i criteri di sicurezza](preset-security-policies.md)

Aggiornarsi sulle [novità di Microsoft Defender per Office 365 (inclusi gli sviluppi di EOP)](whats-new-in-defender-for-office-365.md)

[Usare Esplora minacce o Rilevamenti in tempo reale](threat-explorer.md)

Usare [il training di simulazione degli attacchi](attack-simulation-training.md)
