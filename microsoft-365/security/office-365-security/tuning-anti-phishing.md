---
title: Ottimizzare la protezione anti-phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Gli amministratori possono imparare a identificare i motivi per cui e come è stato ottenuto un messaggio di phishing in Microsoft 365 e cosa fare per evitare ulteriori messaggi di phishing in futuro.
ms.openlocfilehash: 8a2c63d499317427b921d7786dd60b3ad4f18c42
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615385"
---
# <a name="tune-anti-phishing-protection"></a>Ottimizzare la protezione anti-phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Anche se Microsoft 365 viene fornito con una vasta gamma di funzionalità di anti-phishing abilitate per impostazione predefinita, è possibile che alcuni messaggi di phishing possano continuare a passare alle cassette postali. In questo argomento vengono descritte le operazioni che è possibile eseguire per individuare il motivo per cui è stato effettuato un messaggio di phishing e cosa è possibile fare per modificare le impostazioni di anti-phishing nell'organizzazione di Microsoft 365 _senza peggiorare la situazione_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First Things First: Deal with any compromised accounts e assicuratevi di bloccare altri messaggi di phishing dall'ottenere

Se l'account di un destinatario è stato compromesso a causa del messaggio di phishing, seguire la procedura descritta in [risposta a un account di posta elettronica compromesso in Microsoft 365](responding-to-a-compromised-email-account.md).

Se l'abbonamento include Microsoft Defender per Office 365, è possibile utilizzare [office 365 Threat Intelligence](office-365-ti.md) per identificare gli altri utenti che hanno ricevuto anche il messaggio di phishing. Sono disponibili altre opzioni per bloccare i messaggi di phishing:

- [Collegamenti sicuri in Microsoft Defender per Office 365](set-up-atp-safe-links-policies.md)

- [Allegati sicuri in Microsoft Defender per Office 365](set-up-atp-safe-attachments-policies.md)

- [Criteri di anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md). Si noti che è possibile aumentare temporaneamente **le soglie di phishing avanzate** nel criterio da **standard** a **aggressivo**, **più aggressivo** o **più aggressivo**.

Verificare che queste funzionalità di protezione per Office 365 siano attivate.

## <a name="report-the-phishing-message-to-microsoft"></a>Segnalare il messaggio di phishing a Microsoft

La segnalazione dei messaggi di phishing è utile per ottimizzare i filtri utilizzati per proteggere tutti i clienti in Microsoft 365. Per istruzioni, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Esaminare le intestazioni del messaggio

È possibile esaminare le intestazioni del messaggio di phishing per vedere se c'è qualcosa che può essere fatto personalmente per evitare che vengano inviati più messaggi di phishing. In altre parole, l'esame delle intestazioni dei messaggi può essere utile per identificare le impostazioni dell'organizzazione responsabili dell'autorizzazione dei messaggi di phishing.

