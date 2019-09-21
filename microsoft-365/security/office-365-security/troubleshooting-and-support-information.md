---
title: Informazioni sul supporto tecnico e sulla risoluzione dei problemi
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: In questo argomento vengono descritti i passaggi utili alla risoluzione dei problemi a beneficio degli utenti finali e amministratori, inoltre sono fornite le informazioni su come contattare il supporto tecnico per l'assistenza.
ms.openlocfilehash: 2a8019ed58bfb88183d20a8292bd5a30d9b43f13
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084797"
---
# <a name="troubleshooting-and-support-information"></a>Supporto tecnico e risoluzione dei problemi

In questo argomento vengono descritti i passaggi utili alla risoluzione dei problemi a beneficio degli utenti finali e amministratori, inoltre sono fornite le informazioni su come contattare il supporto tecnico per l'assistenza.
  
## <a name="troubleshooting-for-users"></a>Risoluzione dei problemi per gli utenti

Talvolta potrebbero verificarsi alcuni problemi con Microsoft Office Outlook dopo aver aggiunto lo Strumento Rapporto posta indesiderata. Di seguito sono riportati i problemi che si potrebbero incontrare e i suggerimenti per risolverli. 
  
- Non accade nulla quando si fa clic su **Segnala posta indesiderata**
    
- Outlook si blocca dopo la selezione di un messaggio di posta elettronica
    
- La posta indesiderata segnalata non viene recapitata perché "non recapitabile"
    
### <a name="troubleshooting-tip"></a>Suggerimenti per la risoluzione dei problemi

1. Chiudere e riavviare Outlook.
    
2. Verificare che sia possibile creare e inviare un messaggio di prova. A tale scopo, è possibile inviare un messaggio di prova a un altro account di posta elettronica, di cui si abbia l'accesso, per verificare che il messaggio di posta elettronica sia stato ricevuto.
    
Se il problema persiste, contattare l'amministratore IT.
  
> [!TIP]
> È inoltre possibile inviare messaggi di spam direttamente a Microsoft tramite l'indirizzo di posta elettronica [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) e messaggi falsi positivi utilizzando l'indirizzo di posta elettronica [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com). Per ulteriori informazioni, vedere [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md). 
  
## <a name="troubleshooting-for-administrators"></a>Risoluzione dei problemi per gli amministratori

Un amministratore può incontrare problemi quando gli utenti utilizzano il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Office Outlook. Di seguito vengono forniti alcuni suggerimenti per la risoluzione dei problemi possibili. 
  
 **Problema:** Viene visualizzato continuamente un messaggio di errore che chiede agli utenti di contattare l'amministratore di sistema. 
  
### <a name="troubleshooting-tip"></a>Suggerimenti per la risoluzione dei problemi

1. Impostare il valore seguente del Registro di sistema su "Verbose":
    
  - **Outlook a 32 bit installato su sistema operativo a 32 bit:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **Outlook a 32 bit installato su sistema operativo a 64 bit:**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
  - **Outlook a 64 bit (sempre su sistema operativo a 64 bit):**
    
    HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel
    
2. Riavviare Microsoft Office Outlook e chiedere agli utenti di segnalare quando il messaggio di errore viene visualizzato.
    
3. Raccogliere i registri nei percorsi seguenti: 
    
    %LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt
    
4. Contattare il supporto tecnico di Exchange Online Protection per fornire i registri. 
    
 **Problema:** Gli utenti hanno scelto di non ricevere una conferma quando segnalano un messaggio di posta elettronica come indesiderato e ora richiedono di reimpostare l'opzione. 
  
### <a name="troubleshooting-tip"></a>Suggerimenti per la risoluzione dei problemi

1. Impostare il valore seguente del Registro di sistema su "True": HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk
    
2. Riavviare Microsoft Office Outlook
    
## <a name="support-information"></a>Informazioni sul supporto tecnico

Se si ha bisogno di assistenza per l'installazione, la configurazione o la disinstallazione del componente aggiuntivo, contattare il supporto tecnico utilizzando il nuovo collegamento richiesta di servizio nella pagina supporto nell'interfaccia di amministrazione di Microsoft 365. Per ulteriori opzioni, tra cui l'invio di una richiesta di servizio tramite le opzioni telefono e supporto self-service, vedere [Help and Support for EOP](help-and-support-for-eop.md).
  
## <a name="for-more-information"></a>Ulteriori informazioni

[Abilitare il componente aggiuntivo Segnala messaggio](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[Segnalazione di messaggi indesiderati a Microsoft](report-junk-email-messages-to-microsoft.md)
  

