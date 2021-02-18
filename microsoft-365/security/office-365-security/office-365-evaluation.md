---
title: Valutare Microsoft Defender per Office 365
description: Defender per Office 365 in modalità di valutazione crea i criteri di posta elettronica di Defender per Office 365 che registrano i verdetti, ad esempio malware, ma non agiscono sui messaggi.
keywords: valutare Office 365, Microsoft Defender per Office 365, valutazione di Office 365, provare Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d16c0afc675ba759e392c9fe9a44c42b89dbad0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287654"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Valutare Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> La valutazione di Microsoft Defender per Office 365 è in anteprima pubblica. Questa versione di anteprima viene fornita senza un contratto di servizio. Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.

L'esecuzione di una valutazione completa del prodotto per la sicurezza può aiutare a prendere decisioni informate su aggiornamenti e acquisti. Aiuta a provare le funzionalità del prodotto per la sicurezza per valutare in che modo può aiutare il team delle operazioni di sicurezza nelle loro attività quotidiane.

L'esperienza di valutazione di [Microsoft Defender per Office 365](office-365-atp.md) è progettata per eliminare la complessità della configurazione di dispositivi e ambienti, in modo da concentrarsi sulla valutazione delle funzionalità della soluzione di sicurezza. Si applica solo alla protezione della posta elettronica e non a SharePoint, ai client di Office o a Teams.

