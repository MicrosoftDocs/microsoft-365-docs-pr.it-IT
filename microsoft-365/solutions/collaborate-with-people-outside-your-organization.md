---
title: Collaborare con utenti esterni all'organizzazione
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Configurare Microsoft 365 per abilitare la condivisione e la sicurezza aggiuntiva quando si invitano gli utenti esterni a collaborare in teams e a condividere i siti di SharePoint.
ms.openlocfilehash: f8dc81ae32bed7a12daf21955ada60ab852d4617
ms.sourcegitcommit: 195172dd836e8a793e8e0c2db3323b7391bc51ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255792"
---
# <a name="collaborating-with-people-outside-your-organization"></a><span data-ttu-id="7c700-103">Collaborare con utenti esterni all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7c700-103">Collaborating with people outside your organization</span></span>

<span data-ttu-id="7c700-104">Le funzionalità di condivisione esterna di Microsoft 365 offrono agli utenti dell'organizzazione la possibilità di collaborare con partner, fornitori, clienti e altri utenti che non dispongono di un account nella directory.</span><span class="sxs-lookup"><span data-stu-id="7c700-104">The external sharing capabilities in Microsoft 365 provide an opportunity for people in your organization to collaborate with partners, vendors, customers, and others who don't have an account in your directory.</span></span> <span data-ttu-id="7c700-105">È possibile condividere interi team o siti con persone esterne all'organizzazione o solo singoli file.</span><span class="sxs-lookup"><span data-stu-id="7c700-105">You can share entire teams or sites with people outside your organization, or just individual files.</span></span>

<span data-ttu-id="7c700-106">Collaborare con persone esterne all'organizzazione è costituito da due componenti principali:</span><span class="sxs-lookup"><span data-stu-id="7c700-106">Collaborating with people outside your organization consists of two major components:</span></span>

- <span data-ttu-id="7c700-107">**Abilita condivisione** : configurare i controlli di condivisione in Azure Active Directory, teams, Microsoft 365 Groups e SharePoint per consentire il livello di condivisione desiderato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7c700-107">**Enable sharing** - Configure the sharing controls across Azure Active Directory, Teams, Microsoft 365 Groups, and SharePoint to allow the level of sharing that you want for your organization.</span></span>
- <span data-ttu-id="7c700-108">**Abilitare la sicurezza aggiuntiva** -mentre le funzionalità di condivisione di base possono essere configurate in modo da richiedere agli utenti esterni all'organizzazione di eseguire l'autenticazione, Microsoft 365 fornisce numerose funzionalità aggiuntive di sicurezza e conformità che consentono di proteggere i dati e di gestire i criteri di governance durante la condivisione esterna.</span><span class="sxs-lookup"><span data-stu-id="7c700-108">**Enable additional security** - While the basic sharing features can be configured to require people outside your organization to authenticate, Microsoft 365 provides many additional security and compliance features to help you protect your data and maintain your governance policies while sharing externally.</span></span>

## <a name="enable-sharing"></a><span data-ttu-id="7c700-109">Abilita condivisione</span><span class="sxs-lookup"><span data-stu-id="7c700-109">Enable sharing</span></span>

<span data-ttu-id="7c700-110">Per impostazione predefinita, in Microsoft 365, la condivisione con utenti esterni all'organizzazione è abilitata per SharePoint e OneDrive, ma è disabilitata per i team.</span><span class="sxs-lookup"><span data-stu-id="7c700-110">By default, in Microsoft 365, sharing with people outside your organization is enabled for SharePoint and OneDrive, but disabled for Teams.</span></span> <span data-ttu-id="7c700-111">Molti scenari di condivisione esterna di SharePoint e OneDrive funzionano senza ulteriori configurazioni.</span><span class="sxs-lookup"><span data-stu-id="7c700-111">Many SharePoint and OneDrive external sharing scenarios work without further configuration.</span></span> <span data-ttu-id="7c700-112">Per confermare le impostazioni di uno scenario che si sta utilizzando o abilitarne una nuova, scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c700-112">To confirm the settings for a scenario that you're using, or enable a new one, choose from the following options:</span></span>

- <span data-ttu-id="7c700-113">[Collaborare ai documenti](collaborate-on-documents.md) : informazioni su come configurare Microsoft 365 per consentire la condivisione e la collaborazione con persone esterne all'organizzazione (sia ospiti che utenti non autenticati) su file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="7c700-113">[Collaborate on documents](collaborate-on-documents.md) - Learn how to configure Microsoft 365 to allow sharing and collaboration with people outside your organization (both guests and unauthenticated users) on files and folders.</span></span>
- <span data-ttu-id="7c700-114">[Collaborare in un sito](collaborate-in-site.md) : informazioni su come configurare Microsoft 365 per abilitare la condivisione dei siti di SharePoint con gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7c700-114">[Collaborate in a site](collaborate-in-site.md) - Learn how to configure Microsoft 365 to enable sharing SharePoint sites with guests.</span></span>
- <span data-ttu-id="7c700-115">[Collaborare come team](collaborate-as-team.md) -informazioni su come configurare Microsoft 365 per abilitare la collaborazione ospite in teams.</span><span class="sxs-lookup"><span data-stu-id="7c700-115">[Collaborate as a team](collaborate-as-team.md) - Learn how to configure Microsoft 365 to enable guest collaboration in Teams.</span></span>

