---
title: Supporto di Azure Information Protection per Office 365 gestito da 21Vianet
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
description: Ulteriori informazioni su Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e su come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099679"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Supporto di Azure Information Protection per Office 365 gestito da 21Vianet

Questo articolo illustra le differenze tra il supporto di Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e le offerte commerciali, nonché istruzioni specifiche per la configurazione di AIP per i clienti in Cina, tra cui come installare lo scanner AIP locale e gestire i processi di analisi del &mdash; contenuto.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Differenze tra AIP per Office 365 gestito da 21Vianet e offerte commerciali

Anche se l'obiettivo è fornire tutte le funzionalità commerciali ai clienti in Cina con l'offerta AIP per Office 365 gestito da 21Vianet, alcune funzionalità mancanti sono da evidenziare.

L'elenco seguente include le lacune esistenti tra AIP per Office 365 gestito da 21Vianet e le offerte commerciali a partire da gennaio 2021:

- Information Rights Management (IRM) è supportato solo per Microsoft 365 Apps for enterprise (build 11731.10000 o versione successiva). Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportati.

- La migrazione da Active Directory Rights Management Services (AD RMS) ad AIP non è attualmente disponibile.
  
- La condivisione di messaggi di posta elettronica protetti con gli utenti nel cloud commerciale è supportata.
  
- La condivisione di documenti e allegati di posta elettronica con gli utenti nel cloud commerciale non è attualmente disponibile. Sono inclusi Office 365 gestito da utenti di 21Vianet nel cloud commerciale, utenti non di Office 365 gestiti da 21Vianet nel cloud commerciale e utenti con licenza RMS per singoli utenti.
  
- IRM con SharePoint (siti e raccolte protetti tramite IRM) non è attualmente disponibile.
  
- L'estensione per dispositivi mobili per AD RMS non è attualmente disponibile.

- Il [visualizzatore per](/azure/information-protection/rms-client/mobile-app-faq) dispositivi mobili non è supportato da Azure China 21Vianet.

- L'area AIP del portale di Azure non è disponibile per i clienti in Cina. Utilizzare [i comandi di PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) invece di eseguire azioni nel portale, ad esempio l'installazione dello scanner locale e la gestione dei processi di analisi del contenuto.

## <a name="configure-aip-for-customers-in-china"></a>Configurare AIP per i clienti in Cina

Per configurare AIP per i clienti in Cina:
1. [Abilitare Rights Management per il tenant.](#step-1-enable-rights-management-for-the-tenant)

2. [Configurare la crittografia DNS.](#step-2-configure-dns-encryption)

3. [Installare e configurare il client di etichettatura unificato AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Configurare le app AIP in Windows.](#step-4-configure-aip-apps-on-windows)

5. [Installare lo scanner AIP locale e gestire i](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)processi di analisi del contenuto. 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Passaggio 1: abilitare Rights Management per il tenant

Per il corretto funzionamento della crittografia, è necessario che RMS sia abilitato per il tenant.

1. Verificare se RMS è abilitato:

    1. Avviare PowerShell come amministratore.
    2. Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .
    3. Importare il modulo utilizzando `Import-Module AipService` .
    4. Connettersi al servizio utilizzando `Connect-AipService -environmentname azurechinacloud` .
    5. Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .

2. Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Passaggio 2: Configurare la crittografia DNS

Per il corretto funzionamento della crittografia, le applicazioni client di Office devono connettersi all'istanza cina del servizio e avviare il bootstrap da qui. Per reindirizzare le applicazioni client all'istanza del servizio corretto, l'amministratore tenant deve configurare un record DNS SRV con informazioni sull'URL di Azure RMS. Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.

Inoltre, si presuppone che gli utenti accederanno con un nome utente basato sul dominio di proprietà del tenant (ad esempio, ) e non con il nome `joe@contoso.cn` `onmschina` utente (ad esempio, `joe@contoso.onmschina.cn` ). Il nome di dominio del nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.

#### <a name="configure-dns-encryption---windows"></a>Configurare la crittografia DNS - Windows

1. Ottenere l'ID RMS:

    1. Avviare PowerShell come amministratore.
    2. Se il modulo AIPService non è installato, eseguire `Install-Module AipService` .
    3. Connettersi al servizio utilizzando `Connect-AipService -environmentname azurechinacloud` .
    4. Eseguire `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.

2. Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.

    - Servizio = `_rmsredir`
    - Protocol = `_http`
    - Nome = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)
    - Priorità, Peso, Secondi, TTL = valori predefiniti

3. Associare il dominio personalizzato al tenant nel [portale di Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo l'aggiunta del valore alle impostazioni DNS.

4. Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione degli utenti. Nel processo di verifica potrebbero essere necessarie ulteriori modifiche al DNS. Dopo aver eseguito la verifica, gli utenti possono essere creati.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurare la crittografia DNS - Mac, iOS, Android

Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.

- Servizio = `_rmsdisco`
- Protocol = `_http`
- Nome = `_tcp`
- Target = `api.aadrm.cn`
- Port = `80`
- Priorità, Peso, Secondi, TTL = valori predefiniti

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Passaggio 3: Installare e configurare il client di etichettatura unificato AIP

Scaricare il client di etichettatura unificato AIP [dall'Area download Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

Per altre informazioni, vedere:

- [Documentazione AIP](/azure/information-protection/)
- [Cronologia delle versioni AIP e criteri di supporto](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisiti di sistema AIP](/azure/information-protection/requirements)
- [Guida introduttiva AIP: Distribuire il client AIP](/azure/information-protection/quickstart-deploy-client)
- [Guida all'amministratore AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Manuale dell'utente AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Informazioni sulle etichette di riservatezza di Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Passaggio 4: Configurare le app AIP in Windows

Le app AIP in Windows necessitano della chiave del Registro di sistema seguente per puntare al cloud sovrano corretto per Azure Cina:

- Nodo del Registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Nome = `CloudEnvType`
- Valore = `6` (valore predefinito = 0)
- Tipo = `REG_DWORD`

> [!IMPORTANT]
> Assicurati di non eliminare la chiave del Registro di sistema dopo una disinstallazione. Se la chiave è vuota, errata o inesistente, la funzionalità verrà utilizzata come valore predefinito (valore predefinito = 0 per il cloud commerciale). Se la chiave è vuota o errata, al registro viene aggiunto anche un errore di stampa.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Passaggio 5: Installare lo scanner AIP locale e gestire i processi di analisi del contenuto

Installare lo scanner AIP locale per analizzare la rete e le condivisioni di contenuto per i dati sensibili e applicare le etichette di classificazione e protezione configurate nei criteri dell'organizzazione.

Quando si installa lo scanner e si gestiscono i processi di analisi del contenuto, utilizzare i cmdlet seguenti anziché l'interfaccia del portale di Azure utilizzata dalle offerte commerciali:<br><br>

| Cmdlet | Descrizione |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Aggiunge un nuovo archivio al processo di analisi del contenuto. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Ottiene informazioni dettagliate sul processo di analisi del contenuto. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Ottiene informazioni dettagliate sugli archivi definiti per il processo di analisi del contenuto. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Elimina il processo di analisi del contenuto. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Rimuove un archivio dal processo di analisi del contenuto. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definisce le impostazioni per il processo di analisi del contenuto. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto. |

Per altre informazioni, vedere [Che cos'è lo scanner](/azure/information-protection/deploy-aip-scanner) di etichettatura unificata di Azure Information Protection? e Gestire i processi di analisi del contenuto solo tramite [PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)
