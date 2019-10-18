---
title: Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Informazioni su come usare Windows Autopilot per configurare nuovi dispositivi Windows 10 per la propria azienda.
ms.openlocfilehash: d028ea3e902965d55c445dc3b3a02aa315201b25
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574789"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot

È possibile usare Windows Autopilot per configurare **nuovi** dispositivi Windows 10 per la propria azienda in modo che siano pronti per l'utilizzo produttivo non appena vengono conferiti ai dipendenti.
  
## <a name="device-requirements"></a>Requisiti dei dispositivi

I dispositivi devono soddisfare questi requisiti:
  
- Devono eseguire Windows 10 1703 o versione successiva.
    
- Devono essere nuovi dispositivi per i quali non è stata eseguita la Configurazione guidata di Windows.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Creare dispositivi e profili con la guida dettagliata

[![Label che consente di sapere che l'interfaccia di amministrazione sta cambiando ed è possibile trovare ulteriori dettagli su aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Se non sono stati ancora creati gruppi di dispositivi o profili, il modo migliore per iniziare consiste nell'eseguire la guida dettagliata. È anche possibile [aggiungere dispositivi](create-and-edit-autopilot-devices.md) e [assegnare profili](create-and-edit-autopilot-profiles.md) senza usare la guida. 
  
1. Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Nella barra di spostamento a sinistra scegliere **dispositivi** \> **Autopilot**.

    ![Nell'interfaccia di amministrazione scegliere dispositivi e quindi Autopilot.](media/AutoPilot.png)
  
2. Nella pagina **Autopilot** fare clic o toccare **Guida introduttiva**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Nella pagina **Carica file CSV con l'elenco dei dispositivi** passare a un percorso in cui è presente il file CSV preparato e quindi fare clic su **Apri** \> **Avanti**. Il file deve contenere tre intestazioni:
    
  - Colonna A: numero di serie del dispositivo
    
  - Colonna B: ID prodotto Windows
    
  - Colonna C: hash dell'hardware
    
    È possibile ottenere queste informazioni dal produttore dell'hardware o usare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) che consente di generare un file CSV. 
    
    Per altre informazioni, vedere [File CSV dell'elenco dei dispositivi](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). È anche possibile scaricare un file di esempio nella pagina **Carica file CSV con l'elenco dei dispositivi**. 
    
4. Nella pagina **Assegna un profilo** è possibile selezionare un profilo esistente o crearne uno nuovo. Se non esiste alcun profilo, verrà chiesto di crearne uno nuovo. 
    
    Un profilo è un raccolta di impostazioni che è possibile applicare a un singolo dispositivo o a un gruppo di dispositivi.
    
    Le funzionalità predefinite sono obbligatorie e verranno configurate automaticamente. Tali funzionalità sono:
    
  - La registrazione di Cortana, OneDrive e OEM viene ignorata.
    
  - È necessario creare un'esperienza di accesso con il marchio della società.
    
  - I dispositivi verranno connessi ad account Azure Active Directory e registrati automaticamente in modo da essere gestiti da Microsoft 365 Business.
    
    Per altre informazioni, vedere
    
    [Informazioni sulle impostazioni dei profili AutoPilot](autopilot-profile-settings.md) . 
    
5. Le altre impostazioni sono **Ignora impostazioni della privacy** e **Non consentire all'utente di diventare l'amministratore locale**. Per impostazione predefinita, entrambi queste impostazioni sono **disattivate**. 
    
    Scegliere **Avanti**.
    
6. La pagina **Fine** indica che il profilo creato (o scelto) verrà applicato al gruppo di dispositivi creati caricando l'elenco di dispositivi. Queste impostazioni diventeranno effettive al successivo accesso degli utenti del dispositivo. Scegliere **Chiudi**.
    