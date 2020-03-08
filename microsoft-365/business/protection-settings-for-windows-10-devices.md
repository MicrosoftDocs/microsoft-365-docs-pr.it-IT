---
title: Configurare le impostazioni di protezione delle app per i dispositivi Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Informazioni su come creare un criterio di gestione delle app e proteggere i file di lavoro nei dispositivi Windows 10 personali degli utenti.
ms.openlocfilehash: bbfb07302f2d77f7e66301723d176cf053f79cc1
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561341"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="1c20b-103">Configurare le impostazioni di protezione delle app per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="1c20b-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="1c20b-104">Creare criteri di gestione delle app per Windows 10</span><span class="sxs-lookup"><span data-stu-id="1c20b-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="1c20b-105">Se gli utenti hanno dispositivi Windows 10 personali in cui eseguono attività di lavoro, è possibile proteggere anche i dati in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1c20b-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="1c20b-106">Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="1c20b-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="1c20b-107">Nella barra di spostamento sinistra fare clic su **criteri** \> **dispositivi** \> **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1c20b-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="1c20b-108">Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio.</span><span class="sxs-lookup"><span data-stu-id="1c20b-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="1c20b-109">In **Tipo di criterio** scegliere **Gestione applicazioni per Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="1c20b-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="1c20b-110">In **tipo di dispositivo**scegliere **personale** o di **proprietà dell'azienda**.</span><span class="sxs-lookup"><span data-stu-id="1c20b-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="1c20b-111">L'opzione **Crittografa i file di lavoro** viene attivata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1c20b-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="1c20b-112">Impostare **Impedisci agli utenti di copiare dati aziendali in file personali e forzali a salvare i file di lavoro in OneDrive for Business** su **Sì** per evitare che gli utenti salvino i file di lavoro nei rispettivi PC.</span><span class="sxs-lookup"><span data-stu-id="1c20b-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="1c20b-113">Espandere **Recupera dati nei dispositivi Windows**.</span><span class="sxs-lookup"><span data-stu-id="1c20b-113">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="1c20b-114">**È consigliabile attivarla.**</span><span class="sxs-lookup"><span data-stu-id="1c20b-114">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="1c20b-115">Prima di passare al percorso del certificato dell'agente di recupero dati, è necessario crearne uno.</span><span class="sxs-lookup"><span data-stu-id="1c20b-115">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="1c20b-116">Per istruzioni, vedere [creare e verificare un certificato DRA (Encrypting File System) per l'agente di recupero dati](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="1c20b-116">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="1c20b-117">Per impostazione predefinita, i file di lavoro sono crittografati con una chiave segreta archiviata nel dispositivo e associata al profilo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1c20b-117">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="1c20b-118">Solo l'utente può aprire e decrittografare il file.</span><span class="sxs-lookup"><span data-stu-id="1c20b-118">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="1c20b-119">Tuttavia, se un dispositivo viene perso o se un utente viene rimosso, un file può restare bloccato in stato crittografato.</span><span class="sxs-lookup"><span data-stu-id="1c20b-119">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="1c20b-120">Un amministratore può utilizzare il certificato DRA (Data Recovery Agent) per decrittografare il file.</span><span class="sxs-lookup"><span data-stu-id="1c20b-120">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="1c20b-122">Espandere **Proteggi percorsi di rete e cloud aggiuntivi** se si desidera aggiungere ulteriori domini o percorsi di SharePoint Online per assicurarsi che i file in tutte le app elencate siano protetti.</span><span class="sxs-lookup"><span data-stu-id="1c20b-122">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="1c20b-123">Se è necessario immettere più voci per uno dei campi, usare il punto e virgola (;) per separare le voci.</span><span class="sxs-lookup"><span data-stu-id="1c20b-123">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="1c20b-p105">In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="1c20b-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="1c20b-127">Infine, scegliere **Aggiungi** per salvare il criterio e assegnarlo ai dispositivi.</span><span class="sxs-lookup"><span data-stu-id="1c20b-127">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
