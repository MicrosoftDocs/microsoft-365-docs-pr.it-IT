---
title: Elenchi di mittenti attendibili e bloccati in Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: In qualità di amministratore di Exchange Online o Exchange Online Protection (EOP), è possibile fare in modo che i messaggi di posta elettronica inviati tramite il servizio non vengano classificati come posta indesiderata. Un modo per farlo consiste nel creare elenchi di mittenti attendibili e di mittenti bloccati per gli utenti dell'organizzazione.
ms.openlocfilehash: 959af558c32e71e5a4cede2aff7bbcd1dbb092e2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598513"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a>Elenchi di mittenti attendibili e bloccati in Exchange Online

In qualità di amministratore di Exchange Online o Exchange Online Protection (EOP), è possibile fare in modo che i messaggi di posta elettronica inviati tramite il servizio non vengano classificati come posta indesiderata. Un modo per farlo consiste nel creare elenchi di mittenti attendibili e di mittenti bloccati per gli utenti dell'organizzazione.

*Vedere la versione aggiornata dei suggerimenti e delle procedure per la modalità di utilizzo di questi elenchi come amministratore in* [come impedire che la posta elettronica venga contrassegnata come posta indesiderata in Office 365](prevent-email-from-being-marked-as-spam.md).

Se non si è un amministratore e si desidera solo gestire la posta indesiderata in Outlook utilizzando un elenco di mittenti attendibili, vedere la procedura illustrata nella[Panoramica del filtro della posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a>Quali sono i limiti dei mittenti attendibili e bloccati in Exchange Online?

I limiti dei mittenti attendibili e bloccati in Exchange Online sono diversi da quelli di Active Directory e di Outlook. Tali limiti sono elencati di seguito:

- Limite dei mittenti attendibili: 1.024

- Limite dei mittenti bloccati: 500

Nota:

È possibile che si verifichi l'errore descritto in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app). Per risolvere il problema, deselezionare la casella di controllo "Considera attendibili i messaggi di posta elettronica provenienti dai contatti personali". In alternativa, ridurre la quantità di indirizzi di posta elettronica presenti nella cartella Contatti predefinita per riportarla entro il limite massimo consentito di 1024 in Exchange Online impostato per l'attributo "parametri MaxSafeSenders". Per ulteriori informazioni sull'attributo e sul cmdlet Set-Mailbox, vedere l'argomento seguente:

[Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a>Vedere anche

[Filtro mittente in Exchange Server](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
