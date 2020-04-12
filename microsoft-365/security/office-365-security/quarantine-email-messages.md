---
title: Quarantena in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: La quarantena in Office 365 contiene messaggi potenzialmente pericolosi o indesiderati. Gli amministratori e gli utenti finali possono accedere alla quarantena.
ms.openlocfilehash: d3db036210886f7a4607f477bba2cf9f450ed90c
ms.sourcegitcommit: c876d58b34454f211b50ae5d06f193c1a1e5c4ff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2020
ms.locfileid: "43230939"
---
# <a name="quarantine-in-office-365"></a>Quarantena in Office 365

Se si è un cliente di Office 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena è disponibile per contenere messaggi potenzialmente pericolosi o indesiderati.

*I* criteri anti-malware consentono di mettere in quarantena automaticamente un messaggio se viene trovato un allegato contenente malware. Per ulteriori informazioni, vedere [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

Per impostazione predefinita, i criteri di protezione dalla posta indesiderata mettono in quarantena i messaggi di phishing e recapitano posta indesiderata e posta elettronica alla cartella posta indesiderata. Tuttavia, è anche possibile creare e personalizzare i criteri di protezione da posta indesiderata per la quarantena della posta indesiderata e messaggi di posta elettronica. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena:

- Gli amministratori possono utilizzare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono utilizzare i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto). Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).

- Gli utenti possono lavorare con i messaggi in quarantena dove sono un destinatario se il messaggio è stato messo in quarantena come posta indesiderata, posta elettronica in blocco o (da aprile 2020) phishing. Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in Office 365](find-and-release-quarantined-messages-as-a-user.md).

  Per impedire agli utenti di gestire i propri messaggi di phishing in quarantena, gli amministratori possono configurare un'azione diversa per il verdetto del filtro della **posta elettronica di phishing** nei criteri di protezione da posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

- Gli amministratori e gli utenti possono segnalare falsi positivi a Microsoft in quarantena.

Per ulteriori informazioni sulla quarantena, vedere [domande frequenti sulla quarantena](quarantine-faq.md).
