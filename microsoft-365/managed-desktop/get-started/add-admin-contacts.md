---
title: Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione
description: Dicci chi contattare per ogni area di interesse.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925893"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="0ae69-104">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="0ae69-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="0ae69-105">Esistono diversi modi in cui il servizio Microsoft Managed Desktop comunica con i clienti.</span><span class="sxs-lookup"><span data-stu-id="0ae69-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="0ae69-106">Per semplificare la comunicazione e verificare che stiamo controllando con le persone giuste, è necessario fornire un set di contatti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="0ae69-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="0ae69-107">Microsoft Managed Desktop IT Operations contatta queste persone per assistenza nella risoluzione dei problemi relativi al tenant.</span><span class="sxs-lookup"><span data-stu-id="0ae69-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ae69-108">Questi contatti potrebbero essere già stati aggiunti nel portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0ae69-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="0ae69-109">In tal caso, è necessario verificare che l'elenco dei contatti sia accurato, poiché Microsoft Managed **Desktop** deve essere in grado di raggiungerli in caso di incidenti gravi.</span><span class="sxs-lookup"><span data-stu-id="0ae69-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="0ae69-110">Accesso ad Azure Active Directory per il portale di amministrazione di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0ae69-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="0ae69-111">Il portale di amministrazione di Microsoft Managed Desktop richiede che gli utenti che accedono al portale dispongono di uno dei ruoli di Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="0ae69-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="0ae69-112">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="0ae69-112">Global Administrator</span></span>
- <span data-ttu-id="0ae69-113">Amministratore del servizio Intune</span><span class="sxs-lookup"><span data-stu-id="0ae69-113">Intune Service Administrator</span></span>
- <span data-ttu-id="0ae69-114">Lettore globale</span><span class="sxs-lookup"><span data-stu-id="0ae69-114">Global Reader</span></span>
- <span data-ttu-id="0ae69-115">Service Support Administrator</span><span class="sxs-lookup"><span data-stu-id="0ae69-115">Service Support Administrator</span></span>

<span data-ttu-id="0ae69-116">L'amministratore globale deve essere quello per registrare l'organizzazione in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0ae69-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="0ae69-117">Tutti e cinque i ruoli hanno lo stesso accesso nel portale di amministrazione per avviare e visualizzare le attività.</span><span class="sxs-lookup"><span data-stu-id="0ae69-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="0ae69-118">Per ulteriori informazioni sull'assegnazione di questi ruoli in Azure AD, vedere [Autorizzazioni dei ruoli di amministratore in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="0ae69-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="0ae69-119">Aree di contatto dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="0ae69-119">Admin contact areas of focus</span></span>

<span data-ttu-id="0ae69-120">I contatti dell'amministratore devono essere la persona o il gruppo migliori in grado di rispondere alle domande e prendere decisioni per diverse aree di interesse.</span><span class="sxs-lookup"><span data-stu-id="0ae69-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="0ae69-121">**Microsoft Managed Desktop Operations contatta questi contatti dell'amministratore per le domande relative alle richieste di supporto inviate dal cliente.**</span><span class="sxs-lookup"><span data-stu-id="0ae69-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="0ae69-122">Questi contatti di amministratore riceveranno notifiche per gli aggiornamenti delle richieste di supporto e i nuovi messaggi.</span><span class="sxs-lookup"><span data-stu-id="0ae69-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="0ae69-123">Queste aree includono:</span><span class="sxs-lookup"><span data-stu-id="0ae69-123">These areas include:</span></span>

<span data-ttu-id="0ae69-124">Area di messa a fuoco</span><span class="sxs-lookup"><span data-stu-id="0ae69-124">Area of focus</span></span> | <span data-ttu-id="0ae69-125">Per domande su</span><span class="sxs-lookup"><span data-stu-id="0ae69-125">For questions about</span></span>
--- | ---
<span data-ttu-id="0ae69-126">Creazione di pacchetti dell'app</span><span class="sxs-lookup"><span data-stu-id="0ae69-126">App packaging</span></span> | <span data-ttu-id="0ae69-127">Risoluzione dei problemi di creazione di pacchetti delle app</span><span class="sxs-lookup"><span data-stu-id="0ae69-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="0ae69-128">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="0ae69-128">Devices</span></span> | <span data-ttu-id="0ae69-129">Integrità dei dispositivi, risoluzione dei problemi con i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0ae69-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="0ae69-130">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0ae69-130">Security</span></span> | <span data-ttu-id="0ae69-131">Risoluzione dei problemi di sicurezza con i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0ae69-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="0ae69-132">Help desk IT</span><span class="sxs-lookup"><span data-stu-id="0ae69-132">IT help desk</span></span> | <span data-ttu-id="0ae69-133">nei casi in cui il personale del supporto tecnico manita i ticket utente al di fuori delle aree di supporto di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0ae69-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="0ae69-134">Altro</span><span class="sxs-lookup"><span data-stu-id="0ae69-134">Other</span></span> | <span data-ttu-id="0ae69-135">Per problemi non coperti da altre aree</span><span class="sxs-lookup"><span data-stu-id="0ae69-135">For issues not covered by other areas</span></span>

<span data-ttu-id="0ae69-136">**Chiunque scegli per questi contatti deve avere le conoscenze e l'autorità necessarie per prendere decisioni per l'ambiente Microsoft Managed Desktop.**</span><span class="sxs-lookup"><span data-stu-id="0ae69-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="0ae69-137">Quando si esegue l'onboardboard dell'ambiente Microsoft Managed Desktop, viene richiesto di aggiungere contatti per l'helpdesk locale e la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0ae69-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="0ae69-138">I contatti di amministratore sono necessari quando [invii una richiesta di supporto](../service-description/support.md).</span><span class="sxs-lookup"><span data-stu-id="0ae69-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="0ae69-139">Dovrai avere un contatto amministratore per l'area di interesse della richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="0ae69-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="0ae69-140">**Per aggiungere contatti di amministratore**</span><span class="sxs-lookup"><span data-stu-id="0ae69-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="0ae69-141">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="0ae69-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="0ae69-142">In **Supporto** selezionare **Contatti di amministrazione.**</span><span class="sxs-lookup"><span data-stu-id="0ae69-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menu Supporto, Contatti di amministratore nella parte superiore selezionata](../../media/admincontacts.png)

3. <span data-ttu-id="0ae69-144">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0ae69-144">Select **Add**.</span></span>

    ![Portale di amministrazione, pulsante Aggiungi, a sinistra di Esporta e aggiorna](../../media/adminadd.png)

4.  <span data-ttu-id="0ae69-146">Seleziona **un'area di stato attivo** e immetti le informazioni per il contatto.</span><span class="sxs-lookup"><span data-stu-id="0ae69-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![l'elenco delle aree di interesse, ad esempio Altre, App e Sicurezza](../../media/areaoffocus.png)

5. <span data-ttu-id="0ae69-148">Ripetere l'operazione per ogni area dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="0ae69-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="0ae69-149">Passaggi per iniziare a usare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0ae69-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="0ae69-150">Aggiungere e verificare i contatti di amministratore nel portale di amministrazione (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="0ae69-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="0ae69-151">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="0ae69-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="0ae69-152">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="0ae69-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="0ae69-153">Installare il portale aziendale di Intune sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="0ae69-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="0ae69-154">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="0ae69-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="0ae69-155">Configurare dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0ae69-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="0ae69-156">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="0ae69-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="0ae69-157">Distribuire le app sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="0ae69-157">Deploy apps to devices</span></span>](deploy-apps.md)