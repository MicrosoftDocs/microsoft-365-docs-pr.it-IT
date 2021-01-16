---
title: Gestire le impostazioni di accesso ai dispositivi in mobilità e sicurezza di base
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: La sicurezza e la mobilità di base consentono di proteggere e gestire i dispositivi mobili.
ms.openlocfilehash: dd9d777798c2c96776a8f9b40a3c4dfe0b95702a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876949"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a><span data-ttu-id="50bb9-103">Gestire le impostazioni di accesso ai dispositivi in mobilità e sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="50bb9-103">Manage device access settings in Basic Mobility and Security</span></span>

<span data-ttu-id="50bb9-104">Se si utilizza la sicurezza e la mobilità di base, è possibile che i dispositivi non siano in grado di gestire la mobilità e la sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="50bb9-104">If you're using Basic Mobility and Security, there might be devices that you can't manage with Basic Mobility and Security.</span></span> <span data-ttu-id="50bb9-105">In caso affermativo, è consigliabile bloccare l'accesso alle app di Exchange ActiveSync a Microsoft 365 per i dispositivi mobili che non sono supportati da mobilità e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="50bb9-105">If so, you should block Exchange ActiveSync app access to Microsoft 365 email for mobile devices that aren't supported by Basic Mobility and Security.</span></span> <span data-ttu-id="50bb9-106">Questo consente di proteggere le informazioni dell'organizzazione su più dispositivi.</span><span class="sxs-lookup"><span data-stu-id="50bb9-106">This helps secure your organization information across more devices.</span></span>

<span data-ttu-id="50bb9-107">Attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="50bb9-107">Use these steps:</span></span>

1. <span data-ttu-id="50bb9-108">Accedere a Microsoft 365 con l'account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="50bb9-108">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="50bb9-109">Nel browser, digitare:  [https://protection.office.com](https://protection.office.com/) .</span><span class="sxs-lookup"><span data-stu-id="50bb9-109">In your browser, type: [https://protection.office.com](https://protection.office.com/).</span></span>    

    >[!IMPORTANT]
    ><span data-ttu-id="50bb9-110">Se è la prima volta che si utilizza la sicurezza e la mobilità di base per Microsoft 365 business standard, attivarlo qui: [attivare la sicurezza e la mobilità di base](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span><span class="sxs-lookup"><span data-stu-id="50bb9-110">If this is the first time you're using Basic Mobility and Security for Microsoft 365 Business Standard, activate it here: [Activate Basic Security and Mobility](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="50bb9-111">Dopo averlo attivato, gestire i dispositivi con [Office 365 Security & Compliance](https://protection.office.com/).</span><span class="sxs-lookup"><span data-stu-id="50bb9-111">After you've activated it, manage your devices with [Office 365 Security & Compliance](https://protection.office.com/).</span></span>

3. <span data-ttu-id="50bb9-112">Passare a prevenzione della perdita di dati >i criteri per i dispositivi di  **gestione** dei dispositivi   >  \*\*\*\* e selezionare **Gestisci impostazioni di accesso ai dispositivi a livello dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="50bb9-112">Go to Data loss prevention > **Device management** > **Device policies**, and select **Manage organization-wide device access settings**.</span></span>

4. <span data-ttu-id="50bb9-113">Selezionare **blocca**.</span><span class="sxs-lookup"><span data-stu-id="50bb9-113">Select **Block**.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Casella di controllo accesso ai blocchi di sicurezza e mobilità di base":::

5. <span data-ttu-id="50bb9-115">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="50bb9-115">Select **Save**.</span></span>

<span data-ttu-id="50bb9-116">Per sapere quali dispositivi supportano la sicurezza e la mobilità di base, vedere [funzionalità di base per la sicurezza e la mobilità](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="50bb9-116">To learn what devices Basic Mobility and Security supports, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>