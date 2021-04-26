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
description: Rimuovere gruppi o criteri per disattivare Dispositivi mobili e sicurezza di base.
ms.openlocfilehash: 1d81aed01193fb2ba821ebc055958ac6cd8ac382
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023870"
---
# <a name="turn-off-basic-mobility-and-security"></a><span data-ttu-id="8d059-103">Disabilitare Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="8d059-103">Turn off Basic Mobility and Security</span></span>

<span data-ttu-id="8d059-104">Per disattivare in modo efficace Dispositivi mobili e sicurezza di base, rimuovi i gruppi di persone definiti dai gruppi di sicurezza dai criteri di gestione dei dispositivi o rimuovi i criteri stessi.</span><span class="sxs-lookup"><span data-stu-id="8d059-104">To effectively turn off Basic Mobility and Security, you remove groups of people defined by security groups from the device management policies, or remove the policies themselves.</span></span>

- <span data-ttu-id="8d059-105">Rimuovi gruppi di utenti rimuovendo i gruppi di sicurezza degli utenti dai criteri del dispositivo che hai creato.</span><span class="sxs-lookup"><span data-stu-id="8d059-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span>

- <span data-ttu-id="8d059-106">Disabilita Dispositivi mobili e sicurezza di base per tutti rimuovendo tutti i criteri di dispositivi mobili e di sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="8d059-106">Disable Basic Mobility and Security for everyone by removing all Basic Mobility and Security device policies.</span></span>

<span data-ttu-id="8d059-107">Queste opzioni rimuovono l'applicazione di sicurezza e mobilità di base per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d059-107">These options remove Basic Mobility and Security enforcement for devices in your organization.</span></span> <span data-ttu-id="8d059-108">Purtroppo, non puoi semplicemente "annullare il provisioning" di Base Mobility and Security dopo aver configurato il provisioning.</span><span class="sxs-lookup"><span data-stu-id="8d059-108">Unfortunately, you can't simply "unprovision" Basic Mobility and Security after you've set it up.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="8d059-109">Tenere presente l'impatto sui dispositivi degli utenti quando si rimuovono i gruppi di sicurezza degli utenti dai criteri o si rimuovono i criteri stessi.</span><span class="sxs-lookup"><span data-stu-id="8d059-109">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves.</span></span> <span data-ttu-id="8d059-110">Ad esempio, i profili di posta elettronica e i messaggi di posta elettronica memorizzati nella cache potrebbero essere rimossi, a seconda del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8d059-110">For example, email profiles and cached emails might be removed, depending on the device.</span></span> <span data-ttu-id="8d059-111">Per altre info, vedi  [Cosa succede quando elimini un criterio o rimuovi un utente dal criterio?](../../admin/basic-mobility-security/create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8d059-111">For more info, see  [What happens when you delete a policy or remove a user from the policy?](../../admin/basic-mobility-security/create-device-security-policies.md)</span></span>

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a><span data-ttu-id="8d059-112">Rimuovere i gruppi di sicurezza degli utenti dai criteri dei dispositivi mobili e di sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="8d059-112">Remove user security groups from Basic Mobility and Security device policies</span></span>

1. <span data-ttu-id="8d059-113">Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="8d059-113">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span>

2. <span data-ttu-id="8d059-114">Seleziona un criterio dispositivo e seleziona **Modifica criterio.**</span><span class="sxs-lookup"><span data-stu-id="8d059-114">Select a device policy, and select **Edit policy**.</span></span> 

3. <span data-ttu-id="8d059-115">Nella pagina  **Distribuzione**   selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="8d059-115">On the  **Deployment**  page, select **Remove**.</span></span>

4. <span data-ttu-id="8d059-116">In  **Gruppi** selezionare un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8d059-116">Under  **Groups**, select a security group.</span></span>

5. <span data-ttu-id="8d059-117">Selezionare  **Rimuovi** e quindi **Salva.**</span><span class="sxs-lookup"><span data-stu-id="8d059-117">Select  **Remove**, and select **Save**.</span></span>

## <a name="remove-basic-mobility-and-security-device-policies"></a><span data-ttu-id="8d059-118">Rimuovere i criteri dei dispositivi mobili e di sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="8d059-118">Remove Basic Mobility and Security device policies</span></span>

1.  <span data-ttu-id="8d059-119">Nel browser digitare:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .</span><span class="sxs-lookup"><span data-stu-id="8d059-119">In your browser type: [https://protection.office.com/devicev2](https://protection.office.com/devicev2).</span></span> 

2.  <span data-ttu-id="8d059-120">Seleziona un criterio dispositivo e quindi seleziona  **Elimina criterio.**</span><span class="sxs-lookup"><span data-stu-id="8d059-120">Select a device policy, and then select  **Delete policy**.</span></span>
    
3.  <span data-ttu-id="8d059-121">Nella finestra di dialogo Avviso selezionare **Sì.**</span><span class="sxs-lookup"><span data-stu-id="8d059-121">In the Warning dialog box, select **Yes**.</span></span>

>[!NOTE]
><span data-ttu-id="8d059-122">Per altri passaggi per sbloccare i dispositivi se i dispositivi dell'organizzazione sono ancora in uno stato bloccato, vedere il post di blog Rimozione del controllo di accesso da Gestione dispositivi mobili [per Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)</span><span class="sxs-lookup"><span data-stu-id="8d059-122">For more steps to unblock devices if your organization devices are still in a blocked state,  see the blog post [Removing Access Control from Mobile Device Management for Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).</span></span>
