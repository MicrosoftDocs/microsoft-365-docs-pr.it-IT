---
title: Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informazioni su come creare, modificare o eliminare un criterio di gestione app e proteggere i file di lavoro nei dispositivi Android o iOS.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868849"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS

## <a name="create-an-app-management-policy"></a>Creare un criterio di gestione delle app

1. Accedere a [Microsoft 365 Business](https://portal.office.com) con le credenziali di amministratore globale. 
    
2. Nell'interfaccia di amministrazione scegliere **Aggiungi criterio** nella scheda **Criteri dispositivi**.
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
    
4. In **Tipo di criterio** scegliere **Gestione applicazioni per Android** o **Gestione applicazioni per iOS** a seconda del set di criteri che si vuole creare. 
    
5. Espandere **protezione lavoro file quando dispositivi sono perduti o rubati** e **gestire l'accesso al file di Office su dispositivi mobili** \> configurare le impostazioni come desiderato. **Gestire l'accesso al file di Office su dispositivi mobili** è **disattivata** per impostazione predefinita, ma è consigliabile **attivarlo** e accettare i valori predefiniti. Per ulteriori informazioni, vedere [impostazioni disponibili](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) . 
    
    È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita. 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. In **Chi otterrà queste impostazioni?** specificare i destinatari. Se non si vuole usare il gruppo di sicurezza predefinito **Tutti gli utenti**, scegliere **Modifica**, scegliere i gruppi di sicurezza che riceveranno queste impostazioni \> **Seleziona**.
    
7. Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi. 
    
## <a name="edit-an-app-management-policy"></a>Modificare un criterio di gestione delle app

1. Nella scheda **criteri** , selezionare **Modifica criterio**.
    
2. Nel riquadro **Modifica criterio** scegliere il criterio da modificare. 
    
3. Scegliere **Modifica** accanto a ogni impostazione per modificare i valori corrispondenti nel criterio. Quando si modifica un valore, questo viene automaticamente salvato nel criterio. 
    
4. Al termine, chiudere il riquadro **Modifica criterio**. 
    
## <a name="delete-an-app-management-policy"></a>Eliminare un criterio di gestione delle app

1. Nella scheda **Criteri** scegliere **Elimina criterio**.
    
2. Nel riquadro **Elimina criterio** scegliere i criteri da eliminare \> **Seleziona**, quindi **Conferma** per eliminare il criterio o i criteri scelti. 
    
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
|Consenti agli utenti di copiare contenuti dalle app di Office in quelle personali  <br/> |È consentire questa operazione per impostazione predefinita, ma se l'impostazione è **attivata**, l'utente può copiare le informazioni in un file di lavoro in un file personali. Se l'impostazione è **disattivata**, l'utente sarà possibile copiare le informazioni da un account di lavoro in una app personali o in account personale.<br/> |
   

  

