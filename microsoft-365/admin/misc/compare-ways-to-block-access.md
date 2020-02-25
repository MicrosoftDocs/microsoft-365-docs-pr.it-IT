---
title: Confronto tra metodi di blocco dell'accesso a Office 365
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
description: Informazioni su come bloccare l'accesso a Office 365 quando un dipendente lascia l'organizzazione.
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257396"
---
# <a name="compare-ways-to-block-access-to-office-365"></a><span data-ttu-id="6674c-103">Confronto tra metodi di blocco dell'accesso a Office 365</span><span class="sxs-lookup"><span data-stu-id="6674c-103">Compare ways to block access to Office 365</span></span>

<span data-ttu-id="6674c-p101">Quando un dipendente lascia l'organizzazione per qualsiasi motivo, è necessario bloccarne l'accesso a Office 365. Questa operazione si può eseguire in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="6674c-p101">When an employee leaves your organization, on good terms or bad, you need to block their access to Office 365. Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="6674c-106">**Metodo di blocco dell'accesso**</span><span class="sxs-lookup"><span data-stu-id="6674c-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="6674c-107">**Definizione**</span><span class="sxs-lookup"><span data-stu-id="6674c-107">**Definition**</span></span> <br/> |<span data-ttu-id="6674c-108">**Procedura consigliata**</span><span class="sxs-lookup"><span data-stu-id="6674c-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="6674c-109">Bloccare l'accesso</span><span class="sxs-lookup"><span data-stu-id="6674c-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="6674c-p102">Un modo per impedire a un utente di accedere a Office 365 consiste nell'impostare il suo stato di accesso su **Accesso bloccato**. In questo modo l'utente non potrà eseguire l'accesso a Office 365 dal suo computer o dispositivo mobile, ma potrà ancora visualizzare i messaggi di posta elettronica e i documenti precedentemente scaricati o sincronizzati. Se si usa Blackberry Enterprise Service, è possibile disabilitare l'accesso dell'utente anche lì.  </span><span class="sxs-lookup"><span data-stu-id="6674c-p102">One way to block a user from accessing Office 365 is to change their sign-in status to **Sign-in blocked**. This prevents them from signing into Office 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents. If you're using Blackberry Enterprise Service, you can disable their access there as well.  </span></span><br/> |<span data-ttu-id="6674c-113">Usare questo metodo quando un dipendente ha intenzione di lasciare l'azienda definitivamente o per un lungo periodo.</span><span class="sxs-lookup"><span data-stu-id="6674c-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="6674c-114">Reimpostare la password dell'utente</span><span class="sxs-lookup"><span data-stu-id="6674c-114">Reset user password</span></span>  <br/> |<span data-ttu-id="6674c-p103">Un altro modo per impedire a un utente di accedere a Office 365 consiste nel reimpostarne la password. In questo modo l'utente non potrà più usare il suo account, ma potrà ancora visualizzare i messaggi di posta elettronica e i documenti precedentemente scaricati o sincronizzati. È quindi possibile accedere con l'account dell'utente e cambiare la password.</span><span class="sxs-lookup"><span data-stu-id="6674c-p103">Another way to prevent a user from accessing Office 365 is to reset their password. This prevents them from using their account though they can still view previously downloaded or synced email and documents. You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="6674c-118">Usare questo metodo quando un dipendente lascia l'organizzazione improvvisamente e definitivamente e si vogliono proteggere i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="6674c-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="6674c-119">Rimuovere tutte le licenze assegnate</span><span class="sxs-lookup"><span data-stu-id="6674c-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="6674c-120">Un'altra opzione consiste nel rimuovere le licenze di Office 365 assegnate all'utente.</span><span class="sxs-lookup"><span data-stu-id="6674c-120">Another option is to remove any Office 365 licenses assigned to the user.</span></span> <span data-ttu-id="6674c-121">In questo modo è possibile impedire loro di utilizzare applicazioni e servizi quali la famiglia di prodotti Office, le app di Office per il Web, Yammer e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6674c-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="6674c-122">Potrà ancora accedere ma non potrà usare questi servizi.</span><span class="sxs-lookup"><span data-stu-id="6674c-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="6674c-123">Usare questo metodo quando si ritiene che l'utente non abbia più bisogno dell'accesso a determinate caratteristiche di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6674c-123">Use when you feel this user no longer needs access to specific features in Office 365.</span></span>  <br/> <br> <span data-ttu-id="6674c-124">**Importante:** Quando si rimuove una licenza, la cassetta postale dell'utente viene eliminata in 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="6674c-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="6674c-125">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="6674c-125">Related articles</span></span>

[<span data-ttu-id="6674c-126">Rimuovere un utente da Office 365</span><span class="sxs-lookup"><span data-stu-id="6674c-126">Offboard a user from Office 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="6674c-127">Reimpostare la password di un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="6674c-127">Reset a user's password in Office 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="6674c-128">Assegnare licenze agli utenti in Office 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="6674c-128">Assign licenses to users in Office 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="6674c-129">Rimuovere licenze dagli utenti in Office 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="6674c-129">Remove licenses from users in Office 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

