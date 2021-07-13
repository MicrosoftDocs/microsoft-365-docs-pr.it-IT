---
title: Abilitare i dispositivi Windows 10 aggiunti a un dominio per essere gestiti da Microsoft 365 per le aziende
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
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
description: Informazioni su come abilitare Microsoft 365 per proteggere i dispositivi Windows 10 aggiunti ad Active Directory in pochi passaggi.
ms.openlocfilehash: 9cc7ca01cec667465e9114083fecdc56ef4e7ce7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393380"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Abilitare i dispositivi Windows 10 aggiunti a un dominio per essere gestiti da Microsoft 365 Business Premium

Se l'organizzazione usa Windows Server Active Directory locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.
Per configurare questa protezione, è possibile implementare dispositivi aggiunti **ad Azure AD ibridi.** Questi dispositivi vengono aggiunti sia ad Active Directory locale che all'Azure Active Directory.

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>Watch: Configure Hybrid Azure Active Directory join

In questo video vengono descritti i passaggi per configurare questo scenario per lo scenario più comune, descritto anche nei passaggi seguenti.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Prima di iniziare

- Sincronizzare gli utenti con Azure AD con Azure AD Connessione.
- Completare la sincronizzazione Connessione unità organizzativa (OU) di Azure AD.
- Assicurati che tutti gli utenti di dominio sincronizzati siano in grado di Microsoft 365 Business Premium.

Per [la procedura, vedere Sincronizzare gli utenti](manage-domain-users.md) di dominio con Microsoft.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verificare l'autorità MDM in Intune

Vai a [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e nella pagina Microsoft Intune, seleziona Registrazione dispositivo **,** quindi nella pagina Panoramica assicurati che l'autorità **MDM** sia  **Intune**.

- Se **l'autorità MDM** **è None,** fai clic **sull'autorità MDM** per impostarla su **Intune.**
- Se **l'autorità MDM** è Microsoft Office 365 , vai **a** Dispositivi Registra dispositivi e usa la finestra di dialogo Aggiungi autorità MDM a destra per aggiungere l'autorità MDM di Intune (la finestra di dialogo Aggiungi autorità MDM è disponibile solo se l'autorità MDM è impostata su  >   Microsoft Office 365).    

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verificare che Azure AD sia abilitato per l'aggiunta di computer

- Passare all'interfaccia di amministrazione in e selezionare Azure Active Directory (selezionare Mostra tutto se Azure Active Directory non <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> è visibile)  nell'elenco Delle admin **center.** 
- **Nell'Azure Active Directory di amministrazione,** vai a **Azure Active Directory** , scegli **Dispositivi** e quindi **Impostazioni dispositivo**.
- Verificare **che gli utenti possano aggiungere dispositivi ad Azure AD** sia abilitato 
    1. Per abilitare tutti gli utenti, impostare su **Tutti**.
    2. Per abilitare utenti specifici, impostare su **Selezionato** per abilitare un gruppo specifico di utenti.
        - Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza.](../admin/create-groups/create-groups.md)
        - Scegliere **Seleziona gruppi per** abilitare l'ambito utente MDM per il gruppo di sicurezza.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verificare che Azure AD sia abilitato per MDM

- Passare all'interfaccia di amministrazione in e selezionare Gestione endpoint t (selezionare Mostra tutto se Endpoint Manager <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> non è visibile)   
- **Nell'Microsoft Endpoint Manager di amministrazione** passare a Dispositivi  >  **Windows**  >  **Windows registrazione**  >  **automatica**.
- Verificare che l'ambito utente MDM sia abilitato.

    1. Per registrare tutti i computer, impostare su **Tutti** per registrare automaticamente tutti i computer utente aggiunti ad Azure AD e ai nuovi computer quando gli utenti aggiungono un account aziendale a Windows.
    2. Impostare su **Some** per registrare i computer di un gruppo specifico di utenti.
        -  Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza.](../admin/create-groups/create-groups.md)
        -  Scegliere **Seleziona gruppi per** abilitare l'ambito utente MDM per il gruppo di sicurezza.

## <a name="4-create-the-required-resources"></a>4. Creare le risorse necessarie 

L'esecuzione delle attività necessarie per configurare l'aggiunta ibrida [di Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) è stata semplificata tramite l'utilizzo del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) disponibile nel modulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. Quando si richiama questo cmdlet, verrà creato e configurato il punto di connessione del servizio e i criteri di gruppo necessari.

È possibile installare questo modulo richiamando quanto segue da un'istanza di PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> È consigliabile installare questo modulo nel Windows Server che esegue Azure AD Connessione.

Per creare il punto di connessione del servizio e i criteri di gruppo necessari, verrà richiamato il cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Per eseguire questa attività, Microsoft 365 Business Premium le credenziali di amministratore globale. Quando si è pronti per creare le risorse, richiamare quanto segue:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Il primo comando stabilisce una connessione con il cloud Microsoft e, quando richiesto, specifica le credenziali Microsoft 365 Business Premium amministratore globale.

## <a name="5-link-the-group-policy"></a>5. Collegare Criteri di gruppo

1. Nella Console Gestione Criteri di gruppo fare clic con il pulsante destro del mouse sul percorso in cui si desidera collegare il criterio e scegliere Collega un oggetto Criteri di gruppo esistente *dal* menu di scelta rapida.
2. Selezionare il criterio creato nel passaggio precedente, quindi fare clic su **OK.**

## <a name="get-the-latest-administrative-templates"></a>Ottenere i modelli amministrativi più recenti

Se il criterio Abilita registrazione MDM automatica con le credenziali predefinite di **Azure AD** non è visualizzato, è possibile che l'ADMX non sia installato per Windows 10, versione 1803 o successiva. Per risolvere il problema, segui questi passaggi (Nota: l'ultimo file MDM.admx è compatibile con le versioni precedenti):

1. Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).
2. Installare il pacchetto in un controller di dominio.
3. Passare alla cartella **C:\Programmi (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2) a** seconda della versione dei modelli amministrativi.
4. Rinominare la **cartella Policy Definitions** nel percorso precedente in **PolicyDefinitions**.
5. Copiare **la cartella PolicyDefinitions** nella condivisione SYSVOL, per impostazione predefinita in **C:\Windows\SYSVOL\domain\Policies**.
   - Se si prevede di usare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.
6. Nel caso in cui siano presenti più controller di dominio, attendere la replica di SYSVOL per la disponibilità dei criteri. Questa procedura funzionerà anche per qualsiasi versione futura dei modelli amministrativi.

A questo punto dovrebbe essere possibile visualizzare il criterio Abilita registrazione **AUTOMATICA MDM usando le credenziali predefinite di Azure AD** disponibili.

## <a name="related-content"></a>Contenuto correlato

[Sincronizzare gli utenti di dominio Microsoft 365](manage-domain-users.md) (articolo)\
[Creare un gruppo nell'interfaccia di amministrazione](../admin/create-groups/create-groups.md) (articolo)\
[Esercitazione: Configurare l'Azure Active Directory ibrida per i domini gestiti](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (articolo)