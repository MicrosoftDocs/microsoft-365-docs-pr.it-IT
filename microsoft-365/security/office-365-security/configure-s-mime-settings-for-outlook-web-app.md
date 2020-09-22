---
title: Configurare le impostazioni S/MIME-Exchange Online per Outlook sul Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Una breve descrizione di cosa devono fare gli amministratori di Exchange Online per visualizzare e configurare le impostazioni S/MIME in Outlook sul Web in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe561c3a66cf2e7bdb76aabe10ffc875d85f2d77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203336"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="d4392-103">Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="d4392-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d4392-104">In qualità di amministratore di Exchange Online, è possibile configurare Outlook sul Web (in precedenza noto come Outlook Web App) per consentire l'invio e la ricezione di messaggi protetti con S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d4392-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="d4392-105">Utilizzare i cmdlet **Get-SmimeConfig** e **set-SmimeConfig** per visualizzare e gestire questa funzionalità in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d4392-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="d4392-106">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4392-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="d4392-107">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) e [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="d4392-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="d4392-108">Considerazioni per il nuovo Edge Microsoft (basato sul cromo)</span><span class="sxs-lookup"><span data-stu-id="d4392-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="d4392-109">Per utilizzare S/MIME in Outlook sul Web nel nuovo Web browser [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , l'utente (o un altro amministratore) deve impostare e configurare il criterio del browser Microsoft Edge denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME nel nuovo Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="d4392-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="d4392-110">Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="d4392-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d4392-111">Si noti che l'applicazione di questo criterio richiede l'aggiunta di un dominio o di un dispositivo di Azure AD-join, in modo che l'utilizzo di S/MIME nel nuovo browser Microsoft Edge richieda effettivamente i dispositivi associati a un dominio o di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d4392-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="d4392-112">Per informazioni dettagliate sul criterio **ExtensionInstallForcelist** , vedere [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="d4392-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="d4392-113">Questo passaggio è un prerequisito per l'utilizzo di nuovo Microsoft Edge. non sostituisce il controllo S/MIME installato dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="d4392-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d4392-114">Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d4392-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d4392-115">In alternativa, gli utenti possono accedere in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.</span><span class="sxs-lookup"><span data-stu-id="d4392-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="d4392-116">Considerazioni su Chrome</span><span class="sxs-lookup"><span data-stu-id="d4392-116">Considerations for Chrome</span></span>

<span data-ttu-id="d4392-117">Per utilizzare S/MIME in Outlook sul Web nel browser Web di Google Chrome, è necessario che l'utente (o un altro amministratore) debba impostare e configurare il criterio di cromo denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME in Chrome.</span><span class="sxs-lookup"><span data-stu-id="d4392-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="d4392-118">Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="d4392-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d4392-119">Si noti che l'applicazione di questo criterio richiede i computer aggiunti a un dominio, in modo che l'utilizzo di S/MIME in Chrome richiede effettivamente i computer aggiunti a un dominio.</span><span class="sxs-lookup"><span data-stu-id="d4392-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="d4392-120">Per informazioni dettagliate sul criterio **ExtensionInstallForcelist** , vedere [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="d4392-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="d4392-121">Questo passaggio è un prerequisito per l'utilizzo di Chrome. non sostituisce il controllo S/MIME installato dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="d4392-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d4392-122">Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d4392-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d4392-123">In alternativa, gli utenti possono accedere in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.</span><span class="sxs-lookup"><span data-stu-id="d4392-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d4392-124">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d4392-124">For more information</span></span>

[<span data-ttu-id="d4392-125">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d4392-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
