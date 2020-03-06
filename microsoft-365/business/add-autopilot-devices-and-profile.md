---
title: Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot
f1.keywords:
- NOCSH
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Informazioni su come usare Windows Autopilot per configurare nuovi dispositivi Windows 10 per la propria azienda in modo che siano pronti per l'utilizzo dei dipendenti.
ms.openlocfilehash: 8449d5a3672a20b0cd1ba61bbda863073138c04c
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550388"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot

È possibile usare Windows Autopilot per configurare **nuovi** dispositivi Windows 10 per la propria azienda in modo che siano pronti per l'uso quando vengono conferiti ai dipendenti.
  
## <a name="device-requirements"></a>Requisiti dei dispositivi

I dispositivi devono soddisfare i requisiti seguenti:
  
- Windows 10, versione 1703 o successiva
    
- Nuovi dispositivi che non sono stati eseguiti tramite Windows out-of-Box Experience
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Creare dispositivi e profili con la guida dettagliata

[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Se non è ancora stato creato un gruppo di dispositivi o profili, il modo migliore per iniziare è quello di utilizzare la guida dettagliata. È inoltre possibile [aggiungere i dispositivi](create-and-edit-autopilot-devices.md) e [assegnargli i profili](create-and-edit-autopilot-profiles.md) senza utilizzare la guida. 
  
1. Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Nel riquadro di spostamento a sinistra, scegliere **dispositivi** \> **Autopilot**.

    ![Nell'interfaccia di amministrazione, scegliere dispositivi e quindi Autopilot.](../media/AutoPilot.png)
  
2. Nella pagina **Autopilot** fare clic o toccare **Guida introduttiva**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Nella pagina **Carica file CSV con l'elenco dei dispositivi** , passare a una posizione in cui si dispone del preparato. File CSV, quindi **Apri** \> **Avanti**. Il file deve disporre di tre intestazioni:
    
    - Colonna A: numero di serie del dispositivo
    
    - Colonna B: ID prodotto Windows
    
    - Colonna C: hash dell'hardware
    
    È possibile ottenere queste informazioni dal fornitore dell'hardware oppure è possibile utilizzare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV. 
    
    Per altre informazioni, vedere [File CSV dell'elenco dei dispositivi](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). È anche possibile scaricare un file di esempio nella pagina **Carica file CSV con l'elenco dei dispositivi**. 
    
4. Nella pagina **assegna un profilo** è possibile scegliere un profilo esistente oppure crearne uno nuovo. Se non si dispone ancora di un utente, verrà richiesto di crearne uno. 
    
    Un profilo è un raccolta di impostazioni che è possibile applicare a un singolo dispositivo o a un gruppo di dispositivi.
    
    Le funzionalità predefinite sono obbligatorie e vengono impostate automaticamente. Tali funzionalità sono:
    
    - Ignorare la registrazione di Cortana, OneDrive e OEM.
    
    - È necessario creare un'esperienza di accesso con il marchio della società.
    
    - Connettere i dispositivi agli account di Azure Active Directory e registrarli automaticamente per essere gestiti da Microsoft 365 business.
    
    Per ulteriori informazioni, vedere [informazioni sulle impostazioni del profilo Autopilot](autopilot-profile-settings.md). 
    
5. Le altre impostazioni sono **Ignora impostazioni della privacy** e **Non consentire all'utente di diventare l'amministratore locale**. Per impostazione predefinita, entrambi queste impostazioni sono **disattivate**. 
    
    Scegliere **Avanti**.
    
6. L' **operazione è stata eseguita** indica che il profilo creato (o scelto) verrà applicato al gruppo di dispositivi creato caricando l'elenco dei dispositivi. Le impostazioni saranno attive quando gli utenti del dispositivo avranno accesso successivo. Scegliere **Chiudi**.
    
