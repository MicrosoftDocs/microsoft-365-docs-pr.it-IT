---
title: Collaborare con persone esterne all'organizzazione
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni su come configurare le app di Microsoft 365 come Teams, OneDrive e SharePoint per la collaborazione con persone esterne all'organizzazione.
ms.openlocfilehash: 374ad8f5ec37fc0900fb38cb4e0f4743a02c4da4
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613455"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="70f0a-103">Collaborare con persone esterne all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="70f0a-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="70f0a-104">Le funzionalità di condivisione esterna in Microsoft 365 offrono agli utenti dell'organizzazione l'opportunità di collaborare con partner, fornitori, clienti e altri che non dispongono di un account nella directory.</span><span class="sxs-lookup"><span data-stu-id="70f0a-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="70f0a-105">È possibile condividere interi team o siti con persone esterne all'organizzazione o solo singoli file.</span><span class="sxs-lookup"><span data-stu-id="70f0a-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="70f0a-106">La collaborazione con persone esterne all'organizzazione è costituita da due componenti principali:</span><span class="sxs-lookup"><span data-stu-id="70f0a-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="70f0a-107">**Abilitare la** condivisione: configurare i controlli di condivisione in Azure Active Directory, Teams, Gruppi di Microsoft 365 e SharePoint per consentire il livello di condivisione desiderato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70f0a-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="70f0a-108"> Abilitare una sicurezza aggiuntiva: anche se le funzionalità di condivisione di base possono essere configurate per richiedere l'autenticazione di persone esterne all'organizzazione, Microsoft 365 offre molte funzionalità di sicurezza e conformità aggiuntive che consentono di proteggere i dati e mantenere i criteri di governance durante la condivisione esterna.</span><span class="sxs-lookup"><span data-stu-id="70f0a-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="70f0a-109">Abilitare la condivisione</span><span class="sxs-lookup"><span data-stu-id="70f0a-109">Enable sharing</span></span>

<span data-ttu-id="70f0a-110">Per impostazione predefinita, in Microsoft 365 la condivisione con persone esterne all'organizzazione è abilitata per SharePoint e OneDrive, ma disabilitata per Teams.</span><span class="sxs-lookup"><span data-stu-id="70f0a-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="70f0a-111">Molti scenari di condivisione esterna di SharePoint e OneDrive funzionano senza ulteriori configurazioni.</span><span class="sxs-lookup"><span data-stu-id="70f0a-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="70f0a-112">Per confermare le impostazioni per uno scenario in uso o abilitarne uno nuovo, scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="70f0a-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="70f0a-113">[Collaborare ai](collaborate-on-documents.md) documenti: informazioni su come configurare Microsoft 365 per consentire la condivisione e la collaborazione con persone esterne all'organizzazione (utenti guest e utenti non autenticati) su file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="70f0a-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="70f0a-114">[Collaborare in un sito:](collaborate-in-site.md) informazioni su come configurare Microsoft 365 per abilitare la condivisione di siti di SharePoint con utenti guest.</span><span class="sxs-lookup"><span data-stu-id="70f0a-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="70f0a-115">[Collaborare come team:](collaborate-as-team.md) informazioni su come configurare Microsoft 365 per abilitare la collaborazione guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="70f0a-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="70f0a-116">Per una panoramica completa delle impostazioni di condivisione guest disponibili in Microsoft 365, vedere Informazioni di riferimento sulle impostazioni di condivisione [guest di Microsoft 365.](microsoft-365-guest-settings.md)</span><span class="sxs-lookup"><span data-stu-id="70f0a-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="70f0a-117">Abilitare una sicurezza aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="70f0a-117">Enable additional security</span></span>

<span data-ttu-id="70f0a-118">Dopo aver abilitato lo scenario che si desidera utilizzare per la condivisione con persone esterne all'organizzazione, prendere in considerazione misure di sicurezza aggiuntive per proteggere il contenuto da condivisione accidentale o intenzionale inappropriata.</span><span class="sxs-lookup"><span data-stu-id="70f0a-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="70f0a-119">[Procedure consigliate per la condivisione di file](best-practices-anonymous-sharing.md) e cartelle con utenti non autenticati: informazioni sulle procedure consigliate per la condivisione con utenti non autenticati.</span><span class="sxs-lookup"><span data-stu-id="70f0a-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="70f0a-120">[Limitare l'esposizione accidentale:](share-limit-accidental-exposure.md) informazioni su come ridurre le probabilità di condividere accidentalmente contenuti sensibili con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70f0a-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="70f0a-121">Creare un ambiente di condivisione [guest](create-secure-guest-sharing-environment.md) sicuro: informazioni sugli strumenti forniti in Microsoft 365 per garantire che la condivisione con persone esterne all'organizzazione sia eseguita in modo sicuro e conforme ai requisiti di governance.</span><span class="sxs-lookup"><span data-stu-id="70f0a-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="70f0a-122">Collaborare con società partner</span><span class="sxs-lookup"><span data-stu-id="70f0a-122">Collaborate with partner companies</span></span>

<span data-ttu-id="70f0a-123">Quando si lavora a un progetto di grandi dimensioni che coinvolge molti utenti guest di un'altra organizzazione o se si ha una relazione continua con i fornitori in cui gli utenti guest cambiano spesso, è possibile utilizzare la gestione dei diritti in Azure Active Directory per semplificare la gestione degli utenti guest e consentire all'azienda partner di condividere tale responsabilità.</span><span class="sxs-lookup"><span data-stu-id="70f0a-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="70f0a-124">Per informazioni dettagliate, vedere Creare una [extranet B2B con utenti guest](b2b-extranet.md) gestiti.</span><span class="sxs-lookup"><span data-stu-id="70f0a-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="70f0a-125">Limitare la condivisione</span><span class="sxs-lookup"><span data-stu-id="70f0a-125">Limit sharing</span></span>

<span data-ttu-id="70f0a-126">Se alcune delle funzionalità di condivisione in Microsoft 365 sono in conflitto con i criteri di governance, vedere Limitare la condivisione [in Microsoft 365](microsoft-365-limit-sharing.md) per informazioni sulle opzioni per limitare la condivisione.</span><span class="sxs-lookup"><span data-stu-id="70f0a-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="70f0a-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="70f0a-127">Related topics</span></span>

[<span data-ttu-id="70f0a-128">Introduzione alla collaborazione sui file in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70f0a-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="70f0a-129">Pianificare la collaborazione file in SharePoint con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70f0a-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
