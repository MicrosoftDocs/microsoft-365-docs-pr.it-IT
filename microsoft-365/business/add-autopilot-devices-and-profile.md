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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Scopri come usare Windows AutoPilot per configurare nuovi dispositivi Windows 10 per la tua azienda in modo che siano pronti per l'uso da parte dei dipendenti.
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099751"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot

Puoi usare Windows AutoPilot per configurare nuovi dispositivi **Windows** 10 per la tua azienda in modo che siano pronti per l'uso quando li consegni ai dipendenti.
  
## <a name="device-requirements"></a>Requisiti dei dispositivi

I dispositivi devono soddisfare questi requisiti:
  
- Windows 10 versione 1703 o successiva
    
- Nuovi dispositivi che non hanno avuto esperienza di Configurazione guidata di Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Creare dispositivi e profili con la guida dettagliata

[![Etichetta per comunicare all'utente che l'interfaccia di amministrazione sta cambiando ed è possibile trovare altre informazioni alla pagina aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Se non hai ancora creato gruppi di dispositivi o profili, il modo migliore per iniziare consiste nell'usare la guida dettagliata. Puoi anche aggiungere [dispositivi e](create-and-edit-autopilot-devices.md) [assegnare](create-and-edit-autopilot-profiles.md) profili senza usare la guida. 
  
1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Nel riquadro di spostamento sinistro scegliere **Dispositivi** \> **AutoPilot.**

    ![Nell'interfaccia di amministrazione scegliere i dispositivi e quindi AutoPilot.](../media/AutoPilot.png)
  
2. Nella pagina **AutoPilot** tocca o fai clic su **Start Guide.**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Nella pagina **Carica file CSV con l'elenco dei** dispositivi passare a un percorso in cui è stato preparato il file . Csv file, then **Open** \> **Next**. Il file deve avere tre intestazioni:
    
    - Colonna A: numero di serie del dispositivo
    
    - Colonna B: ID prodotto Windows
    
    - Colonna C: hash dell'hardware
    
    È possibile ottenere queste informazioni dal fornitore dell'hardware oppure utilizzare lo [script Di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV. 
    
    Per altre informazioni, vedere [File CSV dell'elenco dei dispositivi](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). È anche possibile scaricare un file di esempio nella pagina **Carica file CSV con l'elenco dei dispositivi**. 
    
> [!NOTE]
> Questo script usa WMI per recuperare le proprietà necessarie a un cliente per registrare un dispositivo con Windows Autopilot. Tieni presente che è normale che il file CSV risultante non raccogli un valore PKID (Windows Product ID) poiché non è necessario per registrare un dispositivo e la PKID è NULL nel file CSV di output. Verranno popolati solo il numero di serie e l'hash hardware.
    
4. Nella pagina **Assegna un profilo** è possibile selezionare un profilo esistente o crearne uno nuovo. Se non ne hai ancora uno, ti verrà richiesto di crearne uno. 
    
    Un profilo è un raccolta di impostazioni che è possibile applicare a un singolo dispositivo o a un gruppo di dispositivi.
    
    Le funzionalità predefinite sono obbligatorie e vengono impostate automaticamente. Tali funzionalità sono:
    
    - Ignora la registrazione di Cortana, OneDrive e OEM.
    
    - È necessario creare un'esperienza di accesso con il marchio della società.
    
    - Connettere i dispositivi agli account Azure Active Directory e registrarli automaticamente per la gestione di Microsoft 365 Business Premium.
    
    Per ulteriori informazioni, vedere [Informazioni sulle impostazioni del profilo AutoPilot.](autopilot-profile-settings.md) 
    
5. Le altre impostazioni sono **Ignora impostazioni della privacy** e **Non consentire all'utente di diventare l'amministratore locale**. Per impostazione predefinita, entrambi queste impostazioni sono **disattivate**. 
    
    Scegliere **Avanti**.
    
6. Il termine indica che il profilo creato (o scelto) verrà applicato al gruppo di dispositivi creato caricando **l'elenco** dei dispositivi. Le impostazioni saranno effettive al successivo accesso degli utenti del dispositivo. Scegliere **Chiudi**.
    