<span data-ttu-id="7c700-116">Per una panoramica completa delle impostazioni di condivisione Guest disponibili in Microsoft 365, vedere [riferimento alle impostazioni di condivisione Guest di microsoft 365](microsoft-365-guest-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7c700-116">For a comprehensive look at the guest sharing settings available across Microsoft 365, see [Microsoft 365 guest sharing settings reference](microsoft-365-guest-settings.md).</span></span>

## <a name="enable-additional-security"></a><span data-ttu-id="7c700-117">Abilitare la sicurezza aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="7c700-117">Enable additional security</span></span>

<span data-ttu-id="7c700-118">Dopo aver abilitato lo scenario che si desidera utilizzare per la condivisione con utenti esterni all'organizzazione, prendere in considerazione ulteriori misure di salvaguardia per proteggere il contenuto da una condivisione accidentale o intenzionale.</span><span class="sxs-lookup"><span data-stu-id="7c700-118">Once you've enabled the scenario that you want to use for sharing with people outside your organization, consider additional safeguards to help protect your content from accidental or intentional inappropriate sharing.</span></span>

- <span data-ttu-id="7c700-119">[Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md) : informazioni sulle procedure consigliate per la condivisione con utenti non autenticati.</span><span class="sxs-lookup"><span data-stu-id="7c700-119">[Best practices for sharing files and folders with unauthenticated users](best-practices-anonymous-sharing.md) - Learn about best practices for sharing with unauthenticated users.</span></span>
- <span data-ttu-id="7c700-120">[Limite di esposizione accidentale](share-limit-accidental-exposure.md) -informazioni su come ridurre le probabilità di condivisione accidentale di contenuti sensibili con utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7c700-120">[Limit accidental exposure](share-limit-accidental-exposure.md) - Learn how to reduce the chances of accidentally sharing sensitive content with people outside your organization.</span></span>
- <span data-ttu-id="7c700-121">[Creare un ambiente di condivisione Guest sicuro](create-secure-guest-sharing-environment.md) -informazioni sugli strumenti forniti in Microsoft 365 per garantire che la condivisione con persone esterne all'organizzazione venga svolta in modo sicuro e conforme ai requisiti di governance.</span><span class="sxs-lookup"><span data-stu-id="7c700-121">[Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) - Learn about the tools provided in Microsoft 365 to help ensure that sharing with people outside your organization is done in a safe and secure manner and meets your governance requirements.</span></span>

## <a name="collaborate-with-partner-companies"></a><span data-ttu-id="7c700-122">Collaborare con le aziende partner</span><span class="sxs-lookup"><span data-stu-id="7c700-122">Collaborate with partner companies</span></span>

<span data-ttu-id="7c700-123">Quando si lavora su un progetto di grandi dimensioni che coinvolge numerosi ospiti di un'altra organizzazione o se si dispone di una relazione del fornitore in corso in cui gli utenti cambiano spesso, è possibile utilizzare la gestione dei diritti in Azure Active Directory per semplificare la gestione degli ospiti e consentire all'azienda partner di condividere tale responsabilità.</span><span class="sxs-lookup"><span data-stu-id="7c700-123">When you're working on a large project that involves many guests from another organization, or if you have an ongoing vendor relationship in which guests are often changing, you can use entitlement management in Azure Active Directory to simplify guest management and allow the partner company to share in that responsibility.</span></span> <span data-ttu-id="7c700-124">Per ulteriori informazioni, vedere [Create a B2B Extranet with Managed guests](b2b-extranet.md) .</span><span class="sxs-lookup"><span data-stu-id="7c700-124">See [Create a B2B extranet with managed guests](b2b-extranet.md) for details.</span></span>

## <a name="limit-sharing"></a><span data-ttu-id="7c700-125">Limitare la condivisione</span><span class="sxs-lookup"><span data-stu-id="7c700-125">Limit sharing</span></span>

<span data-ttu-id="7c700-126">Se alcune delle funzionalità di condivisione in Microsoft 365 sono in conflitto con i criteri di governance, vedere [limitare la condivisione in microsoft 365](microsoft-365-limit-sharing.md) per informazioni sulle opzioni di limitazione della condivisione.</span><span class="sxs-lookup"><span data-stu-id="7c700-126">If some of the sharing features in Microsoft 365 conflict with your governance policies, see [Limit sharing in Microsoft 365](microsoft-365-limit-sharing.md) to learn about options for limiting sharing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c700-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7c700-127">Related topics</span></span>

[<span data-ttu-id="7c700-128">Introduzione alla collaborazione di file in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c700-128">Intro to file collaboration in Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/intro-to-file-collaboration)

[<span data-ttu-id="7c700-129">Pianificare la collaborazione dei file in SharePoint con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7c700-129">Plan file collaboration in SharePoint with Microsoft 365</span></span>](https://docs.microsoft.com/sharepoint/deploy-file-collaboration)
