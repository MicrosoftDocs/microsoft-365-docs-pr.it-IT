---
title: Qual &apos; è la differenza tra posta indesiderata e posta elettronica in blocco?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono conoscere le differenze tra posta indesiderata (posta indesiderata) e posta in blocco (posta grigia) in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fc9c94946c3da2f9a14f45070a86c557a5c7dc85
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206973"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a>Qual è la differenza tra posta indesiderata e posta elettronica in blocco in EOP?

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i clienti a volte si chiedono: "Qual è la differenza tra posta indesiderata e posta elettronica in blocco?" In questo argomento viene illustrata la differenza e vengono descritti i controlli disponibili in EOP.

- **La posta** indesiderata è posta indesiderata, ovvero messaggi indesiderati e universalmente indesiderati (se identificati correttamente). Per impostazione predefinita, EOP rifiuta la posta indesiderata in base alla reputazione del server di posta elettronica di origine. Se un messaggio supera l'ispezione dell'IP di origine, viene inviato al filtro posta indesiderata. Se il messaggio viene classificato come posta indesiderata dal filtro posta indesiderata, il messaggio viene recapitato (per impostazione predefinita) ai destinatari previsti e spostato nella cartella Posta indesiderata.

  - È possibile configurare le azioni da eseguire sui verdetti del filtro posta indesiderata. Per istruzioni, vedere [Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)

  - Se non si è d'accordo con il verdetto del filtro della posta indesiderata, è possibile segnalare i messaggi che si considerano posta indesiderata o non indesiderata a Microsoft in diversi modi, come descritto in Segnalare messaggi e file [a Microsoft](report-junk-email-messages-to-microsoft.md).

- **La posta elettronica** in blocco (nota anche _come posta grigia)_ è più difficile da classificare. Mentre la posta indesiderata è una minaccia costante, la posta elettronica in blocco spesso è una sola volta annunci pubblicitari o messaggi di marketing. Alcuni utenti desiderano che i messaggi di posta elettronica in blocco (e in realtà, si siano deliberatamente registrati per riceverli), mentre altri utenti considerano la posta elettronica in blocco come posta indesiderata. Ad esempio, alcuni utenti desiderano ricevere messaggi pubblicitari da Contoso Corporation o inviti a una conferenza imminente sulla sicurezza informatica, mentre altri utenti considerano questi stessi messaggi come posta indesiderata.

  Per ulteriori informazioni sull'identificazione della posta elettronica in blocco, vedere [Bulk complaint level (BCL) in EOP.](bulk-complaint-level-values.md)

## <a name="how-to-manage-bulk-email"></a>Come gestire la posta elettronica in blocco

A causa della reazione mista alla posta elettronica in blocco, non esistono indicazioni universali che si applicano a ogni organizzazione.

I criteri di protezione da posta indesiderata hanno una soglia BCL predefinita che viene utilizzata per identificare la posta elettronica in blocco come posta indesiderata. Gli amministratori possono aumentare o ridurre la soglia. Per ulteriori informazioni, vedere i seguenti argomenti:

- [Configurare i criteri di protezione da posta indesiderata in EOP](configure-your-spam-filter-policies.md).

- [Impostazioni dei criteri di protezione da posta indesiderata di EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

Un'altra opzione facile da ignorare: se un utente si lamenta di ricevere posta elettronica in blocco, ma i messaggi sono provenienti da mittenti affidabili che superano il filtro posta indesiderata in EOP, fare in modo che l'utente controlli l'opzione di annullamento della sottoscrizione nel messaggio di posta elettronica in blocco.
