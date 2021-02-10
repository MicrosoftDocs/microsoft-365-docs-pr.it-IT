---
title: Configurare le impostazioni S/MIME - Exchange Online per Outlook sul Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descrizione delle attività che gli amministratori di Exchange Online devono eseguire per visualizzare e configurare le impostazioni S/MIME in Outlook sul Web in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165680"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="74a5c-103">Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="74a5c-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="74a5c-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="74a5c-104">**Applies to**</span></span>
- [<span data-ttu-id="74a5c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="74a5c-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="74a5c-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="74a5c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="74a5c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74a5c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="74a5c-108">Gli amministratori di Exchange Online possono configurare Outlook sul Web (in precedenza noto come Outlook Web App) per consentire l'invio e la ricezione di messaggi protetti con S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74a5c-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="74a5c-109">Utilizzare i cmdlet **Get-SmimeConfig** e **Set-SmimeConfig** per visualizzare e gestire questa funzionalità in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="74a5c-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="74a5c-110">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="74a5c-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="74a5c-111">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) e [Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="74a5c-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="74a5c-112">Considerazioni sul nuovo Microsoft Edge (basato su Chromium)</span><span class="sxs-lookup"><span data-stu-id="74a5c-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="74a5c-113">Per utilizzare S/MIME in Outlook sul Web nel nuovo Web browser [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) è necessario impostare e configurare il criterio del browser Microsoft Edge denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME nel nuovo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="74a5c-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="74a5c-114">Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="74a5c-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="74a5c-115">Tieni presente che l'applicazione di questo criterio richiede dispositivi aggiunti a un dominio o ad Azure AD, quindi l'uso di S/MIME nel nuovo browser Microsoft Edge richiede in effetti dispositivi aggiunti a un dominio o aggiunti ad Azure AD.</span><span class="sxs-lookup"><span data-stu-id="74a5c-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="74a5c-116">Per informazioni dettagliate **sul criterio ExtensionInstallForcelist,** vedere [ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="74a5c-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="74a5c-117">Questo passaggio è un prerequisito per l'uso del nuovo Microsoft Edge; non sostituisce il controllo S/MIME installato dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="74a5c-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="74a5c-118">Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74a5c-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="74a5c-119">In alternativa, gli utenti possono passare in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.</span><span class="sxs-lookup"><span data-stu-id="74a5c-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="74a5c-120">Considerazioni per Chrome</span><span class="sxs-lookup"><span data-stu-id="74a5c-120">Considerations for Chrome</span></span>

<span data-ttu-id="74a5c-121">Per utilizzare S/MIME in Outlook sul Web nel Web browser Google Chrome, è necessario impostare e configurare il criterio Chromium denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME in Chrome.</span><span class="sxs-lookup"><span data-stu-id="74a5c-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="74a5c-122">Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="74a5c-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="74a5c-123">Si noti che l'applicazione di questo criterio richiede computer aggiunti a un dominio, quindi l'utilizzo di S/MIME in Chrome richiede in modo efficace computer aggiunti al dominio.</span><span class="sxs-lookup"><span data-stu-id="74a5c-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="74a5c-124">Per informazioni dettagliate **sul criterio ExtensionInstallForcelist,** vedere [ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="74a5c-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="74a5c-125">Questo passaggio è un prerequisito per l'utilizzo di Chrome; non sostituisce il controllo S/MIME installato dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="74a5c-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="74a5c-126">Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME.</span><span class="sxs-lookup"><span data-stu-id="74a5c-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="74a5c-127">In alternativa, gli utenti possono passare in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.</span><span class="sxs-lookup"><span data-stu-id="74a5c-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="74a5c-128">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="74a5c-128">For more information</span></span>

[<span data-ttu-id="74a5c-129">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="74a5c-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
