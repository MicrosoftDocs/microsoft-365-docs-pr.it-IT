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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430035"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="58aa1-103">Gestire Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="58aa1-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="58aa1-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="58aa1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="58aa1-105">Gli amministratori di Skype fo Business online sono responsabili della gestione dei criteri.</span><span class="sxs-lookup"><span data-stu-id="58aa1-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="58aa1-106">Anche se è possibile eseguire alcune di queste operazioni nell'interfaccia di amministrazione di Microsoft 365, altre sono più facili da eseguire in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58aa1-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="58aa1-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="58aa1-107">Before you start</span></span>

<span data-ttu-id="58aa1-108">Scaricare e installare il [Modulo di Windows PowerShell per Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366), quindi riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="58aa1-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="58aa1-109">Connettersi con le credenziali di amministratore di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="58aa1-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="58aa1-110">Aprire la finestra del prompt dei comandi di Windows PowerShell ed eseguire i seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="58aa1-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="58aa1-111">Nella finestra di dialogo **Richiesta credenziali di Windows PowerShell**, scrivere nome utente e password dell'account amministratore di Skype for Business, e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="58aa1-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="58aa1-112">Connettersi con un account di amministratore con l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="58aa1-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="58aa1-113">Aprire la finestra del prompt dei comandi di Windows PowerShell ed eseguire i seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="58aa1-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="58aa1-114">Quando richiesto dal comando **New-CsOnlineSession**, immettere il nome dell'account amministratore di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="58aa1-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="58aa1-115">Nella finestra di dialogo **Accedi al tuo account**, scrivere la password dell'account amministratore di Skype for Business Online e selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="58aa1-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="58aa1-116">Nella finestra di dialogo **Accedi al tuo account** seguire le istruzioni per fornire informazioni di autenticazione aggiuntive, come un codice di verifica, quindi selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="58aa1-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="58aa1-117">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="58aa1-117">For more information, see:</span></span>
  
- [<span data-ttu-id="58aa1-118">Gestire i criteri di Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="58aa1-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="58aa1-119">Assegnare i criteri di Skype for Business Online con PowerShell</span><span class="sxs-lookup"><span data-stu-id="58aa1-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="58aa1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58aa1-120">See also</span></span>

[<span data-ttu-id="58aa1-121">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="58aa1-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="58aa1-122">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58aa1-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="58aa1-123">Riferimenti per i cmdlet di PowerShell per Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58aa1-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
