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
description: Per ulteriori informazioni, vedere l'articolo relativo a Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988045"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Supporto di Azure Information Protection per Office 365 gestito da 21Vianet

In questo articolo vengono illustrate le differenze tra il supporto di Azure Information Protection (AIP) per Office 365 gestito da 21Vianet e le offerte commerciali, nonché istruzioni specifiche per la configurazione di AIP per i clienti in Cina, &mdash; tra cui l'installazione dello scanner di AIP in locale e la gestione dei processi di analisi del contenuto.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Differenze tra AIP per Office 365 gestito da 21Vianet e offerte commerciali

Anche se l'obiettivo è quello di fornire tutti i servizi e le funzionalità commerciali ai clienti in Cina con la nostra AIP per Office 365 gestito dall'offerta 21Vianet, ci sono alcune funzionalità mancanti che vorremmo evidenziare.

L'elenco seguente include gli spazi vuoti esistenti tra AIP per Office 365 gestito da 21Vianet e le offerte commerciali del gennaio 2021:

- Information Rights Management (IRM) è supportato solo per le app Microsoft 365 per Enterprise (Build 11731,10000 o versione successiva). Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportate.

- La migrazione da Active Directory Rights Management Services (AD RMS) a AIP non è attualmente disponibile.
  
- La condivisione dei messaggi di posta elettronica protetti con gli utenti nel cloud commerciale è supportata.
  
- La condivisione dei documenti e degli allegati di posta elettronica con gli utenti nel cloud commerciale non è attualmente disponibile. Questo include Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale, non Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale e gli utenti con una licenza RMS per i singoli.
  
- IRM con SharePoint (siti e raccolte protette con IRM) non è attualmente disponibile.
  
- L'estensione del dispositivo mobile per AD RMS non è attualmente disponibile.

- Il [Visualizzatore per dispositivi mobili](/azure/information-protection/rms-client/mobile-app-faq) non è supportato da Azure China 21ViaNet.

## <a name="configure-aip-for-customers-in-china"></a>Configurare l'AIP per i clienti in Cina

Per configurare l'AIP per i clienti in Cina:
1. [Abilitare Rights Management per il tenant](#step-1-enable-rights-management-for-the-tenant).

2. [Configurare la crittografia DNS](#step-2-configure-dns-encryption).

3. [Installare e configurare il client di etichettatura di AIP Unified](#step-3-install-and-configure-the-aip-unified-labeling-client).

4. [Configurare le app AIP su Windows](#step-4-configure-aip-apps-on-windows).

5. [Installare lo scanner locale di AIP e gestire i processi di analisi del contenuto](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs). 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Passaggio 1: abilitare Rights Management per il tenant

Affinché la crittografia funzioni correttamente, RMS deve essere abilitato per il tenant.

1. Controllare se RMS è abilitato:

    1. Avviare PowerShell come amministratore.
    2. Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .
    3. Importare il modulo utilizzando `Import-Module AipService` .
    4. Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .
    5. Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .

2. Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Passaggio 2: configurare la crittografia DNS

Affinché la crittografia funzioni correttamente, le applicazioni client di Office devono connettersi all'istanza di Cina del servizio e bootstrap da tale posizione. Per reindirizzare le applicazioni client all'istanza del servizio appropriato, è necessario che l'amministratore del tenant configuri un record DNS SRV con informazioni sull'URL di Azure RMS. Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.

Inoltre, si presuppone che gli utenti accedano con un nome utente basato sul dominio di proprietà del tenant (ad esempio, `joe@contoso.cn` ) e non sul `onmschina` nome utente (ad esempio, `joe@contoso.onmschina.cn` ). Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.

#### <a name="configure-dns-encryption---windows"></a>Configurare la crittografia DNS-Windows

1. Ottenere l'ID RMS:

    1. Avviare PowerShell come amministratore.
    2. Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .
    3. Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .
    4. Esegui `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.

2. Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.

    - Servizio = `_rmsredir`
    - Protocol = `_http`
    - Name = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)
    - Priorità, peso, secondi, TTL = valori predefiniti

3. Associare il dominio personalizzato al tenant nel portale di [Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). In questo modo verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.

4. Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione dell'utente. Nel processo di verifica, potrebbero essere necessarie ulteriori modifiche DNS. Dopo aver effettuato la verifica, è possibile creare gli utenti.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurare la crittografia DNS-Mac, iOS, Android

Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.

- Servizio = `_rmsdisco`
- Protocol = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Porta = `80`
- Priorità, peso, secondi, TTL = valori predefiniti

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Passaggio 3: installare e configurare il client di etichettatura di AIP Unified

Scaricare il client di etichettatura AIP Unified dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

Per altre informazioni, vedere:

- [Documentazione su AIP](/azure/information-protection/)
- [AIP cronologia delle versioni e criteri di supporto](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisiti di sistema AIP](/azure/information-protection/requirements)
- [Guida introduttiva a AIP: distribuire il client AIP](/azure/information-protection/quickstart-deploy-client)
- [Guida all'amministratore di AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guida per l'utente AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Informazioni sulle etichette di riservatezza di Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>Passaggio 4: configurare le app AIP su Windows

Le app AIP su Windows richiedono la seguente chiave del registro di sistema per indirizzarle al cloud sovrano corretto per Azure China:

- Nodo del registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Valore = `6` (impostazione predefinita = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Assicurarsi di non eliminare la chiave del registro di sistema dopo una disinstallazione. Se la chiave è vuota, errata o inesistente, la funzionalità si comporterà come valore predefinito (valore predefinito = 0 per il cloud commerciale). Se la chiave è vuota o non è corretta, al registro viene aggiunto anche un errore di stampa.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Passaggio 5: installare lo scanner locale di AIP e gestire i processi di analisi del contenuto

Installare lo scanner di AIP in locale per analizzare le condivisioni di rete e di contenuto per i dati sensibili e applicare etichette di classificazione e protezione configurate nei criteri dell'organizzazione.

Quando si installa lo scanner e si gestiscono i processi di analisi del contenuto, utilizzare i cmdlet seguenti anziché l'interfaccia del portale di Azure utilizzata dalle offerte commerciali:<br><br>

| Cmdlet | Descrizione |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Aggiunge un nuovo repository al processo di analisi del contenuto. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Ottiene informazioni dettagliate sul processo di analisi del contenuto. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Ottiene informazioni dettagliate sui repository definiti per il processo di analisi del contenuto. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Elimina il processo di analisi del contenuto. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Rimuove un repository dal processo di analisi del contenuto. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definisce le impostazioni per il processo di analisi del contenuto. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto. |

Per ulteriori informazioni, vedere [What is the Azure Information Protection Unified Labeling scanner?](/azure/information-protection/deploy-aip-scanner) e [gestire i processi di analisi del contenuto utilizzando solo PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).