---
title: Prerequisiti per gli account Guest
description: Linee guida di configurazione per gli account guest e come regolarli
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694246"
---
# <a name="prerequisites-for-guest-accounts"></a>Prerequisiti per gli account Guest

Microsoft Managed Desktop le impostazioni seguenti nell'organizzazione di Azure AD per l'accesso all'account guest. È possibile modificare queste impostazioni nel portale [di Azure](https://portal.azure.com) in Identità **esterne /Impostazioni di collaborazione esterna:**

-   Per **le restrizioni di invito guest** impostate su Utenti membri e utenti assegnati a ruoli di amministratore specifici possono invitare utenti guest inclusi guest con autorizzazioni di **membro**
-   Per **Restrizioni di collaborazione,** scegliere una delle opzioni seguenti:
    -   Se si seleziona **Consenti l'invio di inviti a qualsiasi dominio (più inclusivo),** non è necessaria alcuna altra configurazione.
    -   Se si seleziona **Nega inviti** ai domini specificati, assicurarsi che Microsoft.com non sia elencato nei domini di destinazione.
    -   Se si seleziona Consenti inviti solo ai domini specificati **(più restrittivi),** assicurarsi Microsoft.com sia elencato nei domini di destinazione. 

Se si impostano restrizioni che interagiscono con queste impostazioni, assicurarsi di escludere l'Azure Active Directory **moderni account del** servizio di lavoro. Ad esempio, se si dispone di un criterio di accesso condizionale che impedisce agli account guest di accedere al portale di Intune, escludere il gruppo **Modern Workplace Service Accounts** da questo criterio.

## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Rivedere i [prerequisiti per Microsoft Managed Desktop](prerequisites.md).
2. Usare gli [strumenti di valutazione dell'idoneità](readiness-assessment-tool.md).
3. [Prerequisiti per gli account guest](guest-accounts.md) (questo articolo)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Preparare l'accesso alle risorse locali per Microsoft Managed Desktop](authentication.md)
7. [App in Microsoft Managed Desktop](apps.md)
8. [Preparare unità mappate per Microsoft Managed Desktop](mapped-drives.md)
9. [Preparare risorse di stampa per Microsoft Managed Desktop](printing.md)
