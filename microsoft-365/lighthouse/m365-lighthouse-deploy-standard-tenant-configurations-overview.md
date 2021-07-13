---
title: Panoramica dell'utilizzo delle linee di base per distribuire configurazioni tenant standard
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Per i provider di servizi gestiti (MSP) Microsoft 365 Lighthouse informazioni sull'utilizzo delle linee di base per distribuire configurazioni tenant standard.
ms.openlocfilehash: ff3fb21e71195f9614870b8e3c65c92ee11fdf69
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409180"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a><span data-ttu-id="853ca-103">Panoramica dell'utilizzo delle linee di base per distribuire configurazioni tenant standard</span><span class="sxs-lookup"><span data-stu-id="853ca-103">Overview of using baselines to deploy standard tenant configurations</span></span> 

> [!NOTE]
> <span data-ttu-id="853ca-104">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="853ca-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="853ca-105">Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="853ca-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="853ca-106">Microsoft 365 Lighthouse di base offrono un modo ripetibile e scalabile per valutare e gestire Microsoft 365 di sicurezza tra più tenant.</span><span class="sxs-lookup"><span data-stu-id="853ca-106">Microsoft 365 Lighthouse baselines provide a repeatable and scalable way for you to assess and manage Microsoft 365 security settings across multiple tenants.</span></span> <span data-ttu-id="853ca-107">Le linee di base consentono inoltre di monitorare i criteri di sicurezza di base e gli standard di conformità del tenant con configurazioni che consentono di proteggere utenti, dispositivi e dati.</span><span class="sxs-lookup"><span data-stu-id="853ca-107">Baselines also help monitor core security policies and tenant compliance standards with configurations that secure users, devices, and data.</span></span>

<span data-ttu-id="853ca-108">Progettato per aiutare i partner a consentire ai clienti l'adozione della sicurezza al proprio ritmo, Microsoft 365 Lighthouse fornisce un set standard di parametri di base e configurazioni predefinite per Microsoft 365 servizi.</span><span class="sxs-lookup"><span data-stu-id="853ca-108">Designed to help partners enable customer adoption of security at their own pace, Microsoft 365 Lighthouse provides a standard set of baseline parameters and pre-defined configurations for Microsoft 365 services.</span></span> <span data-ttu-id="853ca-109">Queste configurazioni di sicurezza consentono di misurare l'avanzamento Microsoft 365 sicurezza e conformità dei tenant.</span><span class="sxs-lookup"><span data-stu-id="853ca-109">These security configurations help measure your tenants' Microsoft 365 security and compliance progress.</span></span>

<span data-ttu-id="853ca-110">È possibile visualizzare la previsione predefinita e i relativi passaggi di distribuzione dall'Microsoft 365 Lighthouse.</span><span class="sxs-lookup"><span data-stu-id="853ca-110">You can view the default baseline and its deployment steps from within Microsoft 365 Lighthouse.</span></span> <span data-ttu-id="853ca-111">Per applicare le linee di base a un tenant, selezionare **Tenant nel** riquadro di spostamento sinistro e quindi selezionare un tenant.</span><span class="sxs-lookup"><span data-stu-id="853ca-111">To apply baselines to a tenant, select **Tenants** in the left navigation pane, and then select a tenant.</span></span> <span data-ttu-id="853ca-112">Passare quindi alla scheda **Piani di distribuzione** e implementare la previsione desiderata.</span><span class="sxs-lookup"><span data-stu-id="853ca-112">Next, go to the **Deployment plans** tab and implement the desired baseline.</span></span>

## <a name="standard-baseline-security-templates"></a><span data-ttu-id="853ca-113">Modelli di sicurezza di base standard</span><span class="sxs-lookup"><span data-stu-id="853ca-113">Standard baseline security templates</span></span>

<span data-ttu-id="853ca-114">Microsoft 365 Lighthouse configurazioni di base standard per i carichi di lavoro di sicurezza sono progettate per consentire a tutti i tenant gestiti di raggiungere uno stato accettabile di conformità e copertura della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="853ca-114">Microsoft 365 Lighthouse standard baseline configurations for security workloads are designed to help all managed tenants reach an acceptable state of security coverage and compliance.</span></span>

