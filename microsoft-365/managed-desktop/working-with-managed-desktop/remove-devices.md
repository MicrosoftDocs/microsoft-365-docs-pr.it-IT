---
title: Rimuovere i dispositivi
description: Rimuovere i dispositivi dalla gestione di Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893814"
---
# <a name="remove-devices"></a><span data-ttu-id="8435d-103">Rimuovere i dispositivi</span><span class="sxs-lookup"><span data-stu-id="8435d-103">Remove devices</span></span>

<span data-ttu-id="8435d-104">Puoi rimuovere i dispositivi dalla gestione di Microsoft Managed Desktop usando il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="8435d-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="8435d-105">Questa azione è permanente, ma è possibile registrarle di nuovo con Microsoft Managed Desktop seguendo la procedura [di registrazione](../get-started/register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="8435d-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="8435d-106">Quando si rimuove un dispositivo, si verificano tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8435d-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="8435d-107">Rimuoviamo il dispositivo da Autopilot.</span><span class="sxs-lookup"><span data-stu-id="8435d-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="8435d-108">Rimuoviamo il dispositivo da tutti i gruppi di dispositivi "Ambiente di lavoro moderno".</span><span class="sxs-lookup"><span data-stu-id="8435d-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="8435d-109">Il dispositivo viene rimosso dal pannello **Dispositivi** nel portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="8435d-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="8435d-110">Quando si rimuove un dispositivo, è possibile rimuoverlo anche da Azure Active Directory (Azure AD) e Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="8435d-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="8435d-111">La rimozione degli oggetti correlati a un dispositivo da Azure AD e Microsoft Intune è permanente.</span><span class="sxs-lookup"><span data-stu-id="8435d-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="8435d-112">Se si rimuovono gli oggetti, non sarà possibile visualizzare o gestire i dispositivi dai portali di Intune e Azure.</span><span class="sxs-lookup"><span data-stu-id="8435d-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="8435d-113">I dispositivi non saranno in grado di accedere alle risorse aziendali dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="8435d-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="8435d-114">I dati aziendali potrebbero essere eliminati se i dispositivi tentano di accedere dopo l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="8435d-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="8435d-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)seleziona Dispositivi **nel** riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="8435d-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="8435d-116">Cerca la **sezione Microsoft Managed Desktop** del menu e seleziona **Dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="8435d-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="8435d-117">Nell'area di lavoro Dispositivi desktop gestiti Microsoft seleziona i dispositivi che vuoi eliminare.</span><span class="sxs-lookup"><span data-stu-id="8435d-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="8435d-118">Seleziona **Azioni dispositivo** e quindi seleziona Elimina **dispositivo** che apre un riquadro a comparsa per rimuovere i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8435d-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="8435d-119">Nel riquadro a comparsa, esamina i dispositivi selezionati e quindi seleziona **Rimuovi dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="8435d-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="8435d-120">Se si desidera rimuovere contemporaneamente anche gli oggetti azure AD e Intune, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="8435d-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="8435d-121">Il completamento della rimozione del dispositivo può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="8435d-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="8435d-122">Non è possibile rimuovere i dispositivi in uno stato di **registrazione** in sospeso.</span><span class="sxs-lookup"><span data-stu-id="8435d-122">You can't remove devices that are in a **pending** registration state.</span></span>