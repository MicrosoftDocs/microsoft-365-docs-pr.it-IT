---
title: Modificare o impostare le impostazioni di protezione delle applicazioni per Windows 10 dispositivi
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Scopri come creare o modificare i criteri di gestione delle app e proteggere i file di lavoro nei dispositivi Windows 10 personali degli utenti.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580015"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="5a14a-103">Impostare o modificare le impostazioni di protezione delle applicazioni Windows 10 dispositivi</span><span class="sxs-lookup"><span data-stu-id="5a14a-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="5a14a-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="5a14a-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="5a14a-105">Modificare un criterio di gestione delle app per Windows 10</span><span class="sxs-lookup"><span data-stu-id="5a14a-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="5a14a-106">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="5a14a-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="5a14a-107">Nel riquadro di spostamento sinistro scegliere **Criteri** \> **dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="5a14a-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="5a14a-108">Scegli un criterio Windows'app esistente e quindi **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5a14a-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="5a14a-109">Scegliere **Modifica** accanto a un'impostazione che si desidera modificare e quindi **Salva.**</span><span class="sxs-lookup"><span data-stu-id="5a14a-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="5a14a-110">Creare criteri di gestione delle app per Windows 10</span><span class="sxs-lookup"><span data-stu-id="5a14a-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="5a14a-111">Se gli utenti hanno dispositivi Windows 10 personali in cui eseguono attività di lavoro, è possibile proteggere anche i dati in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5a14a-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="5a14a-112">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="5a14a-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="5a14a-113">Nel riquadro di spostamento sinistro scegliere **Criteri** \> **dispositivi** \> **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5a14a-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="5a14a-114">Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio.</span><span class="sxs-lookup"><span data-stu-id="5a14a-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="5a14a-115">In **Tipo di criterio** scegliere **Gestione applicazioni per Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="5a14a-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="5a14a-116">In **Tipo di dispositivo** scegliere Personale o Proprietà **società.** </span><span class="sxs-lookup"><span data-stu-id="5a14a-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="5a14a-117">L'opzione **Crittografa i file di lavoro** viene attivata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5a14a-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="5a14a-118">Impostare **Impedisci agli utenti di copiare dati aziendali in file personali e forzali a salvare i file di lavoro in OneDrive for Business** su **Sì** per evitare che gli utenti salvino i file di lavoro nei rispettivi PC.</span><span class="sxs-lookup"><span data-stu-id="5a14a-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="5a14a-119">Espandi **Recupera dati in Windows dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="5a14a-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="5a14a-120">È consigliabile **attivarlo.**</span><span class="sxs-lookup"><span data-stu-id="5a14a-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="5a14a-121">Prima di passare al percorso del certificato dell'agente di recupero dati, è necessario crearne uno.</span><span class="sxs-lookup"><span data-stu-id="5a14a-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="5a14a-122">Per istruzioni, vedere [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span><span class="sxs-lookup"><span data-stu-id="5a14a-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span></span>
    
    <span data-ttu-id="5a14a-123">Per impostazione predefinita, i file di lavoro sono crittografati con una chiave segreta archiviata nel dispositivo e associata al profilo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5a14a-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="5a14a-124">Solo l'utente può aprire e decrittografare il file.</span><span class="sxs-lookup"><span data-stu-id="5a14a-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="5a14a-125">Tuttavia, se un dispositivo viene perso o se un utente viene rimosso, un file può restare bloccato in stato crittografato.</span><span class="sxs-lookup"><span data-stu-id="5a14a-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="5a14a-126">Un amministratore può utilizzare il certificato dell'agente di recupero dati (DRA) per decrittografare il file.</span><span class="sxs-lookup"><span data-stu-id="5a14a-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="5a14a-128">Espandi **Proteggi percorsi di rete** e cloud aggiuntivi se vuoi aggiungere altri domini o percorsi di SharePoint Online per assicurarti che i file in tutte le app elencate siano protetti.</span><span class="sxs-lookup"><span data-stu-id="5a14a-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="5a14a-129">Se è necessario immettere più voci per uno dei campi, usare il punto e virgola (;) per separare le voci.</span><span class="sxs-lookup"><span data-stu-id="5a14a-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="5a14a-p104">In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="5a14a-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="5a14a-133">Infine, scegliere **Aggiungi** per salvare il criterio e assegnarlo ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="5a14a-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span>