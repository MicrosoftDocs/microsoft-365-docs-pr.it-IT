---
title: Valutare Microsoft Defender per Office 365
description: Difensore per Office 365 in modalità di valutazione crea Defender per i criteri di posta elettronica di Office 365 che registrano verdetti, ad esempio malware, ma non agiscono sui messaggi.
keywords: valutare Office 365, Microsoft Defender per Office 365, valutazione di Office 365, provare a Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 12b6499822f8ed97ace8468054f219361d925332
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562991"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Valutare Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

>[!IMPORTANT]
>Valutare Microsoft Defender per Office 365 sarà presto in anteprima pubblica questa versione di anteprima è disponibile senza un contratto di servizio. È possibile che alcune funzionalità non siano supportate o che possano disporre di funzionalità vincolate.

L'esecuzione di una valutazione completa del prodotto di sicurezza può contribuire a prendere decisioni informate sugli aggiornamenti e gli acquisti. Consente di provare le funzionalità del prodotto per la sicurezza per valutare in che modo può aiutare il team delle operazioni di sicurezza nelle attività quotidiane.

L'esperienza di valutazione di [Microsoft Defender per Office 365](office-365-atp.md) è stata progettata per eliminare la complessità della configurazione del dispositivo e dell'ambiente, in modo da poter concentrarsi sulla valutazione delle funzionalità della soluzione di sicurezza. Si applica solo alla protezione della posta elettronica e non ai client di SharePoint, Office o team.

