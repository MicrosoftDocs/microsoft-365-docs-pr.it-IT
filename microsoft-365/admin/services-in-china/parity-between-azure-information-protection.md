---
title: Office 365 gestito da 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Per ulteriori informazioni, vedere Azure Information Protection per Office 365 gestito da 21Vianet e come configurarlo per i clienti in Cina.
monikerRange: o365-21vianet
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627655"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Parità tra Azure Information Protection per Office 365 gestito da 21Vianet e offerte commerciali

Anche se l'obiettivo è quello di fornire tutti i servizi e le funzionalità commerciali ai clienti in Cina con la nostra Azure Information Protection per Office 365 gestito dall'offerta 21Vianet, vi sono alcune funzionalità mancanti che vorremmo evidenziare.

Si tratta degli spazi vuoti esistenti tra Azure Information Protection per Office 365 gestito da 21Vianet e le offerte commerciali del 2019 luglio:

- Information Rights Management (IRM) è supportato solo per le app Microsoft 365 per Enterprise (Build 11731,10000 o versione successiva). Office 2010, Office 2013 e altre versioni di Office 2016 non sono supportate.

- La migrazione da Active Directory Rights Management Services (AD RMS) a Azure Information Protection non è attualmente disponibile.
  
- È supportata la condivisione di messaggi di posta elettronica protetti per gli utenti nel cloud commerciale.
  
- La condivisione dei documenti e degli allegati di posta elettronica per gli utenti nel cloud commerciale non è attualmente disponibile. Questo include Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale, non Office 365 gestito dagli utenti di 21Vianet nel cloud commerciale e gli utenti con una licenza RMS per i singoli.
  
- IRM con SharePoint (siti e raccolte protette con IRM) non è attualmente disponibile.
  
- Il connettore Rights Management non è attualmente disponibile.
  
- L'estensione del dispositivo mobile per AD RMS non è attualmente disponibile.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Configurazione di Azure Information Protection per i clienti in Cina

### <a name="enable-rights-management-for-the-tenant"></a>Abilitare Rights Management per il tenant

Affinché la crittografia funzioni correttamente, è necessario che il server RMS sia abilitato per il tenant.

- Controllare se RMS è abilitato:
  1. Avviare PowerShell come amministratore.
  2. Se il modulo AIPService non è installato, eseguire `Install-Module AipService`.
  3. Importare il modulo utilizzando `Import-Module AipService`.
  4. Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud`.
  5. Eseguire `(Get-AipServiceConfiguration).FunctionalState` e verificare se lo stato è `Enabled`.

- Se lo stato funzionale è `Disabled`, eseguire `Enable-AipService`.

### <a name="dns-configuration-for-encryption-windows"></a>Configurazione DNS per la crittografia (Windows)

Affinché la crittografia funzioni correttamente, le applicazioni client di Office devono connettersi all'istanza di Cina del servizio e bootstrap da tale posizione. Per reindirizzare le applicazioni client all'istanza del servizio appropriato, è necessario che l'amministratore del tenant configuri un record DNS SRV con informazioni sull'URL di Azure RMS. Senza il record DNS SRV, l'applicazione client tenterà di connettersi all'istanza del cloud pubblico per impostazione predefinita e avrà esito negativo.

Inoltre, si presuppone che gli utenti accedano con un nome utente basato sul dominio di proprietà del tenant (ad esempio, `joe@contoso.cn`) e non sul `onmschina` nome utente (ad esempio, `joe@contoso.onmschina.cn`). Il nome di dominio dal nome utente viene utilizzato per il reindirizzamento DNS all'istanza del servizio corretta.

- Ottenere l'ID RMS:
  1. Avviare PowerShell come amministratore.
  2. Se il modulo AIPService non è installato, eseguire `Install-Module AipService`.
  3. Connettersi al servizio tramite `Connect-AipService -environmentname azurechinacloud`.
  4. Esegui `(Get-AipServiceConfiguration).RightsManagementServiceId` per ottenere l'ID RMS.

- Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.
  - Servizio = `_rmsredir`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (dove GUID è l'ID RMS)
  - Priorità, peso, secondi, TTL = valori predefiniti

- Associare il dominio personalizzato al tenant nel portale di [Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). In questo modo verrà aggiunta una voce in DNS, che potrebbe richiedere alcuni minuti per essere verificata dopo aver aggiunto il valore alle impostazioni DNS.

- Accedere all'interfaccia di amministrazione di Microsoft 365 con le credenziali di amministratore globale corrispondenti e aggiungere il dominio (ad esempio `contoso.cn`,) per la creazione dell'utente. Nel processo di verifica, potrebbero essere necessarie ulteriori modifiche DNS. Dopo aver effettuato la verifica, è possibile creare gli utenti.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>Configurazione DNS per la crittografia (Mac, iOS, Android)

- Accedere al provider DNS, passare alle impostazioni DNS per il dominio e quindi aggiungere un nuovo record SRV.
  - Servizio = `_rmsdisco`
  - Protocol = `_http`
  - Name = `_tcp`
  - Target = `api.aadrm.cn`
  - Porta = `80`
  - Priorità, peso, secondi, TTL = valori predefiniti
