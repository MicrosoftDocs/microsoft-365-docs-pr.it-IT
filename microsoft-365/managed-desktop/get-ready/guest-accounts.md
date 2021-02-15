---
title: Prerequisiti per gli account Guest
description: Linee guida di configurazione per gli account guest e come regolarli
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

Microsoft Managed Desktop richiede le impostazioni seguenti nell'organizzazione di Azure AD per l'accesso all'account guest. È possibile modificare queste impostazioni nel portale [di Azure](https://portal.azure.com) in **Identità esterne/Collaborazione esterna:**

-   **Gli amministratori e gli utenti nel ruolo di mittente dell'invito guest possono invitare** impostati su **Sì**
-   Per **le restrizioni di collaborazione,** scegliere una delle opzioni seguenti:
    -   Se si seleziona **Consenti l'invio** degli inviti a qualsiasi dominio (più inclusivo), non sono necessarie altre configurazioni.
    -   Se si seleziona **Nega inviti** ai domini specificati, assicurarsi che Microsoft.com non sia elencato nei domini di destinazione.
    -   Se si seleziona Consenti inviti solo per i domini specificati **(più restrittivi),** assicurarsi che Microsoft.com sia elencato nei domini di destinazione. 

Se si impostano restrizioni che interagiscono con queste impostazioni, assicurarsi di escludere gli account del servizio Azure Active Directory **Modern Workplace Service.** Ad esempio, se si dispone di un criterio di accesso condizionale che impedisce agli account guest di accedere al portale di Intune, escludere il gruppo **Account** del servizio di lavoro moderno da questo criterio.

