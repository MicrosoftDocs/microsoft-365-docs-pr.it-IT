---
title: Ottimizzare la protezione anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Gli amministratori possono imparare a identificare i motivi e il modo in cui un messaggio di phishing è stato inviato in Microsoft 365 e cosa fare per evitare ulteriori messaggi di phishing in futuro.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3abbafce36c589f60eb164fb29c714c980f8b98
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286490"
---
# <a name="tune-anti-phishing-protection"></a>Ottimizzare la protezione anti-phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Anche se Microsoft 365 include una serie di funzionalità anti-phishing abilitate per impostazione predefinita, è possibile che alcuni messaggi di phishing siano ancora in grado di accedere alle cassette postali. In questo argomento vengono descritte le operazioni che è possibile eseguire per individuare il motivo per cui è stato inviato un messaggio di phishing e le operazioni che è possibile eseguire per modificare le impostazioni di anti-phishing nell'organizzazione di Microsoft 365 senza peggiorare accidentalmente le _cose._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Prima di tutto: gestire gli account compromessi e assicurarsi di bloccare altri messaggi di phishing

Se l'account di un destinatario è stato compromesso a seguito del messaggio di phishing, seguire la procedura descritta in Rispondere a un account di posta elettronica compromesso [in Microsoft 365.](responding-to-a-compromised-email-account.md)

Se l'abbonamento include Microsoft Defender per Office 365, è possibile usare [Office 365 Threat Intelligence](office-365-ti.md) per identificare altri utenti che hanno ricevuto anche il messaggio di phishing. Sono disponibili ulteriori opzioni per bloccare i messaggi di phishing:

- [Collegamenti sicuri in Microsoft Defender per Office 365](set-up-atp-safe-links-policies.md)

- [Allegati sicuri in Microsoft Defender per Office 365](set-up-atp-safe-attachments-policies.md)

- [Criteri anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md) Tenere presente che è possibile aumentare temporaneamente le soglie di **phishing** avanzate nel criterio da **Standard** a **Aggressivo,** **Più** aggressivo o **Più aggressivo.**

Verificare che queste funzionalità di Defender per Office 365 siano attivate.

## <a name="report-the-phishing-message-to-microsoft"></a>Segnalare il messaggio di phishing a Microsoft

La segnalazione dei messaggi di phishing è utile per l'ottimizzazione dei filtri utilizzati per proteggere tutti i clienti in Microsoft 365. Per istruzioni, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>Esaminare le intestazioni dei messaggi

È possibile esaminare le intestazioni del messaggio di phishing per vedere se c'è qualcosa che si può fare da soli per impedire l'arrivo di altri messaggi di phishing. In altre parole, l'analisi delle intestazioni dei messaggi consente di identificare tutte le impostazioni dell'organizzazione responsabili dell'autorizzazione dei messaggi di phishing.

In particolare, è consigliabile controllare il campo di intestazione **X-Forefront-Antispam-Report** nelle intestazioni dei messaggi per le indicazioni di filtro ignorato per la posta indesiderata o phishing nel valore SFV (Spam Filtering Verdict). I messaggi che ignorano il filtro avranno una voce di , il che significa che una delle impostazioni ha consentito questo messaggio ignorando i verdetti di posta indesiderata o phishing determinati `SCL:-1` dal servizio. Per ulteriori informazioni su come ottenere le intestazioni dei messaggi e l'elenco completo di tutte le intestazioni dei messaggi di protezione da posta indesiderata e anti-phishing disponibili, vedere Intestazioni dei messaggi di protezione da posta indesiderata [in Microsoft 365.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>Procedure consigliate per la protezione

- Su base mensile, eseguire [Secure Score per](../mtp/microsoft-secure-score.md) valutare le impostazioni di sicurezza dell'organizzazione.

- Per i messaggi che finiscono in quarantena per errore o per i messaggi che sono consentiti, è consigliabile cercare tali messaggi in Esplora minacce e rilevamenti in [tempo reale.](threat-explorer.md) È possibile eseguire ricerche in base al mittente, al destinatario o all'ID messaggio. Dopo aver individuato il messaggio, passare ai dettagli facendo clic sull'oggetto. Per un messaggio in quarantena, esaminare la "tecnologia di rilevamento" in modo da poter utilizzare il metodo appropriato per eseguire l'override. Per un messaggio consentito, vedere quale criterio ha consentito il messaggio.

