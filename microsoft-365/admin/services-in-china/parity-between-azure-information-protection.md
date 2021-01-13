---
title: Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840302"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali

Anche se l'obiettivo è quello di fornire tutte le caratteristiche e le funzionalità commerciali ai clienti in Cina con la nostra Azure Information Protection (AIP) per Office 365 gestito dall'offerta di 21Vianet, ci sono alcune funzionalità mancanti che vorremmo evidenziare.

L'elenco seguente include gli spazi vuoti esistenti tra Azure Information Protection per Office 365 gestito da 21Vianet e le offerte commerciali del gennaio 2021:

- Information Rights Management (IRM) è supportato solo per le app Microsoft 365 per Enterprise (Build 11731,10000 o versione successiva). Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportate.

- La migrazione da Active Directory Rights Management Services (AD RMS) a Azure Information Protection non è attualmente disponibile.
  
- È supportata la condivisione di messaggi di posta elettronica protetti per gli utenti nel cloud commerciale.
  
- La condivisione dei documenti e degli allegati di posta elettronica per gli utenti nel cloud commerciale non è attualmente disponibile. Questo include Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale, non Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale e gli utenti con una licenza RMS per i singoli.
  
- IRM con SharePoint (siti e raccolte protette con IRM) non è attualmente disponibile.
  
- L'estensione del dispositivo mobile per AD RMS non è attualmente disponibile.

- Il [Visualizzatore per dispositivi mobili](/azure/information-protection/rms-client/mobile-app-faq) non è supportato da Azure China 21ViaNet.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Configurazione di Azure Information Protection per i clienti in Cina

### <a name="enable-rights-management-for-the-tenant"></a>Abilitare Rights Management per il tenant

Affinché la crittografia funzioni correttamente, è necessario che il server RMS sia abilitato per il tenant.

- Controllare se RMS è abilitato:
  1. Avviare PowerShell come amministratore.
  2. Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .
  3. Importare il modulo utilizzando `Import-Module AipService` .
  4. Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .
  5. Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled` .

- Se lo stato funzionale è `Disabled` , eseguire `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>Configurazione DNS per la crittografia (Windows)

Affinché la crittografia funzioni correttamente, le applicazioni client di Office devono connettersi all'istanza di Cina del servizio e bootstrap da tale posizione. Per reindirizzare le applicazioni client all'istanza del servizio appropriato, è necessario che l'amministratore del tenant configuri un record DNS SRV con informazioni sull'URL di Azure RMS. Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.

Inoltre, si presuppone che gli utenti accedano con un nome utente basato sul dominio di proprietà del tenant (ad esempio, `joe@contoso.cn` ) e non sul `onmschina` nome utente (ad esempio, `joe@contoso.onmschina.cn` ). Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.

- Ottenere l'ID RMS:
  1. Avviare PowerShell come amministratore.
  2. Se il modulo di AIPService non è installato, eseguire `Install-Module AipService` .
  3. Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud` .
  4. Esegui `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.

- Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.
  - Servizio = `_rmsredir`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)
  - Priorità, peso, secondi, TTL = valori predefiniti

- Associare il dominio personalizzato al tenant nel portale di [Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). In questo modo verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.

- Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio, `contoso.cn` ) per la creazione dell'utente. Nel processo di verifica, potrebbero essere necessarie ulteriori modifiche DNS. Dopo aver effettuato la verifica, è possibile creare gli utenti.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>Configurazione DNS per la crittografia (Mac, iOS, Android)

Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.

- Servizio = `_rmsdisco`
- Protocol = `_http`
- Name = `_tcp`
- Target = `api.aadrm.cn`
- Porta = `80`
- Priorità, peso, secondi, TTL = valori predefiniti

### <a name="aip-client-configuration"></a>Configurazione client AIP

Il client AIP unificato può essere scaricato dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

Per altre informazioni, vedere:

- [Documentazione relativa alla protezione delle informazioni di Azure](/azure/information-protection/)
- [AIP cronologia delle versioni e criteri di supporto](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisiti di sistema AIP](/azure/information-protection/requirements)
- [Guida introduttiva a AIP: distribuire il client AIP](/azure/information-protection/quickstart-deploy-client)
- [Guida all'amministratore di AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guida per l'utente AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Informazioni sulle etichette di riservatezza di Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a>Configurazione delle app AIP (solo client di etichette unificate)

Per la soluzione di etichettatura unificata, le app AIP su Windows richiedono la seguente chiave del registro di sistema per indirizzarle al cloud Sovereign appropriato per Azure China:

- Nodo del registro di sistema = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- Valore = `6` (impostazione predefinita = 0)
- Type = `REG_DWORD`

> [!IMPORTANT]
> Assicurarsi di non eliminare la chiave del registro di sistema dopo una disinstallazione. Se la chiave è vuota, errata o inesistente, la funzionalità si comporterà come valore predefinito (valore predefinito = 0 per il cloud commerciale). Se la chiave è vuota o non è corretta, al registro viene aggiunto anche un errore di stampa.

### <a name="manage-azure-information-protection-content-scan-jobs"></a>Gestire i processi di analisi del contenuto di Azure Information Protection

Per gestire i processi di analisi del contenuto di Azure Information Protection con un server di Azure China scanner, utilizzare i cmdlet seguenti anziché il portale di Azure:<br><br>

| Cmdlet | Descrizione |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Aggiunge un nuovo repository al processo di analisi del contenuto. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Ottiene informazioni dettagliate sul processo di analisi del contenuto. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Ottiene informazioni dettagliate sui repository definiti per il processo di analisi del contenuto. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Elimina il processo di analisi del contenuto. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Rimuove un repository dal processo di analisi del contenuto. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Definisce le impostazioni per il processo di analisi del contenuto. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Definisce le impostazioni per un archivio esistente nel processo di analisi del contenuto. |

Per ulteriori informazioni, vedere [gestire i processi di analisi del contenuto utilizzando solo PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).