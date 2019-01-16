---
title: Installare o disinstallare automaticamente Office nei dispositivi Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: "Installare o disinstallare Office nei dispositivi Windows 10 dall'interfaccia di amministrazione di Microsoft 365 Business. "
ms.openlocfilehash: 997c001ed1520f1ac989255632d36f9b7bedd16c
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868707"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a><span data-ttu-id="d867c-103">Installare o disinstallare automaticamente Office nei dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="d867c-103">Automatically install or uninstall Office on Windows 10 devices</span></span>

<span data-ttu-id="d867c-104">È possibile installare Office in PC Windows 10 dall'interfaccia di amministrazione di Microsoft 365 Business in modo semplice e rapido.</span><span class="sxs-lookup"><span data-stu-id="d867c-104">You can quickly and easily install Office to Windows 10 PCs from the Microsoft 365 Business admin center.</span></span>
  
<span data-ttu-id="d867c-105">Prima di iniziare, leggere [Preparare l'installazione di Office nei client](prepare-for-office-client-deployment.md) per informazioni sulla coesistenza di Office con le app di Office già installate.</span><span class="sxs-lookup"><span data-stu-id="d867c-105">To understand how this works with previously installed Office apps, read [Prepare for Office client installation](prepare-for-office-client-deployment.md) before you get started.</span></span> 
  
## <a name="manage-office-deployments"></a><span data-ttu-id="d867c-106">Gestire le distribuzioni di Office</span><span class="sxs-lookup"><span data-stu-id="d867c-106">Manage Office deployments</span></span>

1. <span data-ttu-id="d867c-107">Accedere al [portale di amministrazione](https://aka.ms/bcsportal) con le credenziali di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d867c-107">Sign in to the [admin center](https://aka.ms/bcsportal) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="d867c-p101">Nella scheda **dispositivi** scegliere **Gestisci la distribuzione di Office**.    Se non viene visualizzata la scheda **Azioni dispositivo** , nella pagina Amministrazione centrale **home page** fare clic su **Aggiungi** (+) per aggiungerlo alla home page di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d867c-p101">On the **Devices** card, choose **Manage Office Deployment**.    If you do not see the **Device actions** card, in the admin center **Home** page, click **Add** (+) to add it to your admin home.</span></span>
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. <span data-ttu-id="d867c-111">Nel riquadro **Gestisci la distribuzione di Office** scegliere **Aggiungi un gruppo** e selezionare i gruppi da usare.</span><span class="sxs-lookup"><span data-stu-id="d867c-111">On the **Manage Office deployment** pane that opens, choose **Add a group**, then select the groups you want use.</span></span>
    
4. <span data-ttu-id="d867c-112">Dopo aver aggiunto il gruppo o i gruppi desiderati, nell'elenco a discesa **Azione di distribuzione** selezionare **Installa Office appena possibile** o **Disinstalla Office**.</span><span class="sxs-lookup"><span data-stu-id="d867c-112">After you have added the group or groups you want to use, from the **Deployment Action** drop-down, select either **Install Office as soon as possible** or **Uninstall Office**.</span></span>
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. <span data-ttu-id="d867c-114">Scegliere **Avanti** \> rivedere le impostazioni e quindi fare clic su **Conferma**.</span><span class="sxs-lookup"><span data-stu-id="d867c-114">Choose **Next** \> review the settings and then choose **Confirm**.</span></span>
    
<span data-ttu-id="d867c-115">Office a 32 bit verrà installato o disinstallato automaticamente nei dispositivi degli utenti specificati dal gruppo o dai gruppi usati.</span><span class="sxs-lookup"><span data-stu-id="d867c-115">A 32-bit Office will be automatically installed, or uninstalled in the devices owned by users specified by the group or groups you used.</span></span>
  
<span data-ttu-id="d867c-116">Verificare di poter aprire Gestione attività in un computer selezionato per l'installazione di Office e cercare il processo Microsoft Office a portata di clic.</span><span class="sxs-lookup"><span data-stu-id="d867c-116">To verify you can open the Task Manager on a computer that was selected for an Office install and look for Microsoft Office Click-to-Run process.</span></span>
  


