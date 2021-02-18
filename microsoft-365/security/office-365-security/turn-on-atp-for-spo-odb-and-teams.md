---
title: Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Gli amministratori possono imparare ad attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams, incluso come impostare avvisi per i file rilevati.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286370"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi. Per ulteriori informazioni, vedere [Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Questo articolo contiene i passaggi per abilitare e configurare allegati sicuri per SharePoint, OneDrive e Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com>. Per passare direttamente alla pagina **Allegati sicuri di ATP,** aprire <https://protection.office.com/safeattachmentv2> .

- Per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams,  è necessario  essere membri dei gruppi di ruoli Gestione organizzazione o Amministratore sicurezza nel Centro sicurezza & conformità. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Per utilizzare PowerShell di SharePoint Online per impedire agli utenti di [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) scaricare file dannosi, è necessario essere membri dei ruoli Amministratore globale o Amministratore di [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD.

- Verificare che la registrazione di controllo sia abilitata per l'organizzazione. Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

- Consentire fino a 30 minuti per l'applicazione delle impostazioni.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Passaggio 1: Usare il Centro sicurezza & conformità per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams

1. Nel Centro sicurezza & conformità passare **a** Allegati sicuri dei criteri di gestione delle minacce ATP e fare clic su \>  \>  **Impostazioni globali.**

2. Nel **riquadro a comparsa** Impostazioni globali visualizzato passare all'impostazione Attiva **Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams.** Spostare l'interruttore a destra per attivare Allegati sicuri ![ ](../../media/scc-toggle-on.png) per SharePoint, OneDrive e Microsoft Teams.

   Al termine, fare clic su **Salva**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Usare PowerShell di Exchange Online per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams

Se si preferisce usare PowerShell per attivare Allegati sicuri per SharePoint, OneDrive e Microsoft Teams, connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Passaggio 2: (scelta consigliata) Utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi

Per impostazione predefinita, gli utenti non possono aprire, spostare, copiare o condividere file dannosi rilevati da ATP. Tuttavia, possono eliminare e scaricare file dannosi.

Per impedire agli utenti di scaricare file dannosi, [connettersi a PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire il comando seguente:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Note**:

- Questa impostazione influisce sia sugli utenti che sugli amministratori.
- Gli utenti possono comunque eliminare file dannosi.

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Passaggio 3 (consigliato) Usare il Centro sicurezza & conformità per creare un criterio di avviso per i file rilevati

È possibile creare un criterio di avviso che informa l'utente e altri amministratori quando Allegati sicuri per SharePoint, OneDrive e Microsoft Teams rileva un file dannoso. Per ulteriori informazioni sugli avvisi, vedere Creare avvisi [attività nel Centro sicurezza & conformità.](../../compliance/create-activity-alerts.md)

1. Nel Centro [sicurezza & conformità](https://protection.office.com)passare a Criteri **avvisi** o \>  aprire <https://protection.office.com/alertpolicies> .

2. Nella pagina **Criteri di avviso** fare clic su Nuovo criterio di **avviso.**

3. La **procedura guidata Nuovo criterio** di avviso si apre in un riquadro a comparsa. Nella pagina **Assegnare un nome all'avviso** configurare le impostazioni seguenti:

   - **Nome**: digitare un nome univoco e descrittivo. Ad esempio, File dannosi nelle raccolte.
   - **Descrizione:** digitare una descrizione facoltativa. Ad esempio, notifica agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft Teams.
   - **Gravità:** lasciare selezionato il valore predefinito **Basso** oppure **selezionare Medio** o **Alto.**
   - **Selezionare una categoria:** selezionare **Gestione delle minacce.**

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Crea impostazioni avviso** configurare le impostazioni seguenti:

   - **What do you want to alert on?: Activity is**: Select **Detected malware in file.**
   - **Come si desidera attivare l'avviso?**: Lasciare il valore predefinito Ogni volta che un'attività **corrisponde alla regola** selezionata.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Imposta destinatari** configurare le impostazioni seguenti:

   - **Invia notifiche tramite posta elettronica:** verificare che questa impostazione sia selezionata. Nella casella **Destinatari di posta** elettronica selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.
   - **Limite di notifica giornaliero:** lasciare selezionato il valore **predefinito Nessun** limite.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Verifica le impostazioni** esaminare le impostazioni e fare clic su **Modifica** in una delle sezioni per apportare modifiche.

   Nella sezione Vuoi attivare il criterio **subito?** lascia selezionato il valore predefinito **Sì, attivalo subito.**

   Al termine dell'operazione, scegliere **Fine**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Usare PowerShell & sicurezza per creare un criterio di avviso per i file rilevati

Se si preferisce usare PowerShell per creare lo stesso criterio di avviso descritto nella sezione precedente, connettersi [a PowerShell per](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) Centro sicurezza & conformità ed eseguire il comando seguente:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Nota:** il valore _di gravità_ predefinito è Basso. Per specificare Medium o High, includere il _parametro Severity_ e il valore nel comando.

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/new-activityalert)

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

- Per verificare che gli allegati sicuri per SharePoint, OneDrive e Microsoft Teams siano stati attivati correttamente, eseguire una delle operazioni seguenti:

  - Nel Centro sicurezza & conformità, accedere  [a](https://protection.office.com)Allegati sicuri atp dei criteri di gestione delle minacce, selezionare Impostazioni globali e verificare il valore dell'impostazione Attiva \>  \> Defender per **Office 365 per SharePoint, OneDrive** e Microsoft Teams.

  - In PowerShell di Exchange Online, eseguire il comando seguente per verificare l'impostazione della proprietà:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)

- Per verificare di aver bloccato correttamente il download di file dannosi, aprire PowerShell di SharePoint Online ed eseguire il comando seguente per verificare il valore della proprietà:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SPOTenant.](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)

- Per verificare di aver configurato correttamente un criterio di avviso per i file rilevati, eseguire una delle operazioni seguenti:

  - Nel Centro sicurezza & conformità, andare a **Criteri avvisi** selezionare i criteri di avviso e verificare \>  \> le impostazioni.

  - In PowerShell & Centro sicurezza e conformità, sostituire con il nome del criterio di avviso, eseguire il comando seguente e \<AlertPolicyName\> verificare i valori delle proprietà:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-ActivityAlert.](https://docs.microsoft.com/powershell/module/exchange/get-activityalert)

- Usare il [report sullo stato di Protezione](view-email-security-reports.md#threat-protection-status-report) dalle minacce per visualizzare informazioni sui file rilevati in SharePoint, OneDrive e Microsoft Teams. In particolare, è possibile utilizzare la **visualizzazione dati da: visualizzazione \> Malware** contenuto.