- La posta falsificata è contrassegnata come phishing in Defender per Office 365. A volte lo spoofing è innocuo e talvolta gli utenti non lo vogliono mettere in quarantena. Per ridurre al minimo l'impatto sugli utenti, rivedere periodicamente il [report spoof intelligence.](learn-about-spoof-intelligence.md) Dopo aver esaminato e apportato le sostituzioni necessarie,  è possibile configurare [spoof intelligence](set-up-anti-phishing-policies.md#spoof-settings) per mettere in quarantena i messaggi sospetti invece di recapitarli nella cartella Posta indesiderata dell'utente.

- È possibile ripetere il passaggio precedente per la rappresentazione (dominio o utente). Il report Rappresentazione è disponibile in **Threat Management** \> **Dashboard** \> **Insights.**

- Esaminare periodicamente il rapporto Sullo stato [di Protezione dalle minacce.](view-reports-for-atp.md#threat-protection-status-report)

- Alcuni clienti consentono inavvertitamente di inviare messaggi di phishing inserendo i propri domini nell'elenco Consenti mittente o Consenti nei criteri di protezione dalla posta indesiderata. Anche se questa configurazione consentirà l'invio di alcuni messaggi legittimi, consentirà anche messaggi dannosi che normalmente verrebbero bloccati dai filtri di posta indesiderata e/o phishing. Anziché consentire il dominio, è consigliabile correggere il problema sottostante.

  Il modo migliore per gestire i messaggi legittimi bloccati da Microsoft 365 (falsi positivi) che coinvolgono i mittenti nel dominio è quello  di configurare completamente i record SPF, DKIM e DMARC in DNS per tutti i domini di posta elettronica:

  - Verificare che il record  SPF identifichi tutte le origini della posta elettronica per i mittenti nel dominio (non dimenticare i servizi di terze parti).).

  - Utilizzare l'esito negativo (tutto) per garantire che i mittenti non autorizzati siano rifiutati dai sistemi di posta \- elettronica configurati per eseguire questa operazione. È possibile utilizzare [spoof intelligence per](learn-about-spoof-intelligence.md) identificare i mittenti che utilizzano il dominio, in modo da poter includere mittenti di terze parti autorizzati nel record SPF.

  Per istruzioni sulla configurazione, vedere:

  - [Configurazione di SPF per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato](use-dkim-to-validate-outbound-email.md)

  - [Usare DMARC per convalidare la posta elettronica](use-dmarc-to-validate-email.md)

- Se possibile, è consigliabile recapitare la posta elettronica per il dominio direttamente a Microsoft 365. In altre parole, puntare il record MX del dominio di Microsoft 365 a Microsoft 365. Exchange Online Protection (EOP) è in grado di fornire la migliore protezione per gli utenti cloud quando la posta viene recapitata direttamente a Microsoft 365. Se è necessario utilizzare un sistema di igiene della posta elettronica di terze parti davanti a EOP, utilizzare il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Gli utenti devono utilizzare il [componente aggiuntivo](enable-the-report-message-add-in.md) Segnala messaggio o Segnala [phishing](enable-the-report-phish-add-in.md) per segnalare i messaggi a Microsoft, che può formare il sistema. Gli amministratori devono inoltre sfruttare le funzionalità [di invio dell'amministratore.](admin-submission.md)

- L'autenticazione a più fattori (MFA) è un buon modo per evitare account compromessi. È consigliabile abilitare l'autenticazione a più fattori per tutti gli utenti. Per un approccio in più fasi, iniziare abilitando l'autenticazione a più fattori per gli utenti più sensibili (amministratori, dirigenti e così via) prima di abilitare la MFA per tutti. Per istruzioni, vedere [Configurare l'autenticazione a più fattori.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Le regole di inoltro ai destinatari esterni vengono spesso utilizzate dagli utenti malintenzionati per estrarre i dati. Utilizzare le **informazioni sulle regole di inoltro delle cassette** postali in Microsoft Secure [Score](../mtp/microsoft-secure-score.md) per trovare e persino impedire le regole di inoltro ai destinatari esterni. Per ulteriori informazioni, vedere [Mitigating Client External Forwarding Rules with Secure Score.](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
