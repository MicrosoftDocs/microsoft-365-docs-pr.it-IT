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
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulla quarantena in Exchange Online Protection (EOP) che contiene messaggi potenzialmente pericolosi o indesiderati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a11f5f9e1e730a3b0cc09625ec8e8cb592d869
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333807"
---
# <a name="quarantined-email-messages-in-eop"></a>Messaggi di posta elettronica in quarantena in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, la quarantena è disponibile per contenere messaggi potenzialmente pericolosi o indesiderati.

I criteri antimalware mettere automaticamente in quarantena un messaggio se *viene* trovato un allegato contenente malware. Per ulteriori informazioni, vedere [Configure anti-malware policies in EOP.](configure-anti-malware-policies.md)

Per impostazione predefinita, i criteri di protezione da posta indesiderata mettere in quarantena i messaggi di phishing e recapitare messaggi di posta elettronica di posta indesiderata e in blocco nella cartella Posta indesiderata dell'utente. Tuttavia, è anche possibile creare e personalizzare i criteri di protezione da posta indesiderata per mettere in quarantena i messaggi di posta indesiderata e di posta elettronica in blocco. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena:

- Gli amministratori possono utilizzare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono utilizzare i messaggi messi in quarantena come malware, phishing ad alta probabilità o come risultato delle regole del flusso di posta (note anche come regole di trasporto). Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).

- Gli utenti possono utilizzare i messaggi in quarantena in cui sono destinatari se il messaggio è stato messo in quarantena come posta indesiderata, posta elettronica in blocco o phishing (a partire da aprile 2020). Per ulteriori informazioni, vedere Trovare e rilasciare i messaggi in quarantena [come utente in EOP.](find-and-release-quarantined-messages-as-a-user.md)

  Per impedire agli utenti di gestire i propri messaggi di phishing in quarantena, gli amministratori possono configurare un'azione diversa per il verdetto **Filtro** posta elettronica di phishing nei criteri di protezione da posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

- Gli amministratori e gli utenti possono segnalare falsi positivi a Microsoft in quarantena.

Per ulteriori informazioni sulla quarantena, vedere [Domande frequenti sulla quarantena.](quarantine-faq.yml)
