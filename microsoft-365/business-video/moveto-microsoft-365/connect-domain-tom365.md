---
title: Connettere il proprio dominio a Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come connettere il dominio a Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925111"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Connettere il dominio a Microsoft 365 per le aziende

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Dopo aver configurato Microsoft 365 e spostato i dati di posta elettronica da Google Workspace, è possibile connettere il dominio a Microsoft 365. 

Prima di tutto sarà necessario eliminare i record DNS esistenti da Google, quindi possiamo aggiungere nuovi record DNS da Microsoft 365.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere alla console di amministrazione di Google Workspace [all'indirizzo admin.google.com](https://admin.google.com).
1. Seleziona **Domini,** **Gestisci domini,** **Visualizza dettagli,** **Gestisci dominio,** **quindi DNS** nel riquadro di spostamento sinistro.
1. Scorrere verso il basso **fino a Record sintetici,** aprire **Google Workspace,** selezionare **Elimina** e quindi **eliminare di** nuovo.
1. Scorrere verso il **basso fino a Record** di risorse personalizzati ed eliminare eventuali record DNS esistenti visualizzati, inclusi quelli creati in precedenza per Microsoft 365.
1. Passare all'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com)
1. In the left nav, choose, **Show all**, **Settings**, **Domains.**
1. Scegliere quindi il dominio predefinito.
1. Selezionare **Continua l'installazione,** quindi, per connettere il dominio, scegliere **Continua.**
1. Scorrere verso il basso per visualizzare i record DNS che devono essere copiati su Google.
1. Aprire **i record MX** e, in Indirizzo o valore di **puntamento,** copiare il record.
1. Tornare a Google e nella sezione **Custom resource records** aprire l'elenco a discesa del tipo di record e selezionare **MX.**
1. Nel campo **Dati** incollare il record copiato.
1. Selezionare **Aggiungi**.
1. Ripetere il processo per i record CNAME e TXT e aggiungere i valori nella pagina di gestione DNS di Google.
1. Tornare all'interfaccia di amministrazione di Microsoft 365 e selezionare **Continua.**

    La configurazione del dominio è stata completata.