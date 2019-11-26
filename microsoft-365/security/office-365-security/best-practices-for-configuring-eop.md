---
title: Procedure consigliate per la configurazione di EOP e Office 365 ATP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Seguire queste procedure consigliate per Exchange Online Protection (EOP) per eseguire una configurazione corretta ed evitare che si verifichino errori comuni.
ms.openlocfilehash: 3146cb9a5141dfe87e9f31791c107be296121126
ms.sourcegitcommit: e27fe0d97b9c446b1cc80561f7190d08c12d9e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2019
ms.locfileid: "39262699"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>Procedure consigliate per la configurazione di EOP e Office 365 ATP

Seguire queste procedure consigliate per Exchange Online Protection (EOP) per eseguire una configurazione corretta ed evitare che si verifichino errori comuni. In questo argomento si presuppone che il processo di installazione sia già stato completato. Se l'installazione di EOP non è stata completata, vedere [Installazione del servizio EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Utilizzo di un dominio di prova

È opportuno utilizzare un dominio di prova, un sottodominio oppure un dominio di volume non elevato per provare le funzionalità del servizio prima di implementarle in domini con volumi di produzione maggiori.

## <a name="synchronize-recipients"></a>Sincronizzazione dei destinatari

Se nell'organizzazione sono presenti account utente esistenti in un ambiente Active Directory locale, è possibile sincronizzare tali account in Azure Active Directory nel cloud. Si consiglia di utilizzare la sincronizzazione della directory. Per ulteriori informazioni sui vantaggi della sincronizzazione della directory e sulla procedura per impostarla, vedere [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Impostazioni consigliate

Gli amministratori della sicurezza sono autorizzati a personalizzare le impostazioni di sicurezza che satistfy le esigenze degli ambienti. Anche se, come regola generale, esistono due livelli di sicurezza in EOP e Office 365 ATP che è consigliabile: standard e Strict. Queste impostazioni sono elencate nelle [impostazioni consigliate per EOP e Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md). 

### <a name="miscellaneousnon-policy-settings"></a>Varie/impostazioni non relative ai criteri

Queste impostazioni riguardano una serie di funzionalità esterne ai criteri di sicurezza.

Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|[Configurazione di SPF in Office 365 per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sì|Sì||
|[Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md)|Sì|Sì||
|[Utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md)|Sì|Sì|Utilizzare Action = Quarantine per standard e Action = Reject per strict.|
|Distribuire il componente aggiuntivo dei messaggi di report per migliorare la segnalazione degli utenti finali di messaggi di posta elettronica sospetti|Sì|Sì||
|Pianificare i report di malware e posta indesiderata|Sì|Sì||
|L'inoltro automatico ai domini esterni deve essere non consentito o monitorato|Sì|Sì||
|Il controllo unificato dovrebbe essere abilitato|Sì|Sì||
|Connettività IMAP alla cassetta postale|Disattivato|Disattivato||
|Connettività POP alla cassetta postale|Disattivato|Disattivato||
|Invio con autenticazione SMTP alla cassetta postale|Disattivato|Disattivato||
|Connettività EWS alla cassetta postale|Disattivato|Disattivato||
|Connettività di PowerShell|Disattivato|Disattivato||
|Utilizzare l'intelligence spoof per i mittenti whitelist quando possibile|Sì|Sì||
|Blocco Edge basato su directory (DBEB)|Abilitato|Abilitato|Tipo di dominio = autorevole|
|[Configurare l'autenticazione a più fattori per tutti gli account di amministrazione](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Abilitato|Abilitato||

## <a name="troubleshooting"></a>Risoluzione dei problemi

Risoluzione dei problemi generali e delle tendenze utilizzando i report nell'interfaccia di amministrazione. Trovare i dati su un messaggio specifici di un singolo punto utilizzando lo strumento di traccia dei messaggi. Per ulteriori informazioni sulla segnalazione, vedere [Creazione di rapporti e traccia dei messaggi in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Per ulteriori informazioni sullo strumento di traccia dei messaggi, vedere [Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message).

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>Segnalazione di falsi positivi e falsi negativi a Microsoft

Gli amministratori devono inviare falsi negativi (posta indesiderata) e falsi positivi (non indesiderati) a Microsoft tramite il portale di amministrazione degli invii. È possibile inviare messaggi di posta elettronica, file e URL per consentire agli amministratori di determinare il motivo per cui è stato recapitato o non è stato recapitato alcun messaggio agli utenti finali Per informazioni dettagliate, vedere [come inviare messaggi di posta indesiderata, phishing, URL e file sospetti a Microsoft per l'analisi di Office 365](admin-submission.md).

Gli utenti finali possono anche segnalare direttamente falsi negativi (posta indesiderata) e falsi positivi (non di posta indesiderata) a Microsoft per l'analisi quando non sono d'accordo con le sentenze fornite. Per informazioni dettagliate, vedere [inviare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).


## <a name="create-mail-flow-rules"></a>Creazione di regole del flusso di posta

Creare regole del flusso di posta o filtri personalizzati per soddisfare le proprie esigenze aziendali.

Quando si distribuisce una nuova regola alla produzione, selezionare prima una delle modalità di prova per verificare l'effetto della regola. Quando si è soddisfatti del funzionamento della regola, cambiare la modalità della regola in **Applica**.

Quando si distribuiscono nuove regole, prendere in considerazione l'aggiunta dell'azione aggiuntiva **Genera rapporto operazioni non consentite** per monitorare la regola in azione.

Negli ambienti ibridi in cui l'organizzazione include sia Exchange locale che Office 365, prendere in considerazione le condizioni che si utilizzano nelle regole del flusso di posta. Se si desidera che le regole vengano applicate all'intera organizzazione, assicurarsi di utilizzare le condizioni disponibili sia in Exchange locale che in Office 365. Anche se la maggior parte delle condizioni sono disponibili in entrambi gli ambienti, sono disponibili solo in un ambiente o nell'altro. Per ulteriori informazioni, vedere [regole del flusso di posta (regole di trasporto) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).


