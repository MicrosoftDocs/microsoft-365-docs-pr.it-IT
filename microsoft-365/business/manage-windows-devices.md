---
title: Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 for business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
description: Informazioni su come consentire a Microsoft 365 di proteggere i dispositivi Windows 10 locali con l'aggiunta di Active Directory in pochi passaggi.
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560844"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 Business Premium

Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.
Per impostare questa protezione, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**. Questi dispositivi sono associati sia a Active Directory locale che a Azure Active Directory.

In questo video vengono illustrati i passaggi da eseguire per la configurazione dello scenario più comune, che è anche dettagliato nei passaggi successivi.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Prima di iniziare, eseguire la procedura seguente:
- Sincronizzare gli utenti con Azure ad con Azure ad Connect.
- Completare la sincronizzazione di Azure AD Connect unità organizzativa (OU).
- Assicurarsi che tutti gli utenti di dominio sincronizzati dispongano delle licenze per Microsoft 365 Business Premium.

Per la procedura, vedere [sincronizzare gli utenti di dominio a Microsoft](manage-domain-users.md) .

## <a name="1-verify-mdm-authority-in-intune"></a>1. verificare l'autorità MDM in Intune

Andare a [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e nella pagina Microsoft Intune, selezionare **registrazione dispositivo**, quindi nella pagina **Panoramica** verificare che l' **autorità MDM** sia **Intune**.

- Se l' **autorità MDM** è **None**, fare clic sull' **autorità MDM** per impostarla su **Intune**.
- Se l' **autorità MDM** è **Microsoft Office 365**, passare **a dispositivi di**  >  **registrazione** e utilizzare la finestra di dialogo **Aggiungi autorità MDM** sulla destra per aggiungere l'autorità di **MDM** (la finestra di dialogo **Aggiungi autorità MDM** è disponibile solo se l' **autorità MDM** è impostata su Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verificare che Azure AD sia abilitato per l'aggiunta di computer

- Accedere all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare **Azure Active Directory** (selezionare Mostra tutto se Azure Active Directory non è visibile) nell'elenco **admin** Centers. 
- Nell'interfaccia di **amministrazione di Azure Active Directory**passare a **Azure Active Directory** , scegliere **dispositivi** e quindi **Impostazioni dispositivo**.
- Verificare**che gli utenti possano aggiungere dispositivi ad Azure ad** sia abilitato 
    1. Per abilitare tutti gli utenti, impostare su **tutti**.
    2. Per abilitare utenti specifici, impostare su **selezionato** per abilitare un gruppo specifico di utenti.
        - Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).
        - Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verificare che Azure AD sia abilitato per MDM

- Andare all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selezionare Seleziona gli amministratori di **endpoint**t (selezionare **Mostra tutto** se **Endpoint Manager** non è visibile)
- Nell'interfaccia di **amministrazione di Microsoft Endpoint Manager**passare alla **Devices**  >  **Windows**  >  **Windows Enrollment**  >  **registrazione automatica**dei dispositivi Windows Windows.
- Verificare che l'ambito dell'utente MDM sia abilitato.

    1. Per registrare tutti i computer, impostare su **tutti** per la registrazione automatica di tutti i computer degli utenti aggiunti a Azure ad e nuovi computer quando gli utenti aggiungono un account di lavoro a Windows.
    2. Impostato su **alcuni** per registrare i computer di un gruppo specifico di utenti.
        -  Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza](../admin/create-groups/create-groups.md).
        -  Scegliere **Seleziona gruppi** per abilitare l'ambito degli utenti MDM per il gruppo di sicurezza.

## <a name="4-create-the-required-resources"></a>4. creare le risorse necessarie 

L'esecuzione delle attività necessarie per la [configurazione di Azure ad join ibrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) è stata semplificata mediante l'utilizzo del cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) trovato nel modulo di [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell. Quando si richiama questo cmdlet, vengono creati e configurati il punto di connessione del servizio e i criteri di gruppo necessari.

È possibile installare questo modulo richiamando quanto segue da un'istanza di PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> È consigliabile installare questo modulo nel Windows Server che esegue Azure AD Connect.

Per creare il punto di connessione del servizio e i criteri di gruppo necessari, verrà richiamato il cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) . Durante l'esecuzione di questa attività, sono necessarie le credenziali di amministratore globale di Microsoft 365 Business Premium. Quando si è pronti per creare le risorse, richiamare le operazioni seguenti:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Il primo comando consentirà di stabilire una connessione con il cloud Microsoft e, quando richiesto, specificare le credenziali di amministratore globale di Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. Collegare i criteri di gruppo

1. Nella console Gestione criteri di gruppo fare clic con il pulsante destro del mouse sul percorso in cui si desidera collegare il criterio e selezionare *collega un oggetto Criteri* di controllo esistente dal menu di scelta rapida.
2. Selezionare il criterio creato nel passaggio precedente, quindi fare clic su **OK**.

## <a name="get-the-latest-administrative-templates"></a>Ottenere i modelli amministrativi più recenti

Se il criterio non viene visualizzato, **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad predefinite**, potrebbe essere perché non è installato ADMX per Windows 10, versione 1803, versione 1809 o versione 1903. Per risolvere il problema, attenersi alla seguente procedura (Nota: l'ultima MDM. admx è compatibile con le versioni precedenti):

1.  Download: [modelli amministrativi (con estensione ADMX) per l'aggiornamento a Windows 10 maggio 2019 (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Installare il pacchetto nel controller di dominio primario (PDC).
3.  Spostarsi, a seconda della versione della cartella: **c:\Programmi (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.
4.  Rinominare la cartella delle **definizioni dei criteri** nel percorso precedente in **PolicyDefinitions**.
5.  Copiare la cartella **PolicyDefinitions** in **C:\Windows\SYSVOL\domain\Policies**. 
    -   Se si prevede di utilizzare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.
6.  Riavviare il controller di dominio principale affinché i criteri siano disponibili. Questa procedura funzionerà anche per qualsiasi versione futura.

A questo punto, è possibile visualizzare i criteri per **abilitare la registrazione automatica MDM utilizzando le credenziali di Azure ad** disponibili.
