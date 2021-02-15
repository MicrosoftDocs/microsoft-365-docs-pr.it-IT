---
title: Criteri di avviso nei Centri sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: 8927b8b9-c5bc-45a8-a9f9-96c732e58264
ms.custom:
- seo-marvel-apr2020
description: Creare criteri di avviso nel Centro sicurezza e conformità in Office 365 e Microsoft 365 per monitorare potenziali minacce, perdita di dati e problemi relativi alle autorizzazioni.
ms.openlocfilehash: a0bf22b8dc4f8b3c40b60509b4230922ba762024
ms.sourcegitcommit: 31be333178b934c519f419656f4c3a53e1beffdc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "49881819"
---
# <a name="alert-policies-in-the-security-and-compliance-center"></a>Criteri di avviso nel Centro sicurezza e conformità

È possibile utilizzare i criteri di avviso e gli strumenti del dashboard degli avvisi nei Centri sicurezza e conformità di Microsoft 365 per creare criteri di avviso e quindi visualizzare gli avvisi generati quando gli utenti eseguono attività che soddisfano le condizioni di un criterio di avviso. Esistono diversi criteri di avviso predefiniti che consentono di monitorare attività quali l'assegnazione di privilegi di amministratore in Exchange Online, attacchi di malware, campagne di phishing e livelli insoliti di eliminazione dei file e condivisione esterna.

I criteri di avviso consentono di categorizzare gli avvisi attivati da un criterio, applicare il criterio a tutti gli utenti dell'organizzazione, impostare un livello di soglia per l'attivazione di un avviso e decidere se ricevere notifiche tramite posta elettronica quando vengono attivati avvisi. Nel Centro sicurezza  e conformità è inoltre disponibile una pagina Visualizza avvisi in cui è possibile visualizzare e filtrare gli avvisi, impostare uno stato di avviso per gestire gli avvisi e quindi ignorare gli avvisi dopo aver risolto o risolto l'evento imprevisto sottostante.

> [!NOTE]
> I criteri di avviso sono disponibili per le organizzazioni con un abbonamento a Microsoft 365 Enterprise, Office 365 Enterprise o Office 365 US Government E1/F1/G1, E3/F3/G3 o E5/G5. Le funzionalità avanzate sono disponibili solo per le organizzazioni con una sottoscrizione E5/G5 o per le organizzazioni che dispongono di una sottoscrizione E1/F1/G1 o E3/F3/G3 e di Microsoft Defender per Office 365 P2 o conformità Microsoft 365 E5 o un abbonamento al componente aggiuntivo eDiscovery e controllo E5. La funzionalità che richiede un abbonamento a E5/G5 o a un componente aggiuntivo è evidenziata in questo argomento. Si noti inoltre che i criteri di avviso sono disponibili negli ambienti office 365 GCC, GCC High e DoD US government.

## <a name="how-alert-policies-work"></a>Funzionamento dei criteri di avviso

Ecco una rapida panoramica del funzionamento dei criteri di avviso e degli avvisi che vengono attivati quando l'attività dell'utente o dell'amministratore soddisfa le condizioni di un criterio di avviso.

![Panoramica del funzionamento dei criteri di avviso](../media/e02a622d-b429-448b-8107-dd1a4770b4e0.png)

1. Un amministratore dell'organizzazione crea, configura e attiva un criterio di avviso usando la pagina **Criteri** di avviso nel Centro sicurezza e conformità. È inoltre possibile creare criteri di avviso utilizzando il cmdlet [New-ProtectionAlert](https://docs.microsoft.com/powershell/module/exchange/new-protectionalert) in PowerShell & Centro sicurezza e conformità.

   Per creare criteri di avviso, è necessario disporre del ruolo Gestisci avvisi o Configurazione organizzazione nel Centro sicurezza e conformità.

   > [!NOTE]
   > Sono necessarie fino a 24 ore dopo la creazione o l'aggiornamento di un criterio di avviso prima che gli avvisi possano essere attivati dal criterio. Questo perché il criterio deve essere sincronizzato con il motore di rilevamento degli avvisi.

2. Un utente esegue un'attività che soddisfa le condizioni di un criterio di avviso. In caso di attacchi malware, i messaggi di posta elettronica infetti inviati agli utenti dell'organizzazione attivano un avviso.

3. Microsoft 365 genera un avviso visualizzato  nella pagina Visualizza avvisi nel Centro sicurezza & conformità. Inoltre, se le notifiche tramite posta elettronica sono abilitate per il criterio di avviso, Microsoft invia una notifica a un elenco di destinatari. Gli avvisi che possono essere visualizzati da un amministratore o da altri utenti nella pagina Visualizza avvisi sono determinati dai ruoli assegnati all'utente. Per ulteriori informazioni, vedere [Autorizzazioni RBAC necessarie per visualizzare gli avvisi.](#rbac-permissions-required-to-view-alerts)

4. Un amministratore gestisce gli avvisi nel Centro sicurezza e conformità. La gestione degli avvisi consiste nell'assegnare uno stato di avviso per tenere traccia e gestire qualsiasi indagine.

## <a name="alert-policy-settings"></a>Impostazioni dei criteri di avviso

Un criterio di avviso è costituito da un set di regole e condizioni che definiscono l'attività dell'utente o dell'amministratore che genera un avviso, un elenco di utenti che attivano l'avviso se eseguono l'attività e una soglia che definisce quante volte deve verificarsi l'attività prima che venga attivato un avviso. È inoltre possibile categorizzare il criterio e assegnare un livello di gravità. Queste due impostazioni consentono di gestire i criteri di avviso (e gli avvisi attivati quando vengono soddisfatte le condizioni dei criteri) perché è possibile filtrare in base a queste impostazioni durante la gestione dei criteri e la visualizzazione degli avvisi nel Centro sicurezza e conformità. Ad esempio, è possibile visualizzare gli avvisi che soddisfano le condizioni della stessa categoria o visualizzare gli avvisi con lo stesso livello di gravità.

