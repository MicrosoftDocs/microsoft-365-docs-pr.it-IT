---
title: Segnalare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Gli amministratori possono conoscere i diversi modi per segnalare messaggi e file a Microsoft per l'analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065146"
---
# <a name="report-messages-and-files-to-microsoft"></a>Segnalazione di messaggi e file a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, sia gli utenti che gli amministratori hanno diversi metodi per segnalare i messaggi di posta elettronica e i file a Microsoft.

****

|Metodo|Descrizione|
|---|---|
|[Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft](admin-submission.md)|Il metodo di creazione di report consigliato per gli amministratori nelle organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo).|
|[Abilitare il componente aggiuntivo Segnala messaggio](enable-the-report-message-add-in.md)|Funziona con Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). <p> A seconda dell'abbonamento, i messaggi segnalati dagli utenti con il componente aggiuntivo sono disponibili nel portale per gli invii di [amministratori,](admin-submission.md)nei risultati di analisi e risposta [automatizzati (AIR),](air-view-investigation-results.md)nel [report](view-email-security-reports.md#user-reported-messages-report)Messaggi segnalati dagli utenti e in [Esplora minacce.](threat-explorer-views.md#email--submissions) <p> È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)
|[Abilitare il componente aggiuntivo Segnala phishing](enable-the-report-phish-add-in.md)|Funziona con Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). <p> A seconda dell'abbonamento, i messaggi segnalati dagli utenti con il componente aggiuntivo sono disponibili nel portale per gli invii di [amministratori,](admin-submission.md)nei risultati di analisi e risposta [automatizzati (AIR),](air-view-investigation-results.md)nel [report](view-email-security-reports.md#user-reported-messages-report)Messaggi segnalati dagli utenti e in [Esplora minacce.](threat-explorer-views.md#email--submissions) <p> È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)|
|[Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Funziona solo in Outlook.|
|[Segnalare posta indesiderata e phishing in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Utilizzare le funzionalità incorporate in Outlook sul Web per le organizzazioni con cassette postali di Exchange Online (non disponibili in EOP autonomo). <p> I messaggi che gli utenti segnalano sono disponibili [nel portale per gli invii di amministratori.](admin-submission.md) <p> È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)|
|[Segnalare posta indesiderata e phishing in Outlook per iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Utilizzare le funzionalità incorporate in Outlook per iOS e Android per le organizzazioni con cassette postali di Exchange Online (non disponibili in EOP autonomo). <p> I messaggi che gli utenti segnalano sono disponibili [nel portale per gli invii di amministratori.](admin-submission.md) <p> È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)|
|[Inviare manualmente i messaggi a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Inviare manualmente i messaggi allegati a indirizzi di posta elettronica Microsoft specifici per posta indesiderata, non posta indesiderata e phishing.|
|[Utilizzare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Informazioni su come creare una regola del flusso di posta (nota anche come regola di trasporto) che invia una notifica quando gli utenti segnalano messaggi a Microsoft per l'analisi.|
|[Inviare malware e non malware a Microsoft per l'analisi](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Utilizzare il sito Microsoft Security Intelligence per inviare allegati e altri file.|

Se i messaggi di posta indesiderata o phishing sono stati messi in quarantena anziché recapitati, gli utenti possono segnalare i messaggi a Microsoft dal portale di quarantena nel Centro sicurezza & conformità. Per informazioni dettagliate, vedere Trovare e rilasciare i messaggi in quarantena [come utente in Microsoft 365.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> I dati degli invii a Microsoft risiedono nel limite di conformità di Office 365 nei data center nordamericani. I dati vengono esaminati dagli analisti del team di progettazione per migliorare l'efficacia dei filtri.
