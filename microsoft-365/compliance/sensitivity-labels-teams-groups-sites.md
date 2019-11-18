---
title: Utilizzare le etichette di riservatezza con Microsoft teams, i gruppi di Office 365 e i siti di SharePoint (anteprima pubblica)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: È possibile applicare etichette a Microsoft teams, gruppi di Office 365 e siti di SharePoint.
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38686529"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Utilizzare le etichette di riservatezza con Microsoft teams, i gruppi di Office 365 e i siti di SharePoint (anteprima pubblica)

Quando si creano etichette di riservatezza nel [centro conformità di microsoft 365](https://protection.office.com/), è possibile applicarle a Microsoft teams, gruppi di Office 365 e siti di SharePoint. È possibile associare i criteri alle etichette da controllare:

- Impostazioni pubbliche/private
- Accesso guest
- Accesso da dispositivi non gestiti

Quando si applica un'etichetta a un team o a un gruppo, l'etichetta viene applicata automaticamente al sito del team di SharePoint connesso e all'altro.

A questo punto, è anche possibile abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive. [Altre informazioni](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Informazioni sull'anteprima pubblica per Microsoft teams, i gruppi di Office 365 e i siti di SharePoint

Le etichette di riservatezza per Microsoft teams, i gruppi di Office 365 e i siti di SharePoint vengono gradualmente distribuite ai tenant e potrebbero cambiare prima del rilascio finale.

## <a name="overview"></a>Panoramica

Quando si pubblicano le etichette di riservatezza, gli utenti di Office 365 hanno accesso allo stesso elenco di etichette.

Queste immagini mostrano:

- Come viene visualizzato l'elenco quando si crea un nuovo sito del team da SharePoint

- Quando si visualizza l'elenco in Word

![Un'etichetta di riservatezza quando si crea un sito del team da SharePoint](media/sensitivity-label-new-team-site.png)

![Un'etichetta di riservatezza visualizzata nell'app desktop Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a>Abilitazione di questa anteprima mediante Azure PowerShell

1. Accedere a Azure come amministratore globale utilizzando Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Eseguire il comando riportato di seguito:

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

Quando si Abilita l'anteprima, Office 365 non utilizza più le vecchie classificazioni per i nuovi gruppi e i siti di SharePoint. Se è stata utilizzata la [classificazione del sito di Azure ad](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($Setting ["classificazione"]), i gruppi e i siti esistenti continuano a visualizzare le vecchie classificazioni. Per visualizzare le nuove classificazioni, convertirle. Per informazioni su come convertirli, vedere [se è stata utilizzata la classificazione del sito di Azure ad classico](#if-you-used-classic-azure-ad-site-classification).

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a>Impostare le impostazioni del sito e del gruppo quando si creano etichette di riservatezza

Dopo aver abilitato l'anteprima, attenersi alla seguente procedura:

1. Nel centro conformità di Microsoft 365, selezionare **classificazione** > **etichette di riservatezza**.

2. Selezionare **Crea un'etichetta**.

3. Selezionare le opzioni desiderate e quindi nella scheda **Impostazioni sito e gruppo** scegliere:

    - Privacy (pubblico/privato): privato significa che solo i membri approvati nell'organizzazione possono vedere cosa c'è all'interno del gruppo. Chiunque altro nell'organizzazione non può vedere cosa c'è nel gruppo. [Altre informazioni](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Accesso Guest: è possibile controllare se gli utenti possono essere aggiunti a un gruppo. [Informazioni sulla gestione dell'accesso guest nei gruppi di Office 365](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Dispositivi non gestiti: questa impostazione consente di bloccare o limitare l'accesso al contenuto di SharePoint da dispositivi che non sono ibridi AD Uniti o conformi a Intune. Se si selezionano dispositivi non gestiti, è necessario passare a Azure AD per completare la configurazione del criterio. Per informazioni, vedere [controllare l'accesso da dispositivi non gestiti](/sharepoint/control-access-from-unmanaged-devices).

![Scheda Impostazioni sito e gruppo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Solo le impostazioni del sito e del gruppo hanno effetto quando si applica un'etichetta a un team, a un gruppo o a un sito. Altre impostazioni, ad esempio la crittografia e la marcatura del contenuto, non vengono applicate a tutto il contenuto all'interno del team, del gruppo o del sito. Analogamente, se si crea un'etichetta e non si attivano le impostazioni del sito e del gruppo, l'etichetta sarà ancora disponibile quando gli utenti creano team, gruppi e siti, ma non eseguiranno alcuna operazione quando gli utenti lo applicano.

[Informazioni su come pubblicare un'etichetta di riservatezza](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Applicazione di un'etichetta di riservatezza a un nuovo team

Gli utenti possono selezionare le etichette di riservatezza quando creano nuovi team in Microsoft teams. Quando si seleziona il livello di riservatezza, l'impostazione della privacy cambia in base alle esigenze. A seconda dell'impostazione di accesso Guest selezionata per l'etichetta, gli utenti possono o non possono aggiungere persone all'esterno dell'organizzazione al team.

![Impostazione della privacy quando si crea un nuovo team](media/privacy-setting-new-team.png)

Dopo aver creato il team, l'etichetta di riservatezza viene visualizzata nell'angolo in alto a destra di tutti i canali.

![L'etichetta di riservatezza viene visualizzata nel team](media/privacy-setting-teams.png)

Il servizio applica automaticamente la stessa etichetta di riservatezza al gruppo di Office 365 e al sito del team di SharePoint connesso.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Applicazione di un'etichetta di riservatezza a un nuovo gruppo

In Outlook sul Web, la nuova casella di **sensibilità** contiene le etichette pubblicate. Se gli utenti desiderano altre informazioni, possono fare clic sull'icona della Guida per leggere i dettagli sulle etichette disponibili e sui criteri associati.

![Creazione di un gruppo e selezione di un'opzione in Sensitivity](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Applicazione di un'etichetta di riservatezza a un nuovo sito

Gli amministratori e gli utenti finali possono selezionare le etichette di riservatezza quando creano siti del team e siti di comunicazione moderni.

[Informazioni su come creare un sito nella nuova interfaccia di amministrazione di SharePoint](/sharepoint/create-site-collection)

Quando gli utenti creano siti di comunicazione e team moderni, per impostazione predefinita è già selezionata un'etichetta di riservatezza. Gli utenti possono selezionare l'icona della Guida per ottenere ulteriori informazioni sulle etichette.

![Creazione di un sito e selezione di un'opzione in Sensitivity](media/sensitivity-label-new-communication-site.png)

Quando gli utenti accedono al sito, possono visualizzare il nome dell'etichetta e i criteri applicati.

![Un sito a cui è applicata un'etichetta di riservatezza](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Gestire le etichette di riservatezza nell'interfaccia di amministrazione di SharePoint

Per visualizzare e modificare le etichette, utilizzare la pagina siti attivi nella nuova interfaccia di amministrazione di SharePoint.

![Colonna Sensitivity nella pagina siti attivi](media/manage-site-sensitivity-labels.png)

[Per ulteriori informazioni, vedere Managing sites in the New SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Modificare le impostazioni del gruppo e del sito per un'etichetta

Come procedura consigliata, non modificare le impostazioni dopo aver applicato un'etichetta a più team, gruppi o siti. Se è necessario apportare una modifica, è necessario utilizzare uno script di Azure AD PowerShell per applicare manualmente gli aggiornamenti. Questo metodo garantisce che tutti i team, i siti e i gruppi esistenti applichino la nuova impostazione.

## <a name="support-for-the-new-sensitivity-labels"></a>Supporto per le nuove etichette di riservatezza

Le app e i servizi seguenti supportano le etichette di riservatezza in questa anteprima:

- Centro conformità Microsoft 365
- SharePoint
- Outlook sul web
- Teams
- Interfaccia di amministrazione di SharePoint
- Interfaccia di amministrazione di Azure AD

Non è possibile utilizzare le app e i servizi seguenti per creare gruppi di Office 365 con le nuove etichette di riservatezza:

- Outlook per Mac
- Outlook Mobile  
- Desktop di Outlook per Windows
- Forms  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Interfaccia di amministrazione di Teams  
- Interfaccia di amministrazione di Microsoft 365  
- Interfaccia di amministrazione di Exchange

## <a name="if-you-used-classic-azure-ad-site-classification"></a>Se è stata utilizzata la classificazione del sito di Azure AD classico

Quando si Abilita l'anteprima, Office 365 non supporta più la classificazione obsoleta per i nuovi gruppi e i siti di SharePoint. Tuttavia, i gruppi e i siti esistenti continuano a visualizzare le vecchie classificazioni, a meno che non vengano convertite. Le classi precedenti includono la classificazione dei siti "moderna" configurata, possibilmente tramite Azure AD PowerShell o la libreria di base PnP, che definisce `ClassificationList` i valori per l'impostazione.

Ad esempio, in PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Per ulteriori informazioni sul vecchio metodo di classificazione, vedere [classificazione dei siti di SharePoint "moderna"](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

In base alla distribuzione corrente, sono disponibili due opzioni per convertire le classificazioni obsolete nelle nuove classificazioni.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Se non sono mai state utilizzate etichette di riservatezza (etichette di Microsoft Information Protection unificate) per file e messaggi di posta elettronica

È consigliabile:

1. Creare nuove etichette di riservatezza nel centro conformità di Microsoft 365 con gli stessi nomi delle classificazioni esistenti.
2. Utilizzare PowerShell per applicare le nuove etichette ai gruppi di Office 365 e ai siti di SharePoint esistenti utilizzando il mapping dei nomi.
3. Eliminare le classificazioni obsolete.

Le app e i servizi che supportano le nuove etichette di riservatezza verranno visualizzati. È possibile creare nuovi team, gruppi e siti con le nuove etichette. Gli utenti possono comunque creare gruppi da app e servizi che non supportano le nuove etichette. Tuttavia, gli utenti non possono applicare un'etichetta a questi gruppi. Utilizzare PowerShell per applicare le nuove etichette di riservatezza a questi gruppi.

È possibile mantenere le classificazioni obsolete; Tuttavia, è consigliabile utilizzare PowerShell per applicare le nuove etichette di riservatezza a questi gruppi.

Le app e i servizi che supportano le nuove etichette di riservatezza vengono creati con le nuove etichette. Quando gli utenti creano gruppi da app e servizi che non supportano le nuove etichette, possono selezionare una classificazione.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Se si utilizzano le etichette di riservatezza (etichette Microsoft per la protezione delle informazioni unificate) per file e messaggi di posta elettronica

Non appena si abilita questa anteprima, passare a ciascuna etichetta nel centro conformità di Microsoft 365 e applicare i criteri desiderati per i siti e i gruppi. Gli utenti inizieranno a visualizzare le etichette esistenti per i siti e i gruppi.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Preparare la shell di gestione di SharePoint Online prima di rietichettare i gruppi di Office 365

Prima di applicare nuove etichette, verificare che sia in esecuzione la versione più recente di SharePoint Online Management Shell. Se si ha già la versione più recente, è possibile procedere e [rietichettare i gruppi di Office 365 con nuove etichette di riservatezza](#relabel-office-365-groups-with-new-sensitivity-labels).

Per preparare SharePoint Online Management Shell per l'anteprima:

1. Se è stata installata una versione precedente di SharePoint Online Management Shell, andare a installazione **applicazioni** e disinstallare "SharePoint Online Management Shell".

2. In un Web browser passare alla pagina Centro download e [scaricare la versione più recente di SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Selezionare la lingua e quindi fare clic su **download**.

4. Scegliere tra il file x64 e x86. msi. Scaricare il file x64 se si esegue la versione di Windows a 64 bit o il file x86 se si esegue la versione a 32 bit. Se non si conosce, vedere [la versione del sistema operativo Windows in esecuzione?](https://support.microsoft.com/help/13443/windows-which-operating-system).

5. Dopo aver scaricato il file, eseguire il file e seguire i passaggi illustrati nell'installazione guidata.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Relabel Office 365 gruppi con nuove etichette di riservatezza

1. Assicurarsi di utilizzare la versione più recente di SharePoint Online Management Shell. Per istruzioni, vedere [preparare la shell di gestione di SharePoint Online prima di rietichettare i gruppi di Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. Utilizzo di un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale o di amministrazione di SharePoint in Office 365, connettersi a SharePoint Online Management Shell. Per informazioni in merito, vedere [Guida introduttiva a SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Eseguire il seguente comando per ottenere l'elenco delle etichette di riservatezza e dei relativi GUID.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Prendere nota del GUID per l'etichetta che si desidera sovrascrivere. Ad esempio, l'etichetta "generale".

5. Utilizzare il seguente comando per ottenere l'elenco dei gruppi che hanno la classificazione "generale". Quando si esegue questo comando, è possibile connettersi a PowerShell di Exchange Online ed eseguire il cmdlet Get-UnifiedGroup.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. Per ogni gruppo, aggiungere il nuovo GUID dell'etichetta di riservatezza.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