Per visualizzare e creare criteri di avviso, passare [https://protection.office.com](https://protection.office.com) a e selezionare Criteri  \> **avvisi.**

![Nel Centro sicurezza e conformità selezionare Avvisi, quindi selezionare Criteri di avviso per visualizzare e creare criteri di avviso](../media/09ebd451-8e84-44e1-aefc-63e70bba4d97.png)

Un criterio di avviso è costituito dalle impostazioni e dalle condizioni seguenti.

- **Attività** monitorata dall'avviso: è possibile creare un criterio per tenere traccia di un'attività o, in alcuni casi, di alcune attività correlate, ad esempio la condivisione di un file con un utente esterno, la condivisione, l'assegnazione delle autorizzazioni di accesso o la creazione di un collegamento anonimo. Quando un utente esegue l'attività definita dal criterio, viene attivato un avviso in base alle impostazioni di soglia dell'avviso.

    > [!NOTE]
    > Le attività che è possibile tenere traccia dipendono dal piano di Office 365 Enterprise o Office 365 US Government dell'organizzazione. In generale, le attività relative alle campagne antimalware e agli attacchi di phishing richiedono una sottoscrizione E5/G5 o una sottoscrizione E1/F1/G1 o E3/F3/G3 con un abbonamento al componente aggiuntivo Defender per [Office 365](../security/office-365-security/office-365-atp.md) Piano 2.

- **Condizioni di** attività: per la maggior parte delle attività, è possibile definire condizioni aggiuntive che devono essere soddisfatte per attivare un avviso. Le condizioni comuni includono gli indirizzi IP (in modo che un avviso sia attivato quando l'utente esegue l'attività su un computer con un indirizzo IP specifico o all'interno di un intervallo di indirizzi IP), se un avviso viene attivato se un utente o un utente specifico esegue tale attività e se l'attività viene eseguita su un nome file o UN URL specifico. È inoltre possibile configurare una condizione che attiva un avviso quando l'attività viene eseguita da qualsiasi utente dell'organizzazione. Le condizioni disponibili dipendono dall'attività selezionata.

- **Quando l'avviso viene attivato:** puoi configurare un'impostazione che definisce la frequenza con cui può verificarsi un'attività prima dell'attivazione di un avviso. Ciò consente di configurare un criterio per generare un avviso ogni volta che un'attività soddisfa le condizioni dei criteri, quando viene superata una determinata soglia o quando l'occorrenza dell'attività che l'avviso sta verificando diventa insolita per l'organizzazione.

    ![Configurare la modalità di attivazione degli avvisi, in base al momento in cui si verifica l'attività, a una soglia o a un'attività insolita per l'organizzazione](../media/97ee1ed2-e7a9-47a2-a980-5f9f63872c65.png)

    Se si seleziona l'impostazione in base a un'attività insolita, Microsoft stabilisce un valore di base che definisce la frequenza normale per l'attività selezionata. Per stabilire questa linea di base sono necessari fino a sette giorni, durante i quali non verranno generati avvisi. Una volta stabilita la linea di base, viene attivato un avviso quando la frequenza dell'attività monitorata dal criterio di avviso supera notevolmente il valore di base. Per le attività correlate al controllo , ad esempio le attività su file e cartelle, è possibile stabilire una linea di base basata su un singolo utente o su tutti gli utenti dell'organizzazione. per le attività correlate al malware, è possibile stabilire una linea di base basata su una singola famiglia di malware, su un singolo destinatario o su tutti i messaggi nell'organizzazione.

    > [!NOTE]
    > La possibilità di configurare i criteri di avviso in base a una soglia o a un'attività insolita richiede una sottoscrizione E5/G5 o una sottoscrizione E1/F1/G1 o E3/F3/G3 con un abbonamento al componente aggiuntivo Microsoft Defender per Office 365 P2, Conformità Microsoft 365 E5 o Microsoft 365 eDiscovery and Audit. Le organizzazioni con una sottoscrizione E1/F1/G1 ed E3/F3/G3 possono creare solo criteri di avviso in cui viene attivato un avviso ogni volta che si verifica un'attività.

- **Categoria di** avviso: per facilitare il rilevamento e la gestione degli avvisi generati da un criterio, è possibile assegnare una delle categorie seguenti a un criterio.

  - Prevenzione della perdita di dati

  - Governance delle informazioni

  - Flusso di posta

  - Autorizzazioni

  - Gestione dei rischi

  - Altri

  Quando si verifica un'attività che soddisfa le condizioni del criterio di avviso, l'avviso generato viene contrassegnato con la categoria definita in questa impostazione. Ciò consente di tenere traccia e gestire gli  avvisi con la stessa impostazione di categoria nella pagina Visualizza avvisi nel Centro sicurezza e conformità perché è possibile ordinare e filtrare gli avvisi in base alla categoria.

- **Gravità dell'avviso:** analogamente alla categoria di avviso, ai criteri di avviso viene assegnato un attributo di gravità (**Basso,** **Medio,** Alto o Informativo). Come la categoria di avviso, quando si verifica un'attività che soddisfa le condizioni del criterio di avviso, l'avviso generato viene contrassegnato con lo stesso livello di gravità impostato per il criterio di avviso. Anche in questo caso, questo consente di tenere traccia e gestire gli avvisi con la stessa impostazione di gravità nella **pagina Visualizza** avvisi. Ad esempio, è possibile filtrare l'elenco  di avvisi in modo che siano visualizzati solo gli avvisi con gravità elevata.

    > [!TIP]
    > Quando si configura un criterio di avviso, è consigliabile assegnare una gravità superiore alle attività che possono comportare conseguenze molto negative, ad esempio il rilevamento di malware dopo la consegna agli utenti, la visualizzazione di dati sensibili o classificati, la condivisione di dati con utenti esterni o altre attività che possono comportare la perdita di dati o minacce alla sicurezza. Ciò consente di definire la priorità degli avvisi e le azioni da intraprendere per analizzare e risolvere le cause sottostanti.

- **Notifiche tramite** posta elettronica: è possibile configurare il criterio in modo che le notifiche tramite posta elettronica siano inviate (o non inviate) a un elenco di utenti quando viene attivato un avviso. Puoi anche impostare un limite giornaliero per le notifiche in modo che, una volta raggiunto il numero massimo di notifiche, non verranno inviate altre notifiche per l'avviso durante tale giorno. Oltre alle notifiche tramite posta elettronica, l'utente o altri amministratori possono visualizzare gli avvisi attivati da un criterio nella **pagina Visualizza** avvisi. Prendere in considerazione l'abilitazione delle notifiche di posta elettronica per i criteri di avviso di una categoria specifica o con un'impostazione di gravità superiore.

## <a name="default-alert-policies"></a>Criteri di avviso predefiniti

Microsoft fornisce criteri di avviso predefiniti che consentono di identificare l'abuso delle autorizzazioni dell'amministratore di Exchange, l'attività di malware, potenziali minacce esterne ed interne e i rischi di governance delle informazioni. Nella pagina **Criteri di** avviso i nomi di questi criteri predefiniti sono in grassetto e il tipo di criterio è definito come **Sistema.** Questi criteri sono attivati per impostazione predefinita. È possibile disattivare questi criteri (o riattivarlo), configurare un elenco di destinatari a cui inviare notifiche tramite posta elettronica e impostare un limite giornaliero per le notifiche. Le altre impostazioni per questi criteri non possono essere modificate.

Nella tabella seguente sono elencati e descritti i criteri di avviso predefiniti disponibili e la categoria a cui è assegnato ogni criterio. La categoria viene utilizzata per determinare quali avvisi possono essere visualizzati da un utente nella pagina Visualizza avvisi. Per ulteriori informazioni, vedere [Autorizzazioni RBAC necessarie per visualizzare gli avvisi.](#rbac-permissions-required-to-view-alerts)

La tabella indica anche il piano di Office 365 Enterprise e Office 365 US Government necessario per ognuno di essi. Alcuni criteri di avviso predefiniti sono disponibili se l'organizzazione dispone dell'abbonamento al componente aggiuntivo appropriato oltre a una sottoscrizione E1/F1/G1 o E3/F3/G3.

| Criterio di avviso predefinito | Descrizione | Categoria | Sottoscrizione Enterprise |
|:-----|:-----|:-----|:-----|
|**È stato rilevato un clic su UN URL potenzialmente dannoso**|Genera un avviso quando un utente protetto da [collegamenti](../security/office-365-security/atp-safe-links.md) sicuri nell'organizzazione fa clic su un collegamento dannoso. Questo evento viene attivato quando le modifiche al verdetto URL vengono identificate da Microsoft Defender per Office 365 o quando gli utenti sostituiscono le pagine Collegamenti sicuri (in base ai criteri collegamenti sicuri di Microsoft 365 per le aziende dell'organizzazione). Questo criterio di avviso ha **un'impostazione** di gravità elevata. Per i clienti di Defender per Office 365 P2, E5, G5, questo avviso attiva automaticamente l'indagine e la risposta [automatizzate in Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Per ulteriori informazioni sugli eventi che attivano questo avviso, vedere [Set up Safe Links policies.](../security/office-365-security/set-up-atp-safe-links-policies.md)|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Risultato dell'invio dell'amministratore completato**|Genera un avviso quando un [invio dell'amministratore](../security/office-365-security/admin-submission.md) completa la nuova analisi dell'entità inviata. Verrà attivato un avviso ogni volta che viene eseguito il rendering di un risultato di nuova analisi da un invio da amministratore. Questi avvisi hanno lo scopo di ricordare all'utente di esaminare i risultati degli invii [precedenti,](https://protection.office.com/reportsubmission)inviare messaggi segnalati dall'utente per ottenere il controllo dei criteri più recente e analizzare nuovamente i verdetti e aiutare a determinare se i criteri di filtro nell'organizzazione hanno l'impatto previsto. Questo criterio ha **un'impostazione di** gravità bassa.|Gestione dei rischi|E1/F1, E3/F3 o E5|
|**L'amministratore ha avviato un'indagine manuale della posta elettronica**|Genera un avviso quando un amministratore attiva l'analisi manuale di un messaggio di posta elettronica da Esplora minacce. Per ulteriori informazioni, vedere [Esempio: un amministratore della sicurezza attiva un'indagine da Esplora minacce] ( https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) . Questo avviso informa l'organizzazione che l'indagine è stata avviata. L'avviso fornisce informazioni su chi l'ha attivato e include un collegamento all'indagine. Questo criterio ha **un'impostazione di gravità** informativo.|Gestione dei rischi| Abbonamento al componente aggiuntivo E5/G5 o Microsoft Defender per Office 365 P2| 
|**Creazione della regola di inoltro/reindirizzamento**|Genera un avviso quando un utente dell'organizzazione crea una regola di Posta in arrivo per la propria cassetta postale che inoltra o reindirizza i messaggi a un altro account di posta elettronica. Questo criterio tiene traccia solo delle regole di Posta in arrivo create utilizzando Outlook sul Web (in precedenza noto come Outlook Web App) o PowerShell di Exchange Online. Questo criterio ha **un'impostazione di** gravità bassa. Per ulteriori informazioni sull'utilizzo delle regole di Posta in arrivo per inoltrare e reindirizzare la posta elettronica in Outlook sul Web, vedere Utilizzare le regole in Outlook sul Web per inoltrare automaticamente i messaggi [a un altro account.](https://support.office.com/article/1433e3a0-7fb0-4999-b536-50e05cb67fed)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Ricerca eDiscovery avviata o esportata**|Genera un avviso quando qualcuno usa lo strumento ricerca contenuto nel Centro sicurezza e conformità. Viene attivato un avviso quando vengono eseguite le attività di ricerca contenuto seguenti: <br/><br/>* Viene avviata una ricerca di contenuto<br/>* I risultati di una ricerca di contenuto vengono esportati<br/>* Viene esportato un report di ricerca di contenuto<br/><br/>Gli avvisi vengono attivati anche quando le precedenti attività di ricerca contenuto vengono eseguite in associazione a un caso di eDiscovery. Questo criterio ha **un'impostazione di** gravità Media. Per ulteriori informazioni sulle attività di ricerca di contenuto, vedere Cercare le attività [di eDiscovery nel log di controllo.](search-for-ediscovery-activities-in-the-audit-log.md#ediscovery-activities)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Elevazione dei privilegi di amministratore di Exchange**|Genera un avviso quando a un utente vengono assegnate autorizzazioni amministrative nell'organizzazione di Exchange Online. Ad esempio, quando un utente viene aggiunto al gruppo di ruoli Gestione organizzazione in Exchange Online. Questo criterio ha **un'impostazione di** gravità bassa.|Autorizzazioni|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Messaggi di posta elettronica contenenti malware rimosso dopo il recapito**|Genera un avviso quando i messaggi contenenti malware vengono recapitati alle cassette postali dell'organizzazione. Se si verifica questo evento, Microsoft rimuove i messaggi infetti dalle cassette postali di Exchange Online utilizzando [l'eliminazione automatica zero-hour.](../security/office-365-security/zero-hour-auto-purge.md) Questo criterio ha **un'impostazione di gravità** informativo e attiva automaticamente l'indagine e la risposta [automatizzate in Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Microsoft Defender per Office 365 P2|
|**Messaggi di posta elettronica contenenti URL di phish rimossi dopo il recapito**|Genera un avviso quando i messaggi contenenti phish vengono recapitati alle cassette postali dell'organizzazione. Se si verifica questo evento, Microsoft rimuove i messaggi infetti dalle cassette postali di Exchange Online utilizzando [l'eliminazione automatica zero-hour.](../security/office-365-security/zero-hour-auto-purge.md) Questo criterio ha **un'impostazione di gravità** informativo e attiva automaticamente l'indagine e la risposta [automatizzate in Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Posta elettronica segnalata dall'utente come malware o malware**|Genera un avviso quando gli utenti dell'organizzazione segnalano i messaggi come posta elettronica di phishing utilizzando il componente aggiuntivo Segnala messaggio. Questo criterio ha **un'impostazione di gravità** informativo. Per ulteriori informazioni su questo componente aggiuntivo, vedere Utilizzare il componente [aggiuntivo Segnala messaggio.](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) Per i clienti di Defender per Office 365 P2, E5, G5, questo avviso attiva automaticamente l'indagine e la risposta [automatizzate in Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Limite di invio della posta elettronica superato**|Genera un avviso quando un utente dell'organizzazione ha inviato più posta di quella consentita dal criterio di posta indesiderata in uscita. Si tratta in genere di un'indicazione che l'utente sta inviando troppi messaggi di posta elettronica o che l'account potrebbe essere compromesso. Questo criterio ha **un'impostazione di** gravità Media. Se si ottiene un avviso generato da questo criterio di avviso, è una buona idea verificare se [l'account utente è compromesso.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Modulo bloccato a causa di un potenziale tentativo di phishing**|Genera un avviso quando a un utente dell'organizzazione è stata consentita la condivisione di moduli e la raccolta delle risposte tramite Microsoft Forms a causa di un tentativo di phishing ripetuto rilevato. Questo criterio ha **un'impostazione di gravità** elevata.|Gestione dei rischi|E1, E3/F3 o E5|
|**Modulo contrassegnato e confermato come phishing**|Genera un avviso quando un modulo creato in Microsoft Forms dall'interno dell'organizzazione è stato identificato come potenziale phishing tramite segnalazione di abuso e confermato come phishing da Microsoft. Questo criterio ha **un'impostazione di** gravità elevata.|Gestione dei rischi|E1, E3/F3 o E5|
|**I messaggi sono stati ritardati**|Genera un avviso quando Microsoft non è in grado di recapitare messaggi di posta elettronica all'organizzazione locale o a un server partner utilizzando un connettore. In questo caso, il messaggio viene accodato in Office 365. Questo avviso viene attivato quando sono presenti 2.000 messaggi o più che sono stati accodati per più di un'ora. Questo criterio ha **un'impostazione di** gravità elevata.|Flusso di posta|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Campagna antimalware rilevata dopo la consegna**|Genera un avviso quando un numero insolitamente elevato di messaggi contenenti malware viene recapitato alle cassette postali dell'organizzazione. Se si verifica questo evento, Microsoft rimuove i messaggi infetti dalle cassette postali di Exchange Online. Questo criterio ha **un'impostazione di** gravità elevata.|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Microsoft Defender per Office 365 P2|
|**Campagna antimalware rilevata e bloccata**|Genera un avviso quando qualcuno ha tentato di inviare un numero insolitamente elevato di messaggi di posta elettronica contenenti un determinato tipo di malware agli utenti dell'organizzazione. Se si verifica questo evento, i messaggi infetti vengono bloccati da Microsoft e non recapitati alle cassette postali. Questo criterio ha **un'impostazione di** gravità bassa.|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Campagna antimalware rilevata in SharePoint e OneDrive**|Genera un avviso quando viene rilevato un volume insolitamente elevato di malware o virus nei file che si trovano nei siti di SharePoint o negli account di OneDrive nell'organizzazione. Questo criterio ha **un'impostazione di** gravità elevata.|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Malware non zapped because ZAP is disabled**| Genera un avviso quando Microsoft rileva il recapito di un messaggio di malware a una cassetta postale perché Zero-Hour l'eliminazione automatica per i messaggi di phish è disabilitata. Questo criterio ha **un'impostazione di gravità** informativo. |Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Phish recapitato perché la cartella Posta indesiderata di un utente è disabilitata**|Genera un avviso quando Microsoft rileva che la cartella Posta indesiderata di un utente è disabilitata, consentendo il recapito di un messaggio di phishing ad alta probabilità a una cassetta postale. Questo criterio ha **un'impostazione di gravità** informativo.|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P1 o P2|
|**Phish recapitato a causa di una sostituzione ETR**|Genera un avviso quando Microsoft rileva una regola di trasporto di Exchange (ETR) che ha consentito il recapito di un messaggio di phishing ad alta probabilità a una cassetta postale. Questo criterio ha **un'impostazione di gravità** informativo. Per ulteriori informazioni sulle regole di trasporto di Exchange (regole del flusso di posta), vedere Regole del flusso di posta [(regole di trasporto) in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P1 o P2|
|**Phish recapitato a causa di un criterio di ip consentiti**|Genera un avviso quando Microsoft rileva un criterio ip consentiti che consente il recapito di un messaggio di phishing ad alta probabilità a una cassetta postale. Questo criterio ha **un'impostazione di gravità** informativo. Per ulteriori informazioni sui criteri ip consentiti (filtro connessioni), vedere Configurare il criterio di filtro delle connessioni [predefinito - Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy)|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P1 o P2|
|**Phish non zapped because ZAP is disabled**| Genera un avviso quando Microsoft rileva il recapito di un messaggio di phishing ad alta probabilità a una cassetta postale perché Zero-Hour l'eliminazione automatica per i messaggi di phishing è disabilitata. Questo criterio ha **un'impostazione di gravità** informativo.|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Phish recapitato a causa della sostituzione del tenant o dell'utente**<sup>1</sup>|Genera un avviso quando Microsoft rileva che l'override di un amministratore o di un utente ha consentito il recapito di un messaggio di phishing a una cassetta postale. Esempi di sostituzioni includono una cartella Posta in arrivo o una regola del flusso di posta che consente i messaggi provenienti da un mittente o dominio specifico o un criterio di protezione da posta indesiderata che consente i messaggi provenienti da domini o mittenti specifici. Questo criterio ha **un'impostazione di** gravità elevata.|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Attività di inoltro della posta elettronica sospetta**|Genera un avviso quando un utente dell'organizzazione ha inviato automaticamente un messaggio di posta elettronica a un account esterno sospetto. Si tratta di un avviso anticipato per il comportamento che potrebbe indicare che l'account è compromesso, ma non abbastanza grave da limitare l'utente. Questo criterio ha **un'impostazione di** gravità Media. Anche se è raro, un avviso generato da questo criterio potrebbe essere un'anomalia. È buona idea verificare se [l'account utente è compromesso.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Rilevati modelli di invio di posta elettronica sospetti**|Genera un avviso quando un utente dell'organizzazione ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato all'invio di posta elettronica. Si tratta di un avviso anticipato per il comportamento che potrebbe indicare che l'account è compromesso, ma non abbastanza grave da limitare l'utente. Questo criterio ha **un'impostazione di** gravità Media. Anche se è raro, un avviso generato da questo criterio potrebbe essere un'anomalia. Tuttavia, è una buona idea verificare [se l'account utente è compromesso.](../security/office-365-security/responding-to-a-compromised-email-account.md)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5  |
|**Tenant con restrizioni per l'invio di posta elettronica**|Genera un avviso quando la maggior parte del traffico di posta elettronica proveniente dall'organizzazione viene rilevata come sospetta e Microsoft ha limitato l'invio di posta elettronica all'organizzazione. Analizzare eventuali account utente e amministratore potenzialmente compromessi, nuovi connettori o inoltri aperti, quindi contattare il supporto tecnico Microsoft per sbloccare l'organizzazione. Questo criterio ha **un'impostazione di** gravità elevata. Per ulteriori informazioni sui motivi per cui le organizzazioni sono bloccate, vedere Risolvere i problemi di recapito della posta elettronica per il codice di errore [5.7.7xx in Exchange Online.](https://go.microsoft.com/fwlink/?linkid=2022138)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Attività insolita nei file degli utenti esterni**|Genera un avviso quando viene eseguito un numero insolitamente elevato di attività sui file in SharePoint o OneDrive da parte di utenti esterni all'organizzazione. Sono incluse attività quali l'accesso ai file, il download e l'eliminazione di file. Questo criterio ha **un'impostazione di** gravità elevata.|Governance delle informazioni|Abbonamento al componente aggiuntivo E5/G5, Microsoft Defender per Office 365 P2 o Microsoft 365 E5|
|**Volume insolito di condivisione file esterna**|Genera un avviso quando un numero insolitamente elevato di file in SharePoint o OneDrive viene condiviso con utenti esterni all'organizzazione. Questo criterio ha **un'impostazione di** gravità Media.|Governance delle informazioni|Abbonamento al componente aggiuntivo E5/G5, Defender per Office 365 P2 o Microsoft 365 E5|
|**Volume insolito di eliminazione dei file**|Genera un avviso quando un numero insolitamente elevato di file viene eliminato in SharePoint o OneDrive in un breve intervallo di tempo. Questo criterio ha **un'impostazione di** gravità Media.|Governance delle informazioni|Abbonamento al componente aggiuntivo E5/G5, Defender per Office 365 P2 o Microsoft 365 E5|
|**Aumento insolito della posta elettronica segnalato come phish**|Genera un avviso quando si verifica un aumento significativo del numero di persone nell'organizzazione utilizzando il componente aggiuntivo Segnala messaggio in Outlook per segnalare i messaggi come posta di phishing. Questo criterio ha **un'impostazione di** gravità elevata. Per ulteriori informazioni su questo componente aggiuntivo, vedere Utilizzare il componente [aggiuntivo Segnala messaggio.](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Phish di rappresentazione utente recapitato nella cartella posta in**<sup>arrivo/cartella 1,</sup><sup>2</sup>|Genera un avviso quando Microsoft rileva che l'override di un amministratore o di un utente ha consentito il recapito di un messaggio di phishing di imitazione utente nella posta in arrivo (o in un'altra cartella accessibile dall'utente) di una cassetta postale. Esempi di sostituzioni includono una cartella Posta in arrivo o una regola del flusso di posta che consente i messaggi provenienti da un mittente o dominio specifico o un criterio di protezione da posta indesiderata che consente i messaggi provenienti da domini o mittenti specifici. Questo criterio ha **un'impostazione di** gravità Media.|Gestione dei rischi|Abbonamento al componente aggiuntivo E5/G5 o Defender per Office 365 P2|
|**Utente con restrizioni per l'invio di posta elettronica**|Genera un avviso quando a un utente dell'organizzazione viene limitato l'invio di posta in uscita. Ciò si verifica in genere quando un account viene  compromesso e l'utente viene elencato nella pagina Utenti con restrizioni nel Centro sicurezza & conformità. Per accedere a questa pagina, passare a **Gestione delle minacce > Esaminare > utenti con restrizioni**). Questo criterio ha **un'impostazione di** gravità elevata. Per ulteriori informazioni sugli utenti con restrizioni, vedere Rimozione di un utente, un dominio o un indirizzo IP da un elenco di blocco dopo l'invio di posta [indesiderata.](https://docs.microsoft.com/office365/securitycompliance/removing-user-from-restricted-users-portal-after-spam)|Gestione dei rischi|E1/F1/G1, E3/F3/G3 o E5/G5|
|**Utenti con restrizioni per la condivisione di moduli e la raccolta di risposte**|Genera un avviso quando a un utente dell'organizzazione è stata consentita la condivisione di moduli e la raccolta delle risposte tramite Microsoft Forms a causa di un tentativo di phishing ripetuto rilevato. Questo criterio ha **un'impostazione di** gravità elevata.|Gestione dei rischi|E1, E3/F3 o E5|
|||||

> [!NOTE]
> <sup>1</sup> Abbiamo rimosso temporaneamente questo criterio di avviso predefinito in base al feedback dei clienti. We're working to improve it, and will replace it with a new version in the near future. Fino a quel momento, puoi creare un criterio di avviso personalizzato per sostituire questa funzionalità usando le impostazioni seguenti:<br/>&nbsp; * L'attività è un messaggio di posta elettronica di phish rilevato al momento del recapito<br/>&nbsp; * Mail is not ZAP'd<br/>&nbsp; * La direzione della posta è in ingresso<br/>&nbsp; * Lo stato del recapito della posta è Recapitato<br/>&nbsp; * La tecnologia di rilevamento è la conservazione degli URL dannosi, la detonazione di URL, il filtro di phish avanzato, il filtro di phish generale, la rappresentazione del dominio, la rappresentazione utente e la rappresentazione del marchio<br/><br/>&nbsp;&nbsp;&nbsp;Per ulteriori informazioni sull'anti-phishing in Office 365, vedere Configurare i criteri [anti-phishing e anti-phishing.](../security/office-365-security/set-up-anti-phishing-policies.md)<br/><br/><sup>2</sup> Per ricreare questo criterio di avviso, seguire le indicazioni riportate nella nota a piè di pagina precedente, ma scegliere La rappresentazione dell'utente come unica tecnologia di rilevamento.

L'attività insolita monitorata da alcuni dei criteri predefiniti si basa sullo stesso processo dell'impostazione di soglia degli avvisi descritta in precedenza. Microsoft stabilisce un valore di base che definisce la frequenza normale per l'attività "normale". Gli avvisi vengono quindi attivati quando la frequenza delle attività monitorate dal criterio di avviso predefinito supera notevolmente il valore di base.

## <a name="viewing-alerts"></a>Visualizzazione degli avvisi

Quando un'attività eseguita dagli utenti dell'organizzazione corrisponde alle impostazioni di un  criterio di avviso, viene generato e visualizzato un avviso nella pagina Visualizza avvisi nel Centro sicurezza e conformità. A seconda delle impostazioni di un criterio di avviso, una notifica tramite posta elettronica viene inviata anche a un elenco di utenti specifici quando viene attivato un avviso. Per ogni avviso, il  dashboard nella pagina Visualizza avvisi visualizza il nome del criterio di avviso corrispondente, la gravità e la categoria dell'avviso (definiti nel criterio di avviso) e il numero di volte in cui si è verificata un'attività che ha generato l'avviso. Questo valore si basa sull'impostazione di soglia del criterio di avviso. Il dashboard mostra anche lo stato di ogni avviso. Per ulteriori informazioni sull'utilizzo della proprietà status per gestire gli avvisi, vedere [Managing alerts.](#managing-alerts)

Per visualizzare gli avvisi, passare [https://protection.office.com](https://protection.office.com) a e selezionare **Visualizzazione** \> **avvisi.**

![Nella sicurezza e conformità, selezionare Avvisi, quindi selezionare Visualizza avvisi per visualizzare gli avvisi](../media/ec5ea59b-bf61-459f-8b65-970ab4bb8bcc.png)

Puoi usare i filtri seguenti per visualizzare un sottoinsieme di tutti gli avvisi nella **pagina Visualizza** avvisi.

- **Stato.** Utilizzare questo filtro per visualizzare gli avvisi a cui è assegnato uno stato specifico. Lo stato predefinito è **Attivo.** L'utente o altri amministratori possono modificare il valore dello stato.

- **Criterio.** Utilizzare questo filtro per visualizzare gli avvisi che corrispondono all'impostazione di uno o più criteri di avviso. Oppure è possibile visualizzare tutti gli avvisi per tutti i criteri di avviso.

- **Intervallo di tempo.** Utilizzare questo filtro per visualizzare gli avvisi generati entro un intervallo di data e ora specifico.

- **Gravità.** Utilizzare questo filtro per visualizzare gli avvisi a cui è assegnata una gravità specifica.

- **Categoria.** Utilizzare questo filtro per visualizzare gli avvisi di una o più categorie di avviso.

- **Tag.** Utilizzare questo filtro per visualizzare gli avvisi di uno o più tag utente. I tag vengono applicati in base alle cassette postali contrassegnate o agli utenti visualizzati negli avvisi. Per altre informazioni, vedere Tag utente [in Office 356 ATP.](..\security\office-365-security\user-tags.md)

- **Origine.** Usare questo filtro per visualizzare gli avvisi attivati dai criteri di avviso nel Centro sicurezza e conformità o gli avvisi attivati dai criteri di Office 365 Cloud App Security o da entrambi. Per ulteriori informazioni sugli avvisi di Office 365 Cloud App Security, vedere [Visualizzazione degli avvisi di Cloud App Security.](#viewing-cloud-app-security-alerts)

> [!IMPORTANT]
> Il filtro e l'ordinamento in base ai tag utente sono attualmente in anteprima pubblica.
> Potrebbe essere sostanzialmente modificato prima del rilascio sul mercato. Microsoft non garantisce alcuna garanzia, espressa o implicita, in relazione alle informazioni fornite.

## <a name="alert-aggregation"></a>Aggregazione degli avvisi

Quando si verificano più eventi che soddisfano le condizioni di un criterio di avviso con un breve periodo di tempo, vengono aggiunti a un avviso esistente da un processo denominato aggregazione *degli avvisi.* Quando un evento attiva un avviso, l'avviso viene generato e visualizzato nella pagina Visualizza **avvisi** e viene inviata una notifica. Se lo stesso evento si verifica entro l'intervallo di aggregazione, Microsoft 365 aggiunge dettagli sul nuovo evento all'avviso esistente invece di attivare un nuovo avviso. L'obiettivo dell'aggregazione degli avvisi è ridurre la "fatica" degli avvisi e permetterti di concentrarti e intervenire su un numero minore di avvisi per lo stesso evento.

La lunghezza dell'intervallo di aggregazione dipende dall'abbonamento a Office 365 o Microsoft 365.

|Abbonamento|Intervallo di aggregazione|
|:---------|:---------:|
|Office 365 o Microsoft 365 E5/G5|1 minuto|
|Defender per Office 365 Piano 2 |1 minuto|
|Componente aggiuntivo conformità E5 o componente aggiuntivo di individuazione e controllo E5|1 minuto|
|Office 365 o Microsoft 365 E1/F1/G1 o E3/F3/G3|15 minuti|
|Defender per Office 365 Piano 1 o Exchange Online Protection|15 minuti|
|||

Quando si verificano eventi che corrispondono allo stesso criterio di avviso entro l'intervallo di aggregazione, i dettagli sull'evento successivo vengono aggiunti all'avviso originale. Per tutti gli eventi, le informazioni sugli eventi aggregati vengono visualizzate nel campo dei dettagli e il numero di volte in cui si è verificato un evento con l'intervallo di aggregazione viene visualizzato nel campo di conteggio attività/risultati. È possibile visualizzare ulteriori informazioni su tutte le istanze di eventi aggregati visualizzando l'elenco delle attività.

Lo screenshot seguente mostra un avviso con quattro eventi aggregati. L'elenco delle attività contiene informazioni sui quattro messaggi di posta elettronica rilevanti per l'avviso.

![Esempio di aggregazione degli avvisi](../media/AggregatedAlertExample.png)

Tenere presente quanto segue sull'aggregazione degli avvisi:

- Gli avvisi attivati dal clic su UN URL potenzialmente **dannoso sono** stati rilevati [criteri](#default-alert-policies) di avviso predefiniti non aggregati. Questo perché gli avvisi attivati da questo criterio sono univoci per ogni utente e messaggio di posta elettronica.

- Al momento, la proprietà **di** avviso Numero di risultati non indica il numero di eventi aggregati per tutti i criteri di avviso. Per gli avvisi attivati da questi criteri di avviso, è possibile visualizzare gli eventi aggregati facendo clic su Visualizza elenco messaggi o Visualizza **attività** nell'avviso.  Stiamo lavorando per rendere disponibile il numero di eventi aggregati elencati nella proprietà **di** avviso numero di risultati per tutti i criteri di avviso.

## <a name="rbac-permissions-required-to-view-alerts"></a>Autorizzazioni RBAC necessarie per visualizzare gli avvisi

Le autorizzazioni RBAC (Role Based Access Control) assegnate agli utenti dell'organizzazione determinano quali avvisi possono essere visualizzati da un utente nella pagina **Visualizza** avvisi. Come viene eseguita questa operazione? I ruoli di gestione assegnati agli utenti (in base all'appartenenza ai gruppi di ruoli nel Centro sicurezza & conformità) determinano le categorie di avviso che un utente può visualizzare nella pagina Visualizza **avvisi.** Ecco alcuni esempi:

- I membri del gruppo di ruoli Gestione record possono visualizzare solo gli avvisi generati dai criteri di avviso assegnati alla **categoria Governance delle** informazioni.

- I membri del gruppo di ruoli Amministratore conformità non possono visualizzare gli avvisi generati dai criteri di avviso assegnati alla **categoria di gestione delle** minacce.

- I membri del gruppo di ruoli Gestore di eDiscovery non possono visualizzare alcun avviso perché nessuno dei ruoli assegnati fornisce l'autorizzazione per visualizzare gli avvisi di qualsiasi categoria di avviso.

Questa progettazione (basata sulle autorizzazioni RBAC) consente di determinare quali avvisi possono essere visualizzati (e gestiti) dagli utenti in ruoli di lavoro specifici nell'organizzazione.

Nella tabella seguente sono elencati i ruoli necessari per visualizzare gli avvisi delle sei diverse categorie di avviso. Nella prima colonna delle tabelle sono elencati tutti i ruoli nel Centro sicurezza & conformità.  Un segno di spunta indica che un utente a cui è assegnato quel ruolo può visualizzare gli avvisi della categoria di avviso corrispondente elencata nella riga superiore.

Per vedere a quale categoria è assegnato un criterio di avviso predefinito, vedere la tabella in [Criteri di avviso predefiniti.](#default-alert-policies)

|Ruolo|Governance delle informazioni|Prevenzione della perdita di dati|Flusso di posta|Autorizzazioni|Gestione dei rischi|Altri|
|:---------|:---------:|:---------:|:---------:|:---------:|:---------:|:---------:|
|Registri di controllo|||||||
|Gestione dei casi|||||||
|Amministratore di conformità|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)||![Segno di spunta](../media/checkmark.png)||![Segno di spunta](../media/checkmark.png)|
|Ricerca di conformità|||||||
|Gestione dei dispositivi|||||||
|Gestione dell'eliminazione|||||||
|Gestione conformità DLP||![Segno di spunta](../media/checkmark.png)|||||
|Esportazione|||||||
|Hold|||||||
|Gestione avvisi||||||![Segno di spunta](../media/checkmark.png)|
|Configurazione organizzazione||||||![Segno di spunta](../media/checkmark.png)|
|Anteprima|||||||
|Gestione record|![Segno di spunta](../media/checkmark.png)||||||
|Gestione della conservazione|![Segno di spunta](../media/checkmark.png)||||||
|Revisione|||||||
|Decrittografia RMS|||||||
|Gestione ruoli||||![Segno di spunta](../media/checkmark.png)|||
|Ricerca ed eliminazione|||||||
|Amministratore della sicurezza||![Segno di spunta](../media/checkmark.png)||![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|
|Ruolo con autorizzazioni di lettura per la sicurezza||![Segno di spunta](../media/checkmark.png)||![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)|![Segno di spunta](../media/checkmark.png)
|Visualizzazione Garanzia del servizio|||||||
|Supervisory Review Administrator|||||||
|View-Only di controllo|||||||
|View-Only dispositivi|||||||
|View-Only conformità DLP||![Segno di spunta](../media/checkmark.png)|||||
|View-Only gestire gli avvisi||||||![Segno di spunta](../media/checkmark.png)|
|Destinatari solo visualizzazione|||![Segno di spunta](../media/checkmark.png)||||
|View-Only record|![Segno di spunta](../media/checkmark.png)||||||
|View-Only conservazione|![Segno di spunta](../media/checkmark.png)||||||
|||||||

> [!TIP]
> Per visualizzare i ruoli assegnati a ognuno dei gruppi di ruoli predefiniti, eseguire i comandi seguenti in PowerShell per Centro sicurezza & conformità:
> 
> ```powershell
> $RoleGroups = Get-RoleGroup
> ```
> 
> ```powershell
> $RoleGroups | foreach {Write-Output -InputObject `r`n,$_.Name,"-----------------------"; Get-RoleGroup $_.Identity | Select-Object -ExpandProperty Roles}
> ```
> 
> È inoltre possibile visualizzare i ruoli assegnati a un gruppo di ruoli nel Centro sicurezza & conformità. Passare alla pagina **Autorizzazioni** e selezionare un gruppo di ruoli. I ruoli assegnati sono elencati nella pagina a comparsa.

## <a name="managing-alerts"></a>Gestione degli avvisi

Dopo che gli avvisi sono  stati generati e visualizzati nella pagina Visualizza avvisi nel Centro sicurezza e conformità, è possibile valutarli, analizzarli e risolverli. Ecco alcune attività che puoi eseguire per gestire gli avvisi.

- **Assegnare uno stato agli avvisi.** È possibile assegnare uno dei seguenti stati agli avvisi: **Attivo** (valore predefinito), **In** **analisi,** Risolto o **Ignorato.** È quindi possibile filtrare in base a questa impostazione per visualizzare gli avvisi con la stessa impostazione di stato. Questa impostazione di stato consente di tenere traccia del processo di gestione degli avvisi.

- **Visualizzare i dettagli dell'avviso.** È possibile selezionare un avviso per visualizzare una pagina a comparsa con i dettagli relativi all'avviso. Le informazioni dettagliate dipendono dal criterio di avviso corrispondente, ma in genere includono quanto segue: nome dell'operazione effettiva che ha attivato l'avviso (ad esempio un cmdlet), descrizione dell'attività che ha attivato l'avviso, utente (o elenco di utenti) che ha attivato l'avviso e nome (e collegamento) del criterio di avviso corrispondente.

  - Nome dell'operazione effettiva che ha attivato l'avviso, ad esempio un cmdlet o un'operazione del registro di controllo.

  - Descrizione dell'attività che ha attivato l'avviso.

  - Utente che ha attivato l'avviso. È incluso solo per i criteri di avviso impostati per tenere traccia di un singolo utente o di una singola attività.

  - Numero di volte in cui è stata eseguita l'attività monitorata dall'avviso. Questo numero potrebbe non corrispondere al numero effettivo di avvisi correlati elencati nella pagina Visualizza avvisi perché potrebbero essere stati attivati più avvisi.

  - Collegamento a un elenco di attività che include un elemento per ogni attività eseguita che ha attivato l'avviso. Ogni voce di questo elenco identifica quando si è verificata l'attività, il nome dell'operazione effettiva (ad esempio "FileDeleted"), l'utente che ha eseguito l'attività, l'oggetto (ad esempio un file, un caso di eDiscovery o una cassetta postale) su cui è stata eseguita l'attività e l'indirizzo IP del computer dell'utente. Per gli avvisi correlati al malware, questo collegamento a un elenco di messaggi.

  - Nome (e collegamento) del criterio di avviso corrispondente.

- **Eliminare le notifiche di posta elettronica.** È possibile disattivare (o eliminare) le notifiche di posta elettronica dalla pagina del riquadro a comparsa per un avviso. Quando si sopprimeno le notifiche di posta elettronica, Microsoft non invierà notifiche quando le attività o gli eventi che soddisfano le condizioni del criterio di avviso. Tuttavia, gli avvisi verranno attivati quando le attività eseguite dagli utenti soddisfano le condizioni del criterio di avviso. È inoltre possibile disattivare le notifiche tramite posta elettronica modificando il criterio di avviso.

- **Risolvere gli avvisi.** Puoi contrassegnare un avviso come risolto nella pagina del riquadro a comparsa per un avviso (che imposta lo stato dell'avviso su **Risolto).** A meno che non si modifica il filtro, gli avvisi risolti non vengono visualizzati nella **pagina Visualizza** avvisi.

## <a name="viewing-cloud-app-security-alerts"></a>Visualizzazione degli avvisi di Cloud App Security

Gli avvisi attivati dai criteri di Office 365 Cloud  App Security vengono ora visualizzati nella pagina Visualizza avvisi nel Centro sicurezza e conformità. Sono inclusi gli avvisi attivati dai criteri attività e dagli avvisi attivati dai criteri di rilevamento delle anomalie in Office 365 Cloud App Security. Ciò significa che è possibile visualizzare tutti gli avvisi nel Centro sicurezza e conformità. Office 365 Cloud App Security è disponibile solo per le organizzazioni con un abbonamento a Office 365 Enterprise E5 o Office 365 US Government G5. Per ulteriori informazioni, vedere [Panoramica di Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

Le organizzazioni che dispongono di Microsoft Cloud App Security come parte di una sottoscrizione Enterprise Mobility + Security E5 o come servizio autonomo possono anche visualizzare gli avvisi di Cloud App Security correlati alle app e ai servizi di Office 365 nel Centro sicurezza & conformità.

Per visualizzare solo gli avvisi di Cloud App  Security nel Centro sicurezza e conformità, usare il filtro origine e **selezionare Cloud App Security.**

![Usare il filtro Origine per visualizzare solo gli avvisi di Cloud App Security](../media/FilterCASAlerts.png)

Analogamente a un avviso attivato da un criterio di avviso nel Centro sicurezza e conformità, è possibile selezionare un avviso di Cloud App Security per visualizzare una pagina a comparsa con i dettagli sull'avviso. L'avviso include un collegamento per visualizzare i dettagli e gestire l'avviso nel portale di Cloud App Security e un collegamento al criterio di Cloud App Security corrispondente che ha attivato l'avviso. Vedi [Monitorare gli avvisi in Cloud App Security.](https://docs.microsoft.com/cloud-app-security/monitor-alerts)

![I dettagli dell'avviso contengono collegamenti al portale di Cloud App Security](../media/CASAlertDetail.png)

> [!IMPORTANT]
> La modifica dello stato di un avviso di Cloud App Security nel Centro sicurezza e conformità non aggiornerà lo stato di risoluzione per lo stesso avviso nel portale di Cloud App Security. Ad esempio, se si contrassegna  lo stato dell'avviso come Risolto nel Centro sicurezza e conformità, lo stato dell'avviso nel portale di Cloud App Security rimane invariato. Per risolvere o ignorare un avviso di Cloud App Security, gestisci l'avviso nel portale di Cloud App Security.
