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
ms.openlocfilehash: 4b111ea0d07453ef4280ec9e57247c8215420074
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167408"
---
# <a name="quarantined-email-messages-in-eop"></a>Messaggi di posta elettronica in quarantena in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
-   [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
-   [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, la quarantena è disponibile per contenere messaggi potenzialmente pericolosi o indesiderati.

I criteri antimalware mettere automaticamente in quarantena un messaggio se *viene rilevato* che un allegato contiene malware. Per ulteriori informazioni, vedere [Configurare i criteri antimalware in EOP.](configure-anti-malware-policies.md)

Per impostazione predefinita, i criteri di protezione dalla posta indesiderata messi in quarantena i messaggi di phishing e recapitare messaggi di posta indesiderata e in blocco nella cartella Posta indesiderata dell'utente. Tuttavia, è anche possibile creare e personalizzare i criteri di protezione dalla posta indesiderata per mettere in quarantena la posta indesiderata e i messaggi di posta elettronica in blocco. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

Sia gli utenti che gli amministratori possono utilizzare i messaggi in quarantena:

- Gli amministratori possono utilizzare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono utilizzare i messaggi messi in quarantena come malware, phishing ad alta probabilità o come risultato delle regole del flusso di posta (note anche come regole di trasporto). Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).

- Gli utenti possono lavorare con i messaggi in quarantena dove sono destinatari se il messaggio è stato messo in quarantena come posta indesiderata, posta elettronica in blocco o phishing (a partire da aprile 2020). Per ulteriori informazioni, vedere [Trovare e rilasciare i messaggi in quarantena come utente in EOP.](find-and-release-quarantined-messages-as-a-user.md)

  Per impedire agli utenti di gestire i propri messaggi di phishing in quarantena, gli amministratori possono configurare un'azione diversa per il verdetto del filtro della posta elettronica di **phishing** nei criteri di protezione dalla posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).

- Gli amministratori e gli utenti possono segnalare falsi positivi a Microsoft in quarantena.

Per ulteriori informazioni sulla quarantena, vedere [Domande frequenti sulla quarantena.](quarantine-faq.md)
