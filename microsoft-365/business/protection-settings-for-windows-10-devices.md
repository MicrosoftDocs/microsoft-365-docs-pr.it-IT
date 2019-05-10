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
ms.openlocfilehash: f649454417dceae05255df6b37760af99c0b8d4f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660386"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>Configurare le impostazioni di protezione delle app per i dispositivi Windows 10

## <a name="create-an-app-management-policy-for-windows-10"></a>Creare criteri di gestione delle app per Windows 10

Se gli utenti hanno dispositivi Windows 10 personali in cui eseguono attività di lavoro, è possibile proteggere anche i dati in questi dispositivi.
  
1. Accedere all'interfaccia di amministrazione all' <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>indirizzo. 
    
2. Nella barra di spostamento sinistra fare clic su **criteri** \> **dispositivi** \> **Aggiungi**.

3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
    
4. In **Tipo di criterio** scegliere **Gestione applicazioni per Windows 10**.
    
5. In **tipo di dispositivo**scegliere **personale** o di **proprietà dell'azienda**.
    
6. L'opzione **Crittografa i file di lavoro** viene attivata automaticamente. 
    
7. Impostare **Impedisci agli utenti di copiare dati aziendali in file personali e forzali a salvare i file di lavoro in OneDrive for Business** su **Sì** per evitare che gli utenti salvino i file di lavoro nei rispettivi PC. 
    
9. Espandere **Recupera i dati nei dispositivi Windows** ed è consigliabile è **attivarla**.
    
    Prima di passare al percorso del certificato dell'agente di recupero dati, è necessario crearne uno. Per istruzioni, vedere [Creare e verificare un certificato dell'agente di recupero dati per EFS (Encrypting File System)](https://go.microsoft.com/fwlink/p/?linkid=853700).
    
    Per impostazione predefinita, i file di lavoro sono crittografati con una chiave segreta archiviata nel dispositivo e associata al profilo dell'utente. Solo l'utente può aprire e decrittografare il file. Tuttavia, se un dispositivo viene perso o se un utente viene rimosso, un file può restare bloccato in stato crittografato. Il certificato DRA (Data Recovery Agent) può essere usato da un amministratore per decrittografare il file.
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Espandere **Proteggi altre posizioni di rete e sul cloud** per aggiungere ulteriori domini o posizioni di SharePoint Online per assicurare la protezione dei file in tutte le app incluse nell'elenco. Se è necessario immettere più voci per uno dei campi, usare il punto e virgola (;) per separare le voci.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.
    
12. Infine, scegliere **Aggiungi** per salvare il criterio e assegnarlo ai dispositivi. 