---
title: Attiva Microsoft Defender per Office 365-SharePoint, OneDrive, & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Informazioni su come abilitare ATP per SharePoint, OneDrive e teams, inclusa la procedura per impostare gli avvisi per i file rilevati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69cb7ffcfb06d5ccda915004a512e7eefc6eb56e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844273"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivare ATP per SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft teams protegge l'organizzazione dalla condivisione involontaria di file dannosi. Per ulteriori informazioni, vedere [ATP for SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md).

In questo articolo sono riportati i passaggi per l'abilitazione e la configurazione di ATP per SharePoint, OneDrive e Microsoft teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com>. Per passare direttamente alla pagina degli **allegati sicuri di ATP** , Apri <https://protection.office.com/safeattachmentv2> .

- Per abilitare ATP per SharePoint, OneDrive e Microsoft teams, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** nel centro sicurezza & Compliance. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Per utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi, è necessario essere membri dell' [amministratore globale](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o dei ruoli di [amministratore di SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure ad.

- Verificare che la registrazione di controllo sia abilitata per l'organizzazione. Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

- Consenti fino a 30 minuti per rendere effettive le impostazioni.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Passaggio 1: utilizzare il Centro sicurezza & conformità per abilitare ATP per SharePoint, OneDrive e Microsoft Teams

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP** e fare clic su **Impostazioni globali**.

2. Nelle **Impostazioni globali** volare che viene visualizzato, passare all'impostazione **attiva ATP per SharePoint, OneDrive e Microsoft teams** . Spostare l'interruttore verso destra per ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) attivare ATP per SharePoint, OneDrive e Microsoft teams.

   Al termine, scegliere **Salva**.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Utilizzo di PowerShell di Exchange Online per abilitare ATP per SharePoint, OneDrive e Microsoft Teams

Se si preferisce utilizzare PowerShell per abilitare ATP per SharePoint, OneDrive e Microsoft teams, [connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) ed eseguire il comando riportato di seguito:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Passaggio 2: (scelta consigliata) utilizzare PowerShell di SharePoint Online per impedire agli utenti di scaricare file dannosi

Per impostazione predefinita, gli utenti non possono aprire, spostare, copiare o condividere file dannosi rilevati da ATP. Tuttavia, è possibile eliminare e scaricare file dannosi.

Per impedire agli utenti di scaricare file dannosi, [connettersi a PowerShell di SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) ed eseguire il comando riportato di seguito:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Note** :

- Questa impostazione interessa sia gli utenti che gli amministratori.
- Gli utenti possono comunque eliminare i file dannosi.

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Passaggio 3 (scelta consigliata) utilizzare il Centro sicurezza & conformità per creare un criterio di avviso per i file rilevati

È possibile creare un criterio di avviso che informa l'utente e gli altri amministratori quando ATP per SharePoint, OneDrive e Microsoft teams rileva un file dannoso. Per ulteriori informazioni sugli avvisi, vedere [creare avvisi di attività nel centro sicurezza & Compliance](../../compliance/create-activity-alerts.md).

1. Nel [Centro sicurezza & conformità](https://protection.office.com), accedere a criteri **Alerts** di \> **avviso** avvisi o Apri <https://protection.office.com/alertpolicies> .

2. Nella pagina **criteri di avviso** fare clic su **nuovi criteri di avviso**.

3. La procedura guidata **nuovo criterio di avviso** viene aperta in un volo. Nella pagina **nome messaggio di avviso** , configurare le seguenti impostazioni:

   - **Nome** : digitare un nome univoco e descrittivo. Ad esempio, i file dannosi nelle raccolte.
   - **Descrizione** : digitare una descrizione facoltativa. Ad esempio, avvisa gli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft teams.
   - **Severity** : lasciare il valore predefinito **basso** selezionato oppure selezionare **medio** o **elevato**.
   - **Selezionare una categoria** : selezionare **gestione minacce**.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Crea impostazioni di avviso** configurare le seguenti impostazioni:

   - **Che cosa si desidera avvisare?: attività è** : selezionare **rilevato malware nel file**.
   - **Come si desidera che venga attivato l'avviso?** : lasciare il valore predefinito **ogni volta che un'attività corrisponde alla regola** selezionata.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **imposta i destinatari** , configurare le seguenti impostazioni:

   - **Invia notifiche tramite posta elettronica** : verificare che questa impostazione sia selezionata. Nella casella **destinatari di posta elettronica** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che dovrebbero ricevere una notifica quando viene rilevato un file dannoso.
   - **Limite di notifica giornaliero** : lasciare il valore predefinito **Nessun limite** selezionato.

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Verifica le impostazioni** , esaminare le impostazioni, quindi fare clic su **modifica** in una delle sezioni per apportare modifiche.

   Nel caso in **cui si desidera trasformare il criterio immediatamente?** , lasciare il valore predefinito **Sì, attivarlo immediatamente** .

   Al termine dell'operazione, scegliere **Fine**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Utilizzare la sicurezza & conformità PowerShell per creare un criterio di avviso per i file rilevati

Se si preferisce utilizzare PowerShell per creare gli stessi criteri di avviso descritti nella sezione precedente, [connettersi al centro di sicurezza & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) ed eseguire il comando seguente:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Nota** : il valore di _gravità_ predefinito è basso. Per specificare medio o alto, includere il parametro _Severity_ e il valore nel comando.

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

- Per verificare di aver correttamente attivato ATP per SharePoint, OneDrive e Microsoft teams, eseguire una delle operazioni seguenti:

  - Nel [Centro sicurezza & conformità](https://protection.office.com), accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP** , selezionare **Impostazioni globali** e verificare il valore dell'impostazione **attiva ATP per SharePoint, OneDrive e Microsoft teams** .

  - In Exchange Online PowerShell, eseguire il comando riportato di seguito per verificare l'impostazione della proprietà:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Per verificare che le persone siano state bloccate correttamente dal Download di file dannosi, aprire PowerShell di SharePoint Online ed eseguire il comando seguente per verificare il valore della proprietà:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Per verificare la corretta configurazione di un criterio di avviso per i file rilevati, eseguire una delle operazioni seguenti:

  - Nel centro sicurezza & conformità, accedere a **Alerts** \> **criteri di avviso** avvisi \> selezionare il criterio di avviso e verificare le impostazioni.

  - In PowerShell Centro sicurezza & conformità, sostituire \<AlertPolicyName\> con il nome del criterio di avviso, eseguire il comando riportato di seguito e verificare i valori delle proprietà:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Utilizzare il [rapporto sullo stato di protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report) per visualizzare le informazioni sui file rilevati in SharePoint, OneDrive e Microsoft teams. In particolare, è possibile utilizzare la visualizzazione **dati di visualizzazione per: contenuto \> antimalware** .
