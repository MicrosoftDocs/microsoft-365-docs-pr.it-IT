---
title: Cortana in Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: Dopo l'accesso con account aziendali o dell'istituto di istruzione validi, gli utenti possono ottenere servizi di assistenza basati su cloud con Cortana nelle esperienze di Microsoft 365 che soddisfano le promesse di privacy, sicurezza e conformità a livello aziendale di Office 365.
ms.openlocfilehash: 00702724a44cd75bc68e9f7adac7170d81c080fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914799"
---
# <a name="cortana-in-microsoft-365"></a>Cortana in Microsoft 365

Cortana, l'assistente per la produttività personale, offre esperienze basate sull'intelligenza artificiale per risparmiare tempo e concentrare l'attenzione su ciò che conta di più. Cortana aiuterà gli utenti ad aumentare la produttività personale per l'intera giornata sia nel lavoro che nella vita. Quando si esegue l'accesso con account aziendali o dell'istituto di istruzione validi, gli utenti possono ottenere servizi di assistenza basati su cloud con Cortana nelle esperienze di Microsoft 365 che soddisfano le promesse di privacy, sicurezza e conformità a livello aziendale di Office 365 ("Servizi aziendali di Cortana"). 

In quanto assistente per la produttività personale, Cortana è progettata per offrire funzionalità che consentono di elaborare in modo sicuro e sicuro i dati di Office 365 come messaggi di posta elettronica, file, chat e così via, per risparmiare tempo, aumentare l'efficienza e migliorare la produttività degli utenti.

In futuro, stiamo concentrando Cortana sulla produttività aziendale.

- Coerentemente con altri servizi di Office 365, i servizi enterprise di Cortana soddisfano le stesse promesse di privacy, sicurezza e conformità a livello aziendale, come illustrato nelle Condizioni dei servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products)

- Le nuove esperienze di Microsoft 365, ad esempio l'e-mail briefing e la funzionalità Riproduci i miei messaggi di posta elettronica, verranno abilitate tramite I servizi enterprise di Cortana e saranno completamente conformi a tali promesse. Queste funzionalità sono attualmente disponibili in tutto il mondo (multi-tenant standard). Per ulteriori informazioni su come trovare il percorso di utilizzo, vedere [Visualizzare valori di proprietà aggiuntivi per gli account](../../enterprise/view-user-accounts-with-microsoft-365-powershell.md?view=o365-worldwide#view-additional-property-values-for-accounts).

- Gli utenti possono connettersi ai servizi enterprise di Cortana descritti qui tramite Cortana in Windows 10 (versione 2004 e successive), nonché alle applicazioni client, come Outlook per iOS e Android, soggetti a condizioni di licenza separate. 

