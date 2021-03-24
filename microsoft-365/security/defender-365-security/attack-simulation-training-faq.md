---
title: Considerazioni e domande frequenti sulla distribuzione della formazione del Simulatore di attacchi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulle considerazioni sulla distribuzione e sulle domande frequenti relative alla simulazione e alla formazione sugli attacchi nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065530"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>Considerazioni e domande frequenti sulla distribuzione della formazione del Simulatore di attacchi

La formazione per la simulazione di attacchi [è ora disponibile in genere.](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291) La formazione sulla simulazione di attacchi consente alle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2 di misurare e gestire i rischi di social engineering consentendo la creazione e la gestione di simulazioni di phishing basate su payload di phishing reali e de-armati. La formazione iper mirata, in collaborazione con la sicurezza di Terranova, aiuta a migliorare le conoscenze e a modificare il comportamento dei dipendenti.

Per ulteriori informazioni sull'introduzione alla formazione sulla simulazione di attacco, vedere Introduzione all'uso della formazione [sulla simulazione di attacco.](attack-simulation-training-get-started.md)

Sebbene l'intera esperienza di creazione e pianificazione della simulazione sia stata progettata per essere senza flusso libero e senza attriti, l'esecuzione di simulazioni su scala aziendale spesso richiede una pianificazione. Questo articolo consente di affrontare sfide specifiche che vediamo quando i nostri clienti eseguono simulazioni nei propri ambienti.

## <a name="issues-with-end-user-experiences"></a>Problemi con le esperienze degli utenti finali

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>URL di simulazione di phishing bloccati da Google Safe Browsing

Un servizio di reputazione URL potrebbe identificare uno o più URL utilizzati dal training di simulazione degli attacchi come non sicuri. L'esplorazione sicura di Google in Google Chrome blocca alcuni DEGLI URL di phishing simulati con un **messaggio di** sito inganneale in anticipo. Anche se lavoriamo con molti fornitori di reputazione URL per consentire sempre gli URL di simulazione, non sempre abbiamo una copertura completa.

![Avviso del sito ingannescente in Google Chrome](../../media/attack-sim-chrome-deceptive-site-message.png)

Tieni presente che questo problema non influisce su Microsoft Edge.

Nell'ambito della fase di pianificazione, verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing. Se gli URL sono bloccati da Google Safe Browsing, segui [queste](https://support.google.com/chrome/a/answer/7532419) indicazioni di Google per consentire l'accesso agli URL.

