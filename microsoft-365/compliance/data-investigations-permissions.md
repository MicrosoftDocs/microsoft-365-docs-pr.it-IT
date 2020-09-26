---
title: Assegnare le autorizzazioni per le indagini sui dati (anteprima)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto come configurare le autorizzazioni necessarie per l'utilizzo dello strumento indagini dati in Microsoft 365.
ms.openlocfilehash: 85a800c3e21c270f46de78bdef77d7b7a98e0eca
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285442"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="8b508-103">Assegnare le autorizzazioni per le indagini sui dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="8b508-103">Assign permissions for Data Investigations (preview)</span></span>

<span data-ttu-id="8b508-104">Per accedere a un'analisi dei dati nel centro conformità di Office 365 o Microsoft 365, è necessario essere membri del gruppo di ruolo ricercatore di dati.</span><span class="sxs-lookup"><span data-stu-id="8b508-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="8b508-105">Per aggiungere membri a un gruppo di ruoli, è necessario essere membri del gruppo di ruoli Gestione organizzazione o assegnare il ruolo di gestione dei ruoli nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="8b508-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="8b508-106">Dopo che un utente diventa membro del gruppo di ruolo ricercatore dati, può creare, accedere e condurre indagini nelle indagini sui dati di cui si è membri.</span><span class="sxs-lookup"><span data-stu-id="8b508-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="8b508-107">Per assegnare le autorizzazioni per le indagini sui dati:</span><span class="sxs-lookup"><span data-stu-id="8b508-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="8b508-108">Passare a [https://protection.office.com](https://protection.office.com) e accedere usando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b508-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8b508-109">Nel centro sicurezza & conformità fare clic su **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="8b508-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="8b508-110">Fare clic sul gruppo di ruoli **ricercatore di dati** e quindi fare clic su **modifica**accanto a **membri** nella pagina riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="8b508-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="8b508-111">Fare clic su **Scegli membri** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8b508-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="8b508-112">Selezionare gli utenti che si desidera aggiungere come investigatori dati e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8b508-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="8b508-113">Dopo aver aggiunto tutti gli utenti, fare clic su **fine** e quindi su **Salva** per salvare le modifiche apportate al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="8b508-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="8b508-114">Il ruolo di gestione analisi dati assegnato al gruppo di ruolo ricercatore di dati fornisce le autorizzazioni necessarie per accedere allo strumento indagini dati nel centro conformità di Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b508-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="8b508-115">Per impostazione predefinita, questo ruolo non è assegnato al gruppo di ruoli Gestione organizzazione, il che significa che gli amministratori globali dell'organizzazione potrebbero non essere in grado di accedere allo strumento indagini dati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8b508-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="8b508-116">Per risolvere il caso, è possibile aggiungere gli amministratori globali al gruppo di ruolo ricercatore di dati o aggiungere il ruolo di gestione analisi dati al gruppo di ruoli Gestione organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b508-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="8b508-117">Una terza opzione consiste nella creazione di un gruppo di ruoli personalizzato e nell'assegnazione del ruolo di gestione dell'analisi dei dati (e di altri ruoli) e quindi dell'aggiunta di membri idonei.</span><span class="sxs-lookup"><span data-stu-id="8b508-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="8b508-118">Per ulteriori informazioni sui ruoli e sui gruppi di ruolo, vedere [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="8b508-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
