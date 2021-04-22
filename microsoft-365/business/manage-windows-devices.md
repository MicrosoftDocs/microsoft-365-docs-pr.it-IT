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
search.appverid:
- BCS160
- MET150
description: Scopri come abilitare Microsoft 365 per proteggere i dispositivi Windows 10 aggiunti ad Active Directory locali in pochi passaggi.
ms.openlocfilehash: c9f5a21d993200abcf9ecf1fa236879245e1c153
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939503"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Abilitare la gestione dei dispositivi Windows 10 aggiunti al dominio da Microsoft 365 Business Premium

Se l'organizzazione usa Windows Server Active Directory in locale, puoi configurare Microsoft 365 Business Premium per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.
Per configurare questa protezione, è possibile implementare dispositivi aggiunti **ad Azure AD ibridi.** Questi dispositivi vengono aggiunti sia ad Active Directory locale che ad Azure Active Directory.

In questo video vengono descritti i passaggi per configurare questo scenario per lo scenario più comune, descritto anche nei passaggi seguenti.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Prima di iniziare, assicurati di completare questi passaggi:
- Sincronizzare gli utenti con Azure AD con Azure AD Connect.
- Completare la sincronizzazione dell'unità organizzativa (OU) di Azure AD Connect.
- Assicurati che tutti gli utenti di dominio sincronizzati siano licenze per Microsoft 365 Business Premium.

Per [la procedura, vedere Sincronizzare gli utenti](manage-domain-users.md) di dominio con Microsoft.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verificare l'autorità MDM in Intune

Vai a [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e nella pagina Microsoft Intune seleziona **Registrazione** dispositivo , quindi nella pagina **Panoramica** assicurati che l'autorità **MDM** sia **Intune**.

- Se **l'autorità MDM** **è None,** fai clic **sull'autorità MDM** per impostarla su **Intune.**
- Se **l'autorità MDM** è **Microsoft Office 365,** vai a Dispositivi Registra dispositivi e usa la finestra di dialogo Aggiungi autorità MDM a destra per aggiungere l'autorità MDM di Intune (la finestra di dialogo Aggiungi autorità MDM è disponibile solo se l'autorità MDM è impostata su Microsoft Office  >   365).    

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verificare che Azure AD sia abilitato per l'aggiunta di computer

- Passare all'interfaccia di amministrazione in e selezionare Azure Active Directory (selezionare Mostra tutto se <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> Azure Active Directory non è visibile) nell'elenco Delle centri  **di** amministrazione. 
- **Nell'interfaccia di amministrazione di Azure Active Directory** passare ad Azure Active **Directory,** scegliere **Dispositivi** e quindi **Impostazioni dispositivo**.
- Verificare **che gli utenti possano aggiungere dispositivi ad Azure AD** sia abilitato 
    1. Per abilitare tutti gli utenti, impostare su **Tutti**.
    2. Per abilitare utenti specifici, impostare su **Selezionato** per abilitare un gruppo specifico di utenti.
        - Aggiungere gli utenti di dominio desiderati sincronizzati in Azure AD a un [gruppo di sicurezza.](../admin/create-groups/create-groups.md)
        - Scegliere **Seleziona gruppi per** abilitare l'ambito utente MDM per il gruppo di sicurezza.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verificare che Azure AD sia abilitato per MDM

- Accedere all'interfaccia di amministrazione in <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  e selezionare Gestione **endpoint** t (selezionare **Mostra tutto** se **Endpoint Manager** non è visibile)
- **Nell'interfaccia di amministrazione di Microsoft Endpoint Manager,** vai a **Dispositivi**  >  **Registrazione automatica registrazione windows**  >    >  **di** Windows .
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
> È consigliabile installare questo modulo in Windows Server che esegue Azure AD Connect.

Per creare il punto di connessione del servizio e i criteri di gruppo necessari, verrà richiamato il cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Per eseguire questa attività, saranno necessarie le credenziali di amministratore globale di Microsoft 365 Business Premium. Quando si è pronti per creare le risorse, richiamare quanto segue:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Il primo comando stabilisce una connessione con il cloud Microsoft e, quando richiesto, specifica le credenziali di amministratore globale di Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. Collegare Criteri di gruppo

1. Nella Console Gestione Criteri di gruppo fare clic con il pulsante destro del mouse sul percorso in cui si desidera collegare il criterio e scegliere Collega un oggetto Criteri di gruppo esistente *dal* menu di scelta rapida.
2. Selezionare il criterio creato nel passaggio precedente, quindi fare clic su **OK.**

## <a name="get-the-latest-administrative-templates"></a>Ottenere i modelli amministrativi più recenti

Se il criterio Abilita registrazione MDM automatica con le credenziali predefinite di **Azure AD** non è visualizzato, è possibile che l'ADMX non sia installato per Windows 10, versione 1803 o successiva. Per risolvere il problema, segui questi passaggi (Nota: l'ultimo file MDM.admx è compatibile con le versioni precedenti):

1.  Download: [Modelli amministrativi (admx) per Windows 10 Ottobre 2020 Update (20H2)](https://www.microsoft.com/download/102157).
2.  Installare il pacchetto in un controller di dominio.
3.  Passare alla cartella **C:\Programmi (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)** a seconda della versione dei modelli amministrativi.
4.  Rinominare la **cartella Policy Definitions** nel percorso precedente in **PolicyDefinitions**.
5.  Copiare **la cartella PolicyDefinitions** nella condivisione SYSVOL, per impostazione predefinita in **C:\Windows\SYSVOL\domain\Policies**. 
    -   Se si prevede di usare un archivio criteri centrale per l'intero dominio, aggiungere il contenuto di PolicyDefinitions.
6.  Nel caso in cui siano presenti più controller di dominio, attendere la replica di SYSVOL per la disponibilità dei criteri. Questa procedura funzionerà anche per qualsiasi versione futura dei modelli amministrativi.

A questo punto dovrebbe essere possibile visualizzare il criterio Abilita registrazione **AUTOMATICA MDM usando le credenziali predefinite di Azure AD** disponibili.

## <a name="related-content"></a>Contenuti correlati

Sincronizzare gli utenti di dominio con [Microsoft 365](manage-domain-users.md) (articolo) Creare un gruppo [nell'interfaccia](../admin/create-groups/create-groups.md) di amministrazione (articolo) [Esercitazione: Configurare](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) l'aggiunta ibrida di Azure Active Directory per i domini gestiti (articolo)