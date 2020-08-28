---
title: Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione
description: Indicare gli utenti che devono contattare per ogni area di interesse.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
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
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="7fa85-104">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="7fa85-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="7fa85-105">Esistono diversi modi in cui il servizio Microsoft Managed Desktop comunica con i clienti.</span><span class="sxs-lookup"><span data-stu-id="7fa85-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="7fa85-106">Per semplificare la comunicazione e verificare che il controllo venga effettuato con gli utenti giusti, è necessario fornire un set di contatti di amministratore.</span><span class="sxs-lookup"><span data-stu-id="7fa85-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="7fa85-107">Microsoft Managed Desktop IT Operations contatterà queste persone per risolvere i problemi di assistenza per il tenant.</span><span class="sxs-lookup"><span data-stu-id="7fa85-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fa85-108">Potrebbe essere già stato aggiunto questi contatti nel portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="7fa85-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="7fa85-109">In caso affermativo, prendere un momento per verificare che l'elenco dei contatti sia accurato, in quanto Microsoft Managed Desktop **deve** essere in grado di raggiungerli se si verifica un grave incidente.</span><span class="sxs-lookup"><span data-stu-id="7fa85-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="7fa85-110">Azure Active Directory Access per il portale di amministrazione di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="7fa85-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="7fa85-111">Il portale di amministrazione di Microsoft Managed Desktop richiede che gli utenti che accedono al portale dispongano di uno di questi ruoli di Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="7fa85-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="7fa85-112">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="7fa85-112">Global Administrator</span></span>
- <span data-ttu-id="7fa85-113">Amministratore del servizio Intune</span><span class="sxs-lookup"><span data-stu-id="7fa85-113">Intune Service Administrator</span></span>
- <span data-ttu-id="7fa85-114">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="7fa85-114">Global Reader</span></span>
- <span data-ttu-id="7fa85-115">Amministratore del supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="7fa85-115">Service Support Administrator</span></span>

<span data-ttu-id="7fa85-116">È necessario che l'amministratore globale sia quello che deve registrare la propria organizzazione in Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="7fa85-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="7fa85-117">Tutti e cinque i ruoli dispongono dello stesso accesso all'interno del portale di amministrazione per avviare e visualizzare le attività.</span><span class="sxs-lookup"><span data-stu-id="7fa85-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="7fa85-118">Per ulteriori informazioni sull'assegnazione di questi ruoli in Azure AD, vedere [autorizzazioni per il ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="7fa85-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="7fa85-119">Aree di contatto di amministrazione dello stato attivo</span><span class="sxs-lookup"><span data-stu-id="7fa85-119">Admin contact areas of focus</span></span>

<span data-ttu-id="7fa85-120">I contatti amministrativi devono essere la persona o il gruppo migliore in grado di rispondere alle domande e prendere decisioni per diverse aree di interesse.</span><span class="sxs-lookup"><span data-stu-id="7fa85-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="7fa85-121">**Microsoft Managed Desktop Operations contatterà questi contatti di amministrazione per le domande relative alle richieste di supporto presentate dal cliente.**</span><span class="sxs-lookup"><span data-stu-id="7fa85-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="7fa85-122">Questi contatti di amministratore ricevono notifiche per gli aggiornamenti delle richieste di supporto e i nuovi messaggi.</span><span class="sxs-lookup"><span data-stu-id="7fa85-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="7fa85-123">Tra queste aree sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fa85-123">These areas include:</span></span>