In particolare, è necessario controllare il campo di intestazione **X-Forefront-antispam-report** nelle intestazioni del messaggio per le indicazioni del filtro ignorato per la posta indesiderata o il phishing nel valore del filtro di posta indesiderata (SFV). I messaggi che ignorano il filtro avranno una voce di `SCL:-1` , il che significa che una delle impostazioni ha consentito questo messaggio mediante l'override dei verdetti di posta indesiderata o di phishing che sono stati determinati dal servizio. Per ulteriori informazioni su come ottenere le intestazioni del messaggio e l'elenco completo di tutte le intestazioni dei messaggi di protezione da posta indesiderata e anti-phishing disponibili, vedere [intestazioni dei messaggi di protezione da posta indesiderata in Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Procedure consigliate per mantenere la protezione

- Su base mensile, eseguire il [Punteggio sicuro](../mtp/microsoft-secure-score.md) per valutare le impostazioni di sicurezza dell'organizzazione.

- Per i messaggi che finiscono in quarantena per sbaglio o per i messaggi consentiti tramite, è consigliabile cercare tali messaggi in [Esplora minacce e rilevamenti in tempo reale](threat-explorer.md). È possibile eseguire una ricerca in base al mittente, al destinatario o all'ID del messaggio. Dopo aver individuato il messaggio, passare a dettagli facendo clic sull'oggetto. Per un messaggio in quarantena, vedere che cos'è la "tecnologia di rilevamento" in modo che sia possibile utilizzare il metodo appropriato per eseguire l'override. Per un messaggio consentito, vedere i criteri consentiti per il messaggio.

- La posta contraffatta è contrassegnata come phishing in Defender per Office 365. A volte lo spoofing è benigno e a volte gli utenti non lo desiderano in quarantena. Per ridurre al minimo l'impatto degli utenti, esaminare periodicamente il [report di intelligence spoof](learn-about-spoof-intelligence.md). Dopo aver esaminato e apportato le modifiche necessarie, è possibile avere la certezza di [configurare l'intelligence spoof](set-up-anti-phishing-policies.md#spoof-settings) per la **quarantena** dei messaggi sospetti anziché recapitarli nella cartella posta indesiderata dell'utente.

- È possibile ripetere il passaggio precedente per la rappresentazione (dominio o utente). Il rapporto di rappresentazione è disponibile in  \>  \> **Insights** dashboard di gestione delle minacce.

- Esaminare periodicamente il [rapporto sullo stato della protezione dalle minacce](view-reports-for-atp.md#threat-protection-status-report).

- Alcuni clienti consentono inavvertitamente di inviare messaggi di phishing inserendo i propri domini nell'elenco Consenti mittente o Consenti dominio nei criteri di protezione da posta indesiderata. Anche se questa configurazione consentirà alcuni messaggi legittimi tramite, consentirà anche messaggi dannosi che verrebbero normalmente bloccati dai filtri di posta indesiderata e/o phishing. Invece di consentire il dominio, è necessario correggere il problema sottostante.

  Il modo migliore per gestire i messaggi legittimi bloccati da Microsoft 365 (falsi positivi) che coinvolgono i mittenti nel dominio consiste nel configurare completamente e completamente i record SPF, DKIM e DMARC in DNS per _tutti_ i domini di posta elettronica:

  - Verificare che il record SPF identifichi _tutte le_ origini della posta elettronica per i mittenti del dominio (non dimenticare i servizi di terze parti).

  - Utilizzare l'operazione non riuscita ( \- tutto) per garantire che i mittenti non autorizzati vengano rifiutati dai sistemi di posta elettronica configurati per l'esecuzione. È possibile utilizzare l' [Intelligence spoof](learn-about-spoof-intelligence.md) per identificare i mittenti che utilizzano il dominio in modo che sia possibile includere mittenti di terze parti autorizzati nel record SPF.

  Per istruzioni sulla configurazione, vedere:

  - [Configurazione di SPF per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato](use-dkim-to-validate-outbound-email.md)

  - [Usare DMARC per convalidare la posta elettronica](use-dmarc-to-validate-email.md)

- Quando possibile, è consigliabile recapitare la posta elettronica per il dominio direttamente a Microsoft 365. In altre parole, puntare il record MX del dominio Microsoft 365 a Microsoft 365. Exchange Online Protection (EOP) è in grado di fornire la migliore protezione per gli utenti del cloud quando la posta viene recapitata direttamente a Microsoft 365. Se è necessario utilizzare un sistema di igiene della posta elettronica di terze parti di fronte a EOP, utilizzare il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Gli utenti devono [segnalare i messaggi](enable-the-report-message-add-in.md) a Microsoft, che possono formare il sistema. Gli amministratori dovrebbero anche avvalersi delle funzionalità di [invio di amministratore](admin-submission.md) .

- L'autenticazione a più fattori è un buon modo per impedire gli account compromessi. È consigliabile prendere in considerazione l'abilitazione dell'AMF per tutti gli utenti. Per un approccio graduale, iniziare abilitando l'AMF per gli utenti più sensibili (amministratori, dirigenti e così via) prima di abilitare l'AMF per tutti. Per istruzioni, vedere [configurare l'autenticazione](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)a più fattori.

- Le regole di inoltro ai destinatari esterni vengono spesso utilizzate dagli utenti malintenzionati per estrarre i dati. Utilizzare le informazioni sulla **revisione delle regole di inoltro delle cassette postali** in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) per individuare e persino impedire l'inoltro delle regole ai destinatari esterni. Per ulteriori informazioni, vedere [attenuazione delle regole di inoltro esterno client con Secure Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
