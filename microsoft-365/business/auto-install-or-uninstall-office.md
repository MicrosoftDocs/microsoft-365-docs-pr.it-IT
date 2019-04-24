---
title: Installare o disinstallare automaticamente Office nei dispositivi Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: "Installare o disinstallare Office nei dispositivi Windows 10 dall'interfaccia di amministrazione di Microsoft 365 business. "
ms.openlocfilehash: fef4a543aed489202bf05dfb1e8cafbb784ca819
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277284"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Installare o disinstallare automaticamente Office nei dispositivi Windows 10

È possibile installare Office in PC Windows 10 dall'interfaccia di amministrazione di Microsoft 365 Business in modo semplice e rapido.
  
Prima di iniziare, leggere [Preparare l'installazione di Office nei client](prepare-for-office-client-deployment.md) per informazioni sulla coesistenza di Office con le app di Office già installate. 
  
## <a name="manage-office-deployments"></a>Gestire le distribuzioni di Office

1. Accedere al [portale di amministrazione](https://aka.ms/bcsportal) con le credenziali di amministratore globale. 
    
2. Nella scheda **Dispositivi** scegliere **Gestisci la distribuzione di Office**.
      Se la scheda **azioni dispositivo** non è visualizzata, nella **Home** page dell'interfaccia di amministrazione fare clic su **Aggiungi** (+) per aggiungerla alla Home page di amministrazione.
    
    ![Screenshot of the Devices card in the admin center](media/9982e784-dbf9-4a76-a159-bb3e2e5aa23f.png)
  
3. Nel riquadro **Gestisci la distribuzione di Office** scegliere **Aggiungi un gruppo** e selezionare i gruppi da usare.
    
4. Dopo aver aggiunto il gruppo o i gruppi desiderati, nell'elenco a discesa **Azione di distribuzione** selezionare **Installa Office appena possibile** o **Disinstalla Office**.
    
    ![In the Manage Office deployment pane, choose either Install Office as soon as possible, or Uninstall Office.](media/00f24a61-1848-40c0-b037-78d726c7d757.png)
  
5. Choose **Next** \> review the settings and then choose **Confirm**.
    
Office a 32 bit verrà installato o disinstallato automaticamente nei dispositivi degli utenti specificati dal gruppo o dai gruppi usati.
  
Verificare di poter aprire Gestione attività in un computer selezionato per l'installazione di Office e cercare il processo Microsoft Office a portata di clic.
  


