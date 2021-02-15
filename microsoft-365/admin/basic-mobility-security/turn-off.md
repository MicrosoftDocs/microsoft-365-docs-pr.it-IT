---
title: Disabilitare Basic Mobility + Security
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Rimuovere gruppi o criteri per disattivare i dispositivi mobili e la sicurezza di base.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876841"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="8aa5c-103">Disabilitare Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="8aa5c-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="8aa5c-104">Per disattivare in modo efficace i criteri di sicurezza e mobilità di base, rimuovi i gruppi di persone definiti dai gruppi di sicurezza dai criteri di gestione dei dispositivi o rimuovi i criteri stessi.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="8aa5c-105">Rimuovere gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri di dispositivo creati.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="8aa5c-106">Disabilita dispositivi mobili e sicurezza di base per tutti rimuovendo tutti i criteri dei dispositivi di sicurezza e mobilità di base.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="8aa5c-107">Queste opzioni rimuovono l'applicazione di sicurezza e mobilità di base per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="8aa5c-108">Purtroppo, non è possibile semplicemente "annullare il provisioning" di Basic Mobility and Security dopo aver configurato il provisioning.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="8aa5c-109">Tenere presente l'impatto sui dispositivi degli utenti quando si rimuovono i gruppi di sicurezza degli utenti dai criteri o si rimuovono i criteri stessi.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="8aa5c-110">Ad esempio, i profili di posta elettronica e i messaggi di posta elettronica memorizzati nella cache potrebbero essere rimossi, a seconda del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="8aa5c-111">Per altre info, vedi  [Cosa succede quando si elimina un criterio o si rimuove un utente dal criterio?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="8aa5c-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="8aa5c-112">Rimuovere i gruppi di sicurezza degli utenti dai criteri dei dispositivi di sicurezza e mobilità di base</span><span class="sxs-lookup"><span data-stu-id="8aa5c-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="8aa5c-113">Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="8aa5c-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="8aa5c-114">Seleziona un criterio dispositivo e seleziona **Modifica criterio.**</span><span class="sxs-lookup"><span data-stu-id="8aa5c-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="8aa5c-115">Nella pagina  **Distribuzione**   selezionare **Rimuovi.**</span><span class="sxs-lookup"><span data-stu-id="8aa5c-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="8aa5c-116">In  **Gruppi** selezionare un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8aa5c-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="8aa5c-117">Selezionare  **Rimuovi** e quindi **Salva.**</span><span class="sxs-lookup"><span data-stu-id="8aa5c-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="8aa5c-118">Rimuovere i criteri dei dispositivi mobili e di sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="8aa5c-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="8aa5c-119">Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="8aa5c-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="8aa5c-120">Selezionare un criterio dispositivo e quindi selezionare  **Elimina criterio.**</span><span class="sxs-lookup"><span data-stu-id="8aa5c-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="8aa5c-121">Nella finestra di dialogo Avviso selezionare **Sì.**</span><span class="sxs-lookup"><span data-stu-id="8aa5c-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="8aa5c-122">Per altri passaggi per sbloccare i dispositivi se i dispositivi dell'organizzazione sono ancora in uno stato bloccato, vedere il post di blog Sulla rimozione del controllo di accesso da Gestione dispositivi mobili per [Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="8aa5c-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
