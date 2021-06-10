---
title: Supporto di Azure Information Protection Office 365 gestito da 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Altre informazioni su Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e su come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535843"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Supporto di Azure Information Protection Office 365 gestito da 21Vianet

In questo articolo vengono illustrate le differenze tra il supporto di Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e le offerte commerciali, nonché istruzioni specifiche per la configurazione di AIP per i clienti in Cina, tra cui come installare lo scanner AIP locale e gestire i processi di analisi del &mdash; contenuto.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Differenze tra AIP per Office 365 gestito da 21Vianet e offerte commerciali

Anche se il nostro obiettivo è fornire tutte le funzionalità commerciali ai clienti in Cina con la nostra offerta AIP per Office 365 gestita da 21Vianet, alcune funzionalità mancanti sono da evidenziare.

L'elenco seguente include le lacune esistenti tra AIP per Office 365 gestito da 21Vianet e le offerte commerciali a partire da gennaio 2021:

- Information Rights Management (IRM) è supportato solo per Microsoft 365 Apps for enterprise (build 11731.10000 o versione successiva). Office 2010, Office 2013 e altre Office 2016 non sono supportate.

- La migrazione da Active Directory Rights Management Services (AD RMS) ad AIP non è attualmente disponibile.
  
- È supportata la condivisione di messaggi di posta elettronica protetti con gli utenti nel cloud commerciale.
  
- La condivisione di documenti e allegati di posta elettronica con gli utenti nel cloud commerciale non è attualmente disponibile. Sono inclusi Office 365 gestiti da 21 utentiVianet nel cloud commerciale, non Office 365 gestiti da 21 utentiVianet nel cloud commerciale e utenti con una licenza RMS per singoli utenti.
  
- IRM con SharePoint (siti e raccolte protetti da IRM) non è attualmente disponibile.
  
- L'estensione per dispositivi mobili per AD RMS non è attualmente disponibile.

- Il [visualizzatore per](/azure/information-protection/rms-client/mobile-app-faq) dispositivi mobili non è supportato da Azure China 21Vianet.

- L'area AIP del portale di Azure non è disponibile per i clienti in Cina. Utilizzare [i comandi di PowerShell](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) invece di eseguire azioni nel portale, ad esempio la gestione e l'esecuzione dei processi di analisi del contenuto.

## <a name="configure-aip-for-customers-in-china"></a>Configurare AIP per i clienti in Cina

