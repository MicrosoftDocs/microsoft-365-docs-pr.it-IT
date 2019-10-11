---
title: Informazioni sul supporto tecnico e sulla risoluzione dei problemi
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: c87744608930603f70e6be1132a0b405e9646b57
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441193"
---
# <a name="troubleshooting-and-support-information"></a>Supporto tecnico e risoluzione dei problemi

In questo argomento vengono descritti i passaggi utili alla risoluzione dei problemi a beneficio degli utenti finali e amministratori, inoltre sono fornite le informazioni su come contattare il supporto tecnico per l'assistenza.

## <a name="troubleshooting-for-users"></a>Risoluzione dei problemi per gli utenti

Occasionalmente, è possibile che si verifichino problemi con Microsoft Outlook dopo l'aggiunta del componente aggiuntivo per la segnalazione della posta indesiderata. Di seguito sono riportati i problemi che si potrebbero incontrare e i suggerimenti per risolverli.

- Non accade nulla quando si fa clic su **Segnala posta indesiderata**

- Outlook si blocca dopo la selezione di un messaggio di posta elettronica

- La posta indesiderata segnalata non viene recapitata perché "non recapitabile"

Per risolvere il problema, eseguire le operazioni seguenti:

1. Chiudere e riavviare Outlook.

2. Verificare che sia possibile creare e inviare un messaggio di prova. A tale scopo, è possibile inviare un messaggio di prova a un altro account di posta elettronica, di cui si abbia l'accesso, per verificare che il messaggio di posta elettronica sia stato ricevuto.

Se il problema persiste, contattare l'amministratore.

> [!TIP]
> È inoltre possibile inviare messaggi di spam direttamente a Microsoft tramite l'indirizzo di posta elettronica [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com) e messaggi falsi positivi utilizzando l'indirizzo di posta elettronica [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com). Per ulteriori informazioni, vedere [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="troubleshooting-for-administrators"></a>Risoluzione dei problemi per gli amministratori

In qualità di amministratore, è possibile che si verifichino problemi con gli utenti che utilizzano il componente aggiuntivo per la segnalazione della posta indesiderata per Outlook. Di seguito vengono forniti alcuni suggerimenti per la risoluzione dei problemi possibili.

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>Problema: viene visualizzato continuamente un messaggio di errore che chiede agli utenti di contattare l'amministratore di sistema

1. Impostare il valore seguente del Registro di sistema su "Verbose":

   - **32 bit Outlook installato su un sistema operativo a 32 bit**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32 bit Outlook installato su un sistema operativo a 64 bit**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **Outlook a 64 bit (sempre installato su un sistema operativo a 64 bit)**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Riavviare Outlook e chiedere agli utenti di riferire quando visualizzano il messaggio di errore.

3. Raccogliere i registri nei percorsi seguenti:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Contattare il supporto tecnico di Exchange Online Protection per fornire i registri.

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>Problema: gli utenti scelgono di non ricevere una conferma quando inviano un messaggio di posta elettronica come indesiderato e ora desiderano che l'opzione venga restituita

1. Impostare il seguente valore della chiave del registro di sistema su `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`"true":.

2. Riavviare Outlook.

## <a name="support-information"></a>Informazioni sul supporto tecnico

Se si ha bisogno di assistenza per l'installazione, la configurazione o la disinstallazione del componente aggiuntivo, contattare il supporto tecnico utilizzando il nuovo collegamento richiesta di servizio nella pagina supporto nell'interfaccia di amministrazione di Microsoft 365. Per ulteriori opzioni, tra cui l'invio di una richiesta di servizio tramite le opzioni telefono e supporto self-service, vedere [Help and Support for EOP](help-and-support-for-eop.md).

## <a name="for-more-information"></a>Ulteriori informazioni

[Abilitare il componente aggiuntivo Segnala messaggio](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)

[Segnalazione di messaggi indesiderati a Microsoft](report-junk-email-messages-to-microsoft.md)
