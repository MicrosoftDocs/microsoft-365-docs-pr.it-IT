---
title: App in Microsoft Managed Desktop
description: Spiega come vengono gestite le app, incluso come creare un pacchetto, distribuirle e supportarle.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028945"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="ea503-104">App in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ea503-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="ea503-105">App in genere</span><span class="sxs-lookup"><span data-stu-id="ea503-105">Apps generally</span></span>

<span data-ttu-id="ea503-106">Microsoft include alcune app chiave insieme alla licenza Microsoft 365 E3 o E5 necessaria per partecipare Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ea503-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ea503-107">Tuttavia, anche se forniamo queste app, hai ancora alcune responsabilità e azioni da completare.</span><span class="sxs-lookup"><span data-stu-id="ea503-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="ea503-108">Puoi anche distribuire altre app non Microsoft agli utenti per il self-service tramite il Portale aziendale o un'installazione in background necessaria, il tutto usando la pipeline di distribuzione di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ea503-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="ea503-109">App fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ea503-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="ea503-110">Nella licenza Microsoft Managed Desktop sono incluse le versioni a 64 bit delle app in Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business e OneNote). Le versioni A livello di Microsoft Project e Visio non  sono incluse per impostazione predefinita, ma è possibile richiederle di essere aggiunte.</span><span class="sxs-lookup"><span data-stu-id="ea503-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="ea503-111">Per altre informazioni su queste app, vedi [Installare Microsoft Project o Microsoft Visio su Microsoft Managed Desktop dispositivi](../get-started/project-visio.md).</span><span class="sxs-lookup"><span data-stu-id="ea503-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="ea503-112">Cosa fa Microsoft per supportare le app fornite</span><span class="sxs-lookup"><span data-stu-id="ea503-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="ea503-113">Microsoft fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto per le app Microsoft 365 Apps for enterprise incluse.</span><span class="sxs-lookup"><span data-stu-id="ea503-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="ea503-114">Le versioni di Microsoft Project e Visio a clic non  sono incluse per impostazione predefinita, ma Microsoft Managed Desktop fornirà gruppi di distribuzione che consentono all'amministratore IT di gestire le licenze e distribuire queste applicazioni in modo appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea503-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="ea503-115">Microsoft supporterà gli utenti di queste applicazioni tramite i canali Microsoft Managed Desktop supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="ea503-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="ea503-116">Cosa è necessario fare per supportare le app fornite</span><span class="sxs-lookup"><span data-stu-id="ea503-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="ea503-117">Esistono ancora alcune operazioni da eseguire con queste app:</span><span class="sxs-lookup"><span data-stu-id="ea503-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="ea503-118">**Assegnare licenze:** l'utente è responsabile dell'ottenimento e dell'assegnazione delle licenze appropriate agli utenti per Microsoft 365 Apps for enterprise.</span><span class="sxs-lookup"><span data-stu-id="ea503-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="ea503-119">**Aggiungere utenti ai gruppi** di sicurezza: se si utilizza Microsoft Project o Visio, l'amministratore IT deve aggiungere tali utenti ai gruppi di distribuzione appropriati.</span><span class="sxs-lookup"><span data-stu-id="ea503-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="ea503-120">Gli amministratori IT sono inoltre responsabili del recupero delle licenze da tali utenti se lasciano l'azienda.</span><span class="sxs-lookup"><span data-stu-id="ea503-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="ea503-121">**Distribuire Microsoft 365** componenti aggiuntivi: se sono necessari componenti aggiuntivi per qualsiasi app di Microsoft 365 Apps for enterprise, distribuirli centralmente come qualsiasi altra app Windows 32.</span><span class="sxs-lookup"><span data-stu-id="ea503-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="ea503-122">App fornite</span><span class="sxs-lookup"><span data-stu-id="ea503-122">Apps you provide</span></span>

<span data-ttu-id="ea503-123">Probabilmente hai altre app necessarie per le tue operazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="ea503-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="ea503-124">Queste app possono essere distribuite solo Microsoft Managed Desktop dispositivi usando Microsoft Intune pipeline di distribuzione di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ea503-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="ea503-125">Per altre informazioni sulla distribuzione delle applicazioni, segui i passaggi descritti in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span><span class="sxs-lookup"><span data-stu-id="ea503-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="ea503-126">Preparazione delle tue app per l'inclusione in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ea503-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="ea503-127">Controlla le app, controllando:</span><span class="sxs-lookup"><span data-stu-id="ea503-127">Review your apps, checking:</span></span>

- <span data-ttu-id="ea503-128">Nessuna delle app è proibita o ha un comportamento limitato, come descritto in [Microsoft Managed Desktop app.](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ea503-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="ea503-129">Le app devono essere pronte per la gestione Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ea503-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="ea503-130">Per altre informazioni su questo argomento, vedi [distribuzione](/intune/apps-windows-10-app-deploy) Windows 10 app usando Microsoft Intune e Aggiungi app [a Microsoft Intune](/intune/apps-add).</span><span class="sxs-lookup"><span data-stu-id="ea503-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="ea503-131">Altri requisiti di pre-creazione del pacchetto, ad esempio la fornitura di codici di licenza, il contratto con le condizioni di licenza e la pre-impostazione delle connessioni server.</span><span class="sxs-lookup"><span data-stu-id="ea503-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="ea503-132">Passaggi per prepararsi</span><span class="sxs-lookup"><span data-stu-id="ea503-132">Steps to get ready</span></span>

1. <span data-ttu-id="ea503-133">Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="ea503-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="ea503-134">Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="ea503-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="ea503-135">Prerequisiti per gli account Guest</span><span class="sxs-lookup"><span data-stu-id="ea503-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="ea503-136">Configurazione rete in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ea503-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="ea503-137">Preparare certificati e profili di rete per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ea503-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="ea503-138">Preparare l'accesso alle risorse locali per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ea503-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="ea503-139">[App in Microsoft Managed Desktop](apps.md) (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="ea503-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="ea503-140">Preparare unità mappate per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ea503-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="ea503-141">Preparare risorse di stampa per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="ea503-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
