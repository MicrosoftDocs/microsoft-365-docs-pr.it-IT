---
title: Gestire Skype for Business Online con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Usare PowerShell per Microsoft 365 per gestire i criteri, i criteri per gli utenti e le impostazioni delle riunioni di Skype for Business online.
ms.openlocfilehash: 1992edfb6d1c141c7ed4db22064960873b768865
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514957"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="21ff5-103">Gestire Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="21ff5-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="21ff5-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="21ff5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="21ff5-105">Gli amministratori di Skype fo Business online sono responsabili della gestione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="21ff5-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="21ff5-106">Anche se è possibile eseguire alcune di queste operazioni nell'interfaccia di amministrazione di Microsoft 365, altre sono più facili da eseguire in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21ff5-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="21ff5-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="21ff5-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="21ff5-108">Il connettore di Skype for Business Online fa parte al momento del modulo PowerShell di Teams più recente.</span><span class="sxs-lookup"><span data-stu-id="21ff5-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="21ff5-109">Se si usa la versione pubblica di PowerShell di Teams più recente, non è necessario installare il connettore di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="21ff5-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="21ff5-110">Installare il [modulo di PowerShell di Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="21ff5-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="21ff5-111">Connettersi con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="21ff5-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="21ff5-112">Aprire la finestra del prompt dei comandi di Windows PowerShell ed eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="21ff5-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. <span data-ttu-id="21ff5-113">Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, digitare il nome utente e password dell'account amministratore, poi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="21ff5-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="21ff5-114">Connettersi con un account di amministratore con l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="21ff5-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="21ff5-115">Aprire la finestra del prompt dei comandi di Windows PowerShell ed eseguire i seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="21ff5-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. <span data-ttu-id="21ff5-116">Quando richiesto, immettere il nome e dell'account Administrator di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="21ff5-116">When prompted enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="21ff5-117">Nella finestra di dialogo **Accedi al tuo account**, scrivere la password dell'account amministratore di Skype for Business Online e selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="21ff5-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="21ff5-118">Nella finestra di dialogo **Accedi al tuo account** seguire le istruzioni per fornire informazioni di autenticazione aggiuntive, come un codice di verifica, quindi selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="21ff5-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="21ff5-119">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="21ff5-119">For more information, see:</span></span>
  
- [<span data-ttu-id="21ff5-120">Gestire i criteri di Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="21ff5-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="21ff5-121">Assegnare i criteri di Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="21ff5-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="21ff5-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21ff5-122">See also</span></span>

[<span data-ttu-id="21ff5-123">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="21ff5-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="21ff5-124">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="21ff5-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="21ff5-125">Riferimenti per i cmdlet di PowerShell per Skype for Business</span><span class="sxs-lookup"><span data-stu-id="21ff5-125">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
