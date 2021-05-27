---
title: Segnalare messaggi di posta indesiderata, non di posta indesiderata e phishing a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
ms.openlocfilehash: 7b062c9529364e9fe26133fd1c039affcb8b7011
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689074"
---
# <a name="report-messages-and-files-to-microsoft"></a>Segnalazione di messaggi e file a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, sia gli utenti che gli amministratori hanno diversi metodi per segnalare i messaggi di posta elettronica e i file a Microsoft.

<br>

****

|Metodo|Descrizione|
|---|---|
|[Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft](admin-submission.md)|Il metodo di creazione di report consigliato per gli amministratori nelle organizzazioni con Exchange Online cassette postali (non disponibile in EOP autonomo).|
|[Abilitare i componenti aggiuntivi Segnala messaggio o Segnala phishing](enable-the-report-message-add-in.md)|Funziona con Outlook e Outlook sul Web (in precedenza noto come Outlook Web App). <p> A seconda dell'abbonamento, i messaggi segnalati dagli utenti con i componenti aggiuntivi sono disponibili nel portale per gli invii di [amministratori,](admin-submission.md)nei risultati di analisi e risposta [automatizzati (AIR),](air-view-investigation-results.md)nel [report](view-email-security-reports.md#user-reported-messages-report)Messaggi segnalati dagli utenti e in [Esplora minacce.](threat-explorer-views.md#email--submissions) <p> È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)
|[Segnalare i falsi positivi e i falsi negativi in Outlook](report-false-positives-and-false-negatives.md)|Inviare falsi positivi (buona posta elettronica bloccata o inviata alla cartella posta indesiderata) e falsi negativi (posta elettronica indesiderata o phish recapitati nella posta in arrivo) a Exchange Online Protection (EOP) utilizzando la funzionalità Segnala messaggio.|
|[Inviare manualmente i messaggi a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Inviare manualmente i messaggi allegati a indirizzi di posta elettronica Microsoft specifici per posta indesiderata, non posta indesiderata e phishing.|
|[Usare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Informazioni su come creare una regola del flusso di posta (nota anche come regola di trasporto) che invia una notifica quando gli utenti segnalano messaggi a Microsoft per l'analisi.|
|[Inviare malware e non malware a Microsoft per l'analisi](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Utilizzare il Intelligence di sicurezza Microsoft per inviare allegati e altri file.|
|

Se i messaggi di posta indesiderata o phishing sono stati messi in quarantena anziché recapitati, gli utenti possono segnalare i messaggi a Microsoft dal portale di quarantena nel Centro sicurezza & conformità. Per informazioni dettagliate, vedere [Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).

> [!NOTE]
> I dati degli invii a Microsoft risiedono nel Office 365 di conformità nei data center nordamericani. I dati vengono esaminati dagli analisti del team di progettazione per migliorare l'efficacia dei filtri.
