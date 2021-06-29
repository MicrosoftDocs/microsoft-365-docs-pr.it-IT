---
title: Valutare Microsoft Defender per Office 365
description: Defender per Office 365 in modalità di valutazione crea Defender per Office 365 criteri di posta elettronica che registrano i verdetti, ad esempio malware, ma non agiscono sui messaggi.
keywords: valutare Office 365, Microsoft Defender per Office 365, valutazione di Office 365, provare Office 365, Microsoft Defender, Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
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
ms.openlocfilehash: 79d736330a40d33f5334196d165e72f487b6d959
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194782"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Valutare Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender for Office 365 valutazione è in anteprima pubblica. Questa versione di anteprima viene fornita senza un contratto di servizio. Alcune funzionalità potrebbero non essere supportate o avere funzionalità vincolate.

L'esecuzione di una valutazione approfondita del prodotto per la sicurezza può aiutare a prendere decisioni informate su aggiornamenti e acquisti. Aiuta a provare le funzionalità del prodotto di sicurezza per valutare in che modo può aiutare il team delle operazioni di sicurezza nelle attività quotidiane.

[L'esperienza](defender-for-office-365.md) di valutazione di Microsoft Defender per Office 365 è progettata per eliminare le complessità della configurazione di dispositivi e ambienti, in modo che tu possa concentrarti sulla valutazione delle funzionalità di Microsoft Defender per Office 365. Con la modalità di valutazione, tutti i messaggi inviati Exchange Online cassette postali possono essere valutati senza puntare i record MX a Microsoft. La funzionalità si applica solo alla protezione della posta elettronica e non Office client come Word, SharePoint o Teams.

Se non hai già una licenza che supporta Microsoft Defender per Office 365, puoi avviare una valutazione gratuita di [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) giorni e testare le funzionalità nel portale di Microsoft 365 Defender all'indirizzo <https://security.microsoft.com> . Ti piacerà la configurazione rapida e puoi disattivarla facilmente se necessario.

> [!NOTE]
> Se si è nel portale di Microsoft 365 Defender ( ), è possibile avviare un Defender per la valutazione <https://security.microsoft.com> di Office 365 qui: **Email & Collaboration** Policies \> **& Rules** \> **Threat policies** page \> **Others** section \> **Evaluation mode**.

## <a name="how-the-evaluation-works"></a>Funzionamento della valutazione

Defender per Office 365 in modalità di valutazione crea Defender per Office 365 criteri di posta elettronica che registrano i verdetti, ad esempio malware, ma non agiscono sui messaggi. Non è necessario modificare la configurazione del record MX.

Con la modalità di valutazione, [Cassaforte allegati,](safe-attachments.md) [Cassaforte](safe-links.md)e i criteri di rappresentazione basati [sull'intelligence](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) delle cassette postali vengono impostati per conto dell'utente. Tutti i criteri di Office 365 defender vengono creati in modalità non di imposizione in background e non sono visibili all'utente.

Nell'ambito dell'installazione, la modalità di valutazione configura anche [il filtro avanzato per i connettori.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Migliora l'accuratezza del filtro conservando le informazioni sull'indirizzo IP e sul mittente, che altrimenti vengono perse quando la posta passa attraverso un gateway di sicurezza della posta elettronica (ESG) davanti a Defender per Office 365. Il filtro avanzato per i connettori migliora inoltre l'accuratezza del filtro per i criteri di protezione da posta indesiderata e anti-phishing Exchange Online Protection (EOP) esistenti.

Il filtro avanzato per i connettori migliora l'accuratezza del filtro, ma può alterare la recapitabilità di alcuni messaggi se si dispone di un gruppo di protezione di Exchange davanti a Defender per Office 365 e attualmente non ignorare il filtro EOP. L'impatto è limitato ai criteri EOP; Defender per Office 365 criteri impostati come parte della valutazione vengono creati in modalità non di imposizione. Per ridurre al minimo il potenziale impatto sulla produzione, è possibile ignorare tutti i filtri EOP creando una regola del flusso di posta (nota anche come regola di trasporto) per impostare il livello di probabilità di posta indesiderata (SCL) dei messaggi su -1. Per informazioni dettagliate, vedere Use [mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)  

Quando viene impostata la modalità di valutazione, ogni giorno verrà aggiornato un rapporto con fino a 90 giorni di dati che quantificano i messaggi che sarebbero stati bloccati se i criteri fossero stati implementati (ad esempio, eliminare, inviare alla posta indesiderata, mettere in quarantena). I report vengono generati per tutti i rilevamenti di Defender Office 365 ed EOP. Vengono aggregati per tecnologia di rilevamento (ad esempio, la rappresentazione) e possono essere filtrati in base all'intervallo di tempo. Inoltre, i rapporti dei messaggi possono essere creati su richiesta per creare pivot personalizzati o per approfondire i messaggi usando Explorer.

Con l'esperienza di configurazione semplificata, puoi concentrarti su:

- Esecuzione della valutazione
- Ottenere un report dettagliato
- Analisi del report per l'azione
- Presentazione del risultato della valutazione

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="licensing"></a>Licenze

Per accedere alla valutazione, è necessario soddisfare i requisiti di licenza. Una delle licenze seguenti funzionerà:

- Microsoft Defender per Office 365 Piano 1
- Microsoft Defender per Office 365 Piano 2
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Se non hai una di queste licenze, dovrai ottenere una licenza di valutazione.

#### <a name="trial"></a>Valutazione

Per ottenere una licenza di valutazione per Microsoft Defender per  Office 365, è necessario disporre del ruolo amministratore fatturazione o **amministratore globale.** Richiedere l'autorizzazione a un utente con il ruolo amministratore globale. [Informazioni sulle sottoscrizioni e sulle licenze](../../commerce/licenses/subscriptions-and-licenses.md)

Dopo aver ottenuto il ruolo appropriato, il percorso consigliato è ottenere una licenza di valutazione per Microsoft Defender per Office 365 (Piano 2) nel interfaccia di amministrazione di Microsoft 365 andando a Fatturazione > Servizi di acquisto. La versione di valutazione include una versione di valutazione gratuita di 30 giorni per 25 licenze. [Ottenere una versione di valutazione per Microsoft Defender per Office 365 (Piano 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Avrai una finestra di 30 giorni con la valutazione per monitorare e segnalare le minacce avanzate. Avrai anche la possibilità di acquistare un abbonamento a pagamento se vuoi la versione completa di Defender per Office 365 funzionalità.

### <a name="roles"></a>Ruoli

**Exchange Online ruoli sono necessari** per configurare Defender per Office 365 in modalità di valutazione. L'assegnazione di un Microsoft 365 di conformità o di amministratore della sicurezza non funzionerà.

- [Informazioni sulle autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Informazioni sull'assegnazione dei ruoli di amministratore](../../admin/add-users/assign-admin-roles.md)

Sono necessari i ruoli seguenti:

|Attività|Ruolo (in Exchange Online)|
|---|---|
|Ottenere una versione di valutazione gratuita o acquistare Microsoft Defender per Office 365 (Piano 2)|Ruolo amministratore fatturazione O Ruolo amministratore globale|
|Creare criteri di valutazione|Ruolo Domini remoti e accettati; Ruolo di amministratore della sicurezza|
|Modificare i criteri di valutazione|Ruolo Domini remoti e accettati; Ruolo di amministratore della sicurezza|
|Eliminare i criteri di valutazione|Ruolo Domini remoti e accettati; Ruolo di amministratore della sicurezza |
|Visualizzare il report di valutazione|Ruolo di amministratore della sicurezza O ruolo lettore di sicurezza|
|

### <a name="enhanced-filtering"></a>Filtro avanzato

I Exchange Online Protection, ad esempio la protezione da posta indesiderata e in blocco, rimarranno invariati. Tuttavia, la valutazione attiva un filtro avanzato per i connettori, che può influire sul flusso di posta e sui criteri Exchange Online Protection se non ignorati.

Il filtro avanzato per i connettori consente ai tenant di utilizzare la protezione anti-spoofing. Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.

### <a name="urls"></a>URL

Gli URL verranno detonati durante il flusso di posta. Se non vuoi detonare URL specifici, gestisci l'elenco degli URL consentiti in modo appropriato. Per [informazioni dettagliate, vedere Manage the Tenant Allow/Block List.](tenant-allow-block-list.md)

I collegamenti URL nei corpi dei messaggi di posta elettronica non vengono inclusi, per ridurre l'impatto dei clienti.

### <a name="email-routing"></a>Routing della posta elettronica

Preparare i dettagli corrispondenti che sarà necessario configurare come viene instradato il messaggio di posta elettronica, incluso il nome del connettore in ingresso che instrada la posta. Se si utilizza solo Exchange Online Protection, non si dispone di un connettore.  [Informazioni sul flusso di posta e sul routing della posta elettronica](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Gli scenari di routing della posta elettronica supportati includono:

- Partner di terze parti **e/o provider** di servizi locali: il connettore in ingresso che si desidera valutare utilizza un provider di terze parti e/o si sta utilizzando una soluzione per la sicurezza della posta elettronica locale.
- **Microsoft Exchange Online protezione:** il tenant che si desidera valutare utilizza Office 365 per la sicurezza della posta elettronica e il record Mail Exchange (MX) punta a Microsoft.

### <a name="email-security-gateway"></a>Gateway di sicurezza della posta elettronica

Se si utilizza un gateway di sicurezza della posta elettronica di terze parti, è necessario conoscere il nome del provider. Se si usa un gruppo di protezione dei dati locale o fornitori non supportati, è necessario conoscere gli indirizzi IP pubblici per i dispositivi.

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

Trova la scheda di configurazione Office 365 di valutazione di Microsoft Defender per la versione di valutazione nel portale di Microsoft 365 Defender ( ) da <https://security.microsoft.com> tre punti di accesso:

- **Endpoint** \> **Gestione delle vulnerabilità** \> **Dashboard** ( <https://security.microsoft.com/tvm_dashboard> )
- **Collaborazione & posta elettronica** \> **Criteri & regole** \> **Criteri di minaccia** ( <https://security.microsoft.com/threatpolicy> )
- **Report** \> **Collaborazione & posta elettronica** \> **Rapporti & di collaborazione tramite posta elettronica** ( <https://security.microsoft.com/emailandcollabreport> )

## <a name="setting-up-the-evaluation"></a>Impostazione della valutazione

Dopo aver avviato il flusso di configurazione per la valutazione, ti verranno date due opzioni di routing. A seconda delle esigenze di configurazione e valutazione del routing della posta dell'organizzazione, è possibile scegliere se si utilizza un provider di servizi di terze parti e/o locale o solo Microsoft Exchange Online.

- Se si utilizza un partner di terze parti e/o un provider di servizi locale, è necessario selezionare il nome del fornitore dal menu a discesa. Fornire gli altri dettagli relativi al connettore.

- Selezionare Microsoft Exchange Online se il record MX punta a Microsoft e si dispone di una Exchange Online cassetta postale.

Rivedere le impostazioni e modificarle, se necessario. Selezionare quindi **Crea valutazione**. Dovresti ricevere un messaggio di conferma per indicare che la configurazione è stata completata.

Il report di valutazione Office 365 Microsoft Defender for Office 365 viene generato una volta al giorno. La compilazione dei dati potrebbe richiedere fino a 24 ore.

### <a name="exchange-mail-flow-rules-optional"></a>Exchange del flusso di posta elettronica (facoltativo)

Se si dispone di un gateway esistente, l'abilitazione della modalità di valutazione attiverà il filtro avanzato per i connettori. Questa funzionalità migliora l'accuratezza del filtro modificando l'indirizzo IP del mittente in ingresso. Questa funzionalità potrebbe modificare i verdetti del filtro e, se non si sta ignorando Exchange Online Protection, ciò potrebbe alterare il recapito per determinati messaggi. In questo caso, potrebbe essere necessario ignorare temporaneamente il filtro per analizzare l'impatto. Per ignorare il filtro, aprire l'interfaccia di amministrazione di Exchange e creare una regola del flusso di posta che imposta il livello di probabilità di posta indesiderata dei messaggi su -1 (se non ne hai già <https://admin.exchange.microsoft.com> uno). Per istruzioni, vedere [Use mail flow rules to set the spam confidence level (SCL) in messages in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).

## <a name="evaluate-capabilities"></a>Valutare le funzionalità

Dopo aver generato il report di valutazione, vedere quanti collegamenti alle minacce avanzate, allegati di minacce avanzate e potenziali imitazioni sono stati identificati nei messaggi di posta elettronica e nelle aree di lavoro di collaborazione nell'organizzazione.

Una volta scaduta la versione di valutazione, è possibile continuare ad accedere al report per 90 giorni. Tuttavia, non raccoglie ulteriori informazioni. Se vuoi continuare a usare Microsoft Defender per Office 365 dopo la scadenza della versione di valutazione, assicurati di acquistare un abbonamento a pagamento per [Microsoft Defender per Office 365 (Piano 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

È possibile passare a **Impostazioni** aggiornare il routing o disattivare la valutazione in qualsiasi momento. Tuttavia, è necessario eseguire di nuovo lo stesso processo di configurazione se si decide di continuare la valutazione dopo averlo disattivato.

## <a name="provide-feedback"></a>Inviare feedback

Il tuo feedback ci aiuta a migliorare la protezione dell'ambiente da attacchi avanzati. Condividere l'esperienza e le impression delle funzionalità del prodotto e dei risultati della valutazione.

Seleziona **Invia commenti e** suggerimenti per inviare commenti e suggerimenti.
