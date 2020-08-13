---
title: Segnalare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft
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
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui diversi modi per segnalare messaggi buoni e non validi e file a Microsoft per l'analisi.
ms.openlocfilehash: 44254aa6e5c43e0eac1d63c153b1212b4f099840
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652826"
---
# <a name="report-messages-and-files-to-microsoft"></a>Segnalazione di messaggi e file a Microsoft

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, sia gli utenti che gli amministratori dispongono di diversi metodi per la segnalazione di messaggi di posta elettronica e file a Microsoft.

****

|Metodo|Descrizione|
|---|---|
|[Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft](admin-submission.md)|Il metodo di report consigliato per gli amministratori nelle organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo).|
|[Abilitare il componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md)|È compatibile con Outlook, Outlook per Mac e Outlook sul Web (in precedenza noto come Outlook Web App) ed è il componente aggiuntivo consigliato. <br/><br/> A seconda dell'abbonamento, i messaggi segnalati dagli utenti con il componente aggiuntivo sono disponibili nel [portale](admin-submission.md)di gestione delle risorse, nei [risultati di ricerca e di risposta automatizzati (aria)](air-view-investigation-results.md), nel [rapporto messaggi segnalati dall'utente](view-email-security-reports.md#user-reported-messages-report)e in [Esplora minacce](threat-explorer-views.md#email--submissions). <br/><br/> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in EOP](user-submission.md).|
|[Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Funziona solo in Outlook.|
|[Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Utilizzare le funzionalità predefinite in Outlook sul Web per le organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo). <br/><br/> I messaggi segnalati dagli utenti sono disponibili nel [portale di amministrazione degli invii](admin-submission.md). <br/><br/> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Exchange Online](user-submission.md).|
|[Inviare manualmente messaggi a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Inviare manualmente messaggi allegati a indirizzi di posta elettronica Microsoft specifici per la posta indesiderata, non la posta indesiderata e il phishing|
|[Utilizzare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Informazioni su come creare una regola del flusso di posta (nota anche come regola di trasporto) che informa quando gli utenti segnalano i messaggi a Microsoft per l'analisi.
|||
|[Inviare malware e non malware a Microsoft per l'analisi](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Utilizzare il sito di Microsoft Security Intelligence per inviare allegati e altri file.|
|

Se i messaggi di posta indesiderata o di phishing sono stati messi in quarantena anziché recapitati, gli utenti possono segnalare i messaggi a Microsoft dal portale di quarantena nel centro sicurezza & Compliance. Per informazioni dettagliate, vedere [trovare e rilasciare i messaggi in quarantena come utente in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).
