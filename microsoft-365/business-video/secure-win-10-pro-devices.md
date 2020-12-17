---
title: Gestire i criteri per i dispositivi Windows 10 Pro con Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come gestire i criteri per i dispositivi Windows 10 Pro con Microsoft 365 Business Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703194"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="7039b-103">Gestire i criteri per i dispositivi Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="7039b-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="7039b-104">È possibile utilizzare Microsoft 365 business per garantire che Windows Defender antivirus sia attivato nei dispositivi Windows 10 e che Microsoft Updates venga scaricato automaticamente nei dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7039b-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="7039b-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="7039b-105">Try it!</span></span>

1. <span data-ttu-id="7039b-106">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7039b-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="7039b-107">In **criteri** scegliere Aggiungi criterio.</span><span class="sxs-lookup"><span data-stu-id="7039b-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="7039b-108">Nel riquadro **Aggiungi criterio** , immettere un nome in **Nome criterio** e quindi selezionare **Configurazione dispositivo Windows 10** in tipo di **criterio**.</span><span class="sxs-lookup"><span data-stu-id="7039b-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="7039b-109">Scegliere **Secure Windows 10 Devices** per visualizzare le impostazioni secondarie.</span><span class="sxs-lookup"><span data-stu-id="7039b-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="7039b-110">Assicurarsi che la **protezione dei PC da virus e altre minacce tramite Windows Defender Antivirus** e che i **dispositivi Windows 10** siano aggiornati automaticamente siano attivati.</span><span class="sxs-lookup"><span data-stu-id="7039b-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="7039b-111">In **chi otterrà queste impostazioni?**, tutti gli utenti sono selezionati per impostazione predefinita, ma è possibile scegliere **Cambia** per selezionare i gruppi di sicurezza creati.</span><span class="sxs-lookup"><span data-stu-id="7039b-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="7039b-112">Per completare la creazione del criterio, scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7039b-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="7039b-113">Nella pagina **Aggiungi criterio** scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7039b-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="7039b-114">Nella Home page dell'interfaccia di amministrazione, verificare che il nuovo criterio sia stato aggiunto scegliendo **criteri** e rivedendo i criteri nella pagina **criteri** .</span><span class="sxs-lookup"><span data-stu-id="7039b-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="7039b-115">Per verificare che il criterio abbia avuto effetto, nel dispositivo Windows 10 di un utente passare a Windows Update, scegliere **Opzioni avanzate** e verificare che le impostazioni siano disabilitate.</span><span class="sxs-lookup"><span data-stu-id="7039b-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="7039b-116">Fare quindi clic su **Scegli la modalità** di recapito degli aggiornamenti e verificare che le impostazioni siano disabilitate e che venga visualizzato il messaggio seguente: **alcune impostazioni sono nascoste o gestite dall'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="7039b-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

