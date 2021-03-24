---
title: Procedure consigliate per la configurazione di EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Seguire queste procedure consigliate per Exchange Online Protection (EOP) autonomo per configurare se stessi per l'esito positivo ed evitare errori di configurazione comuni.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfd0b7290bdcded887ef6b81d5b0d4acbdd6cddb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065450"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Procedure consigliate per la configurazione di EOP autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

Seguire queste procedure consigliate per Exchange Online Protection (EOP) autonomo per configurare se stessi per l'esito positivo ed evitare errori di configurazione comuni. In questo argomento si presuppone che il processo di installazione sia già stato completato. Se l'installazione di EOP non è stata completata, vedere [Installazione del servizio EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Utilizzo di un dominio di prova

È opportuno utilizzare un dominio di prova, un sottodominio oppure un dominio di volume non elevato per provare le funzionalità del servizio prima di implementarle in domini con volumi di produzione maggiori.

## <a name="synchronize-recipients"></a>Sincronizzazione dei destinatari

Se l'organizzazione dispone di account utente esistenti in un ambiente Active Directory locale, è possibile sincronizzare tali account con Azure Active Directory nel cloud. Si consiglia di utilizzare la sincronizzazione della directory. Per ulteriori informazioni sui vantaggi della sincronizzazione della directory e sulla procedura per impostarla, vedere [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Impostazioni consigliate

Microsoft consente agli amministratori della sicurezza di personalizzare le impostazioni di sicurezza per soddisfare le esigenze dell'organizzazione. Anche se, come regola generale, sono disponibili due livelli di sicurezza in EOP e Microsoft Defender per Office 365 che è consigliabile: Standard e Strict. Queste impostazioni sono elencate in [Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365.](recommended-settings-for-eop-and-office365.md)

### <a name="miscellaneousnon-policy-settings"></a>Impostazioni varie/non relative ai criteri

Queste impostazioni coprono un'ampia gamma di funzionalità esterne ai criteri di sicurezza.

<br>

****

|Nome funzionalità di sicurezza|Standard|Strict|Comment|
|---|---|---|---|
|[Configurazione di SPF per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sì|Sì||
|[Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md)|Sì|Sì||
|[Utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md)|Sì|Sì|Utilizzare `action=quarantine` per Standard e per `action=reject` Strict.|
|Distribuire il [componente aggiuntivo Segnala](enable-the-report-message-add-in.md) messaggio o Segnala [phishing](enable-the-report-phish-add-in.md) per migliorare la segnalazione da parte dell'utente finale della posta elettronica sospetta|Sì|Sì||
|Pianificare i rapporti di malware e posta indesiderata|Sì|Sì||
|L'inoltro automatico ai domini esterni deve essere non consentito o monitorato|Sì|Sì||
|Il controllo unificato deve essere abilitato|Sì|Sì||
|[Connettività IMAP alla cassetta postale](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disattivato|Disattivato||
|[Connettività POP alla cassetta postale](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disattivato|Disattivato||
|Invio SMTP autenticato|Disattivato|Disattivato|L'invio SMTP del client autenticato (noto anche come invio SMTP client o AUTENTICAZIONE SMTP) è necessario per i client POP3 e IMAP4 e per le applicazioni e i dispositivi che generano e inviano posta elettronica. <p> Per istruzioni su come abilitare e disabilitare l'autenticazione SMTP a livello globale o selettivo, vedere [Enable or disable authenticated client SMTP submission in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission).|
|Connettività EWS alla cassetta postale|Disattivato|Disattivato|Outlook utilizza i Servizi Web Exchange per la disponibilità, le impostazioni fuori sede e la condivisione del calendario. Se non è possibile disabilitare EWS a livello globale, sono disponibili le opzioni seguenti: <ul><li>Utilizzare [i criteri di](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) autenticazione per impedire a EWS di utilizzare l'autenticazione di base se i client supportano l'autenticazione moderna (autenticazione moderna).</li><li>Utilizzare [le regole di Accesso](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) client per limitare EWS a utenti specifici o indirizzi IP di origine.</li><li>Controllare l'accesso di EWS a applicazioni specifiche a livello globale o per utente. Per istruzioni, vedere [Control access to EWS in Exchange](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange).</li></ul> <p> Il [componente aggiuntivo Segnala](enable-the-report-message-add-in.md) [](enable-the-report-phish-add-in.md) messaggio e segnala phishing usa REST per impostazione predefinita negli ambienti supportati, ma verrà nuovamente visualizzato in EWS se REST non è disponibile. Gli ambienti supportati che utilizzano REST sono:<ul><li>Exchange Online</li><li>Exchange 2019 o Exchange 2016</li><li>Outlook per Windows corrente da un abbonamento a Microsoft 365 o acquisto una sola volta di Outlook 2019.</li><li>Outlook corrente per Mac da un abbonamento a Microsoft 365 o un acquisto una sola volta di Outlook per Mac 2016 o versione successiva.</li><li>Outlook per iOS e Android</li><li>Outlook sul Web</li></ul>|
|[Connettività di PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)|Disattivato|Disattivato|Disponibile per gli utenti delle cassette postali o gli utenti di posta (oggetti utente restituiti dal cmdlet [Get-User).](/powershell/module/exchange/get-user)|
|Usare [spoof intelligence per](learn-about-spoof-intelligence.md) aggiungere mittenti all'elenco consenti|Sì|Sì||
|[Blocco edge basato su directory (DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Abilitato|Abilitato|Tipo di dominio = Autorevole|
|[Configurare l'autenticazione a più fattori per tutti gli account amministratore](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Abilitato|Abilitato||
|

## <a name="troubleshooting"></a>Risoluzione dei problemi

Risolvere i problemi e le tendenze generali utilizzando i report nell'interfaccia di amministrazione. Trovare i dati su un messaggio specifici di un singolo punto utilizzando lo strumento di traccia dei messaggi. Per ulteriori informazioni sulla segnalazione, vedere [Creazione di rapporti e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Per ulteriori informazioni sullo strumento di traccia dei messaggi, vedere Traccia dei messaggi nel [Centro sicurezza & conformità.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Segnalare falsi positivi e falsi negativi a Microsoft

Per migliorare il filtro della posta indesiderata nel servizio per tutti gli utenti, è consigliabile segnalare a Microsoft falsi positivi (buona posta elettronica contrassegnata come non buona) e falsi negativi (posta elettronica non consentita) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Creazione di regole del flusso di posta

Creare regole del flusso di posta (note anche come regole di trasporto) o filtri personalizzati per soddisfare le esigenze aziendali.

Quando si distribuisce una nuova regola alla produzione, selezionare prima una delle modalità di prova per verificare l'effetto della regola. Quando si è soddisfatti del funzionamento della regola, cambiare la modalità della regola in **Applica**.

Quando si distribuiscono nuove regole, prendere in considerazione l'aggiunta dell'azione aggiuntiva **Genera rapporto operazioni non consentite** per monitorare la regola in azione.

Negli ambienti ibridi in cui l'organizzazione include Sia Exchange locale che Exchange Online, prendere in considerazione le condizioni utilizzate nelle regole del flusso di posta. Se si desidera applicare le regole all'intera organizzazione, assicurarsi di utilizzare le condizioni disponibili sia in Exchange locale che in Exchange Online. Sebbene la maggior parte delle condizioni sia disponibile in entrambi gli ambienti, alcune sono disponibili solo in un ambiente o nell'altro. Per ulteriori informazioni, [vedere Mail flow rules (transport rules) in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)