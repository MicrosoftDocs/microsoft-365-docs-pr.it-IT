---
title: Configurare le impostazioni di protezione delle app per i dispositivi Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Informazioni su come creare un criterio di gestione delle app e proteggere i file di lavoro nei dispositivi Windows 10.
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278179"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Configurare le impostazioni di protezione delle app per i dispositivi Windows 10

## <a name="create-an-app-management-policy-for-windows-10"></a>Creare criteri di gestione delle app per Windows 10

Se gli utenti hanno dispositivi Windows 10 personali in cui eseguono attività di lavoro, è possibile proteggere anche i dati in questi dispositivi.
  
1. Accedere all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=837890) con le credenziali di amministratore globale. Selezionare il riquadro **Amministratore** per passare all'interfaccia di amministrazione. 
    
2. Nella barra di spostamento sinistra fare clic su **criteri** \> **dispositivi** \> **Aggiungi**.

3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
    
4. In **Tipo di criterio** scegliere **Gestione applicazioni per Windows 10**.
    
5. Under ** Device type **, choose either **Personal** or **Company Owned**.
    
6. L'opzione **Crittografa i file di lavoro** viene attivata automaticamente. 
    
7. Impostare **Impedisci agli utenti di copiare dati aziendali in file personali e forzali a salvare i file di lavoro in OneDrive for Business** su **Sì** per evitare che gli utenti salvino i file di lavoro nei rispettivi PC. 
    
8. Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. Per ulteriori informazioni, vedere [available Settings](#available-settings). 
    
    È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita. 
    
9. Espandere **Recupera i dati nei dispositivi Windows** ed è consigliabile è **attivarla**.
    
    Prima di passare al percorso del certificato dell'agente di recupero dati, è necessario crearne uno. Per istruzioni, vedere [Creare e verificare un certificato dell'agente di recupero dati per EFS (Encrypting File System)](https://go.microsoft.com/fwlink/p/?linkid=853700).
    
    Per impostazione predefinita, i file di lavoro sono crittografati con una chiave segreta archiviata nel dispositivo e associata al profilo dell'utente. Solo l'utente può aprire e decrittografare il file. Tuttavia, se un dispositivo viene perso o se un utente viene rimosso, un file può restare bloccato in stato crittografato. Il certificato DRA (Data Recovery Agent) può essere usato da un amministratore per decrittografare il file.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Espandere **Proteggi altre posizioni di rete e sul cloud** per aggiungere ulteriori domini o posizioni di SharePoint Online per assicurare la protezione dei file in tutte le app incluse nell'elenco. Se è necessario immettere più voci per uno dei campi, usare il punto e virgola (;) per separare le voci. 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.
    
12. Infine, scegliere **Aggiungi** per salvare il criterio e assegnarlo ai dispositivi. 
    
## <a name="available-settings"></a>Impostazioni disponibili

Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office.
  
Per altre informazioni, vedere [Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune](map-protection-features-to-intune-settings.md).
  
|**Impostazione**|**Descrizione**|
|:-----|:-----|
|Richiedi un PIN o l'impronta digitale per accedere alle app di Office  <br/> |Se questa impostazione è **attivata**, gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di potere usare le app di Office nel dispositivo mobile.  <br/> |
|Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente  <br/> |Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.  <br/> |
|Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per  <br/> |Questa impostazione determina per quanto tempo un utente può rimanere inattivo prima che venga richiesta la ripetizione dell'accesso.  <br/> |
   

