---
title: Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informazioni su come creare, modificare o eliminare un criterio di gestione delle app e proteggere i file di lavoro su dispositivi Android o iOS.
ms.openlocfilehash: a829cfbcb3209313a53e0a1406f5252d3d5580d8
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574739"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS

![Banner che puntano https://aka.ms/aboutM365previewa.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>Creare un criterio di gestione delle app

1. Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Nel NAV sinistro, scegliere **Devices** \> **** \> **Add**.
  
3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
    
4. In **Tipo di criterio** scegliere **Gestione applicazioni per Android** o **Gestione applicazioni per iOS** a seconda del set di criteri che si vuole creare. 
    
5. Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. Per ulteriori informazioni, vedere [available Settings](#available-settings) . 
    
    È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.
    
7. Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi. 
    
## <a name="edit-an-app-management-policy"></a>Modificare un criterio di gestione delle app

1. Nella scheda **criteri** scegliere **modifica criterio**.
    
2. Nel riquadro **Modifica criterio** scegliere il criterio da modificare. 
    
3. Scegliere **Modifica** accanto a ogni impostazione per modificare i valori corrispondenti nel criterio. Quando si modifica un valore, questo viene automaticamente salvato nel criterio. 
    
4. Al termine, chiudere il riquadro **Modifica criterio**. 
    
## <a name="delete-an-app-management-policy"></a>Eliminare un criterio di gestione delle app

1. Nella pagina **criteri** scegliere un criterio e quindi **Elimina**.
    
2. Nel riquadro **Elimina criteri** scegliere **conferma** per eliminare i criteri o i criteri scelti. 
    
## <a name="available-settings"></a>Impostazioni disponibili

Le tabelle seguenti forniscono informazioni dettagliate sulle impostazioni disponibili per proteggere i file di lavoro nei dispositivi e sulle impostazioni che controllano il modo in cui gli utenti accedono ai file di Office dai dispositivi mobili.
  
 Per altre informazioni, vedere [Corrispondenza tra le caratteristiche di protezione in Microsoft 365 Business e le impostazioni di Intune](map-protection-features-to-intune-settings.md). 
  
### <a name="settings-that-protect-work-files"></a>Impostazioni per la protezione dei file di lavoro

Le impostazioni seguenti sono disponibili per la protezione dei file di lavoro in caso di perdita o di furto del dispositivo di un utente:
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Elimina i file di lavoro dai dispositivi inattivi dopo questo numero di giorni  <br/> |Se un dispositivo non viene usato per il numero di giorni specificato qui, eventuali file di lavoro archiviati nel dispositivo verranno eliminati automaticamente.  <br/> |
|Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business  <br/> |Se questa impostazione è **attivata**, l'unico percorso disponibile per il salvataggio dei file di lavoro sarà OneDrive for Business.  <br/> |
|Crittografa i file di lavoro  <br/> |Mantenere **attivata** questa impostazione in modo che i file di lavoro siano protetti dalla crittografia. Anche in caso di perdita o di furto del dispositivo, nessuno sarà in grado di leggere i dati aziendali.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili

Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Richiedi un PIN o l'impronta digitale per accedere alle app di Office  <br/> |Se questa impostazione è **attivata**, gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di potere usare le app di Office nel dispositivo mobile.  <br/> |
|Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente  <br/> |Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.  <br/> |
|Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per  <br/> |Questa impostazione determina per quanto tempo un utente può rimanere inattivo prima che venga richiesta la ripetizione dell'accesso.  <br/> |
|Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted  <br/> |È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. L'utente può quindi modificare il sistema operativo, rendendo il dispositivo più vulnerabile a malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  <br/> |
|Consenti agli utenti di copiare contenuti dalle app di Office in quelle personali  <br/> |Questa operazione è consentita per impostazione predefinita, ma se l'impostazione è **attivata** l'utente potrebbe copiare le informazioni di un file di lavoro in un file personale. Se l'impostazione è **disattivata**, l'utente non potrà copiare informazioni da un account aziendale a un'app personale o un account personale.  <br/> |
   

  

