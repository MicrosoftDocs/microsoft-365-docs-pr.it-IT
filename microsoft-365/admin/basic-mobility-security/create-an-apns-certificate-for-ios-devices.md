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
description: Gestire i dispositivi iOS in Dispositivi mobili e sicurezza di base.
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228244"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="ad29e-103">Creare un certificato APNs per i dispositivi iOS</span><span class="sxs-lookup"><span data-stu-id="ad29e-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="ad29e-104">Per gestire dispositivi iOS come iPad e iPhone in Dispositivi mobili e sicurezza di base, crea un certificato APNs.</span><span class="sxs-lookup"><span data-stu-id="ad29e-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="ad29e-105">Accedi a Microsoft 365 con il tuo account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="ad29e-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="ad29e-106">Nel browser digitare  <https://protection.office.com/> .</span><span class="sxs-lookup"><span data-stu-id="ad29e-106">In your browser, type <https://protection.office.com/>.</span></span>

3. <span data-ttu-id="ad29e-107">Seleziona  **Prevenzione della perdita dei dati** Gestione   >  **dei** dispositivi e scegli Certificato **APNs per i dispositivi iOS.**</span><span class="sxs-lookup"><span data-stu-id="ad29e-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="ad29e-108">Nella pagina Apple Push Notification Certificate Impostazioni scegliere **Next**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="ad29e-109">Selezionare Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span><span class="sxs-lookup"><span data-stu-id="ad29e-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="ad29e-110">Selezionare  **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-110">Select  **Next**.</span></span>

6. <span data-ttu-id="ad29e-111">Nella pagina Crea un certificato APNs:</span><span class="sxs-lookup"><span data-stu-id="ad29e-111">On the Create an APNs certificate page:</span></span>

    1. <span data-ttu-id="ad29e-112">Seleziona Apple APNS Portal per aprire il portale dei certificati Push Apple.</span><span class="sxs-lookup"><span data-stu-id="ad29e-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="ad29e-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="ad29e-113">Sign in with an Apple ID.</span></span>

       > [!IMPORTANT]
       > <span data-ttu-id="ad29e-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="ad29e-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="ad29e-116">Selezionare  **Crea un certificato** e accettare le Condizioni per   l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="ad29e-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="ad29e-117">Passare alla richiesta di firma del certificato scaricata nel computer da Microsoft 365 e selezionare **Upload**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

       <span data-ttu-id="ad29e-118">Scarica il certificato APNs creato dal portale dei certificati Push Apple nel computer.</span><span class="sxs-lookup"><span data-stu-id="ad29e-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       > [!TIP]
       > <span data-ttu-id="ad29e-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="ad29e-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="ad29e-120">Torna a Microsoft 365 e seleziona **Avanti** per accedere alla pagina Upload     **certificato APNS.**  </span><span class="sxs-lookup"><span data-stu-id="ad29e-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="ad29e-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="ad29e-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="ad29e-122">Selezionare  **Fine.**</span><span class="sxs-lookup"><span data-stu-id="ad29e-122">Select  **Finish**.</span></span>

<span data-ttu-id="ad29e-123">Per completare la configurazione, tornare al Centro sicurezza & conformità > **Criteri** di sicurezza   >  **Gestione dispositivi**   >  **Gestisci impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="ad29e-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
