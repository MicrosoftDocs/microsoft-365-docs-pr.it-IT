---
title: Disattiva mobilità e sicurezza di base
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
description: Rimuovere gruppi o criteri per disattivare la sicurezza e la mobilità di base.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336924"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="ef270-103">Disattiva mobilità e sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="ef270-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="ef270-104">Per disattivare in modo efficace la mobilità e la sicurezza di base, è possibile rimuovere i gruppi di persone definiti dai gruppi di sicurezza dai criteri di gestione dei dispositivi o rimuovere i criteri stessi.</span><span class="sxs-lookup"><span data-stu-id="ef270-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="ef270-105">Rimuovere gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri di dispositivo creati.</span><span class="sxs-lookup"><span data-stu-id="ef270-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>
    
- <span data-ttu-id="ef270-106">Disabilitare la sicurezza e la mobilità di base per tutti rimuovendo tutti i criteri di mobilità e dispositivi di sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="ef270-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>
    
<span data-ttu-id="ef270-107">Queste opzioni rimuovono la mobilità di base e l'applicazione della sicurezza per i dispositivi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ef270-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="ef270-108">Purtroppo, non è possibile semplicemente "annullare la provisioning" della mobilità e della sicurezza di base dopo averla configurata.</span><span class="sxs-lookup"><span data-stu-id="ef270-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="ef270-109">Tenere presente l'impatto sui dispositivi degli utenti quando si rimuovono i gruppi di sicurezza utente dai criteri o si rimuovono i criteri stessi.</span><span class="sxs-lookup"><span data-stu-id="ef270-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="ef270-110">Ad esempio, i profili e-mail e i messaggi di posta elettronica memorizzati nella cache potrebbero essere rimossi, a seconda del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ef270-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="ef270-111">Per altre informazioni, vedere  [cosa succede quando si elimina un criterio o si rimuove un utente dal criterio?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span><span class="sxs-lookup"><span data-stu-id="ef270-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="ef270-112">Rimuovere i gruppi di sicurezza degli utenti dai criteri di base per dispositivi mobili e di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ef270-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="ef270-113">Nel tipo di browser:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="ef270-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="ef270-114">Selezionare un criterio di dispositivo e selezionare **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="ef270-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="ef270-115">Nella pagina  **distribuzione**   selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="ef270-115">On the  **Deployment**  page, select **Remove**.</span></span>
    
4. <span data-ttu-id="ef270-116">In  **gruppi**selezionare un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ef270-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="ef270-117">Selezionare  **Rimuovi**e quindi **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ef270-117">Select  **Remove**, and select **Save**.</span></span>
    

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="ef270-118">Rimuovere i criteri di base per dispositivi mobili e di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ef270-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="ef270-119">Nel tipo di browser:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="ef270-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="ef270-120">Selezionare un criterio di dispositivo, quindi selezionare  **Elimina criterio**.</span><span class="sxs-lookup"><span data-stu-id="ef270-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="ef270-121">Nella finestra di dialogo di avviso selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ef270-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE] 
><span data-ttu-id="ef270-122">Per ulteriori passaggi per sbloccare i dispositivi se i dispositivi dell'organizzazione sono ancora bloccati, vedere il post di Blog che [rimuove il controllo di accesso dalla gestione dei dispositivi mobili per Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span><span class="sxs-lookup"><span data-stu-id="ef270-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