- Le esperienze utente esistenti, tra cui Cortana in Windows 10 (versione 1909 e versioni precedenti) e l'app Cortana in iOS e Android, sono disciplinate dal Contratto di servizi [Microsoft](https://www.microsoft.com/licensing/product-licensing/products) e dall'Informativa sulla [privacy Microsoft](https://privacy.microsoft.com/privacystatement) (vedi la sezione "Servizi esistenti per i consumatori" di seguito). Queste condizioni regolano anche i servizi enterprise di Cortana forniti all'utente dopo l'accesso con le credenziali dell'utente.

## <a name="what-data-is-processed-by-cortana-enterprise-services"></a>Quali dati vengono elaborati da Cortana Enterprise Services? 

Cortana Enterprise Services elabora le query dell'utente, i dati di Office necessari per soddisfare la richiesta dell'utente e altri dati di telemetria generati dai sistemi Microsoft per eseguire il servizio. I dati raccolti da Cortana Enterprise Services includono la rappresentazione testuale delle query vocali dell'utente (ad esempio, trascrizioni dal riconoscimento vocale). Questi dati di testo sono dati del cliente e vengono gestiti in conformità alle Condizioni [dei Servizi online.](https://www.microsoft.com/licensing/product-licensing/products) Viene usato solo per sviluppare e migliorare modelli di apprendimento automatico coerenti con le Condizioni del servizio online.

## <a name="what-is-the-governance-model-for-customer-data-in-cortana-enterprise-services"></a>Qual è il modello di governance per i dati dei clienti in Cortana Enterprise Services?

Coerentemente con altri servizi di Office 365, i servizi enterprise di Cortana sono protetti e soggetti alle Condizioni [dei Servizi online.](https://www.microsoft.com/licensing/product-licensing/products) Questo include una serie di promesse per la protezione dei dati dei clienti da perdita accidentale, alterazione, divulgazione o accesso non autorizzato o distruzione illecita. I dati dei clienti sono inoltre soggetti a rigide limitazioni di accesso. Microsoft utilizza i dati dei clienti solo per fornire i servizi concordati e per scopi compatibili con tali servizi. Per informazioni dettagliate, vedere la tabella seguente.

## <a name="how-does-microsoft-store-retain-process-and-use-customer-data-in-cortana"></a>In che modo Microsoft archivia, conserva, elabora e usa i dati dei clienti in Cortana?

La tabella seguente descrive la gestione dei dati per Cortana Enterprise Services.

| Nome | Descrizione |
|:-----|:-----|
|**Spazio di archiviazione**  <br/> |I dati dei clienti vengono archiviati nei server Microsoft all'interno del cloud di Office 365. I dati fanno parte del tenant. <br/><br/>L'audio vocale non viene conservato.  <br/> |
|**Stays in Geo**  <br/> |I dati dei clienti vengono archiviati nei server Microsoft all'interno del cloud di Office 365 in Geo. I dati fanno parte del tenant.  <br/> |
|**Conservazione**  <br/> |I dati del cliente vengono eliminati quando l'account viene chiuso dall'amministratore tenant o quando viene effettuata una richiesta di eliminazione dei diritti dell'oggetto dei dati GDPR. <br/><br/>L'audio vocale non viene conservato.  <br/> |
|**Trattamento e riservatezza**  <br/> |Il personale impegnato nel trattamento dei dati dei clienti e dei dati personali (i) e trattamento di tali dati solo su istruzioni del Cliente e (ii) sarà obbligato a mantenere la riservatezza e la sicurezza di tali dati anche dopo la fine del loro impegno.  <br/> |
|**Usage**  <br/> |Microsoft utilizza i dati dei clienti solo per fornire i servizi concordati e per scopi compatibili con tali servizi. L'apprendimento automatico per sviluppare e migliorare i modelli è uno di questi scopi. L'apprendimento automatico viene eseguito all'interno del cloud di Office 365 e non è disponibile alcuna visualizzazione, revisione o etichettatura dei dati dei clienti. <br/><br/>I dati non vengono utilizzati per la pubblicità.  <br/> |

## <a name="cortana-enterprise-services-in-microsoft-365-experiences"></a>Cortana Enterprise Services nelle esperienze di Microsoft 365

### <a name="cortana-in-windows-10-version-2004-and-later"></a>Cortana in Windows 10 (versione 2004 e successive)

L'app Cortana in Windows 10 consente agli utenti di ottenere rapidamente informazioni in Microsoft 365, usando query digitate o vocali per connettersi con le persone, controllare i calendari, impostare promemoria e altro ancora.

Cortana in Windows può aiutare gli utenti a gestire meglio la pianificazione e le attività. Possono aggiungere ai propri elenchi in Microsoft To Do, cercare informazioni locali, ottenere definizioni e tenere traccia delle ultime notizie, meteo e informazioni finanziarie con la ricerca di Bing.

Cortana in Windows 10, versione 2004 e successive, soddisfa le stesse promesse di privacy, sicurezza e conformità a livello aziendale per I servizi aziendali di Cortana, come illustrato nelle Condizioni dei servizi online [(OST).](https://www.microsoft.com/licensing/product-licensing/products)

### <a name="how-to-opt-out-of-cortana-in-windows-10"></a>Come rifiutare esplicitamente Cortana in Windows 10

Gli amministratori possono configurare Cortana in Windows 10 per l'organizzazione usando il criterio MDM Experience\AllowCortana o tramite Criteri di gruppo: Configurazione computer\Modelli amministrativi\Componenti di Windows\Ricerca\Consenti Cortana.

A partire da Windows 10, versione 2004, Cortana è un'app UWP (Universal Windows Platform) preinstallata con Windows e viene aggiornata regolarmente tramite Microsoft Store. Per ricevere gli aggiornamenti più recenti di Cortana, dovrai [abilitare gli aggiornamenti tramite Microsoft Store.](/windows/configuration/stop-employees-from-using-microsoft-store)

[Altre informazioni su Cortana in Windows 10](/windows/configuration/cortana-at-work/cortana-at-work-overview)

### <a name="cortana-voice-assistance-in-teams"></a>Assistenza vocale Cortana in Teams

L'assistenza vocale di Cortana nell'app Per dispositivi mobili di Teams e nei dispositivi di visualizzazione di Microsoft Teams consente agli utenti di Microsoft 365 Enterprise di semplificare le attività di comunicazione, collaborazione e riunioni tramite il linguaggio naturale parlato. Gli utenti possono parlare con Cortana selezionando il pulsante del microfono in alto a destra nell'app per dispositivi mobili di Teams o pronunciando &#8220;Cortana&#8221; nel display di Microsoft Teams. Per connettersi rapidamente con il proprio team senza problemi e mentre sono in viaggio, gli utenti possono pronunciare query come &#8220;chiamare Megan&#8221; o &#8220;inviare un messaggio alla riunione&#8221;. Gli utenti possono anche partecipare alle riunioni &#8220;partecipare al&#8221; riunione successiva e usare l'assistenza vocale per condividere file, controllare il calendario e altro ancora. Queste esperienze di assistenza vocale vengono consegnate utilizzando servizi di livello enterprise di Cortana che rispettano completamente le promesse di privacy, sicurezza e conformità di Office 365, come illustrato nelle Condizioni dei servizi [online (OST).](https://www.microsoft.com/licensing/product-licensing/products)

**Controllo amministratore**

L'assistenza vocale di Cortana verrà abilitata per impostazione predefinita per i tenant. Gli amministratori possono controllare chi nel tenant può usare l'assistenza vocale di Cortana in Teams tramite un criterio (TeamsCortanaPolicy). Questo criterio può essere impostato a livello di account utente o tenant. Gli amministratori possono anche usare il campo CortanaVoiceInvocationMode all'interno di questo controllo dei criteri per determinare se Cortana è disabilitata, abilitata solo con la chiamata al pulsante push o abilitata anche con la chiamata della parola di riattivazione (applicabile ai dispositivi che la supportano, come la visualizzazione di Microsoft Teams). Nota che al momento della versione iniziale per gli utenti di Microsoft 365 Enterprise negli Stati Uniti in inglese, l'app per dispositivi mobili Teams non supporterà l'attivazione delle parole di riattivazione, ma sarà supportata in futuro.

**Controllo utente**

I singoli utenti possono provare l'assistenza vocale di Cortana nell'app Per dispositivi mobili di Teams facendo clic sul pulsante del microfono. Possono provare l'assistenza vocale di Cortana nei dispositivi di visualizzazione di Microsoft Teams semplicemente pronunciando &#8220;Cortana.&#8221; Possono anche controllare se Cortana in Teams è abilitata per il proprio dispositivo tramite un'impostazione nell'app Per dispositivi mobili di Teams o sul display di Microsoft Teams: 

1. Aprire l'app Teams per dispositivi mobili o passare alla schermata ambientale (home) dello schermo di Microsoft Teams.

2. Nell'app Teams per dispositivi mobili passare a **Impostazioni**. Nella visualizzazione Di Microsoft Teams, selezionare l'avatar dell'utente e quindi selezionare Impostazioni. Se Cortana è abilitata, ad esempio, &#8220;Cortana, vai a Impostazioni.&#8221;

3. Seleziona **Cortana.**

4. Sposta l'interruttore **su Attivato** **o Disattivato,** a seconda che tu voglia assistenza vocale Cortana nel dispositivo.

[Altre informazioni sull'assistenza vocale di Cortana in Teams](/microsoftteams/cortana-in-teams)

### <a name="conversational-ai-in-outlook-for-ios-with-cortana"></a>IA conversazionale in Outlook per iOS con Cortana

In Outlook per iOS, l'esperienza di IA conversazionale basata sulla voce di Cortana consente agli utenti di chiedere all'assistente per la produttività di pianificare riunioni, comporre messaggi di posta elettronica, gestire il calendario e la posta in arrivo e trovare tutti i tipi di informazioni.

Usando il linguaggio naturale, il riconoscimento vocale, l'apprendimento automatico e la linguistica basati sulla tecnologia ai Microsoft, Cortana conosce il contesto per aiutarti a rimanere organizzato, connesso alle persone e alle cose importanti per te e controllare la tua giornata.

Usa semplicemente il pulsante del microfono per chiedere a Cortana di aggiungere destinatari della riunione o modificare date, ore o posizioni. Puoi anche chiedere a Cortana di trovare eventi specifici. Infine, puoi chiedere a Cortana di comporre messaggi di posta elettronica rapidi, inoltrare messaggi o rispondere ai thread. Il microfono di Cortana può anche aiutarti ad avviare Ascolta i miei messaggi di posta elettronica in Outlook per iOS, in modo da poter ascoltare la posta in arrivo senza problemi.

Inizialmente, questa nuova funzionalità di IA conversazionale con Cortana sarà disponibile in inglese per i clienti negli Stati Uniti che usano Outlook per iOS con un account aziendale di Microsoft 365. Per altre informazioni, vai [a Avviare una conversazione con l'assistente per la produttività personale in Outlook con Cortana.](https://techcommunity.microsoft.com/t5/outlook-blog/start-a-conversation-with-your-personal-productivity-assistant/ba-p/2071416#:~:text=Conversational%20AI%20allows%20you%20to,time%2C%20all%20with%20your%20voice)

### <a name="conversational-ai-with-cortana-in-outlook-with-ios-is-an-opt-in-experience"></a>L'IA conversazionale con Cortana in Outlook con iOS è un'esperienza di consenso esplicito

Ai singoli utenti verrà richiesto di acconsentire esplicitamente all'esperienza di IA conversazionale la prima volta che selezionano il pulsante del microfono "Chiedi a Cortana" in Outlook su iOS.

### <a name="play-my-emails"></a>Riproduci i miei messaggi di posta elettronica

Ascolta i miei messaggi di posta elettronica (connessi tramite Outlook mobile) è un'esperienza vocale e senza mani per consentire agli utenti di ascoltare nuovi messaggi nella posta in arrivo con stato attivo e le modifiche apportate alla giornata tramite gli altoparlanti del telefono, delle cuffie o del dispositivo audio connesso. Gli utenti possono chiedere a Cortana di leggere ad alta voce i messaggi di posta elettronica recenti e di chiedere a Cortana di eseguire azioni quali contrassegnare, archiviare, eliminare e ignorare i messaggi. Questa funzionalità è particolarmente utile per recuperare la posta elettronica durante il tragitto, il multitasking o in viaggio. Quando l'utente parla con Cortana in Riproduci i miei messaggi di posta elettronica, la richiesta audio vocale viene inviata direttamente a Cortana Enterprise Services. Un text to speech readout del messaggio di posta elettronica dell'utente viene elaborato all'interno del cloud di Office 365. Durante questo processo, i dati di Office 365 non vengono elaborati nel dispositivo mobile dell'utente e non vengono salvati dati di posta elettronica. Una trascrizione dei comandi pronunciati (ad esempio"segna come letto", "successivo", "contrassegno" e così via) può essere mantenuta in conformità alle Condizioni per la protezione dei dati nelle Condizioni dei Microsoft [Online Services.](https://www.microsoft.com/licensing/product-licensing/products)

Cortana chiamerà quando un messaggio di posta elettronica è protetto e si sospende brevemente prima di leggere il messaggio per concedere agli utenti tempo sufficiente per sospendere la riproduzione o passare al messaggio successivo. Analogamente a una telefonata privata, gli utenti devono prestare attenzione quando avviano la riproduzione in posizioni in cui le informazioni riservate potrebbero essere potenzialmente udite. In questi casi, è consigliabile che i dipendenti dell'organizzazione indossino le cuffie in ambienti appropriati quando si utilizza Play My Emails in Outlook mobile.


### <a name="opt-out-of-play-my-emails"></a>Rifiutare esplicitamente l'opzione Riproduci i miei messaggi di posta elettronica

Gli utenti possono rifiutare esplicitamente la funzionalità Riproduci i miei messaggi di posta elettronica seguendo la procedura seguente.

1. Aprire Outlook mobile.

2. Vai a **Impostazioni**.
  
3. Seleziona **Riproduci i miei messaggi di posta elettronica**.

4. Spostare l'interruttore su off per gli account che si desidera disabilitare.

[Ulteriori informazioni su Riproduci i miei messaggi di posta elettronica](https://support.microsoft.com/help/4558256)

### <a name="briefing-email"></a>Briefing email

Cortana invia un messaggio di posta elettronica di briefing personalizzato con  le attività e gli impegni presi con un modo pratico per contrassegnarli come completati o pianificare il tempo di messa a fuoco per farli fare. Include inoltre un riepilogo delle riunioni e dei documenti rilevanti per la giornata. Cortana estrae le informazioni dai messaggi di posta elettronica di un utente e le archivia nella cassetta postale di Exchange Online finché non vengono consolidate nel messaggio di posta elettronica briefing. In nessun momento i dati personali sono accessibili all'esterno della cassetta postale di Exchange Online.

### <a name="how-to-opt-out-of-briefing-email"></a>Come rifiutare esplicitamente la posta elettronica di briefing

Gli amministratori possono configurare briefing per l'organizzazione usando [PowerShell](/briefing/be-admin) in Exchange Online. Gli utenti possono rifiutare esplicitamente l'e-mail di briefing di Cortana selezionando **Annulla** sottoscrizione nel piè di pagina del messaggio.

[Ulteriori informazioni sul messaggio di posta elettronica briefing](https://support.microsoft.com/help/4558259)

Continueremo a presentare altre esperienze come le precedenti per aumentare la produttività dell'organizzazione.

[Ulteriori informazioni sulle offerte di conformità Microsoft](/compliance/regulatory/offering-home)

## <a name="how-is-the-delivery-of-cortana-enterprise-services-different-from-the-delivery-of-other-cortana-features-i-may-have-previously-experienced"></a>In che modo la distribuzione dei servizi enterprise di Cortana è diversa dalla distribuzione di altre funzionalità di Cortana che ho già riscontrato in precedenza?

Ecco i due modi per pensare al funzionamento di Cortana nella tua azienda:

**Nuove esperienze per le organizzazioni con Cortana Enterprise Services**: I servizi enterprise di Cortana sono progettati per soddisfare le esigenze di sicurezza e conformità delle organizzazioni: 

1. Si tratta di un nuovo servizio e viene illustrato qui in questo documento.

2. Per i servizi soggetti alle Condizioni per i Servizi online, Microsoft è un data processor: Microsoft raccoglie e utilizza i dati dei clienti solo per fornire i servizi online richiesti dai clienti e per gli scopi forniti dai clienti. Ai sensi del Regolamento generale sulla protezione dei dati (GDPR) dell'UE, il cliente è il controllore dei dati dei dati. Vedi le [Condizioni per i Servizi online](https://www.microsoft.com/licensing/product-licensing/products) e Introduzione a una maggiore trasparenza della privacy per i nostri clienti di cloud [commerciali.](https://blogs.microsoft.com/eupolicy/2019/11/18/introducing-privacy-transparency-commercial-cloud-customers/)

3. Ad esempio, Play My Emails è un servizio Cortana a cui gli utenti possono connettersi tramite Outlook per iOS e utilizza I servizi aziendali di Cortana. 

4. Gli amministratori IT avranno sempre controlli per le esperienze connesse facoltative per Cortana, in modo analogo alle esperienze connesse facoltative durante l'uso delle applicazioni di Office ProPlus.  

Servizi **esistenti** per i consumatori : I servizi connessi facoltativi di Cortana sono progettati principalmente per le esperienze degli utenti e sono attualmente disponibili in Windows 10 (versione 1909 e versioni precedenti) e nell'app Cortana in iOS e Android.

1. Queste esperienze consentono funzionalità quali meteo, notizie e traffico.

2. Gli amministratori tenant possono controllare se Cortana in Windows 10 (versione 1909 e versioni precedenti) e l'app Cortana in iOS e Android sono in grado di consentire a Cortana di connettersi ai dati del tenant di Office 365.

Disattivare l'accesso di Cortana ai dati ospitati da Microsoft dell'organizzazione

1. Nell'interfaccia di amministrazione di Microsoft 365 seleziona **Impostazioni**  >  **Impostazioni organizzazione** e seleziona **Cortana.**

2. Deseleziona la casella di controllo Consenti **a Cortana in Windows 10 (versione 1909** e versioni precedenti) e all'app Cortana in iOS e Android di accedere ai dati ospitati da Microsoft per conto delle persone dell'organizzazione per disabilitare le esperienze connesse a Cortana.

3. Selezionare **Salva modifiche**.

Per i servizi disciplinati dal [Contratto di servizi Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=2109174) e dall'Informativa sulla privacy [Microsoft,](https://privacy.microsoft.com/privacystatement)Microsoft è il controllore dei dati. In qualità di data controller, Microsoft usa i dati per migliorare prodotti e servizi in conformità [all'Informativa sulla privacy microsoft.](https://privacy.microsoft.com/privacystatement)