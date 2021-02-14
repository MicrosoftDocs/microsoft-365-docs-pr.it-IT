---
title: Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione
description: Indicare chi contattare per ogni area di interesse.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289262"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="d1e71-104">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="d1e71-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="d1e71-105">Esistono diversi modi in cui il servizio Microsoft Managed Desktop comunica con i clienti.</span><span class="sxs-lookup"><span data-stu-id="d1e71-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="d1e71-106">Per semplificare la comunicazione e garantire che stiamo controllando con le persone giuste, è necessario fornire un set di contatti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="d1e71-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="d1e71-107">Microsoft Managed Desktop IT Operations contatta queste persone per assistenza nella risoluzione dei problemi relativi al tenant.</span><span class="sxs-lookup"><span data-stu-id="d1e71-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1e71-108">Questi contatti potrebbero essere già stati aggiunti nel portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d1e71-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="d1e71-109">In tal caso, verificare che l'elenco contatti sia accurato, perché Microsoft Managed **Desktop** deve essere in grado di contattarli in caso di grave incidente.</span><span class="sxs-lookup"><span data-stu-id="d1e71-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="d1e71-110">Accesso ad Azure Active Directory per il portale di amministrazione di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d1e71-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="d1e71-111">Il portale di amministrazione di Microsoft Managed Desktop richiede che gli utenti che accedono al portale dispongono di uno di questi ruoli di Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="d1e71-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="d1e71-112">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="d1e71-112">Global Administrator</span></span>
- <span data-ttu-id="d1e71-113">Amministratore del servizio Intune</span><span class="sxs-lookup"><span data-stu-id="d1e71-113">Intune Service Administrator</span></span>
- <span data-ttu-id="d1e71-114">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="d1e71-114">Global Reader</span></span>
- <span data-ttu-id="d1e71-115">Amministratore del supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="d1e71-115">Service Support Administrator</span></span>

<span data-ttu-id="d1e71-116">L'amministratore globale deve essere l'unico a registrare l'organizzazione in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="d1e71-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="d1e71-117">Tutti e cinque i ruoli hanno lo stesso accesso nel portale di amministrazione per avviare e visualizzare le attività.</span><span class="sxs-lookup"><span data-stu-id="d1e71-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="d1e71-118">Per altre informazioni sull'assegnazione di questi ruoli in Azure AD, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="d1e71-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="d1e71-119">Aree di contatto dell'amministratore incentrate</span><span class="sxs-lookup"><span data-stu-id="d1e71-119">Admin contact areas of focus</span></span>

<span data-ttu-id="d1e71-120">I contatti dell'amministratore devono essere la persona o il gruppo migliori in grado di rispondere alle domande e prendere decisioni per diverse aree di interesse.</span><span class="sxs-lookup"><span data-stu-id="d1e71-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="d1e71-121">**Microsoft Managed Desktop Operations contatta questi contatti dell'amministratore per le domande relative alle richieste di supporto inviate dal cliente.**</span><span class="sxs-lookup"><span data-stu-id="d1e71-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="d1e71-122">Questi contatti dell'amministratore riceveranno notifiche per gli aggiornamenti delle richieste di supporto e i nuovi messaggi.</span><span class="sxs-lookup"><span data-stu-id="d1e71-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="d1e71-123">Queste aree includono:</span><span class="sxs-lookup"><span data-stu-id="d1e71-123">These areas include:</span></span>

<span data-ttu-id="d1e71-124">Area di stato attivo</span><span class="sxs-lookup"><span data-stu-id="d1e71-124">Area of focus</span></span> | <span data-ttu-id="d1e71-125">Per domande su</span><span class="sxs-lookup"><span data-stu-id="d1e71-125">For questions about</span></span>
--- | ---
<span data-ttu-id="d1e71-126">Creazione di pacchetti dell'app</span><span class="sxs-lookup"><span data-stu-id="d1e71-126">App packaging</span></span> | <span data-ttu-id="d1e71-127">Risoluzione dei problemi di creazione di pacchetti di app</span><span class="sxs-lookup"><span data-stu-id="d1e71-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="d1e71-128">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="d1e71-128">Devices</span></span> | <span data-ttu-id="d1e71-129">Integrità dei dispositivi, risoluzione dei problemi con i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d1e71-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d1e71-130">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1e71-130">Security</span></span> | <span data-ttu-id="d1e71-131">Risoluzione dei problemi di sicurezza con i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d1e71-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d1e71-132">Help desk IT</span><span class="sxs-lookup"><span data-stu-id="d1e71-132">IT help desk</span></span> | <span data-ttu-id="d1e71-133">nei casi in cui il personale di supporto si conse tasser ticket utente al di fuori delle aree di supporto di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d1e71-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="d1e71-134">Altro</span><span class="sxs-lookup"><span data-stu-id="d1e71-134">Other</span></span> | <span data-ttu-id="d1e71-135">Per problemi non coperti da altre aree</span><span class="sxs-lookup"><span data-stu-id="d1e71-135">For issues not covered by other areas</span></span>

<span data-ttu-id="d1e71-136">**Chiunque scegli per questi contatti deve avere le conoscenze e l'autorità necessarie per prendere decisioni per il tuo ambiente Microsoft Managed Desktop.**</span><span class="sxs-lookup"><span data-stu-id="d1e71-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="d1e71-137">Quando si esegue l'onboarded dell'ambiente Microsoft Managed Desktop, viene richiesto di aggiungere contatti per l'helpdesk locale e la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d1e71-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="d1e71-138">I contatti dell'amministratore sono necessari quando [invii una richiesta di supporto.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="d1e71-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="d1e71-139">Dovrai avere un contatto amministratore per l'area di interesse della richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="d1e71-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="d1e71-140">**Per aggiungere contatti di amministrazione**</span><span class="sxs-lookup"><span data-stu-id="d1e71-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="d1e71-141">Accedere al portale [di amministrazione di Microsoft Managed Desktop.](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d1e71-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="d1e71-142">In **Supporto** selezionare **Contatti amministratore.**</span><span class="sxs-lookup"><span data-stu-id="d1e71-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menu Supporto, contatti dell'amministratore nella parte superiore selezionata](../../media/admincontacts.png)

3. <span data-ttu-id="d1e71-144">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d1e71-144">Select **Add**.</span></span>

    ![Portale di amministrazione, pulsante Aggiungi, a sinistra di Esporta e aggiorna](../../media/adminadd.png)

4.  <span data-ttu-id="d1e71-146">Seleziona **un'area di interesse** e immetti le informazioni per il contatto.</span><span class="sxs-lookup"><span data-stu-id="d1e71-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![l'elenco delle aree di interesse, ad esempio Altri, App e Sicurezza](../../media/areaoffocus.png)

5. <span data-ttu-id="d1e71-148">Ripetere l'operazione per ogni area dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="d1e71-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="d1e71-149">Procedura per iniziare a usare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d1e71-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="d1e71-150">Aggiungere e verificare i contatti dell'amministratore nel portale di amministrazione (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="d1e71-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="d1e71-151">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="d1e71-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="d1e71-152">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="d1e71-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="d1e71-153">Installare il portale aziendale di Intune sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="d1e71-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="d1e71-154">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="d1e71-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="d1e71-155">Configurare dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d1e71-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="d1e71-156">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="d1e71-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="d1e71-157">Distribuire le app sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="d1e71-157">Deploy apps to devices</span></span>](deploy-apps.md)
