---
title: Passaggio 5 - Cancellare e bloccare il dispositivo mobile di un ex dipendente
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Segui questa procedura per bloccare l'accesso al dispositivo mobile di un ex dipendente.
ms.openlocfilehash: 1ce12b06b6a0a74615ff8ac43b8f333456a469bb
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244240"
---
# <a name="step-5---wipe-and-block-a-former-employees-mobile-device"></a><span data-ttu-id="9a133-103">Passaggio 5 - Cancellare e bloccare il dispositivo mobile di un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="9a133-103">Step 5 - Wipe and block a former employee's mobile device</span></span>

<span data-ttu-id="9a133-104">Se l'ex dipendente aveva un telefono dell'organizzazione, puoi usare l'interfaccia di amministrazione di Exchange per cancellare e bloccare il dispositivo in modo che tutti i dati dell'organizzazione siano rimossi dal dispositivo e non possano più connettersi a Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a133-104">If your former employee had an organization phone, you can use the Exchange admin center to wipe and block that device so that all organization data is removed from the device and it can no longer connect to Office 365.</span></span> <span data-ttu-id="9a133-105">Se l'organizzazione usa Dispositivi mobili e sicurezza di base per gestire i dispositivi mobili, è possibile cancellare e bloccare tali dispositivi tramite Dispositivi mobili e sicurezza di base.</span><span class="sxs-lookup"><span data-stu-id="9a133-105">If your organization uses Basic Mobility and Security to manage mobile devices, you can wipe and block those devices using Basic Mobility and Security.</span></span>

## <a name="wipe-mobile-device-using-the-exchange-admin-center"></a><span data-ttu-id="9a133-106">Cancellare il dispositivo mobile con l'Exchange di amministrazione</span><span class="sxs-lookup"><span data-stu-id="9a133-106">Wipe mobile device using the Exchange admin center</span></span>

1. <span data-ttu-id="9a133-107">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="9a133-107">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="9a133-108">Nell'Interfaccia di amministrazione di Exchange passare a **Destinatari** \> **Cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="9a133-108">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="9a133-109">Selezionare l'utente e in **Dispositivi mobili** selezionare **Visualizza dettagli.**</span><span class="sxs-lookup"><span data-stu-id="9a133-109">Select the user, and under **Mobile Devices**, select **View details**.</span></span>
4. <span data-ttu-id="9a133-110">Nella pagina **Dettagli dispositivo** mobile, in **Dispositivi mobili,** selezionare il dispositivo mobile, selezionare **Cancella** dati cancella dispositivo e quindi ![ selezionare ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **Blocca.**</span><span class="sxs-lookup"><span data-stu-id="9a133-110">On the **Mobile Device Details** page, under **Mobile devices**, select the mobile device, select **Wipe Data**![Wipe Device](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png), and then select **Block**.</span></span>
5. <span data-ttu-id="9a133-111">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9a133-111">Select **Save**.</span></span>
   > [!TIP]
   > <span data-ttu-id="9a133-112">Assicurarsi di rimuovere o disabilitare l'utente dal servizio blackberry Enterprise locale.</span><span class="sxs-lookup"><span data-stu-id="9a133-112">Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service.</span></span> <span data-ttu-id="9a133-113">Occorre anche disabilitare gli eventuali dispositivi Blackberry per l'utente.</span><span class="sxs-lookup"><span data-stu-id="9a133-113">You should also disable any Blackberry devices for the user.</span></span> <span data-ttu-id="9a133-114">Per informazioni sui passaggi specifici da eseguire per disabilitare l'utente, vedere la guida all'amministrazione di Blackberry Business Cloud Services.</span><span class="sxs-lookup"><span data-stu-id="9a133-114">Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user.</span></span>
