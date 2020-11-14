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
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="3f047-104">Prerequisiti per gli account Guest</span><span class="sxs-lookup"><span data-stu-id="3f047-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="3f047-105">Microsoft Managed Desktop richiede le impostazioni seguenti nell'organizzazione di Azure AD per l'accesso agli account Guest.</span><span class="sxs-lookup"><span data-stu-id="3f047-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="3f047-106">È possibile modificare queste impostazioni nel [portale di Azure](https://portal.azure.com) in **identità esterne/collaborazione esterna** :</span><span class="sxs-lookup"><span data-stu-id="3f047-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="3f047-107">**Gli amministratori e gli utenti del ruolo invitato dell'ospite possono invitare il** set a **Yes**</span><span class="sxs-lookup"><span data-stu-id="3f047-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="3f047-108">Per le **restrizioni di collaborazione** , scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f047-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="3f047-109">Se si seleziona **Consenti l'invio di inviti a qualsiasi dominio (più inclusivo)** , non sono necessarie altre configurazioni.</span><span class="sxs-lookup"><span data-stu-id="3f047-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="3f047-110">Se si seleziona **Nega inviti ai domini specificati** , assicurarsi che Microsoft.com non sia elencato nei domini di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3f047-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="3f047-111">Se si seleziona **Consenti solo gli inviti ai domini specificati (più restrittivi)** , assicurarsi che Microsoft.com *sia* elencato nei domini di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3f047-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="3f047-112">Se si impostano restrizioni che interagiscono con queste impostazioni, assicurarsi di escludere gli **account di servizio moderni** di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f047-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="3f047-113">Ad esempio, se si dispone di un criterio di accesso condizionale che impedisce agli account Guest di accedere al portale di Intune, escludere il gruppo di **account del servizio di lavoro moderno** da questo criterio.</span><span class="sxs-lookup"><span data-stu-id="3f047-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