Per [l'elenco degli](attack-simulation-training-get-started.md) URL attualmente utilizzati dal training di simulazione di attacco, vedere Introduzione all'uso del training di simulazione degli attacchi.

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>Simulazione di phishing e URL di amministratore bloccati dalle soluzioni proxy di rete e dai driver di filtro

Sia gli URL di simulazione di phishing che gli URL di amministrazione potrebbero essere bloccati o eliminati dai filtri o dai dispositivi di sicurezza intermedi. Ad esempio:

- Firewall
- Soluzioni WaF (Web Application Firewall)
- Driver di filtro di terze parti (ad esempio, filtri in modalità kernel)

Anche se abbiamo visto pochi clienti bloccati a questo livello, si verifica. In caso di problemi, è consigliabile configurare gli URL seguenti per ignorare l'analisi da parte dei dispositivi di sicurezza o dei filtri in base alle esigenze:

- Gli URL di phishing simulati, come descritto in [Introduzione all'uso della simulazione di attacco.](attack-simulation-training-get-started.md)
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>Messaggi di simulazione non recapitati a tutti gli utenti di destinazione

È possibile che il numero di utenti che effettivamente ricevono i messaggi di posta elettronica di simulazione sia inferiore al numero di utenti mirati dalla simulazione. Nell'ambito della convalida di destinazione verranno esclusi i tipi di utenti seguenti:

- Indirizzi di posta elettronica dei destinatari non validi.
- Utenti guest.
- Utenti che non sono più attivi in Azure Active Directory (Azure AD).

Nelle simulazioni verranno inclusi solo gli utenti non guest validi con una cassetta postale valida. Se si utilizzano gruppi di distribuzione o gruppi di sicurezza abilitati alla posta elettronica per gli utenti di destinazione, è possibile utilizzare il cmdlet [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) in [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) di Exchange Online per visualizzare e convalidare i membri del gruppo di distribuzione.

## <a name="issues-with-attack-simulation-training-reporting"></a>Problemi relativi alla creazione di report di formazione sulla simulazione di attacchi

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>I report di formazione sulla simulazione di attacchi non contengono dettagli sull'attività

La formazione sulla simulazione di attacchi include informazioni dettagliate e utilizzabili che ti tengono informati sullo stato di preparazione alle minacce dei dipendenti. Se i report di training della simulazione di attacco non sono popolati con dati, verificare che la ricerca nei log di controllo sia attivata nell'organizzazione (è attivata per impostazione predefinita).

La ricerca nel log di controllo è necessaria per la formazione sulla simulazione degli attacchi in modo che gli eventi possano essere acquisiti, registrati e letti. La disattivazione della ricerca nei log di controllo ha le seguenti conseguenze per il training di simulazione degli attacchi:

- I dati dei report non sono disponibili in tutti i report. I report verranno visualizzati vuoti.
- Le assegnazioni di formazione sono bloccate perché i dati non sono disponibili.

Per attivare o disattivare la ricerca nei log di controllo, vedere Attivare o [disattivare la ricerca nei log di controllo.](../../compliance/turn-audit-log-search-on-or-off.md)

> [!NOTE]
> I dettagli delle attività vuote possono anche essere causati dall'assenza di licenze E5 assegnate agli utenti. Verificare che almeno una licenza E5 sia assegnata a un utente attivo per assicurarsi che gli eventi di segnalazione siano acquisiti e registrati.

### <a name="simulation-reports-are-not-updated-immediately"></a>I report di simulazione non vengono aggiornati immediatamente

I report di simulazione dettagliati non vengono aggiornati immediatamente dopo l'avvio di una campagna. Non preoccuparti; questo comportamento è previsto.

Ogni campagna di simulazione ha un ciclo di vita. Quando viene creata per la prima volta, la simulazione è nello **stato Pianificato.** All'avvio, la simulazione passa allo **stato In** corso. Al termine, la simulazione passa allo **stato Completed.**

Mentre una simulazione è nello **stato Pianificato,** i report di simulazione saranno per lo più vuoti. Durante questa fase, il motore di simulazione sta risolvendo gli indirizzi di posta elettronica degli utenti di destinazione, espandendo i gruppi di distribuzione, rimuovendo gli utenti guest dall'elenco e così via:

![Creazione di report nello stato Pianificato](../../media/attack-sim-empty-reporting.png)

Una volta che la simulazione entra **nella fase In** corso, noterai che le informazioni iniziano a entrano nel report:

![Creazione di report nello stato In corso](../../media/attack-sim-in-progress.png)

L'aggiornamento dei singoli report di simulazione dopo la transizione allo stato **In** corso può richiedere fino a 30 minuti. I dati del report continuano a essere compilati fino a quando la simulazione non raggiunge lo **stato Completed.** Gli aggiornamenti dei report vengono eseguiti a intervalli seguenti:

- Ogni 10 minuti per i primi 60 minuti.
- Ogni 15 minuti dopo 60 minuti fino a 2 giorni.
- Ogni 30 minuti dopo 2 giorni fino a 7 giorni.
- Ogni 60 minuti dopo 7 giorni.

I widget nella pagina **Panoramica** offrono un rapido snapshot della posizione di sicurezza basata sulla simulazione dell'organizzazione nel tempo. Poiché questi widget riflettono la tua posizione di sicurezza complessiva e il percorso nel tempo, vengono aggiornati al termine di ogni campagna di simulazione.

> [!NOTE]
> È possibile utilizzare **l'opzione Esporta** nelle varie pagine di report per estrarre i dati.

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>I messaggi segnalati come phishing dagli utenti non vengono visualizzati nei report di simulazione

I report di simulazione nel training del simulatore di attacco forniscono informazioni dettagliate sull'attività degli utenti. Ad esempio:

- Utenti che hanno fatto clic sul collegamento nel messaggio.
- Utenti che hanno rinunciato alle proprie credenziali.
- Utenti che hanno segnalato il messaggio come phishing.

Se i messaggi segnalati dagli utenti come phishing non vengono acquisiti nei report di simulazione della simulazione di attacco, potrebbe essere presente una regola del flusso di posta di Exchange (nota anche come regola di trasporto) che blocca il recapito dei messaggi segnalati a Microsoft. Verificare che le regole del flusso di posta non blocchino il recapito ai seguenti indirizzi di posta elettronica:

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- non \_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>Altre domande frequenti

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>D: Qual è il metodo consigliato per gli utenti di destinazione per le campagne di simulazione?

A: Sono disponibili diverse opzioni per gli utenti di destinazione:

- Includere tutti gli utenti (attualmente disponibili per le organizzazioni con meno di 40.000 utenti).
- Scegliere utenti specifici.
- Selezionare gli utenti da un file CSV.
- Targeting basato su gruppo di Azure AD.

È stato rilevato che le campagne in cui gli utenti di destinazione sono identificati dai gruppi di Azure AD sono in genere più facili da gestire.

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>D: Esistono limiti per la destinazione degli utenti durante l'importazione da un file CSV o l'aggiunta di utenti?

A: Il limite per l'importazione di destinatari da un file CSV o l'aggiunta di singoli destinatari a una simulazione è di 40.000.

Un destinatario può essere un singolo utente o un gruppo. Un gruppo può contenere centinaia o migliaia di destinatari, quindi non viene posto un limite effettivo al numero di singoli utenti.

La gestione di un file CSV di grandi dimensioni o l'aggiunta di molti singoli destinatari può essere complicata. L'uso dei gruppi di Azure AD semplifica la gestione complessiva della simulazione.

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>D: Microsoft fornisce payload in altre lingue?

A: Attualmente sono disponibili 5 payload localizzati. Abbiamo notato che qualsiasi traduzione diretta o automatica di payload esistenti in altre lingue comporta imprecisioni e una minore pertinenza.

Detto questo, puoi creare il tuo payload nella lingua desiderata usando l'esperienza di creazione del payload personalizzato. È inoltre consigliabile raccogliere i payload esistenti usati per gli utenti di una specifica area geografica. In altre parole, consenti agli utenti malintenzionati di localizzare il contenuto per te.

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>D: Come è possibile passare ad altre lingue per il portale di amministrazione e l'esperienza di formazione?

A: In Microsoft 365 o Office 365, la configurazione della lingua è specifica e centralizzata per ogni account utente. Per istruzioni su come modificare l'impostazione della lingua, vedere Modificare la lingua di visualizzazione e il fuso [orario in Microsoft 365 per le aziende.](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)

Si noti che la sincronizzazione della modifica della configurazione potrebbe richiedere fino a 30 minuti tra tutti i servizi.

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>D: È possibile attivare una simulazione di test per comprendere come appare prima di avviare una campagna completa?

A: Sì, è possibile! Nell'ultima pagina **Verifica simulazione** della procedura guidata per creare una nuova simulazione, è disponibile un'opzione per **inviare un test.** Questa opzione invierà un messaggio di simulazione di phishing di esempio all'utente attualmente connesso. Dopo aver convalidato il messaggio di phishing nella posta in arrivo, è possibile inviare la simulazione.

![Pulsante Invia un test nella pagina Di simulazione revisione](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>D: È possibile scegliere come target gli utenti che appartengono a un tenant diverso nell'ambito della stessa campagna di simulazione?

R: No. Attualmente, le simulazioni tra tenant non sono supportate. Verificare che tutti gli utenti di destinazione siano nello stesso tenant. Tutti gli utenti cross-tenant o guest verranno esclusi dalla campagna di simulazione.

### <a name="q-how-does-region-aware-delivery-work"></a>D: Come funziona il recapito con informazioni sull'area geografica?

A: Il recapito in grado di riconoscere l'area geografica usa l'attributo TimeZone della cassetta postale dell'utente di destinazione e la logica "non prima" per determinare quando recapitare il messaggio. Si consideri, ad esempio, lo scenario seguente:

- Alle 7:00 del fuso orario del Pacifico (UTC-8), un amministratore crea e pianifica una campagna per iniziare alle 9.00 dello stesso giorno.
- UserA si trova nel fuso orario orientale (UTC-5).
- UserB si trova anche nel fuso orario del Pacifico.

Alle 9:00 dello stesso giorno, il messaggio di simulazione viene inviato all'utenteB. Con il recapito in grado di riconoscere l'area geografica, il messaggio non viene inviato a UserA lo stesso giorno, perché le 9.00 ora del Pacifico sono le 12.00 ora orientale. Il messaggio viene invece inviato all'UtenteA alle 9.00 ora orientale del giorno successivo.

Pertanto, all'esecuzione iniziale di una campagna con il recapito in grado di riconoscere l'area geografica abilitato, potrebbe sembrare che il messaggio di simulazione sia stato inviato solo agli utenti in un fuso orario specifico. Tuttavia, con il passare del tempo e l'accesso di un numero maggiore di utenti all'ambito, gli utenti di destinazione aumenteranno.