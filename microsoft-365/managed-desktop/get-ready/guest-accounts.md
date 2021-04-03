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
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574608"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="11dc7-104">Prerequisiti per gli account Guest</span><span class="sxs-lookup"><span data-stu-id="11dc7-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="11dc7-105">Microsoft Managed Desktop richiede le impostazioni seguenti nell'organizzazione di Azure AD per l'accesso all'account guest.</span><span class="sxs-lookup"><span data-stu-id="11dc7-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="11dc7-106">È possibile modificare queste impostazioni nel portale [di Azure](https://portal.azure.com) in Identità **esterne /Collaborazione esterna:**</span><span class="sxs-lookup"><span data-stu-id="11dc7-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="11dc7-107">**Gli amministratori e gli utenti nel ruolo di invitatore guest possono invitare impostato** su **Sì**</span><span class="sxs-lookup"><span data-stu-id="11dc7-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="11dc7-108">Per **Restrizioni di collaborazione,** scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="11dc7-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="11dc7-109">Se si seleziona **Consenti l'invio di inviti a qualsiasi dominio (più inclusivo),** non è necessaria alcuna altra configurazione.</span><span class="sxs-lookup"><span data-stu-id="11dc7-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="11dc7-110">Se si seleziona **Nega inviti** ai domini specificati, assicurarsi che Microsoft.com non sia elencato nei domini di destinazione.</span><span class="sxs-lookup"><span data-stu-id="11dc7-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="11dc7-111">Se si seleziona Consenti inviti solo ai domini specificati **(più restrittivi),** assicurarsi Microsoft.com sia elencato nei domini di destinazione. </span><span class="sxs-lookup"><span data-stu-id="11dc7-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="11dc7-112">Se si impostano restrizioni che interagiscono con queste impostazioni, assicurarsi di escludere gli account del servizio Azure Active Directory **Modern Workplace Service.**</span><span class="sxs-lookup"><span data-stu-id="11dc7-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="11dc7-113">Ad esempio, se si dispone di un criterio di accesso condizionale che impedisce agli account guest di accedere al portale di Intune, escludere il gruppo **Modern Workplace Service Accounts** da questo criterio.</span><span class="sxs-lookup"><span data-stu-id="11dc7-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="11dc7-114">Passaggi per prepararsi</span><span class="sxs-lookup"><span data-stu-id="11dc7-114">Steps to get ready</span></span>

1. <span data-ttu-id="11dc7-115">Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="11dc7-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="11dc7-116">Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="11dc7-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="11dc7-117">[Prerequisiti per gli account guest](guest-accounts.md) (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="11dc7-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="11dc7-118">Configurazione rete in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="11dc7-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="11dc7-119">Preparare certificati e profili di rete per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="11dc7-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="11dc7-120">Preparare l'accesso alle risorse locali per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="11dc7-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="11dc7-121">App in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="11dc7-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="11dc7-122">Preparare unità mappate per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="11dc7-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="11dc7-123">Preparare risorse di stampa per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="11dc7-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)