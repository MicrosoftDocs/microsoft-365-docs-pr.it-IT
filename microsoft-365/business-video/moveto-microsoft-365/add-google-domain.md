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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come spostare il dominio da Google Workspace a Microsoft 365 for business.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794673"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="3436d-103">Aggiungere il dominio di Google Workspace a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3436d-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="3436d-104">Aggiungere il dominio di Google Workspace a Microsoft 365 for business in modo da poter continuare a utilizzare l'indirizzo di posta elettronica aziendale.</span><span class="sxs-lookup"><span data-stu-id="3436d-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="3436d-105">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="3436d-105">Try it!</span></span>

1. <span data-ttu-id="3436d-106">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3436d-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="3436d-107">Nell'interfaccia di amministrazione di Microsoft 365, nella barra di spostamento sinistra, selezionare **Mostra tutto**, **Impostazioni** e quindi **domini**.</span><span class="sxs-lookup"><span data-stu-id="3436d-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="3436d-108">Scegliere **Aggiungi dominio**, immettere il proprio nome di dominio, quindi selezionare **Usa questo dominio**.</span><span class="sxs-lookup"><span data-stu-id="3436d-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="3436d-109">Scegliere, **aggiungere un record TXT ai record DNS dei domini**, selezionare **continua** e copiare il valore txt.</span><span class="sxs-lookup"><span data-stu-id="3436d-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="3436d-110">Tornare alla console di [amministrazione di Google](https://admin.google.com), scegliere **Domains**, **Manage** Domains, **View details**, **Manage Domain**, **DNS**, quindi scorrere verso il basso fino a **record di risorse personalizzati**.</span><span class="sxs-lookup"><span data-stu-id="3436d-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="3436d-111">Aprire il menu a discesa tipo di record, scegliere **txt**, incollare il valore txt copiato e quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3436d-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="3436d-112">L'aggiornamento di solito richiede un dato di fatto in pochi minuti, ma può richiedere fino a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="3436d-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="3436d-113">Tornare all'interfaccia di amministrazione di Microsoft 365, selezionare **Verifica** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3436d-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="3436d-114">Per impostare il dominio come messaggio di posta elettronica principale per gli utenti, nel NAV **sinistro selezionare utenti**  >  **attivi**.</span><span class="sxs-lookup"><span data-stu-id="3436d-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="3436d-115">Scegliere un utente, selezionare **Gestisci nome utente e posta elettronica**, **modifica**, selezionare il dominio dall'elenco a discesa, quindi fare clic su **fine** e **salvare le modifiche**.</span><span class="sxs-lookup"><span data-stu-id="3436d-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="3436d-116">Ripetere questa procedura per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="3436d-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="3436d-117">Al termine dell'installazione, sarà possibile installare le app di Office e migrare gli elementi di posta elettronica e del calendario a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3436d-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 