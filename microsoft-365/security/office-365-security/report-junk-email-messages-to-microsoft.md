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
description: Gli amministratori possono conoscere i diversi modi per segnalare messaggi buoni e non validi a Microsoft.
ms.openlocfilehash: b5f0d24e7e7edf3119f49965be73a1386ebd219e
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921469"
---
# <a name="report-messages-and-files-to-microsoft"></a>Segnalazione di messaggi e file a Microsoft

Gli utenti e gli amministratori di Microsoft 365 organizzazioni con cassette postali in Exchange Online o organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online dispongono di diversi metodi per la creazione di report di messaggi e file a Microsoft.

|||
|---|---|
|**Metodo**|**Descrizione**|
|[Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft](admin-submission.md)|Il metodo di report consigliato per gli amministratori nelle organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo).|
|[Abilitare il componente aggiuntivo per i messaggi di report in Office 365](enable-the-report-message-add-in.md)|È compatibile con Outlook, Outlook per Mac e Outlook sul Web (in precedenza noto come Outlook Web App) ed è il componente aggiuntivo consigliato. <br/><br/> A seconda dell'abbonamento, i messaggi segnalati dagli utenti con il componente aggiuntivo sono disponibili nel [portale](admin-submission.md)di gestione delle risorse, nei [risultati di ricerca e di risposta automatizzati (aria)](air-view-investigation-results.md), nel [rapporto messaggi segnalati dall'utente](view-email-security-reports.md#user-reported-messages-report)e in [Esplora minacce](threat-explorer-views.md#email--submissions). <br/><br/> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Office 365](user-submission.md).|
|[Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook in Office 365](junk-email-reporting-add-in-for-microsoft-outlook.md)|Funziona solo in Outlook.|
|[Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web in Office 365](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Utilizzare le funzionalità predefinite in Outlook sul Web per le organizzazioni con cassette postali di Exchange Online (non disponibile in EOP autonomo). <br/><br/> I messaggi segnalati dagli utenti sono disponibili nel [portale di amministrazione degli invii](admin-submission.md). <br/><br/> È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Office 365](user-submission.md).|
|[Inviare manualmente messaggi a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Inviare manualmente messaggi allegati a indirizzi di posta elettronica Microsoft specifici per la posta indesiderata, non la posta indesiderata e il phishing <br/><br/> Vengono inoltre fornite informazioni su come creare una regola del flusso di posta (nota anche come regola di trasporto) che informa quando gli utenti inviano messaggi a questi indirizzi di posta elettronica per la creazione di report.|
|[Inviare malware e non malware a Microsoft per l'analisi](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Utilizzare il sito di Microsoft Security Intelligence per inviare allegati e altri file.|
|

Se i messaggi di posta indesiderata o di phishing sono stati messi in quarantena anziché recapitati, gli utenti possono segnalare i messaggi a Microsoft dal portale di quarantena nel centro sicurezza & Compliance. Per informazioni dettagliate, vedere [trovare e rilasciare i messaggi in quarantena come utente in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).