Se non si dispone già di una licenza che supporta Microsoft Defender per Office 365, è possibile avviare una [valutazione gratuita di 30 giorni](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) e testare le funzionalità nel centro sicurezza & conformità di Office 365 ( https://protection.office.com/homepage) . È possibile utilizzare la configurazione rapida e disattivarla se necessario.

## <a name="how-the-evaluation-works"></a>Modalità di funzionamento della valutazione

Difensore per Office 365 in modalità di valutazione crea Defender per i criteri di posta elettronica di Office 365 che registrano verdetti, ad esempio malware, ma non agiscono sui messaggi. Non è necessario modificare la configurazione del record MX.

Con la modalità di valutazione, gli [allegati sicuri](atp-safe-attachments.md), i [collegamenti sicuri](atp-safe-links.md)e i [criteri di rappresentazione anti-phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) sono impostati per conto dell'utente. Tutti i criteri di protezione per Office 365 vengono creati in modalità di non applicazione in background e non sono visibili all'utente.

Come parte del programma di installazione, la modalità di valutazione configura anche il [filtro avanzato per i connettori](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). Migliora l'accuratezza del filtro conservando le informazioni sull'indirizzo IP e sul mittente, che sono altrimenti perse quando la posta passa attraverso un gateway di sicurezza della posta elettronica (ESG) davanti a Defender per Office 365. Ciò migliora anche l'accuratezza del filtro per i criteri di protezione da posta indesiderata e anti-phishing di Exchange Online Protection (EOP).

Per ridurre al minimo l'impatto della produzione su alcuni scenari non supportati, è possibile ignorare tutti i filtri di EOP creando una regola di trasporto per impostare il livello di probabilità di posta indesiderata su-1. Per informazioni dettagliate, vedere Utilizzo dell'interfaccia di amministrazione [di Exchange per creare una regola del flusso di posta che imposta il livello SCL di un messaggio](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   .

Quando la modalità di valutazione è configurata, si avrà un rapporto aggiornato giornalmente con un massimo di 90 giorni di dati quantificando i messaggi che sarebbero stati bloccati se i criteri fossero stati apportati e implementati (ad esempio, DELETE, Send to Junk, Quarantine). I report vengono generati per tutti i rilevamenti di protezione per Office 365 e EOP. Sono aggregati per la tecnologia di rilevamento (ad esempio, rappresentazione) e possono essere filtrati in base all'intervallo di tempo. Inoltre, i report dei messaggi possono essere creati su richiesta per creare pivot personalizzati o per i messaggi di Deep Dive tramite Esplora minacce.

Con l'utilizzo di set-up semplificato, è possibile concentrarsi su:

- Esecuzione della valutazione
- Ottenere un report dettagliato
- Analisi del report per l'azione
- Presentazione del risultato della valutazione

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="licensing"></a>Licenze

Per accedere alla valutazione, è necessario soddisfare i requisiti di licenza. Funzionerà una delle licenze seguenti:

- Microsoft Defender per Office 365 piano 1
- Microsoft Defender per Office 365 piano 2
- Microsoft 365 E5, sicurezza di Microsoft 365 E5
- Office 365 E5

Se non si dispone di una di queste licenze, sarà necessario ottenere una licenza di valutazione.

#### <a name="trial"></a>Valutazione

Per ottenere una licenza di valutazione per Microsoft Defender per Office 365, è necessario avere il ruolo di **amministratore di fatturazione** o il **ruolo di amministratore globale**. Richiedere l'autorizzazione a un utente che ha il ruolo di amministratore globale. [Informazioni su abbonamenti e licenze](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Dopo aver ottenuto il ruolo appropriato, è consigliabile ottenere una licenza di valutazione per Microsoft Defender per Office 365 (piano 2) nell'interfaccia di amministrazione di Microsoft 365 accedendo a fatturazione > servizi di acquisto. La versione di valutazione include una versione di valutazione gratuita di 30 giorni per 25 licenze. [Ottenere una versione di valutazione di Microsoft Defender per Office 365 (piano 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA). 

Verrà visualizzata una finestra di 30 giorni con la valutazione da monitorare e riferire su minacce avanzate. È inoltre possibile acquistare un abbonamento a pagamento se si desidera che il servizio di protezione completo per le funzionalità di Office 365.

### <a name="roles"></a>Ruoli

I ruoli di Exchange Online sono necessari per configurare Defender per Office 365 in modalità di valutazione. Sono necessari i ruoli seguenti:

|Attività | Ruolo |
|-----| -----|
| Ottenere una versione di valutazione gratuita o acquistare Microsoft Defender per Office 365 (piano 2)| Ruolo di amministratore di fatturazione o ruolo di amministratore globale|
| Creare criteri di valutazione| Ruolo di domini accettati e remoti; Ruolo di amministratore della sicurezza|
| Modifica criteri di valutazione | Ruolo di domini accettati e remoti; Ruolo di amministratore della sicurezza |
| Eliminare i criteri di valutazione | Ruolo di domini accettati e remoti; Ruolo di amministratore della sicurezza |
|Visualizzare il report di valutazione | Ruolo di amministratore della sicurezza o lettore di sicurezza|

### <a name="enhanced-filtering"></a>Filtro migliorato

I criteri di protezione di Exchange Online, ad esempio la massa e la protezione dalla posta indesiderata, rimarranno invariati. Anche il recapito dei messaggi rimarrà invariato. Tuttavia, la valutazione attiva il filtro avanzato per i connettori, che avrà un impatto sui criteri di flusso di posta e di protezione di Exchange Online, a meno che non vengano ignorati.

Il filtro avanzato per i connettori consentirà ai tenant di usare la protezione anti-spoofing. L'anti-spoofing non è supportato se si utilizza un gateway di sicurezza della posta elettronica (ESG) senza che sia stato attivato il filtro avanzato per i connettori.

### <a name="urls"></a>URL

Gli URL verranno detonati durante il flusso di posta. Se non si desidera che gli URL specifici vengano detonati, gestire l'elenco degli URL consentiti in modo appropriato. Per informazioni dettagliate, vedere [gestire gli URL nell'elenco Consenti/blocca tenant](tenant-allow-block-list.md) .

I collegamenti URL nei corpi dei messaggi di posta elettronica non vengono adattati per ridurre l'impatto del cliente.

### <a name="email-routing"></a>Routing della posta elettronica

È necessario preparare i dettagli corrispondenti che saranno necessari per configurare la modalità di instradamento della posta elettronica, incluso il nome del connettore in ingresso che instrada la posta. Se si utilizza solo Exchange Online Protection, non si avrà un connettore. Informazioni  [sul flusso di posta e il routing della posta elettronica](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Gli scenari di routing della posta elettronica supportati includono:

- **Partner di terze parti e/o provider di servizi locali**: il connettore in ingresso che si desidera valutare utilizza un provider di terze parti e/o utilizza una soluzione per la sicurezza della posta elettronica in locale.  
- **Solo Microsoft Exchange Online Protection**: il tenant che si desidera valutare utilizza Office 365 per la sicurezza della posta elettronica e il record MX (mail Exchange) punta a Microsoft.

### <a name="email-security-gateway"></a>Gateway di sicurezza della posta elettronica

Se si utilizza un gateway di sicurezza per la posta elettronica di terze parti (ESG), è necessario conoscere il nome del provider. Se si utilizza un ESG locale o un fornitore non supportato, è necessario conoscere gli indirizzi IP pubblici per i dispositivi.

I partner di terze parti supportati includono:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Ambito

Si sarà in grado di applicare la valutazione a un connettore in ingresso. Se non è configurato alcun connettore, l'ambito di valutazione consentirà agli amministratori di raccogliere dati da qualsiasi utente del tenant per valutare Defender per Office 365.

## <a name="get-started-with-the-evaluation"></a>Iniziare a utilizzare la valutazione

Trovare la scheda di configurazione di valutazione di Microsoft Defender per Office 365 nel centro conformità & sicurezza di Office 365 ( https://protection.office.com/homepage) da tre punti di accesso:

- Dashboard di gestione delle minacce >
- Criteri di > di gestione delle minacce
- Report > dashboard

## <a name="setting-up-the-evaluation"></a>Configurazione della valutazione

Dopo aver avviato il flusso di configurazione per la valutazione, verranno fornite due opzioni di routing. A seconda delle esigenze di valutazione e configurazione del routing della posta dell'organizzazione, è possibile scegliere se si sta utilizzando un provider di servizi di terze parti e/o locale o solo Microsoft Exchange Online.

- Se si utilizza un partner di terze parti e/o un provider di servizi locale, è necessario selezionare il nome del fornitore dal menu a discesa. Fornire gli altri dettagli correlati al connettore.

- Selezionare Microsoft Exchange Online se il record MX punta a Microsoft e si dispone di una cassetta postale di Exchange Online.

Rivedere le impostazioni e modificarle, se necessario. Fare quindi clic su **Crea valutazione**. Si dovrebbe ottenere un messaggio di conferma per indicare che l'installazione è stata completata.

Il report di valutazione di Microsoft Defender per Office 365 viene generato una volta al giorno. I dati possono richiedere fino a 24 ore.

### <a name="exchange-rules-optional"></a>Regole di Exchange (facoltativa)

Se si dispone di un gateway esistente, potrebbe essere necessario ignorare il filtro perché attiverà il filtro avanzato per i connettori e altererà l'indirizzo IP del mittente in ingresso. Per ignorare, passare all'interfaccia di amministrazione di Exchange e creare un criterio di SCL-1 (se non è già presente). Per informazioni dettagliate sui componenti delle regole e sul relativo funzionamento, vedere Mail Flow Rules (Transport Rules) in Exchange Online.

## <a name="evaluate-capabilities"></a>Valutare le funzionalità

Dopo aver generato il report di valutazione, vedere il numero di collegamenti a minacce avanzati, allegati a minacce avanzate e potenziali rappresentazioni sono stati identificati nelle aree di lavoro di posta elettronica e collaborazione nell'organizzazione.  

Una volta scaduta la versione di valutazione, è possibile continuare ad accedere al report per 90 giorni. Tuttavia, non raccoglierà altre informazioni. Se si desidera continuare a utilizzare Microsoft Defender per Office 365 dopo la scadenza del periodo di prova, assicurarsi di [acquistare un abbonamento a pagamento per Microsoft Defender per office 365 (piano 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

È possibile accedere alle **Impostazioni** per aggiornare il routing o disattivare la valutazione in qualsiasi momento. Tuttavia, è necessario eseguire di nuovo lo stesso processo di configurazione se si decide di continuare la valutazione dopo averla disattivata.

## <a name="provide-feedback"></a>Inviare feedback

I commenti e suggerimenti consentono di migliorare la protezione dell'ambiente da attacchi avanzati. Condividere la propria esperienza e le proprie impressioni sulle funzionalità del prodotto e sui risultati della valutazione.

Selezionare **Invia commenti e suggerimenti** per farci sapere cosa ne pensi.
