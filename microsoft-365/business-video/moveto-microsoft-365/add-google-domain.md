---
title: Aggiungere il dominio di Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: Scopri come spostare il dominio da Google Workspace a Microsoft 365 per le aziende.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578772"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="07bcb-103">Aggiungere il dominio di Google Workspace a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07bcb-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="07bcb-104">Aggiungi il dominio di Google Workspace a Microsoft 365 per le aziende in modo da poter continuare a usare l'indirizzo di posta elettronica aziendale.</span><span class="sxs-lookup"><span data-stu-id="07bcb-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="07bcb-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="07bcb-105">Try it!</span></span>

1. <span data-ttu-id="07bcb-106">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="07bcb-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="07bcb-107">Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, selezionare **Mostra tutto**, **Impostazioni** e quindi **Domini**.</span><span class="sxs-lookup"><span data-stu-id="07bcb-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="07bcb-108">Scegliere **Aggiungi dominio,** immettere il nome del dominio e quindi **selezionare Usa questo dominio.**</span><span class="sxs-lookup"><span data-stu-id="07bcb-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="07bcb-109">Scegliere Aggiungi **un record TXT ai** record DNS dei domini, selezionare **Continua** e copiare il valore TXT.</span><span class="sxs-lookup"><span data-stu-id="07bcb-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="07bcb-110">Torna alla Console di amministrazione [di Google,](https://admin.google.com)scegli **Domini,** Gestisci **domini,** Visualizza **dettagli,** **Gestisci** dominio, **DNS** e quindi scorri verso il basso fino a Record di **risorse personalizzati.**</span><span class="sxs-lookup"><span data-stu-id="07bcb-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="07bcb-111">Aprire l'elenco a discesa tipo di record, scegliere **TXT,** incollare il valore TXT copiato e quindi **selezionare Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="07bcb-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="07bcb-112">L'aggiornamento in genere richiede alcuni minuti, ma può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="07bcb-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="07bcb-113">Tornare all'interfaccia di amministrazione di Microsoft 365, selezionare **Verifica** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="07bcb-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="07bcb-114">Per impostare il dominio come posta elettronica principale per gli utenti, nel riquadro di spostamento sinistro selezionare **Utenti**  >  **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="07bcb-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="07bcb-115">Scegliere un utente, selezionare **Gestisci nome utente e posta** elettronica , Modifica , selezionare il dominio dall'elenco a discesa, quindi selezionare Fatto e salva le **modifiche**.  </span><span class="sxs-lookup"><span data-stu-id="07bcb-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="07bcb-116">Ripetere questo processo per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="07bcb-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="07bcb-117">Al termine, sarà possibile installare le app di Office ed eseguire la migrazione della posta elettronica e degli elementi del calendario a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07bcb-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 