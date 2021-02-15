---
title: Aggiungere il dominio di Google Workspace
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come spostare il dominio da Google Workspace a Microsoft 365 per le aziende.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925003"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="91505-103">Aggiungere il dominio di Google Workspace a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91505-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="91505-104">Aggiungere il dominio di Google Workspace a Microsoft 365 per le aziende in modo da poter continuare a usare l'indirizzo di posta elettronica dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="91505-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="91505-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="91505-105">Try it!</span></span>

1. <span data-ttu-id="91505-106">Passare all'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="91505-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="91505-107">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, selezionare **Mostra tutto**, **Impostazioni** e quindi **Domini.**</span><span class="sxs-lookup"><span data-stu-id="91505-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="91505-108">Choose **Add domain**, enter your domain name then select Use this **domain.**</span><span class="sxs-lookup"><span data-stu-id="91505-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="91505-109">Choose, **Add a TXT record to the domains DNS records,** select **Continue**, and copy the TXT value.</span><span class="sxs-lookup"><span data-stu-id="91505-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="91505-110">Tornare alla Console di amministrazione di [Google,](https://admin.google.com)scegliere **Domini,** Gestisci **domini,** Visualizza **dettagli,** Gestisci **dominio,** **DNS** e quindi scorrere verso il basso fino a Record di **risorse personalizzati.**</span><span class="sxs-lookup"><span data-stu-id="91505-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="91505-111">Aprire l'elenco a discesa relativo al tipo di record, scegliere **TXT,** incollare il valore TXT copiato e selezionare **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="91505-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="91505-112">L'aggiornamento in genere richiede pochi minuti, ma può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="91505-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="91505-113">Tornare all'interfaccia di amministrazione di Microsoft 365, selezionare **Verifica** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="91505-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="91505-114">Per impostare il dominio come posta elettronica principale per gli utenti, nel riquadro di spostamento sinistro selezionare **Utenti**  >  **attivi.**</span><span class="sxs-lookup"><span data-stu-id="91505-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="91505-115">Choose a user, select **Manage username and email**, **Edit,** select your domain from the dropdown, then select **Done** and **Save changes.**</span><span class="sxs-lookup"><span data-stu-id="91505-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="91505-116">Ripetere questo processo per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="91505-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="91505-117">Al termine, sarà possibile installare le app di Office ed eseguire la migrazione della posta elettronica e degli elementi del calendario a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="91505-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 