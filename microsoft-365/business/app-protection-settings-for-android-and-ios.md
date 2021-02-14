---
title: Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS
f1.keywords:
- NOCSH
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Scopri come creare, modificare o eliminare criteri di gestione delle app e proteggere i file di lavoro nei dispositivi Android o iOS.
ms.openlocfilehash: 67e7aaec5ff5a28f1e2d489913246c1c15c2f7b6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471200"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS

Questo articolo si applica a Microsoft 365 Business Premium.

## <a name="create-an-app-management-policy"></a>Creare un criterio di gestione delle app

1. Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>. 
    
2. Nel riquadro di spostamento sinistro scegliere **Aggiungi** \> **criteri** \> **dispositivi.**
  
3. Nel riquadro **Aggiungi criterio** immettere un nome univoco per il criterio. 
    
4. In **Tipo di criterio** scegliere Gestione applicazioni per **Android** o Gestione applicazioni **per iOS,** a seconda del set di criteri che si desidera creare. 
    
5. Espandere **Proteggi i file di lavoro quando i dispositivi vengono smarriti o rubati** e Gestire il modo in cui gli utenti **accedono ai file di Office nei dispositivi mobili.** Configurare le impostazioni come si desidera. **La modalità di accesso degli utenti** ai file di Office nei  dispositivi mobili è disattivata per impostazione predefinita, ma è consigliabile attivarla e accettare i valori predefiniti.  Per ulteriori informazioni, vedere [Impostazioni disponibili.](#available-settings) 
    
    È sempre possibile usare il collegamento **Ripristina impostazioni predefinite** per ripristinare l'impostazione predefinita. 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Decidere quindi **chi otterrà queste impostazioni?** Se non si desidera utilizzare  il gruppo di sicurezza Predefinito Tutti gli utenti, **scegliere** Cambia , scegliere i gruppi di sicurezza che ottengono queste \> **impostazioni Selezionare.**
    
7. Infine, scegliere **Fatto** per salvare il criterio e assegnarlo ai dispositivi. 
    
## <a name="edit-an-app-management-policy"></a>Modificare un criterio di gestione delle app

1. Nella scheda **Criteri** scegliere **Modifica criterio.**
    
2. Nel riquadro **Modifica criterio** scegliere il criterio da modificare. 
    
3. Scegliere **Modifica** accanto a ogni impostazione per modificare i valori corrispondenti nel criterio. Quando si modifica un valore, questo viene salvato automaticamente nel criterio.
    
4. Al termine, chiudere il riquadro **Modifica** criteri. 
    
## <a name="delete-an-app-management-policy"></a>Eliminare un criterio di gestione delle app

1. Nella pagina **Criteri** scegliere un criterio e quindi **Elimina.**
    
2. Nel riquadro **Elimina criterio** scegliere **Conferma** per eliminare il criterio o i criteri scelti. 
    
## <a name="available-settings"></a>Impostazioni disponibili

Nelle tabelle seguenti vengono fornite informazioni dettagliate sulle impostazioni disponibili per proteggere i file di lavoro nei dispositivi e sulle impostazioni che controllano il modo in cui gli utenti accedono ai file di Office dai dispositivi mobili.
  
 Per altre informazioni, vedere Come vengono mappate le funzionalità di protezione [in Microsoft 365 Business Premium alle impostazioni di Intune.](map-protection-features-to-intune-settings.md) 
  
### <a name="settings-that-protect-work-files"></a>Impostazioni per la protezione dei file di lavoro

Le impostazioni seguenti sono disponibili per la protezione dei file di lavoro in caso di perdita o di furto del dispositivo di un utente:
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Elimina i file di lavoro dai dispositivi inattivi dopo questo numero di giorni  <br/> |Se un dispositivo non viene usato per il numero di giorni specificato qui, tutti i file di lavoro archiviati nel dispositivo verranno eliminati automaticamente.  <br/> |
|Forza gli utenti a salvare tutti i file di lavoro in OneDrive for Business  <br/> |Se questa impostazione è **attivata,** l'unico percorso di salvataggio disponibile per i file di lavoro è OneDrive for Business.  <br/> |
|Crittografa i file di lavoro  <br/> |Mantenere **attivata** questa impostazione in modo che i file di lavoro siano protetti dalla crittografia. Anche se il dispositivo viene smarrito o rubato, nessuno può leggere i dati aziendali.  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili

Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:
  
|||
|:-----|:-----|
|Impostazione  <br/> |Descrizione  <br/> |
|Richiedi un PIN o l'impronta digitale per accedere alle app di Office  <br/> |Se questa impostazione è **Attivata,** gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di poter usare le app di Office nei dispositivi mobili.<br/> |
|Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente  <br/> |Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.  <br/> |
|Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per  <br/> |Questa impostazione determina per quanto tempo un utente può essere inattivo prima che venga richiesto di accedere di nuovo.  <br/> |
|Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted  <br/> |È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. L'utente può quindi modificare il sistema operativo, rendendo il dispositivo più vulnerabile a malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  <br/> |
|Non consentire agli utenti di copiare il contenuto dalle app di Office nelle app personali  <br/> |Questa operazione è consentita per impostazione predefinita, ma se l'impostazione è **attivata** l'utente potrebbe copiare le informazioni di un file di lavoro in un file personale. Se l'impostazione è **disattivata**, l'utente non potrà copiare informazioni da un account aziendale a un'app personale o un account personale.  <br/> |
