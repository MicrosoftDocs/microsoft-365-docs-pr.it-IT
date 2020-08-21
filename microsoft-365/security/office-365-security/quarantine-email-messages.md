---
title: Messaggi di posta elettronica in quarantena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulla quarantena in Exchange Online Protection (EOP) che contiene messaggi potenzialmente pericolosi o indesiderati.
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826802"
---
# <a name="quarantined-email-messages-in-eop"></a>Messaggi di posta elettronica in quarantena in EOP

In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, la quarantena è disponibile per contenere messaggi potenzialmente pericolosi o indesiderati.

*I* criteri anti-malware consentono di mettere in quarantena automaticamente un messaggio se viene trovato un allegato contenente malware. Per ulteriori informazioni, vedere [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).

Per impostazione predefinita, la protezione da posta indesiderata consente di mettere in quarantena i messaggi di phishing e inviare messaggi di posta indesiderata alla cartella posta indesiderata dell'utente. Tuttavia, è anche possibile creare e personalizzare i criteri di protezione da posta indesiderata per la quarantena della posta indesiderata e messaggi di posta elettronica. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena:

- Gli amministratori possono utilizzare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono utilizzare i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto). Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).

- Gli utenti possono lavorare con i messaggi in quarantena dove sono un destinatario se il messaggio è stato messo in quarantena come posta indesiderata, posta in blocco o (da aprile 2020) phishing. Per ulteriori informazioni, vedere [trovare e rilasciare i messaggi in quarantena come utente in EOP](find-and-release-quarantined-messages-as-a-user.md).

  Per impedire agli utenti di gestire i propri messaggi di phishing in quarantena, gli amministratori possono configurare un'azione diversa per il verdetto del filtro della **posta elettronica di phishing** nei criteri di protezione da posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

- Gli amministratori e gli utenti possono segnalare falsi positivi a Microsoft in quarantena.

Per ulteriori informazioni sulla quarantena, vedere [domande frequenti sulla quarantena](quarantine-faq.md).
