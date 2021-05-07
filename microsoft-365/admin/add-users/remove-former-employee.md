---
title: Rimuovere un ex dipendente - Panoramica
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Seguire i passaggi descritti in questa soluzione per rimuovere un ex dipendente Microsoft 365 e proteggere i dati dell'organizzazione.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241737"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="19944-103">Panoramica: rimuovere un ex dipendente e proteggere i dati</span><span class="sxs-lookup"><span data-stu-id="19944-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="19944-104">Una domanda che spesso ci viene data è: "Cosa devo fare per proteggere i dati e proteggere l'accesso quando un dipendente lascia l'organizzazione?"</span><span class="sxs-lookup"><span data-stu-id="19944-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="19944-105">In questa serie di articoli viene illustrato come bloccare l'accesso a Microsoft 365, i passaggi da eseguire per proteggere i dati e come consentire ad altri dipendenti di accedere ai dati.</span><span class="sxs-lookup"><span data-stu-id="19944-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="19944-106">Guarda un breve video sulla rimozione di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="19944-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="19944-107">Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="19944-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="19944-108">Per impedire a un dipendente di accedere:</span><span class="sxs-lookup"><span data-stu-id="19944-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="19944-109">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="19944-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="19944-110">Selezionare la casella accanto al nome dell'utente e quindi selezionare **Reimposta password.**</span><span class="sxs-lookup"><span data-stu-id="19944-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="19944-111">Immettere una nuova password e quindi selezionare **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="19944-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="19944-112">Non inviarlo a loro.</span><span class="sxs-lookup"><span data-stu-id="19944-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="19944-113">Selezionare il nome dell'utente per passare al riquadro delle proprietà e nella **scheda Account** selezionare **Avvia disconnessione.**</span><span class="sxs-lookup"><span data-stu-id="19944-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="19944-114">È necessario essere un amministratore globale per avviare la disconnessione.</span><span class="sxs-lookup"><span data-stu-id="19944-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="19944-115">Entro un'ora o dopo aver lasciato la pagina Microsoft 365 corrente in cui si trova, viene richiesto di accedere di nuovo.</span><span class="sxs-lookup"><span data-stu-id="19944-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="19944-116">Un token di accesso è valido per un'ora, quindi la sequenza temporale dipende dal tempo che rimane su quel token e dal fatto che si snavigare fuori dalla pagina Web corrente.</span><span class="sxs-lookup"><span data-stu-id="19944-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19944-117">Anche se i passaggi di questa soluzione sono stati numerati e non è necessario completare la soluzione utilizzando l'ordine esatto, è consigliabile eseguire la procedura in questo modo.</span><span class="sxs-lookup"><span data-stu-id="19944-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="19944-118">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="19944-118">Before you begin</span></span>

<span data-ttu-id="19944-119">Per completare i passaggi di questa soluzione, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="19944-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="19944-120">**Passaggio**</span><span class="sxs-lookup"><span data-stu-id="19944-120">**Step**</span></span> <br/> |<span data-ttu-id="19944-121">**Perché eseguire questa operazione**</span><span class="sxs-lookup"><span data-stu-id="19944-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="19944-122">Passaggio 1 - Impedire a un ex dipendente di accedere e bloccare l'accesso Microsoft 365 servizi</span><span class="sxs-lookup"><span data-stu-id="19944-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="19944-123">Questo impedisce all'ex dipendente di accedere a Microsoft 365 e impedisce all'utente di accedere Microsoft 365 servizi.</span><span class="sxs-lookup"><span data-stu-id="19944-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="19944-124">Passaggio 2 - Salvare il contenuto della cassetta postale di un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="19944-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="19944-125">Ciò è utile per la persona che prenderà il controllo del lavoro del dipendente o in caso di controversia legale.</span><span class="sxs-lookup"><span data-stu-id="19944-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="19944-126">Passaggio 3 - Inoltrare la posta elettronica di un ex dipendente a un altro dipendente o convertirlo in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="19944-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="19944-p104">Consente di mantenere attivo l'indirizzo di posta elettronica dell'ex dipendente. Se i clienti o i partner continuano a inviare la posta elettronica all'indirizzo dell'ex dipendente, questa operazione consente di inoltrare i messaggi alla persona che ne prende il posto.</span><span class="sxs-lookup"><span data-stu-id="19944-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="19944-129">Passaggio 4 - Concedere a un altro dipendente l'accesso OneDrive e Outlook dati</span><span class="sxs-lookup"><span data-stu-id="19944-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="19944-130">Se si rimuove solo la licenza di un utente, senza eliminare l'account, il contenuto del suo OneDrive rimarrà accessibile anche dopo i 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="19944-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="19944-131">Prima di eliminare l'account, è consigliabile concedere l'accesso OneDrive e Outlook a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="19944-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="19944-132">Dopo aver eliminato l'account di un dipendente, il contenuto OneDrive e Outlook viene conservato per **30** giorni.</span><span class="sxs-lookup"><span data-stu-id="19944-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="19944-133">Durante questi 30 giorni, tuttavia, è possibile ripristinare l'account dell'utente e ottenere l'accesso al contenuto.</span><span class="sxs-lookup"><span data-stu-id="19944-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="19944-134">Se si ripristina l'account dell'utente, il contenuto OneDrive e Outlook rimarrà accessibile anche dopo 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="19944-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="19944-135">Passaggio 5 - Cancellare e bloccare il dispositivo mobile di un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="19944-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="19944-136">Rimuove i dati aziendali dal telefono o dal tablet.</span><span class="sxs-lookup"><span data-stu-id="19944-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="19944-137">Passaggio 6 - Rimuovere ed eliminare la licenza Microsoft 365 da un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="19944-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="19944-p106">Quando si rimuove una licenza, è possibile assegnarla a un'altra persona. In alternativa, è possibile eliminare la licenza in modo da interromperne il pagamento finché non si assume un'altra persona.  </span><span class="sxs-lookup"><span data-stu-id="19944-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="19944-p107">Quando si rimuove o si elimina una licenza, la posta elettronica, i contatti e il calendario dell'utente vengono conservati per **30 giorni**, quindi eliminati definitivamente. Se si rimuove o si elimina la licenza di un utente, senza eliminare l'account, il contenuto del suo OneDrive rimarrà accessibile anche dopo i 30 giorni.  </span><span class="sxs-lookup"><span data-stu-id="19944-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="19944-142">Passaggio 7 - Eliminare l'account utente di un ex dipendente</span><span class="sxs-lookup"><span data-stu-id="19944-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="19944-143">In questo modo l'account viene rimosso dall'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="19944-143">This removes the account from your admin center.</span></span> <span data-ttu-id="19944-144">Consente di tenere tutto in ordine.</span><span class="sxs-lookup"><span data-stu-id="19944-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="19944-145">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="19944-145">Related articles</span></span>

[<span data-ttu-id="19944-146">Ripristinare un utente</span><span class="sxs-lookup"><span data-stu-id="19944-146">Restore a user</span></span>](restore-user.md)
