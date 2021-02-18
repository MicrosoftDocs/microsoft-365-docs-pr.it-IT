---
title: Informazioni dettagliate sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare le informazioni dettagliate sullo stato del flusso di posta del dominio principale nel dashboard del flusso di posta nel Centro sicurezza & conformità per risolvere i problemi del flusso di posta correlati ai record MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290622"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Informazioni dettagliate sullo stato del flusso di posta del dominio principale nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Le **informazioni dettagliate sullo** stato del flusso di posta del dominio principale nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità forniscono lo stato corrente del flusso di posta per l'organizzazione.

Queste informazioni consentono di identificare e risolvere i problemi relativi ai domini in cui si verificano ***problemi relativi al flusso di*** posta. Ad esempio, il dominio non è in grado di ricevere posta elettronica esterna perché il dominio è scaduto o il dominio ha un record MX non corretto.

![Widget stato flusso dominio principale nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-top-domain-mail-flow-status-widget.png)

Quando si fa **clic su Visualizza** dettagli nel widget, viene visualizzato un riquadro a comparsa Stato dominio che mostra ulteriori dettagli sullo stato di ogni dominio: 

- **Dominio**
- **Record MX precedente**
- **Record MX corrente**
- **Stato ricezione posta elettronica**
- **Stato dominio**: un segno di spunta verde indica che il record MX corrente (nel momento in cui si è fatto clic sul widget) corrisponde al valore che abbiamo nel record e il dominio ha ricevuto posta elettronica nelle ultime due ore.

  Una X rossa indica che il record MX è stato modificato e che il dominio non ha ricevuto messaggi di posta elettronica nelle ultime 6 ore. Questo probabilmente indica che il dominio è scaduto o che il record MX è stato aggiornato in modo errato. Rivolgersi al registrar o al servizio di hosting DNS per verificare se il dominio è scaduto o se il record MX del dominio non è corretto.

È possibile fare **clic su Visualizza** altro per visualizzare le stesse informazioni per altri domini.

![Riquadro a comparsa Dettagli in Informazioni dettagliate sullo stato del flusso di posta del dominio principale](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
