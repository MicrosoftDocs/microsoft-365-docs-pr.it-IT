---
title: Modificare o impostare le impostazioni di protezione delle applicazioni per Windows 10 dispositivi
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Scopri come creare o modificare i criteri di gestione delle app e proteggere i file di lavoro nei dispositivi Windows 10 personali degli utenti.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580015"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>Impostare o modificare le impostazioni di protezione delle applicazioni Windows 10 dispositivi

Questo articolo si applica a Microsoft 365 Business Premium.

## <a name="edit-an-app-management-policy-for-windows-10"></a>Modificare un criterio di gestione delle app per Windows 10

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.     
2. Nel riquadro di spostamento sinistro scegliere **Criteri** \> **dispositivi.**
1. Scegli un criterio Windows'app esistente e quindi **Modifica**.
1. Scegliere **Modifica** accanto a un'impostazione che si desidera modificare e quindi **Salva.**

## <a name="create-an-app-management-policy-for-windows-10"></a>Creare criteri di gestione delle app per Windows 10

Se gli utenti hanno dispositivi Windows 10 personali in cui eseguono attività di lavoro, è possibile proteggere anche i dati in questi dispositivi.
  
1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
2. Nel riquadro di spostamento sinistro scegliere **Criteri** \> **dispositivi** \> **Aggiungi**.
3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
4. In **Tipo di criterio** scegliere **Gestione applicazioni per Windows 10**.
5. In **Tipo di dispositivo** scegliere Personale o Proprietà **società.** 
6. L'opzione **Crittografa i file di lavoro** viene attivata automaticamente. 
7. Impostare **Impedisci agli utenti di copiare dati aziendali in file personali e forzali a salvare i file di lavoro in OneDrive for Business** su **Sì** per evitare che gli utenti salvino i file di lavoro nei rispettivi PC. 
9. Espandi **Recupera dati in Windows dispositivi**. È consigliabile **attivarlo.**
    Prima di passare al percorso del certificato dell'agente di recupero dati, è necessario crearne uno. Per istruzioni, vedere [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).
    
    Per impostazione predefinita, i file di lavoro sono crittografati con una chiave segreta archiviata nel dispositivo e associata al profilo dell'utente. Solo l'utente può aprire e decrittografare il file. Tuttavia, se un dispositivo viene perso o se un utente viene rimosso, un file può restare bloccato in stato crittografato. Un amministratore può utilizzare il certificato dell'agente di recupero dati (DRA) per decrittografare il file.
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. Espandi **Proteggi percorsi di rete** e cloud aggiuntivi se vuoi aggiungere altri domini o percorsi di SharePoint Online per assicurarti che i file in tutte le app elencate siano protetti. Se è necessario immettere più voci per uno dei campi, usare il punto e virgola (;) per separare le voci.
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.
12. Infine, scegliere **Aggiungi** per salvare il criterio e assegnarlo ai dispositivi.