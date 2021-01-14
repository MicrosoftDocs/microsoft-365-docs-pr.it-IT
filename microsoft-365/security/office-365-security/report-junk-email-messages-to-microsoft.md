---
title: Segnalare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui diversi modi per segnalare messaggi buoni e non validi e file a Microsoft per l'analisi.
ms.openlocfilehash: 52ca0287e65fa338b06dc7df7c1e6c214af860c2
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865093"
---
# <a name="report-messages-and-files-to-microsoft"></a>Segnalazione di messaggi e file a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, sia gli utenti che gli amministratori dispongono di diversi metodi per la segnalazione di messaggi di posta elettronica e file a Microsoft.

****

|Metodo|Descrizione|
|---|---|
|[Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft](admin-submission.md)|Il metodo di report consigliato per gli amministratori nelle organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo).|
|[Abilitare il componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md)|Compatibile con Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). <p> A seconda dell'abbonamento, i messaggi segnalati dagli utenti con il componente aggiuntivo sono disponibili nel [portale](admin-submission.md)di gestione delle risorse, nei [risultati di ricerca e di risposta automatizzati (aria)](air-view-investigation-results.md), nel [rapporto messaggi segnalati dall'utente](view-email-security-reports.md#user-reported-messages-report)e in [Esplora minacce](threat-explorer-views.md#email--submissions). <p> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).
|[Abilitare il componente aggiuntivo per il phishing dei report](enable-the-report-phish-add-in.md)|Compatibile con Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). <p> A seconda dell'abbonamento, i messaggi segnalati dagli utenti con il componente aggiuntivo sono disponibili nel [portale](admin-submission.md)di gestione delle risorse, nei [risultati di ricerca e di risposta automatizzati (aria)](air-view-investigation-results.md), nel [rapporto messaggi segnalati dall'utente](view-email-security-reports.md#user-reported-messages-report)e in [Esplora minacce](threat-explorer-views.md#email--submissions). <p> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).|
|[Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Funziona solo in Outlook.|
|[Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Utilizzare le funzionalità predefinite in Outlook sul Web per le organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo). <p> I messaggi segnalati dagli utenti sono disponibili nel [portale di amministrazione degli invii](admin-submission.md). <p> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).|
|[Segnalare messaggi di posta indesiderata e di phishing in Outlook per iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Utilizzare le funzionalità predefinite di Outlook per iOS e Android per le organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo). <p> I messaggi segnalati dagli utenti sono disponibili nel [portale di amministrazione degli invii](admin-submission.md). <p> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).|
|[Inviare manualmente messaggi a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Inviare manualmente messaggi allegati a indirizzi di posta elettronica Microsoft specifici per la posta indesiderata, non la posta indesiderata e il phishing|
|[Utilizzare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Informazioni su come creare una regola del flusso di posta (nota anche come regola di trasporto) che informa quando gli utenti segnalano i messaggi a Microsoft per l'analisi.
|||
|[Inviare malware e non malware a Microsoft per l'analisi](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Utilizzare il sito di Microsoft Security Intelligence per inviare allegati e altri file.|

Se i messaggi di posta indesiderata o di phishing sono stati messi in quarantena anziché recapitati, gli utenti possono segnalare i messaggi a Microsoft dal portale di quarantena nel centro sicurezza & Compliance. Per informazioni dettagliate, vedere [trovare e rilasciare i messaggi in quarantena come utente in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).
