---
title: Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Scopri come usare Windows AutoPilot per configurare nuovi dispositivi Windows 10 per la tua azienda in modo che siano pronti per l'uso da parte dei dipendenti.
ms.openlocfilehash: f160ddcd1e41bd44c908ecc8bbd30a9819f76902
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393440"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Usare la guida dettagliata per aggiungere profili e dispositivi Autopilot

Puoi usare Windows AutoPilot per configurare nuovi dispositivi **Windows 10** per la tua azienda in modo che siano pronti per l'uso quando li forni ai dipendenti.
  
## <a name="device-requirements"></a>Requisiti dei dispositivi

I dispositivi devono soddisfare questi requisiti:
  
- Windows 10 versione 1703 o successiva
    
- Nuovi dispositivi che non sono stati Windows'esperienza out-of-box
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Creare dispositivi e profili con la guida dettagliata

Se non hai ancora creato gruppi di dispositivi o profili, il modo migliore per iniziare consiste nell'usare la guida dettagliata. Puoi anche aggiungere [dispositivi](create-and-edit-autopilot-devices.md) e [assegnare](create-and-edit-autopilot-profiles.md) profili senza usare la guida. 
  
1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. Nel riquadro di spostamento sinistro scegliere **Dispositivi** \> **AutoPilot.**

    ![Nell'interfaccia di amministrazione scegli i dispositivi e quindi AutoPilot.](../media/AutoPilot.png)
  
2. Nella pagina **AutoPilot** toccare o fare clic su **Guida iniziale.**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Nella pagina Upload .csv file con **l'elenco** dei dispositivi passare a un percorso in cui si dispone del file .CSV preparato, quindi **aprire** \> **Avanti**. Il file deve avere tre intestazioni:
    
    - Colonna A: numero di serie del dispositivo
    
    - Colonna B: ID prodotto Windows
    
    - Colonna C: hash dell'hardware
    
    È possibile ottenere queste informazioni dal fornitore dell'hardware oppure è possibile utilizzare lo [script di PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) per generare un file CSV. 
    
    Per altre informazioni, vedere [File CSV dell'elenco dei dispositivi](../admin/misc/device-list.md). È anche possibile scaricare un file di esempio nella pagina **Carica file CSV con l'elenco dei dispositivi**. 
    
> [!NOTE]
> Questo script utilizza WMI per recuperare le proprietà necessarie a un cliente per registrare un dispositivo con Windows Autopilot. Tenere presente che è normale che il file CSV risultante non raccogli un valore PKID (Product ID) di Windows poiché non è necessario registrare un dispositivo e il valore PKID null nel file CSV di output è completamente valido. Verranno popolati solo il numero di serie e l'hash hardware.
    
4. Nella pagina **Assegna un profilo** è possibile selezionare un profilo esistente o crearne uno nuovo. Se non ne hai ancora uno, ti verrà richiesto di crearne uno. 
    
    Un profilo è un raccolta di impostazioni che è possibile applicare a un singolo dispositivo o a un gruppo di dispositivi.
    
    Le funzionalità predefinite sono obbligatorie e vengono impostate automaticamente. Tali funzionalità sono:
    
    - Ignorare Cortana, OneDrive e la registrazione OEM.
    
    - È necessario creare un'esperienza di accesso con il marchio della società.
    
    - Connessione i dispositivi per Azure Active Directory account e registrarli automaticamente per essere gestiti da Microsoft 365 Business Premium.
    
    Per ulteriori informazioni, vedere [Informazioni sulle impostazioni del profilo AutoPilot.](autopilot-profile-settings.md) 
    
5. Le altre impostazioni sono **Ignora impostazioni della privacy** e **Non consentire all'utente di diventare l'amministratore locale**. Per impostazione predefinita, entrambi queste impostazioni sono **disattivate**. 
    
    Scegliere **Avanti**.
    
6. Il termine indica che il profilo creato (o scelto) verrà applicato al gruppo di dispositivi creato caricando **l'elenco** dei dispositivi. Le impostazioni saranno effettive al successivo accesso degli utenti del dispositivo. Scegliere **Chiudi**.

## <a name="related-content"></a>Contenuto correlato

[Informazioni sulle impostazioni del profilo AutoPilot](autopilot-profile-settings.md) (articolo)\
[Opzioni per proteggere i dispositivi e i dati dell'app](../admin/devices/choose-device-security.md) (articolo)
