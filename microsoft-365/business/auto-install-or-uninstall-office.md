---
title: Installare o disinstallare automaticamente Office nei dispositivi Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: cbc6bfe5-565a-4fb8-95f0-b06e7b74ac46
description: "Installare o disinstallare Office nei dispositivi Windows 10 dall'interfaccia di amministrazione di Microsoft 365 business. "
ms.openlocfilehash: d82ab8292211d1adacba732922bf693dd2157ad6
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287536"
---
# <a name="automatically-install-or-uninstall-office-on-windows-10-devices"></a>Installare o disinstallare automaticamente Office nei dispositivi Windows 10

[![Label che consente di sapere che l'interfaccia di amministrazione sta cambiando ed è possibile trovare ulteriori dettagli su aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

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
  


