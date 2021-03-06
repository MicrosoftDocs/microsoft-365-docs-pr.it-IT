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
description: Gli amministratori possono informazioni su come attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams, incluso come impostare gli avvisi per i file rilevati.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083093"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivare allegati sicuri per SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams protegge l'organizzazione dalla condivisione accidentale di file dannosi. Per ulteriori informazioni, vedere [Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).

In questo articolo vengono descritti i passaggi per abilitare e configurare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla pagina **Cassaforte allegati,** aprire <https://security.microsoft.com/safeattachmentv2> .

- Per attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams, è necessario essere membri dei gruppi di  ruoli  Gestione organizzazione o Amministratore sicurezza nel portale di Microsoft 365 Defender. Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Per usare SharePoint PowerShell online per impedire agli utenti di scaricare file dannosi, [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) è necessario essere membri dei ruoli [Amministratore](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) globale o Amministratore SharePoint in Azure AD.

- Verificare che la registrazione di controllo sia abilitata per l'organizzazione. Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

- Consentire fino a 30 minuti per l'applicazione delle impostazioni.

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Passaggio 1: usare il portale Microsoft 365 Defender per attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams

1. Nel portale Microsoft 365 Defender, passare alla sezione **Criteri & criteri** di minaccia Cassaforte \>  \>  \> **allegati**.

2. Nella pagina **Cassaforte allegati** fare clic su **Impostazioni globali.**

3. Nel **riquadro a comparsa** Impostazioni globali visualizzato passare alla sezione Proteggi **file in SharePoint, OneDrive e Microsoft Teams.**

   Sposta l'interruttore Attiva Defender per Office 365 per **SharePoint, OneDrive** e Microsoft Teams verso destra Attiva per attivare gli allegati Cassaforte per SharePoint, OneDrive e ![ ](../../media/scc-toggle-on.png) Microsoft Teams.

   Al termine, scegliere **Salva**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Usare Exchange Online PowerShell per attivare Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams

Se si preferisce utilizzare PowerShell per attivare Cassaforte Attachments per SharePoint, OneDrive e Microsoft Teams, connettersi [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando seguente:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Passaggio 2: (scelta consigliata) Utilizzare SharePoint PowerShell online per impedire agli utenti di scaricare file dannosi

Per impostazione predefinita, gli utenti non possono aprire, spostare, copiare o condividere file dannosi rilevati dagli allegati di Cassaforte per <sup>\*</sup> SharePoint, OneDrive e Microsoft Teams. Tuttavia, possono eliminare e scaricare file dannosi.

<sup>\*</sup> Se gli utenti passano **a Gestisci accesso,** **l'opzione** Condividi è ancora disponibile.

Per impedire agli utenti di scaricare file dannosi, [connettersi SharePoint PowerShell online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire il comando seguente:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Note**:

- Questa impostazione influisce sia sugli utenti che sugli amministratori.
- Gli utenti possono comunque eliminare file dannosi.

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>Passaggio 3 (consigliato) Usare il portale Microsoft 365 Defender per creare un criterio di avviso per i file rilevati

È possibile creare un criterio di avviso che notifica all'utente e ad altri amministratori quando Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams rileva un file dannoso. Per ulteriori informazioni sugli avvisi, vedere [Create activity alerts in the Microsoft 365 Defender portal.](../../compliance/create-activity-alerts.md)

1. Nel portale Microsoft 365 Defender, passare a Criteri **& criteri** \> **di avviso** o aprire <https://security.microsoft.com/alertpolicies> .

2. Nella pagina **Criterio avviso** fare clic su Nuovo criterio **di avviso.**

3. La **procedura guidata Nuovo criterio** di avviso viene aperta in un riquadro a comparsa. Nella pagina **Assegnare un nome all'avviso** configurare le impostazioni seguenti:
   - **Nome**: digitare un nome univoco e descrittivo. Ad esempio, File dannosi nelle raccolte.
   - **Descrizione:** digitare una descrizione facoltativa. Ad esempio, notifica agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft Teams.
   - **Gravità:** selezionare **Bassa,** **Media** o **Alta** nell'elenco a discesa.
   - **Categoria**: selezionare **Gestione delle minacce** nell'elenco a discesa.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Crea impostazioni avviso** configurare le impostazioni seguenti:
   - **Cosa si desidera avvisare?** sezione \> **Attività è** \> Seleziona malware rilevato nel **file** dall'elenco a discesa.
   - **Come si desidera attivare l'avviso?** sezione: lasciare selezionato il valore predefinito **Ogni volta che un'attività corrisponde alla regola.**

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Imposta i destinatari** configurare le impostazioni seguenti:
   - Verificare che **l'opzione Invia notifiche tramite posta** elettronica sia selezionata. Nella casella **Destinatari di posta elettronica** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che devono ricevere una notifica quando viene rilevato un file dannoso.
   - **Limite notifiche giornaliere**: lasciare selezionato il valore **predefinito Nessun** limite.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Rivedere le impostazioni** esaminare le impostazioni. È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.

   Nella sezione Vuoi attivare subito il **criterio?** lascia selezionato il valore predefinito **Sì, attivalo subito.**

   Al termine dell'operazione, scegliere **Fine**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Usare PowerShell & sicurezza per creare un criterio di avviso per i file rilevati

Se si preferisce usare PowerShell per creare lo stesso criterio di avviso descritto nella sezione precedente, connettersi & Centro sicurezza e conformità [PowerShell](/powershell/exchange/connect-to-scc-powershell) ed eseguire il comando seguente:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Nota:** il valore _di gravità_ predefinito è Low. Per specificare Medium o High, includere il _parametro Severity_ e il valore nel comando.

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-ActivityAlert](/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

- Per verificare di aver attivato correttamente Cassaforte allegati per SharePoint, OneDrive e Microsoft Teams, eseguire una delle operazioni seguenti:

  - Nel portale di Microsoft 365 Defender passare **alla** sezione Criteri & regole criteri di minaccia Cassaforte Allegati, selezionare Impostazioni globali e verificare il valore dell'impostazione Attiva Defender per Office 365 per \>  \>  \>  **SharePoint, OneDrive e Microsoft Teams.** 

  - In Exchange Online PowerShell, eseguire il comando seguente per verificare l'impostazione della proprietà:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).

- Per verificare di aver bloccato correttamente il download di file dannosi, aprire SharePoint PowerShell online ed eseguire il comando seguente per verificare il valore della proprietà:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

- Per verificare di aver configurato correttamente un criterio di avviso per i file rilevati, eseguire una delle operazioni seguenti:
  - Nel portale Microsoft 365 Defender, andare a Criteri **& criteri** di avviso Selezionare il criterio di avviso e verificare \>  \> le impostazioni.
  - In Microsoft 365 Defender PowerShell del portale, sostituire con il nome del criterio di avviso, eseguire il \<AlertPolicyName\> comando seguente e verificare i valori delle proprietà:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-ActivityAlert](/powershell/module/exchange/get-activityalert).

- Usa il [rapporto sullo stato di Threat Protection](view-email-security-reports.md#threat-protection-status-report) per visualizzare le informazioni sui file rilevati in SharePoint, OneDrive e Microsoft Teams. In particolare, puoi usare la **visualizzazione Visualizza dati per: Malware contenuto. \>**
