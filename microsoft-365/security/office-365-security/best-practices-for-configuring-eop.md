---
title: Procedure consigliate per la configurazione di EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Seguire queste procedure consigliate per l'uso autonomo di Exchange Online Protection (EOP) per essere configurati per l'esito positivo ed evitare errori comuni di configurazione.
ms.openlocfilehash: ade41b5343e19f75658f01e6c395c470e230b315
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351928"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Procedure consigliate per la configurazione di EOP autonomo

Seguire queste procedure consigliate per l'uso autonomo di Exchange Online Protection (EOP) per essere configurati per l'esito positivo ed evitare errori comuni di configurazione. In questo argomento si presuppone che il processo di installazione sia già stato completato. Se l'installazione di EOP non è stata completata, vedere [Installazione del servizio EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Utilizzo di un dominio di prova

È opportuno utilizzare un dominio di prova, un sottodominio oppure un dominio di volume non elevato per provare le funzionalità del servizio prima di implementarle in domini con volumi di produzione maggiori.

## <a name="synchronize-recipients"></a>Sincronizzazione dei destinatari

Se nell'organizzazione sono presenti account utente esistenti in un ambiente Active Directory locale, è possibile sincronizzare tali account in Azure Active Directory nel cloud. Si consiglia di utilizzare la sincronizzazione della directory. Per ulteriori informazioni sui vantaggi della sincronizzazione della directory e sulla procedura per impostarla, vedere [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Impostazioni consigliate

Gli amministratori della sicurezza sono autorizzati a personalizzare le impostazioni di sicurezza per soddisfare le esigenze della propria organizzazione. Anche se, come regola generale, esistono due livelli di sicurezza in EOP e Office 365 ATP che è consigliabile: standard e Strict. Queste impostazioni sono elencate nelle [impostazioni consigliate per EOP e Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Varie/impostazioni non relative ai criteri

Queste impostazioni riguardano una serie di funzionalità esterne ai criteri di sicurezza.

|||||
|---|---|---|---|
|**Nome della funzionalità di sicurezza**|**Standard**|**Rigorosa**|**Commento**|
|[Configurazione di SPF per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sì|Sì||
|[Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md)|Sì|Sì||
|[Utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md)|Sì|Sì|Utilizzare `action=quarantine` per standard e `action=reject` per strict.|
|Distribuire il [componente aggiuntivo](enable-the-report-message-add-in.md) per i messaggi di report per migliorare la segnalazione degli utenti finali di messaggi di posta elettronica sospetti|Sì|Sì||
|Pianificare i report di malware e posta indesiderata|Sì|Sì||
|L'inoltro automatico ai domini esterni deve essere non consentito o monitorato|Sì|Sì||
|Il controllo unificato dovrebbe essere abilitato|Sì|Sì||
|[Connettività IMAP alla cassetta postale](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disattivato|Disattivato||
|[Connettività POP alla cassetta postale](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disattivato|Disattivato||
|Inoltro SMTP autenticato|Disattivato|Disattivato|Inoltro SMTP client autenticato (noto anche come invio SMTP client o autenticazione SMTP) per i client POP3 e IMAP4 per l'invio di posta elettronica.|
|Connettività EWS alla cassetta postale|Disattivato|Disattivato||
|[Connettività di PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Disattivato|Disattivato|Disponibile per gli utenti di cassette postali o per gli utenti di posta (oggetti utente restituiti dal cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) ).|
|Utilizzare l' [Intelligence spoof](learn-about-spoof-intelligence.md) per i mittenti whitelist quando possibile|Sì|Sì||
|[Blocco Edge basato su directory (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Abilitato|Abilitato|Tipo di dominio = autorevole|
|[Configurare l'autenticazione a più fattori per tutti gli account di amministrazione](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Abilitato|Abilitato||
|

## <a name="troubleshooting"></a>Risoluzione dei problemi

Risoluzione dei problemi generali e delle tendenze utilizzando i report nell'interfaccia di amministrazione. Trovare i dati su un messaggio specifici di un singolo punto utilizzando lo strumento di traccia dei messaggi. Per ulteriori informazioni sulla segnalazione, vedere [Creazione di rapporti e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Per ulteriori informazioni sullo strumento di traccia dei messaggi, vedere [Message Trace in the Security & Compliance Center](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Segnalare falsi positivi e falsi negativi a Microsoft

Per migliorare il filtraggio della posta indesiderata nel servizio per tutti, è necessario segnalare falsi positivi (buona posta elettronica contrassegnata come difettosa) e falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Creazione di regole del flusso di posta

Creare regole del flusso di posta (note anche come regole di trasporto) oppure filtri personalizzati per soddisfare le proprie esigenze aziendali.

Quando si distribuisce una nuova regola alla produzione, selezionare prima una delle modalità di prova per verificare l'effetto della regola. Quando si è soddisfatti del funzionamento della regola, cambiare la modalità della regola in **Applica**.

Quando si distribuiscono nuove regole, prendere in considerazione l'aggiunta dell'azione aggiuntiva **Genera rapporto operazioni non consentite** per monitorare la regola in azione.

Negli ambienti ibridi in cui l'organizzazione include sia Exchange locale sia Exchange Online, prendere in considerazione le condizioni che si utilizzano nelle regole del flusso di posta. Se si desidera che le regole vengano applicate all'intera organizzazione, assicurarsi di utilizzare le condizioni disponibili sia in Exchange locale che in Exchange Online. Anche se la maggior parte delle condizioni sono disponibili in entrambi gli ambienti, sono disponibili solo in un ambiente o nell'altro. Per ulteriori informazioni, vedere [regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
