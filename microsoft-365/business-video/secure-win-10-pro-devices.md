---
title: Gestire i criteri dei dispositivi Windows 10 Pro con Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Scopri come gestire i criteri dei dispositivi Windows 10 Pro con Microsoft 365 Business Premium.
ms.openlocfilehash: 0f7cfff227e1ab4ea992414b513e341adbd9ef22
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578688"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="ff39f-103">Gestire i criteri dei dispositivi Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="ff39f-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="ff39f-104">Puoi usare Microsoft 365 Business per assicurarti che Windows Defender Antivirus sia attivato nei dispositivi Windows 10 e che gli aggiornamenti Microsoft siano scaricati automaticamente nei dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ff39f-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="ff39f-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="ff39f-105">Try it!</span></span>

1. <span data-ttu-id="ff39f-106">Accedere all'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff39f-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="ff39f-107">In **Criteri** scegliere Aggiungi criterio.</span><span class="sxs-lookup"><span data-stu-id="ff39f-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="ff39f-108">Nel riquadro **Aggiungi criterio** immetti un nome in **Nome** criterio e quindi seleziona Configurazione dispositivo **Windows 10** in **Tipo di criterio.**</span><span class="sxs-lookup"><span data-stu-id="ff39f-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="ff39f-109">Scegli **Proteggi i dispositivi Windows 10** per visualizzare le impostazioni secondarie.</span><span class="sxs-lookup"><span data-stu-id="ff39f-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="ff39f-110">Assicurati che La **protezione dei** PC da virus e altre minacce tramite Windows Defender Antivirus e Mantenere automaticamente aggiornati i dispositivi Windows **10** sia attivata.</span><span class="sxs-lookup"><span data-stu-id="ff39f-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="ff39f-111">In **Chi otterrà queste impostazioni?**, tutti gli utenti  sono selezionati per impostazione predefinita, ma è possibile scegliere Cambia per selezionare i gruppi di sicurezza creati.</span><span class="sxs-lookup"><span data-stu-id="ff39f-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="ff39f-112">Per completare la creazione del criterio, scegliere **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="ff39f-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="ff39f-113">Nella pagina **Aggiungi criterio** scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="ff39f-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="ff39f-114">Nella home page dell'interfaccia di amministrazione verificare  che il nuovo criterio sia stato aggiunto scegliendo Criteri ed esaminando i criteri nella **pagina** Criteri.</span><span class="sxs-lookup"><span data-stu-id="ff39f-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="ff39f-115">Per verificare che il criterio abbia effetto, nel dispositivo Windows 10 di un utente passare a Windows Update, scegliere **Opzioni** avanzate e verificare che le impostazioni siano disattivate.</span><span class="sxs-lookup"><span data-stu-id="ff39f-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="ff39f-116">Fare quindi clic **su Scegli** la modalità di recapito degli aggiornamenti e verificare che le impostazioni siano disattivate e che venga visualizzato il messaggio seguente: Alcune impostazioni sono nascoste o gestite **dall'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="ff39f-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

