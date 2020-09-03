---
title: Creare un certificato APNs per i dispositivi iOS
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
description: Gestire i dispositivi iOS in mobilità e sicurezza di base.
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336947"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="07978-103">Creare un certificato APNs per i dispositivi iOS</span><span class="sxs-lookup"><span data-stu-id="07978-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="07978-104">Per gestire i dispositivi iOS, come iPads e iPhone, in mobilità e sicurezza di base, creare un certificato di APNs.</span><span class="sxs-lookup"><span data-stu-id="07978-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="07978-105">Accedere a Microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="07978-105">Sign in to Microsoft 365 with your global admin account.</span></span>
    
2. <span data-ttu-id="07978-106">Nel browser digitare  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="07978-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>
    
3. <span data-ttu-id="07978-107">Selezionare Gestione dei dispositivi per la prevenzione della perdita di  **dati**   >  **Device management**e scegliere **APNs certificate for iOS Devices**.</span><span class="sxs-lookup"><span data-stu-id="07978-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>    

4. <span data-ttu-id="07978-108">Nella pagina impostazioni del certificato di notifica push di Apple scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="07978-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>
    
5. <span data-ttu-id="07978-109">Selezionare Scarica il file CSR e salvare la richiesta di firma del certificato in un punto qualsiasi del computer da ricordare.</span><span class="sxs-lookup"><span data-stu-id="07978-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="07978-110">Selezionare  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="07978-110">Select  **Next**.</span></span>
    
6. <span data-ttu-id="07978-111">Nella pagina Create an APNs certificate:</span><span class="sxs-lookup"><span data-stu-id="07978-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="07978-112">Selezionare il portale Apple APNS per aprire il portale Apple Push Certificates.</span><span class="sxs-lookup"><span data-stu-id="07978-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
    
    2. <span data-ttu-id="07978-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="07978-113">Sign in with an Apple ID.</span></span>   

    >[!IMPORTANT]
    ><span data-ttu-id="07978-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="07978-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="07978-116">Selezionare  **Create a certificate**   e accettate le condizioni per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="07978-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>
    
    4. <span data-ttu-id="07978-117">Passare alla richiesta di firma del certificato scaricata nel computer da Microsoft 365 e selezionare **carica**.</span><span class="sxs-lookup"><span data-stu-id="07978-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>
    
        <span data-ttu-id="07978-118">Scaricare il certificato APNs creato dal portale Apple Push certificate nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="07978-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>
    
       >[!TIP]
       ><span data-ttu-id="07978-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="07978-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="07978-120">Tornare a Microsoft 365 e fare clic su **Avanti**   per accedere alla pagina  **carica APNs certificate**   .</span><span class="sxs-lookup"><span data-stu-id="07978-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>
    
8. <span data-ttu-id="07978-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="07978-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
9. <span data-ttu-id="07978-122">Selezionare  **fine**.</span><span class="sxs-lookup"><span data-stu-id="07978-122">Select  **Finish**.</span></span>
    
<span data-ttu-id="07978-123">Per completare l'installazione, tornare al centro sicurezza & Compliance > **criteri di sicurezza**   >  **Gestione dispositivi**   >  **gestire le impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="07978-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
