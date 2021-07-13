---
title: Distribuire Microsoft 365 Lighthouse di base
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
description: Per i provider di servizi gestiti (MSP) che usano Microsoft 365 Lighthouse, scopri come distribuire le Microsoft 365 Lighthouse di base.
ms.openlocfilehash: f329993443b4bd3003a3e8460d77f9b73ac10fc6
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53409105"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a><span data-ttu-id="9a0fe-103">Distribuire Microsoft 365 Lighthouse di base</span><span class="sxs-lookup"><span data-stu-id="9a0fe-103">Deploy Microsoft 365 Lighthouse baselines</span></span> 

> [!NOTE]
> <span data-ttu-id="9a0fe-104">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e sono disponibili solo per i partner che soddisfano i [requisiti](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fe-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="9a0fe-105">Se l'organizzazione non dispone di Microsoft 365 Lighthouse, vedere [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fe-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="9a0fe-106">Microsoft 365 Lighthouse di base consentono di distribuire configurazioni tenant gestite standard per proteggere utenti, dispositivi e dati tenant.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-106">Microsoft 365 Lighthouse baselines let you deploy standard managed tenant configurations to secure tenant users, devices, and data.</span></span> <span data-ttu-id="9a0fe-107">Esistono sei configurazioni di base predefinite standard con Microsoft 365 Lighthouse:</span><span class="sxs-lookup"><span data-stu-id="9a0fe-107">There are six default baseline configurations that come standard with Microsoft 365 Lighthouse:</span></span>

- <span data-ttu-id="9a0fe-108">Richiedi MFA per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="9a0fe-108">Require MFA for admins</span></span>
- <span data-ttu-id="9a0fe-109">Richiedi MFA per gli utenti finali</span><span class="sxs-lookup"><span data-stu-id="9a0fe-109">Require MFA for end users</span></span>
- <span data-ttu-id="9a0fe-110">Blocca autenticazione legacy</span><span class="sxs-lookup"><span data-stu-id="9a0fe-110">Block Legacy Authentication</span></span>
- <span data-ttu-id="9a0fe-111">Configurare Registrazione dispositivi in Microsoft Endpoint Manager - Aggiunta ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="9a0fe-111">Set up Device Enrollment in Microsoft Endpoint Manager – Azure AD Join</span></span>
- <span data-ttu-id="9a0fe-112">Configurare i criteri anti-virus defender per Windows dispositivi</span><span class="sxs-lookup"><span data-stu-id="9a0fe-112">Configure Defender Anti-virus policy for Windows devices</span></span>
- <span data-ttu-id="9a0fe-113">Configurare i criteri di conformità per Windows dispositivi</span><span class="sxs-lookup"><span data-stu-id="9a0fe-113">Configure Compliance Policy for Windows devices</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9a0fe-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9a0fe-114">Before you begin</span></span>

<span data-ttu-id="9a0fe-115">Assicurati che tu e i tenant dei clienti soddisfino i requisiti elencati in [Requisiti per Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a0fe-115">Make sure you and your customer tenants meet the requirements listed in [Requirements for Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).</span></span>

## <a name="learn-more-about-the-default-baseline"></a><span data-ttu-id="9a0fe-116">Ulteriori informazioni sulla previsione predefinita</span><span class="sxs-lookup"><span data-stu-id="9a0fe-116">Learn more about the default baseline</span></span>

<span data-ttu-id="9a0fe-117">Selezionare **Baselines** nel riquadro di spostamento sinistro per aprire la pagina Baselines.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-117">Select **Baselines** from the left navigation pane to open the Baselines page.</span></span> <span data-ttu-id="9a0fe-118">Vedrai che la linea di base predefinita è già stata aggiunta al gruppo tenant predefinito (tutti i tenant).</span><span class="sxs-lookup"><span data-stu-id="9a0fe-118">You'll see that the default baseline has already been added to the Default tenant group (all tenants).</span></span> <span data-ttu-id="9a0fe-119">Per visualizzare le configurazioni di base predefinite, selezionare **Visualizza** previsione per aprire la pagina Previsione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-119">To view the default baseline configurations, select **View baseline** to open the Default baseline page.</span></span> <span data-ttu-id="9a0fe-120">Le configurazioni sono elencate come passaggi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-120">The configurations are listed as deployment steps.</span></span> <span data-ttu-id="9a0fe-121">Selezionare uno dei passaggi di distribuzione per visualizzare i dettagli della distribuzione e l'impatto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-121">Select any of the deployment steps to view deployment details and user impact.</span></span>

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Screenshot of the Default baseline page.>.":::

## <a name="deploy-a-baseline-configuration"></a><span data-ttu-id="9a0fe-123">Distribuire una configurazione di base</span><span class="sxs-lookup"><span data-stu-id="9a0fe-123">Deploy a baseline configuration</span></span>  

1. <span data-ttu-id="9a0fe-124">Nella pagina di spostamento sinistra selezionare **Tenant per** visualizzare un elenco dei tenant onboarded.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-124">In the left navigation page, select **Tenants** to view a list of your onboarded tenants.</span></span>

2. <span data-ttu-id="9a0fe-125">Selezionare il tenant in cui si desidera distribuire la configurazione di base.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-125">Select the tenant you want to deploy the baseline configuration to.</span></span>

3. <span data-ttu-id="9a0fe-126">Selezionare la **scheda Piano di** distribuzione per visualizzare tutti i passaggi di distribuzione dalla linea di base che sono stati aggiunti al piano di distribuzione del tenant.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-126">Select the **Deployment plan** tab to see all the deployment steps from the baseline that have been added to the tenant's deployment plan.</span></span>

4. <span data-ttu-id="9a0fe-127">Selezionare un passaggio di distribuzione per aprire la pagina del passaggio di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-127">Select a deployment step to open the deployment step page.</span></span>

5. <span data-ttu-id="9a0fe-128">Selezionare **Applica** per applicare il passaggio di distribuzione selezionato al tenant.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-128">Select **Apply** to apply the selected deployment step to the tenant.</span></span> <span data-ttu-id="9a0fe-129">Se il passaggio di distribuzione indica "Questa azione richiede un passaggio manuale", assicurarsi di completare il passaggio manuale in modo che il passaggio di distribuzione venga applicato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9a0fe-129">If the deployment step indicates "This action requires a manual step", make sure to complete the manual step so the deployment step is applied correctly.</span></span>

## <a name="related-content"></a><span data-ttu-id="9a0fe-130">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="9a0fe-130">Related content</span></span>

<span data-ttu-id="9a0fe-131">[Panoramica dell'utilizzo delle linee di base per distribuire configurazioni tenant standard](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="9a0fe-131">[Overview of using baselines to deploy standard tenant configurations](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (article)</span></span>\
<span data-ttu-id="9a0fe-132">[Microsoft 365 Lighthouse domande frequenti](m365-lighthouse-faq.yml) (articolo)</span><span class="sxs-lookup"><span data-stu-id="9a0fe-132">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>