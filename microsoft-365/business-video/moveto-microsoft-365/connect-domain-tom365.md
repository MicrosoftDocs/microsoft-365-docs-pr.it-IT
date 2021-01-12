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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come connettere il dominio a Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794643"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Connettere il dominio a Microsoft 365 for business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Dopo aver configurato Microsoft 365 e aver spostato i dati della posta elettronica da Google Workspace, è possibile connettere il dominio a Microsoft 365. 

Per prima cosa, è necessario eliminare i record DNS esistenti da Google, quindi è possibile aggiungere nuovi record DNS da Microsoft 365.

## <a name="try-it"></a>Perché non provarlo?

1. Accedere alla console di amministrazione di Google Workspace all' [admin.Google.com](https://admin.google.com).
1. Selezionare **domini**, **Gestisci domini**, **Visualizza dettagli**, **Gestisci dominio** e quindi **DNS** nel NAV sinistro.
1. Scorrere verso il basso fino a **record sintetici**, aprire **Google Workspace**, selezionare **Elimina**, quindi **eliminare** di nuovo.
1. Scorrere verso il basso fino a **record di risorse personalizzati** ed eliminare tutti i record DNS esistenti che vengono visualizzati, compresi quelli eventualmente creati in precedenza per Microsoft 365.
1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).
1. Nella barra di spostamento a sinistra, scegliere, **mostrare tutto**, **Impostazioni**, **domini**.
1. Scegliere quindi il dominio predefinito.
1. Selezionare **Continua installazione**, quindi, per connettere il dominio, scegliere  **continue**.
1. Scorrere verso il basso per visualizzare i record DNS che devono essere copiati su Google.
1. Aprire i **record MX** e in **punti a indirizzo o valore**, copiare il record.
1. Torna a Google e nella sezione **Custom Resource Records** Apri il menu a discesa tipo di record e seleziona **MX**.
1. Nel campo **dati** incollare il record copiato.
1. Selezionare **Aggiungi**.
1. Ripetere il processo per i record CNAME e TXT e aggiungere i valori nella pagina Gestione DNS di Google.
1. Tornare all'interfaccia di amministrazione di Microsoft 365 e selezionare **continua**.

    La configurazione del dominio è stata completata.