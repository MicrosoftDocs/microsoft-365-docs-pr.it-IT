---
title: Differenza tra posta elettronica indesiderata e posta elettronica in blocco
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
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: In questo argomento viene illustrata la differenza tra posta indesiderata (posta indesiderata) e posta elettronica in blocco e i relativi controlli in Office 365.
ms.openlocfilehash: 56e997235a374ee9f56956be96458b46bffcdc21
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033627"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a>Differenza tra posta elettronica indesiderata e posta elettronica inviata in blocco

I clienti di Office 365 con cassette postali in Exchange Online o autonomo Exchange Online Protection (EOP) i clienti che non dispongono di cassette postali di Exchange Online chiedono: "Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco In questo argomento viene illustrata la differenza e vengono descritti i controlli disponibili in EOP.

- La **posta** indesiderata è posta indesiderata, ovvero messaggi non richiesti e universalmente non necessari (se identificati correttamente). Per impostazione predefinita, il EOP respinge la posta indesiderata in base alla reputazione del server di posta elettronica di origine. Se un messaggio passa il controllo IP di origine, viene inviato al filtro per la posta indesiderata. Se il messaggio viene classificato come posta indesiderata dal filtro posta indesiderata, il messaggio viene (per impostazione predefinita) recapitato ai destinatari previsti e spostato nella cartella posta indesiderata.

  - È possibile configurare le azioni da intraprendere sui verdetti del filtro della posta indesiderata. Per istruzioni, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

  - Se non si è d'accordo con il verdetto del filtro della posta indesiderata, è possibile segnalare i messaggi che si considerano come posta indesiderata o non indesiderata a Microsoft in diversi modi, come descritto in [messaggi e file di report a Microsoft](report-junk-email-messages-to-microsoft.md)

- La posta **elettronica in blocco** (nota anche come _posta grigia_) è più difficile da classificare. Se la posta indesiderata è una minaccia costante, la posta elettronica in blocco è spesso una pubblicità o un messaggio di marketing. Alcuni utenti desiderano messaggi di posta elettronica in blocco (e, in effetti, hanno deliberatamente iscritto per riceverli), mentre altri utenti considerano la posta elettronica in blocco come posta indesiderata. Ad esempio, alcuni utenti desiderano ricevere messaggi pubblicitari dalla Contoso Corporation o inviti a una conferenza imminente sulla sicurezza cibernetica, mentre altri utenti considerano gli stessi messaggi come posta indesiderata.

  Per ulteriori informazioni su come viene identificato il messaggio di posta elettronica in blocco, vedere [bulk lamentel Level (BCL) in Office 365](bulk-complaint-level-values.md).

## <a name="how-to-manage-bulk-email"></a>Come gestire la posta elettronica in blocco

A causa della reazione mista al messaggio di posta elettronica in blocco, non vi sono indicazioni universali valide per ogni organizzazione.

I criteri di protezione dalla posta indesiderata hanno una soglia BCL predefinita utilizzata per identificare la posta elettronica in blocco come posta indesiderata. Gli amministratori possono aumentare o diminuire la soglia. Per ulteriori informazioni, vedere i seguenti argomenti:

- [Configurazione dei criteri di protezione da posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

- [Impostazioni dei criteri di protezione da posta indesiderata di EOP](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

Un'altra opzione facilmente trascurabile: se un utente si lamenta della ricezione di posta elettronica in blocco, ma i messaggi vengono inviati da mittenti affidabili che passano il filtro per la posta indesiderata in EOP, fare in modo che l'utente verifichi un'opzione di annullamento della sottoscrizione nel messaggio di posta elettronica in blocco.