<span data-ttu-id="853ca-115">Le configurazioni di base nella tabella seguente sono standard con la Microsoft 365 Lighthouse predefinita.</span><span class="sxs-lookup"><span data-stu-id="853ca-115">The baseline configurations in the following table come standard with the Microsoft 365 Lighthouse default baseline.</span></span><br><br>

| <span data-ttu-id="853ca-116">Configurazione di base</span><span class="sxs-lookup"><span data-stu-id="853ca-116">Baseline configuration</span></span> | <span data-ttu-id="853ca-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="853ca-117">Description</span></span> |
|--|--|
| <span data-ttu-id="853ca-118">Richiedi MFA per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="853ca-118">Require MFA for admins</span></span> | <span data-ttu-id="853ca-119">Criteri di accesso condizionale solo report che richiedono l'autenticazione a più fattori per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="853ca-119">A report-only Conditional Access policy requiring multifactor authentication for admins.</span></span> <span data-ttu-id="853ca-120">È necessario per tutte le applicazioni cloud.</span><span class="sxs-lookup"><span data-stu-id="853ca-120">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="853ca-121">Richiedi MFA per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="853ca-121">Require MFA for end users</span></span> | <span data-ttu-id="853ca-122">Criteri di accesso condizionale solo report che richiedono l'autenticazione a più fattori per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="853ca-122">A report-only Conditional Access policy that requires multifactor authentication for users.</span></span> <span data-ttu-id="853ca-123">È necessario per tutte le applicazioni cloud.</span><span class="sxs-lookup"><span data-stu-id="853ca-123">It's required for all cloud applications.</span></span> |
| <span data-ttu-id="853ca-124">Bloccare l'autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="853ca-124">Block legacy authentication</span></span> | <span data-ttu-id="853ca-125">Criteri di accesso condizionale solo report per bloccare l'autenticazione client legacy.</span><span class="sxs-lookup"><span data-stu-id="853ca-125">A report-only Conditional Access policy to block legacy client authentication.</span></span> |
| <span data-ttu-id="853ca-126">Registrare i dispositivi in Microsoft Endpoint Manager - Aggiunta ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="853ca-126">Enroll devices in Microsoft Endpoint Manager – Azure AD Join</span></span> | <span data-ttu-id="853ca-127">Registrazione dei dispositivi per consentire ai dispositivi tenant di registrarsi Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="853ca-127">Device enrollment to allow your tenant devices to enroll in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="853ca-128">Questa operazione viene eseguita configurando la registrazione automatica tra Azure Active Directory e Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="853ca-128">This is done by setting up Auto Enrollment between Azure Active Directory and Microsoft Endpoint Manager.</span></span> |
| <span data-ttu-id="853ca-129">Configurazione dei criteri antivirus</span><span class="sxs-lookup"><span data-stu-id="853ca-129">Antivirus (AV) policy configuration</span></span> | <span data-ttu-id="853ca-130">Un profilo di configurazione dei dispositivi Windows dispositivi con impostazioni Antivirus Microsoft Defender preconfigurato.</span><span class="sxs-lookup"><span data-stu-id="853ca-130">A Device Configuration profile for Windows devices with pre-configured Microsoft Defender Antivirus settings.</span></span> |
| <span data-ttu-id="853ca-131">Window 10 Compliance policy set up</span><span class="sxs-lookup"><span data-stu-id="853ca-131">Window 10 Compliance policy set up</span></span> | <span data-ttu-id="853ca-132">Un Windows dei dispositivi con impostazioni preconfigurato per soddisfare i requisiti di conformità di base.</span><span class="sxs-lookup"><span data-stu-id="853ca-132">A Windows device policy with pre-configured settings to meet basic compliance requirements.</span></span> |

## <a name="related-content"></a><span data-ttu-id="853ca-133">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="853ca-133">Related content</span></span>

<span data-ttu-id="853ca-134">[Distribuire Microsoft 365 Lighthouse di base](m365-lighthouse-deploy-baselines.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="853ca-134">[Deploy Microsoft 365 Lighthouse baselines](m365-lighthouse-deploy-baselines.md) (article)</span></span>\
<span data-ttu-id="853ca-135">[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)</span><span class="sxs-lookup"><span data-stu-id="853ca-135">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