Per configurare AIP per i clienti in Cina:
1. [Abilitare Rights Management per il tenant](#step-1-enable-rights-management-for-the-tenant).

1. [Aggiungere l'entità servizio di sincronizzazione](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)di Microsoft Information Protection .

1. [Configurare la crittografia DNS](#step-3-configure-dns-encryption).

1. [Installare e configurare il client di etichettatura unificato AIP](#step-4-install-and-configure-the-aip-unified-labeling-client).

1. [Configurare le app AIP in Windows](#step-5-configure-aip-apps-on-windows).

1. [Installare lo scanner AIP locale e gestire i processi di analisi del contenuto.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Passaggio 1: Abilitare Rights Management per il tenant

Per il corretto funzionamento della crittografia, è necessario che RMS sia abilitato per il tenant.

1. Verificare se RMS è abilitato:

    1. Avviare PowerShell come amministratore.
    2. Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .
    3. Importare il modulo utilizzando `Import-Module AipService` .
    4. Connessione al servizio tramite `Connect-AipService -environmentname azurechinacloud` .
    5. Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .

2. Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Passaggio 2: Aggiungere l'entità servizio di sincronizzazione di Microsoft Information Protection

L'entità servizio di **sincronizzazione** di Microsoft Information Protection non è disponibile nei tenant di Azure Cina per impostazione predefinita ed è necessaria per Azure Information Protection.

1. Creare manualmente questa entità servizio utilizzando il cmdlet [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) e `870c4f2e-85b6-4d43-bdda-6ed9a579b725` l'ID applicazione per il servizio di sincronizzazione di Microsoft Information Protection. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. Dopo aver aggiunto l'entità servizio, aggiungere le autorizzazioni rilevanti necessarie al servizio.

### <a name="step-3-configure-dns-encryption"></a>Passaggio 3: Configurare la crittografia DNS

Per il corretto funzionamento della crittografia, Office applicazioni client devono connettersi all'istanza cina del servizio e avviare il bootstrap da lì. Per reindirizzare le applicazioni client all'istanza del servizio giusta, l'amministratore tenant deve configurare un record DNS SRV con informazioni sull'URL di Azure RMS. Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.

Inoltre, il presupposto è che gli utenti accederanno con un nome utente basato sul dominio di proprietà del tenant (ad esempio, ) e non con il nome `joe@contoso.cn` `onmschina` utente (ad esempio, `joe@contoso.onmschina.cn` ). Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.

#### <a name="configure-dns-encryption---windows"></a>Configurare la crittografia DNS - Windows

1. Ottenere l'ID RMS:

    1. Avviare PowerShell come amministratore.
    2. Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .
    3. Connessione al servizio tramite `Connect-AipService -environmentname azurechinacloud` .
    4. Eseguire `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.

2. Accedere al provider DNS, accedere alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.

    - Servizio = `_rmsredir`
    - Protocollo = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)
    - Priorità, Peso, Secondi, TTL = valori predefiniti

3. Associare il dominio personalizzato al tenant nel [portale di Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.

4. Accedere all'interfaccia Microsoft 365 di amministrazione con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione degli utenti. Nel processo di verifica potrebbero essere necessarie ulteriori modifiche al DNS. Al termine della verifica, gli utenti possono essere creati.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurare la crittografia DNS - Mac, iOS, Android

Accedere al provider DNS, accedere alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.

- Servizio = `_rmsdisco`
- Protocollo = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Priorità, Peso, Secondi, TTL = valori predefiniti


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Passaggio 4: Installare e configurare il client di etichettatura unificato AIP

Scaricare e installare il client di etichettatura unificato AIP [dall'Area download Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

Per altre informazioni, vedere:

- [Documentazione AIP](/azure/information-protection/)
- [Cronologia delle versioni AIP e criteri di supporto](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisiti di sistema AIP](/azure/information-protection/requirements)
- [Guida introduttiva AIP: Distribuire il client AIP](/azure/information-protection/quickstart-deploy-client)
- [Guida all'amministratore AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guida per l'utente AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Informazioni sulle Microsoft 365 di riservatezza](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Passaggio 5: Configurare le app AIP Windows

Le app AIP Windows la chiave del Registro di sistema seguente per puntare al cloud sovrano corretto per Azure Cina:

- Nodo del Registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Value = `6` (valore predefinito = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Assicurarsi di non eliminare la chiave del Registro di sistema dopo una disinstallazione. Se la chiave è vuota, errata o inesistente, la funzionalità si comporterà come valore predefinito (valore predefinito = 0 per il cloud commerciale). Se la chiave è vuota o errata, al registro viene aggiunto anche un errore di stampa.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Passaggio 6: Installare lo scanner AIP locale e gestire i processi di analisi del contenuto

Installare lo scanner AIP locale per analizzare la rete e le condivisioni di contenuto alla ricerca di dati sensibili e applicare etichette di classificazione e protezione come configurato nei criteri dell'organizzazione.

Quando configuri e gestisci i processi di analisi del contenuto, usa la procedura seguente invece dell'interfaccia del portale di [Azure](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) usata dalle offerte commerciali.

Per ulteriori informazioni, vedere [Che cos'è lo scanner](/azure/information-protection/deploy-aip-scanner) di etichettatura unificato di Azure Information Protection? e Gestire i processi di analisi del contenuto solo tramite [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)

**Per installare e configurare lo scanner:**

1. Accedere al computer Windows Server che eseguirà lo scanner. Utilizzare un account con diritti di amministratore locale e che dispone delle autorizzazioni per scrivere nel database master SQL Server database master.

1. Iniziare con PowerShell chiuso. Se in precedenza sono stati installati il client AIP e lo scanner, assicurarsi che il **servizio AIPScanner** sia arrestato.

1. Aprire una Windows PowerShell sessione con **l'opzione Esegui come** amministratore.

1. Eseguire il cmdlet [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) specificando l'istanza di SQL Server in cui creare un database per lo scanner di Azure Information Protection e un nome significativo per il cluster di scanner.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > È possibile utilizzare lo stesso nome del cluster nel [comando Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) per associare più nodi scanner allo stesso cluster. L'utilizzo dello stesso cluster per più nodi scanner consente a più scanner di lavorare insieme per eseguire le analisi.
    > 

1. Verificare che il servizio sia installato utilizzando Strumenti **di** amministrazione  >  .

    Il servizio installato è denominato **Scanner di Azure Information Protection** ed è configurato per l'esecuzione utilizzando l'account di servizio dello scanner creato.

1. Ottenere un token di Azure da usare con lo scanner. Un token Azure AD consente allo scanner di eseguire l'autenticazione nel servizio Azure Information Protection, consentendo l'esecuzione non interattiva dello scanner. 

    1. Aprire il portale di Azure e creare un'applicazione Azure AD per specificare un token di accesso per l'autenticazione. Per ulteriori informazioni, vedere [Come etichettare i file in modo non interattivo per Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)
    
        > [!TIP]
        > Quando si creano e configurano le applicazioni di Azure AD per il  comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) nel riquadro Richiedi **autorizzazioni API** viene visualizzata la scheda API utilizzate dall'organizzazione anziché la scheda **API Microsoft.** Seleziona le **API utilizzate dall'organizzazione** per selezionare **Azure Rights Management Services.** 
        >

    1. Dal computer Windows Server, se all'account del servizio  scanner è stato concesso il diritto Di accesso locale per l'installazione, accedere con questo account e avviare una sessione di PowerShell. 
    
        Se all'account del servizio  scanner non è possibile concedere il diritto di accesso locale per l'installazione, utilizzare il parametro *OnBehalfOf* con [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), come descritto in Come etichettare i file in modo non interattivo per [Azure Information Protection.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)

    1. Eseguire [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specificando i valori copiati dall'applicazione Azure AD:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Ad esempio:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    Lo scanner ora dispone di un token per l'autenticazione in Azure AD. Questo token è valido per un anno, due anni o mai, in base alla configurazione del segreto **client dell'app Web /API** in Azure AD. Quando il token scade, è necessario ripetere questa procedura.

1. Eseguire il cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) per impostare lo scanner in modo che funzioni in modalità offline. Eseguire: 

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Eseguire il cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) per creare un processo di analisi del contenuto predefinito.

    L'unico parametro obbligatorio nel cmdlet **Set-AIPScannerContentScanJob** è **Enforce**. È tuttavia possibile definire altre impostazioni per il processo di analisi del contenuto in questo momento. Ad esempio:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    La sintassi precedente configura le impostazioni seguenti mentre si continua la configurazione:

    - Mantiene manuale la pianificazione dell'esecuzione dello *scanner*
    - Imposta i tipi di informazioni da individuare in base al criterio di etichettatura di riservatezza
    - Non *applica un* criterio di etichettatura di riservatezza
    - Etichetta automaticamente i file in base al contenuto, utilizzando l'etichetta predefinita definita per il criterio di etichettatura di riservatezza
    - Non *consente la* rietichettatura dei file
    - Mantiene i dettagli dei file durante l'analisi e l'etichettatura automatica, tra cui *data* di *modifica,* ultima modifica *e modifica in base ai* valori
    - Imposta lo scanner in modo da escludere i file con estensione msg e tmp durante l'esecuzione
    - Imposta il proprietario predefinito sull'account che si desidera utilizzare quando si esegue lo scanner

1. Utilizzare il cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) per definire gli archivi che si desidera analizzare nel processo di analisi del contenuto. Ad esempio, eseguire:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Utilizzare una delle sintassi seguenti, a seconda del tipo di repository che si sta aggiungendo:

    - Per una condivisione di rete, utilizzare `\\Server\Folder` .
    - Per una SharePoint, utilizzare `http://sharepoint.contoso.com/Shared%20Documents/Folder` .
    - Per un percorso locale: `C:\Folder`
    - Per un percorso UNC: `\\Server\Folder`

    > [!NOTE]
    > I caratteri jolly non sono supportati e i percorsi WebDav non sono supportati.
    >
    > Per modificare l'archivio in un secondo momento, utilizzare invece il cmdlet [Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository) 


Continuare con i passaggi seguenti in base alle esigenze:

- [Eseguire un ciclo di individuazione e visualizzare i report per lo scanner](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Usare PowerShell per configurare lo scanner per applicare la classificazione e la protezione](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Utilizzare PowerShell per configurare un criterio DLP con lo scanner](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

Nella tabella seguente sono elencati i cmdlet di PowerShell rilevanti per l'installazione dello scanner e la gestione dei processi di analisi del contenuto:

| Cmdlet | Descrizione |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Aggiunge un nuovo repository al processo di analisi del contenuto. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|Restituisce i dettagli sul cluster. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Ottiene informazioni dettagliate sul processo di analisi del contenuto. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Ottiene i dettagli sugli archivi definiti per il processo di analisi del contenuto. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Elimina il processo di analisi del contenuto. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Rimuove un repository dal processo di analisi del contenuto. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definisce le impostazioni per il processo di analisi del contenuto. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto. |
| | |

Per altre informazioni, vedere:

- [Che cos'è lo scanner di etichettatura unificato di Azure Information Protection?](/azure/information-protection/deploy-aip-scanner)
- [Configurazione e installazione dello scanner di etichettatura unificato di Azure Information Protection (AIP)](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Gestire i processi di analisi del contenuto solo tramite PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