<span data-ttu-id="7fa85-124">Area di interesse</span><span class="sxs-lookup"><span data-stu-id="7fa85-124">Area of focus</span></span> | <span data-ttu-id="7fa85-125">Per domande su</span><span class="sxs-lookup"><span data-stu-id="7fa85-125">For questions about</span></span>
--- | ---
<span data-ttu-id="7fa85-126">Pacchetti app</span><span class="sxs-lookup"><span data-stu-id="7fa85-126">App packaging</span></span> | <span data-ttu-id="7fa85-127">Risoluzione dei problemi relativi agli imballaggi delle app</span><span class="sxs-lookup"><span data-stu-id="7fa85-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="7fa85-128">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="7fa85-128">Devices</span></span> | <span data-ttu-id="7fa85-129">Integrità del dispositivo, risoluzione dei problemi con i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="7fa85-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="7fa85-130">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7fa85-130">Security</span></span> | <span data-ttu-id="7fa85-131">Risoluzione dei problemi di sicurezza con i dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="7fa85-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="7fa85-132">Supporto tecnico IT</span><span class="sxs-lookup"><span data-stu-id="7fa85-132">IT help desk</span></span> | <span data-ttu-id="7fa85-133">nei casi in cui il personale di supporto passa sopra i ticket degli utenti al di fuori delle aree di supporto di Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="7fa85-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="7fa85-134">Altro</span><span class="sxs-lookup"><span data-stu-id="7fa85-134">Other</span></span> | <span data-ttu-id="7fa85-135">Per i problemi non coperti da altre aree</span><span class="sxs-lookup"><span data-stu-id="7fa85-135">For issues not covered by other areas</span></span>

<span data-ttu-id="7fa85-136">**Chiunque sia scelto per questi contatti deve avere le conoscenze e l'autorità necessarie per prendere decisioni per l'ambiente desktop Microsoft gestito.**</span><span class="sxs-lookup"><span data-stu-id="7fa85-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="7fa85-137">Quando si esegue l'onboarding dell'ambiente Microsoft Managed Desktop, viene richiesto di aggiungere contatti per il supporto tecnico e la sicurezza locali.</span><span class="sxs-lookup"><span data-stu-id="7fa85-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="7fa85-138">I contatti amministrativi sono necessari quando si [Invia una richiesta di supporto](../service-description/support.md).</span><span class="sxs-lookup"><span data-stu-id="7fa85-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="7fa85-139">È necessario disporre di un contatto di amministrazione per l'area dello stato attivo della richiesta di supporto.</span><span class="sxs-lookup"><span data-stu-id="7fa85-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="7fa85-140">**Per aggiungere contatti di amministratore**</span><span class="sxs-lookup"><span data-stu-id="7fa85-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="7fa85-141">Accedere al [portale di amministrazione di Microsoft Managed Desktop](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="7fa85-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="7fa85-142">In **supporto**, selezionare **contatti di amministratore**.</span><span class="sxs-lookup"><span data-stu-id="7fa85-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menu di supporto, contatti amministrativi vicino alla parte superiore selezionata](../../media/admincontacts.png)

3. <span data-ttu-id="7fa85-144">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7fa85-144">Select **Add**.</span></span>

    ![Portale di amministrazione, pulsante Aggiungi, a sinistra di esportazione e aggiornamento](../../media/adminadd.png)

4.  <span data-ttu-id="7fa85-146">Selezionare un' **area di messa a fuoco** e immettere le informazioni per il contatto.</span><span class="sxs-lookup"><span data-stu-id="7fa85-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![elenco delle aree di interesse, ad esempio altre, app e sicurezza](../../media/areaoffocus.png)

5. <span data-ttu-id="7fa85-148">Ripetere l'attività per ogni area di interesse.</span><span class="sxs-lookup"><span data-stu-id="7fa85-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="7fa85-149">Passaggi per iniziare a utilizzare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="7fa85-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="7fa85-150">Aggiungere e verificare i contatti di amministratore nel portale di amministrazione (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="7fa85-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="7fa85-151">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="7fa85-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="7fa85-152">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="7fa85-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="7fa85-153">Installare il portale aziendale di Intune sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="7fa85-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="7fa85-154">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="7fa85-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="7fa85-155">Configurare dispositivi Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="7fa85-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="7fa85-156">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="7fa85-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="7fa85-157">Distribuire le app sui dispositivi</span><span class="sxs-lookup"><span data-stu-id="7fa85-157">Deploy apps to devices</span></span>](deploy-apps.md)
