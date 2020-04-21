---
title: Confronto delle modalità di blocco dell'accesso
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
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: Informazioni su come bloccare l'accesso a Microsoft 365 quando un dipendente lascia l'organizzazione.
ms.openlocfilehash: 9383c970ea1c17d9116299d5788c8faf0ed0659f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627933"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="4cc1b-103">Confronto delle modalità di blocco dell'accesso</span><span class="sxs-lookup"><span data-stu-id="4cc1b-103">Compare ways to block access</span></span>

<span data-ttu-id="4cc1b-104">Quando un dipendente lascia l'organizzazione, in termini buoni o cattivi, è necessario bloccare l'accesso a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="4cc1b-105">Questa operazione si può eseguire in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-105">Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="4cc1b-106">**Metodo di blocco dell'accesso**</span><span class="sxs-lookup"><span data-stu-id="4cc1b-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="4cc1b-107">**Definizione**</span><span class="sxs-lookup"><span data-stu-id="4cc1b-107">**Definition**</span></span> <br/> |<span data-ttu-id="4cc1b-108">**Procedura consigliata**</span><span class="sxs-lookup"><span data-stu-id="4cc1b-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="4cc1b-109">Bloccare l'accesso</span><span class="sxs-lookup"><span data-stu-id="4cc1b-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="4cc1b-110">Un modo per impedire a un utente di accedere a Microsoft 365 consiste nel cambiare lo stato di accesso per il **login bloccato**.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="4cc1b-111">Ciò impedisce all'utente di accedere a Microsoft 365 dai propri computer e dispositivi mobili, anche se è ancora in grado di visualizzare la posta elettronica e i documenti precedentemente scaricati o sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="4cc1b-112">Se si usa Blackberry Enterprise Service, è possibile disabilitare l'accesso dell'utente anche lì.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="4cc1b-113">Usare questo metodo quando un dipendente ha intenzione di lasciare l'azienda definitivamente o per un lungo periodo.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="4cc1b-114">Reimpostare la password dell'utente</span><span class="sxs-lookup"><span data-stu-id="4cc1b-114">Reset user password</span></span>  <br/> |<span data-ttu-id="4cc1b-115">Un altro modo per impedire a un utente di accedere a Microsoft 365 consiste nel reimpostare la propria password.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="4cc1b-116">In questo modo l'utente non potrà più usare il suo account, ma potrà ancora visualizzare i messaggi di posta elettronica e i documenti precedentemente scaricati o sincronizzati.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="4cc1b-117">È quindi possibile accedere con l'account dell'utente e cambiare la password.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="4cc1b-118">Usare questo metodo quando un dipendente lascia l'organizzazione improvvisamente e definitivamente e si vogliono proteggere i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="4cc1b-119">Rimuovere tutte le licenze assegnate</span><span class="sxs-lookup"><span data-stu-id="4cc1b-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="4cc1b-120">Un'altra opzione consiste nel rimuovere tutte le licenze Microsoft 365 assegnate all'utente.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="4cc1b-121">In questo modo è possibile impedire loro di utilizzare applicazioni e servizi quali la famiglia di prodotti Office, le app di Office per il Web, Yammer e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="4cc1b-122">Potrà ancora accedere ma non potrà usare questi servizi.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="4cc1b-123">Utilizzare quando si ritiene che l'utente non abbia più bisogno di accedere a funzionalità specifiche in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="4cc1b-124">**Importante:** Quando si rimuove una licenza, la cassetta postale dell'utente viene eliminata in 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4cc1b-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="4cc1b-125">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="4cc1b-125">Related articles</span></span>

[<span data-ttu-id="4cc1b-126">Trasferisce un utente da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4cc1b-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="4cc1b-127">Reimpostare la password di un utente in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4cc1b-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="4cc1b-128">Assegnare licenze agli utenti in Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="4cc1b-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="4cc1b-129">Rimuovere le licenze dagli utenti in Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="4cc1b-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