Se non si dispone già di una licenza che supporta Microsoft Defender per Office 365, è possibile avviare una valutazione gratuita di [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) giorni e testare le funzionalità nel Centro sicurezza & e conformità di Office 365 ( https://protection.office.com/homepage) . Potrai usufruire della configurazione rapida ed è possibile disattivarla facilmente, se necessario.

## <a name="how-the-evaluation-works"></a>Funzionamento della valutazione

Defender per Office 365 in modalità di valutazione crea i criteri di posta elettronica di Defender per Office 365 che registrano i verdetti, ad esempio malware, ma non agiscono sui messaggi. Non è necessario modificare la configurazione del record MX.

Con la modalità di valutazione, [gli](atp-safe-attachments.md)allegati sicuri, [i collegamenti](atp-safe-links.md)sicuri e i criteri di rappresentazione [anti-phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) vengono impostati per conto dell'utente. Tutti i criteri di Defender per Office 365 vengono creati in modalità non di imposizione in background e non sono visibili all'utente.

Durante l'installazione, la modalità di valutazione configura anche [il filtro avanzato per i connettori.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Migliora l'accuratezza del filtro preservando l'indirizzo IP e le informazioni del mittente, che altrimenti vengono perse quando la posta passa attraverso un gateway di sicurezza della posta elettronica (ESG) davanti a Defender per Office 365. Il filtro avanzato migliora inoltre l'accuratezza del filtro per i criteri di protezione da posta indesiderata e anti-phishing di Exchange Online Protection (EOP).

Per ridurre al minimo il potenziale impatto sulla produzione in alcuni scenari non supportati, è possibile ignorare tutti i filtri EOP creando una regola di trasporto per impostare il livello di probabilità di posta indesiderata (SCL) su -1. Per informazioni dettagliate, vedere Use [the EAC to create a mail flow rule that sets the SCL of a](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   message.

Quando è impostata la modalità di valutazione, ogni giorno verrà aggiornato un rapporto con fino a 90 giorni di dati che quantificano i messaggi che sarebbero stati bloccati se i criteri fossero stati implementati (ad esempio, eliminare, inviare posta indesiderata, quarantena). Vengono generati report per tutti i rilevamenti di Defender per Office 365 ed EOP. Vengono aggregati in base alla tecnologia di rilevamento (ad esempio, la rappresentazione) e possono essere filtrati in base all'intervallo di tempo. Inoltre, i rapporti dei messaggi possono essere creati su richiesta per creare pivot personalizzati o per approfondire i messaggi con Esplora minacce.

Con l'esperienza di configurazione semplificata, è possibile concentrarsi su:

- Esecuzione della valutazione
- Recupero di un report dettagliato
- Analisi del report per l'azione
- Presentazione del risultato della valutazione

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="licensing"></a>Licenze

Per accedere alla valutazione, è necessario soddisfare i requisiti di licenza. Una delle licenze seguenti funzionerà:

- Microsoft Defender per Office 365 Piano 1
- Microsoft Defender per Office 365 Piano 2
- Microsoft 365 E5, Sicurezza Microsoft 365 E5
- Office 365 E5

Se non hai una di queste licenze, dovrai ottenere una licenza di prova.

#### <a name="trial"></a>Valutazione

Per ottenere una licenza di valutazione per Microsoft Defender per  Office 365, è necessario disporre del ruolo amministratore fatturazione o **amministratore globale.** Richiedere l'autorizzazione a un utente con il ruolo di amministratore globale. [Informazioni su abbonamenti e licenze](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Dopo aver ottenuto il ruolo appropriato, il percorso consigliato è ottenere una licenza di valutazione per Microsoft Defender per Office 365 (Piano 2) nell'interfaccia di amministrazione di Microsoft 365 andando a Fatturazione > Purchase services. La versione di valutazione include una versione di valutazione gratuita di 30 giorni per 25 licenze. [Ottenere una versione di valutazione per Microsoft Defender per Office 365 (Piano 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Avrai una finestra di 30 giorni con la valutazione per monitorare e segnalare le minacce avanzate. You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.

### <a name="roles"></a>Ruoli

I ruoli di Exchange Online sono necessari per configurare Defender per Office 365 in modalità di valutazione.

- [Informazioni sulle autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Informazioni sull'assegnazione dei ruoli di amministratore](../../admin/add-users/assign-admin-roles.md)

Sono necessari i ruoli seguenti:

|Attività|Ruolo|
|---|---|
|Ottenere una versione di valutazione gratuita o acquistare Microsoft Defender per Office 365 (Piano 2)|Ruolo amministratore fatturazione O ruolo di amministratore globale|
|Creare criteri di valutazione|Ruolo Domini accettati e remoti; Ruolo di amministratore della sicurezza|
|Modificare i criteri di valutazione|Ruolo Domini accettati e remoti; Ruolo di amministratore della sicurezza|
|Eliminare i criteri di valutazione|Ruolo Domini accettati e remoti; Ruolo di amministratore della sicurezza |
|Visualizzare il report di valutazione|Ruolo di amministratore della sicurezza O ruolo lettore di sicurezza|
|


### <a name="enhanced-filtering"></a>Filtro avanzato

I criteri di Exchange Online Protection, ad esempio la protezione da posta indesiderata e in blocco, rimarranno invariati. Anche il recapito dei messaggi rimarrà invariato. Tuttavia, la valutazione attiva il filtro avanzato per i connettori, che influirà sul flusso di posta e sui criteri di Exchange Online Protection, a meno che non venga ignorato.

Il filtro avanzato per i connettori consentirà ai tenant di utilizzare la protezione anti-spoofing. L'anti-spoofing non è supportato se si utilizza un gateway di sicurezza della posta elettronica (ESG) senza aver attivato il filtro avanzato per i connettori.

### <a name="urls"></a>URL

Gli URL verranno detonati durante il flusso di posta. Se non vuoi che url specifici detonino, gestisci l'elenco degli URL consentiti in modo appropriato. Per [informazioni dettagliate, vedere Manage the Tenant Allow/Block List.](tenant-allow-block-list.md)

I collegamenti URL nei corpi dei messaggi di posta elettronica non vengono inclusi, per ridurre l'impatto del cliente.

### <a name="email-routing"></a>Routing della posta elettronica

Preparare i dettagli corrispondenti che sarà necessario configurare come viene attualmente instradata la posta elettronica, incluso il nome del connettore in ingresso che instrada la posta. Se si utilizza solo Exchange Online Protection, non si dispone di un connettore.  [Informazioni sul flusso di posta e sul routing della posta elettronica](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Gli scenari di routing della posta elettronica supportati includono:

- Partner di terze parti **e/o provider** di servizi locali: il connettore in ingresso che si desidera valutare utilizza un provider di terze parti e/o si sta utilizzando una soluzione per la sicurezza della posta elettronica locale.
- **Microsoft Exchange Online protezione:** il tenant che si desidera valutare utilizza Office 365 per la sicurezza della posta elettronica e il record Mail Exchange (MX) punta a Microsoft.

### <a name="email-security-gateway"></a>Gateway di sicurezza della posta elettronica

Se si utilizza un gateway di sicurezza della posta elettronica (ESG) di terze parti, è necessario conoscere il nome del provider. Se si usa un ESG locale o fornitori non supportati, è necessario conoscere gli indirizzi IP pubblici per i dispositivi.

I partner di terze parti supportati includono:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Ambito

Sarà possibile impostare l'ambito della valutazione su un connettore in ingresso. Se non è configurato alcun connettore, l'ambito di valutazione consentirà agli amministratori di raccogliere dati da qualsiasi utente nel tenant per valutare Defender per Office 365.

## <a name="get-started-with-the-evaluation"></a>Introduzione alla valutazione

Trovare la scheda di configurazione di valutazione di Microsoft Defender per Office 365 nel Centro sicurezza & e conformità di Office 365 ( da tre https://protection.office.com/homepage) punti di accesso:

- Dashboard di gestione delle > minacce
- Criteri di gestione > delle minacce
- Report > Dashboard

## <a name="setting-up-the-evaluation"></a>Impostazione della valutazione

Dopo aver avviato il flusso di configurazione per la valutazione, ti verranno date due opzioni di routing. A seconda delle esigenze di configurazione e valutazione del routing della posta dell'organizzazione, è possibile scegliere se si utilizza un provider di servizi di terze parti e/o locale o solo un Microsoft Exchange Online.

- Se si utilizza un partner di terze parti e/o un provider di servizi locale, è necessario selezionare il nome del fornitore dal menu a discesa. Fornire gli altri dettagli relativi al connettore.

- Selezionare Microsoft Exchange Online se il record MX punta a Microsoft e si dispone di una cassetta postale di Exchange Online.

Rivedere le impostazioni e modificarle, se necessario. Selezionare quindi Crea **valutazione.** Dovresti ricevere un messaggio di conferma per indicare che la configurazione è stata completata.

Il report di valutazione di Microsoft Defender per Office 365 viene generato una volta al giorno. La compilazione dei dati potrebbe richiedere fino a 24 ore.

### <a name="exchange-rules-optional"></a>Regole di Exchange (facoltativo)

Se si dispone di un gateway esistente, l'abilitazione della modalità di valutazione attiverà il filtro avanzato per i connettori. In questo modo si migliora l'accuratezza del filtro modificando l'indirizzo IP del mittente in ingresso. Ciò potrebbe modificare i verdetti del filtro e, se non si sta ignorando Exchange Online Protection, ciò potrebbe alterare il recapito di determinati messaggi. In questo caso potrebbe essere necessario ignorare temporaneamente il filtro per analizzare l'impatto. To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one). Per informazioni dettagliate sui componenti delle regole e sul loro funzionamento, vedere Mail flow rules (transport rules) in Exchange Online.

## <a name="evaluate-capabilities"></a>Valutare le funzionalità

Dopo aver generato il report di valutazione, vedere quanti collegamenti alle minacce avanzate, allegati di minacce avanzate e potenziali imitazioni sono stati identificati nelle aree di lavoro di collaborazione e posta elettronica dell'organizzazione.

Una volta scaduta la versione di valutazione, è possibile continuare ad accedere al report per 90 giorni. Tuttavia, non raccoglierà altre informazioni. Se si desidera continuare a usare Microsoft Defender per Office 365 dopo la scadenza della versione di valutazione, assicurarsi di acquistare un abbonamento a pagamento per [Microsoft Defender per Office 365 (Piano 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Puoi passare a Impostazioni **per** aggiornare il routing o disattivare la valutazione in qualsiasi momento. Tuttavia, è necessario eseguire di nuovo lo stesso processo di configurazione nel caso in cui si decida di continuare la valutazione dopo averlo disattivato.

## <a name="provide-feedback"></a>Inviare feedback

Il feedback degli utenti ci aiuta a migliorare la protezione dell'ambiente da attacchi avanzati. Condividi l'esperienza e le impressioni delle funzionalità del prodotto e dei risultati della valutazione.

Seleziona **Inviare commenti** e suggerimenti per inviare commenti e suggerimenti.
