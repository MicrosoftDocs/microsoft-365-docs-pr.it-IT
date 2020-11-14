---
title: Prerequisiti per gli account Guest
description: Linee guida di configurazione per gli account Guest e come adattarli
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073225"
---
# <a name="prerequisites-for-guest-accounts"></a>Prerequisiti per gli account Guest

Microsoft Managed Desktop richiede le impostazioni seguenti nell'organizzazione di Azure AD per l'accesso agli account Guest. È possibile modificare queste impostazioni nel [portale di Azure](https://portal.azure.com) in **identità esterne/collaborazione esterna** :

-   **Gli amministratori e gli utenti del ruolo invitato dell'ospite possono invitare il** set a **Yes**
-   Per le **restrizioni di collaborazione** , scegliere una delle opzioni seguenti:
    -   Se si seleziona **Consenti l'invio di inviti a qualsiasi dominio (più inclusivo)** , non sono necessarie altre configurazioni.
    -   Se si seleziona **Nega inviti ai domini specificati** , assicurarsi che Microsoft.com non sia elencato nei domini di destinazione.
    -   Se si seleziona **Consenti solo gli inviti ai domini specificati (più restrittivi)** , assicurarsi che Microsoft.com *sia* elencato nei domini di destinazione.

Se si impostano restrizioni che interagiscono con queste impostazioni, assicurarsi di escludere gli **account di servizio moderni** di Azure Active Directory. Ad esempio, se si dispone di un criterio di accesso condizionale che impedisce agli account Guest di accedere al portale di Intune, escludere il gruppo di **account del servizio di lavoro moderno** da questo criterio.

