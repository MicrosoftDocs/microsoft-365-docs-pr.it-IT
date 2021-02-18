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
ms.openlocfilehash: c64a9592d93ef046ad1c023a49bf378ccf6cf503
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290834"
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

Microsoft consente agli amministratori della sicurezza di personalizzare le impostazioni di sicurezza per soddisfare le esigenze dell'organizzazione. Anche se, come regola generale, esistono due livelli di sicurezza in EOP e Microsoft Defender per Office 365 che è consigliabile: Standard e Strict. Queste impostazioni sono elencate nelle impostazioni [consigliate per EOP e Microsoft Defender per la sicurezza di Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Impostazioni varie/non relative ai criteri

Queste impostazioni riguardano un'ampia gamma di funzionalità esterne ai criteri di sicurezza.

****

|Nome caratteristica di sicurezza|Standard|Strict|Commento|
|---|---|---|---|
|[Configurazione di SPF per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sì|Sì||
|[Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md)|Sì|Sì||
|[Utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md)|Sì|Sì|Utilizzare `action=quarantine` per Standard e `action=reject` Strict.|
|Distribuire il [componente aggiuntivo Segnala messaggio o](enable-the-report-message-add-in.md) Segnala [phishing](enable-the-report-phish-add-in.md) per migliorare la segnalazione di messaggi di posta elettronica sospetti da parte dell'utente finale|Sì|Sì||
|Pianificare i rapporti di malware e posta indesiderata|Sì|Sì||
|L'inoltro automatico ai domini esterni deve essere non consentito o monitorato|Sì|Sì||
|Il controllo unificato deve essere abilitato|Sì|Sì||
|[Connettività IMAP alla cassetta postale](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disattivato|Disattivato||
|[Connettività POP alla cassetta postale](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Disattivato|Disattivato||
|Invio SMTP autenticato|Disattivato|Disattivato|L'invio SMTP del client autenticato (noto anche come invio SMTP client o AUTH SMTP) è necessario per l'invio di posta elettronica da parte dei client POP3 e IMAP4.|
|Connettività EWS alla cassetta postale|Disattivato|Disattivato||
|[Connettività PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Disattivato|Disattivato|Disponibile per gli utenti delle cassette postali o gli utenti di posta (oggetti utente restituiti dal cmdlet [Get-User).](https://docs.microsoft.com/powershell/module/exchange/get-user)|
|Usare [spoof intelligence per](learn-about-spoof-intelligence.md) aggiungere mittenti all'elenco Consenti|Sì|Sì||
|[Blocco edge basato su directory (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Abilitato|Abilitato|Tipo di dominio = Autorevole|
|[Configurare l'autenticazione a più fattori per tutti gli account amministratore](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Abilitato|Abilitato||
|

## <a name="troubleshooting"></a>Risoluzione dei problemi

Risolvere i problemi e le tendenze generali utilizzando i report nell'interfaccia di amministrazione. Trovare i dati su un messaggio specifici di un singolo punto utilizzando lo strumento di traccia dei messaggi. Per ulteriori informazioni sulla segnalazione, vedere [Creazione di rapporti e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Per ulteriori informazioni sullo strumento di traccia dei messaggi, vedere [Traccia messaggio nel Centro sicurezza & conformità.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Segnalare falsi positivi e falsi negativi a Microsoft

Per migliorare il filtro della posta indesiderata nel servizio per tutti, è consigliabile segnalare falsi positivi (buona posta elettronica contrassegnata come non buona) e falsi negativi (posta elettronica non consentita) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Creazione di regole del flusso di posta

Creare regole del flusso di posta (note anche come regole di trasporto) o filtri personalizzati per soddisfare le esigenze aziendali.

Quando si distribuisce una nuova regola alla produzione, selezionare prima una delle modalità di prova per verificare l'effetto della regola. Quando si è soddisfatti del funzionamento della regola, cambiare la modalità della regola in **Applica**.

Quando si distribuiscono nuove regole, prendere in considerazione l'aggiunta dell'azione aggiuntiva **Genera rapporto operazioni non consentite** per monitorare la regola in azione.

Negli ambienti ibridi in cui l'organizzazione include sia Exchange locale che Exchange Online, considerare le condizioni utilizzate nelle regole del flusso di posta. Se si desidera applicare le regole all'intera organizzazione, assicurarsi di utilizzare le condizioni disponibili sia in Exchange locale che in Exchange Online. Anche se la maggior parte delle condizioni è disponibile in entrambi gli ambienti, alcune sono disponibili solo in un ambiente o nell'altro. Per ulteriori informazioni, vedere Regole del [flusso di posta (regole di trasporto) in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
