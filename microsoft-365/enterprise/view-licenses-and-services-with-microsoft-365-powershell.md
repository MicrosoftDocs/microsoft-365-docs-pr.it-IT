---
title: Visualizzare Microsoft 365 licenze e servizi con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Spiega come usare PowerShell per visualizzare informazioni sui piani di licenza, i servizi e le licenze disponibili nell'organizzazione Microsoft 365 locale.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924637"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Visualizzare Microsoft 365 licenze e servizi con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Ogni Microsoft 365 è costituito dai seguenti elementi:

- **Piani di licenza** Questi sono noti anche come piani di licenza o Microsoft 365 licenza. I piani di gestione delle Microsoft 365 definiscono i servizi di licenza disponibili per gli utenti. La Microsoft 365 può contenere più piani di licenza. Un piano di licenza di esempio è Microsoft 365 E3.
    
- **Servizi** Questi sono noti anche come piani di servizio. I servizi sono Microsoft 365, funzionalità e funzionalità disponibili in ogni piano di gestione delle licenze, ad esempio Exchange Online e Microsoft 365 Apps for enterprise (in precedenza denominato Office 365 ProPlus). Gli utenti possono disporre di più licenze tramite diversi piani di licenza che garantiscono l'accesso ai diversi servizi.
    
- **Licenze** Ogni piano di licenze contiene il numero di licenze acquistate. Le licenze vengono assegnate agli utenti in modo che possano usare i servizi Microsoft 365 definiti dal piano di gestione delle licenze. Ogni account utente richiede almeno una licenza di un piano di licenza in modo che possa accedere a Microsoft 365 e usare i servizi.
    
È possibile usare PowerShell per Microsoft 365 per visualizzare i dettagli sui piani di licenza, sulle licenze e sui servizi disponibili nell'organizzazione Microsoft 365 locale. Per ulteriori informazioni sui prodotti, le funzionalità e i servizi disponibili in diverse sottoscrizioni Office 365, vedere Office 365 [Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Per visualizzare informazioni di riepilogo sui piani di licenza correnti e sulle licenze disponibili per ogni piano, eseguire questo comando:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

I risultati contengono:
  
- **SkuPartNumber:** Mostra i piani di licenza disponibili per l'organizzazione. Ad esempio, `ENTERPRISEPACK` è il nome del piano di licenza per Office 365 Enterprise E3.
    
- **Abilitato:** Numero di licenze acquistate per un piano di licenze specifico.
    
- **ConsumedUnits:** Numero di licenze assegnate agli utenti da un piano di licenze specifico.
    
Per visualizzare i dettagli sui Microsoft 365 disponibili in tutti i piani di licenza, visualizzare innanzitutto un elenco dei piani di licenza.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Archiviare quindi le informazioni sui piani di licenza in una variabile.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Successivamente, visualizzare i servizi in un piano di licenza specifico.

```powershell
$licenses[<index>].ServicePlans
```

\<index> è un numero intero che specifica il numero di riga del piano di licenza dalla visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando, meno 1.

Ad esempio, se la visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando è la seguente:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Il comando per visualizzare i servizi per il piano di licenza ENTERPRISEPREMIUM è il seguente:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM è la terza riga. Di conseguenza, il valore di indice è (3 - 1) o 2.

Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

>[!Note]
>Uno script PowerShell è disponibile per rendere automatiche le procedure descritte in questo argomento. In particolare, lo script consente di visualizzare e disabilitare i servizi nell'organizzazione Microsoft 365, incluso Sway. Per ulteriori informazioni, vedere [Disabilitare l'accesso a Sway con PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)
>
    
Per visualizzare informazioni di riepilogo sui piani di licenza correnti e sulle licenze disponibili per ogni piano, eseguire il comando seguente:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

I risultati contengono le seguenti informazioni:
  
- **AccountSkuId:** Visualizzare i piani di licenza disponibili per l'organizzazione utilizzando la sintassi `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ è il valore specificato al momento della registrazione a Microsoft 365 ed è univoco per l'organizzazione. Il _\<LicensingPlan>_ valore è lo stesso per tutti. Ad esempio, nel valore , il nome della società è e il nome del piano di licenza , che è il nome di sistema per Office 365 Enterprise `litwareinc:ENTERPRISEPACK` `litwareinc` `ENTERPRISEPACK` E3.
    
- **ActiveUnits:** Numero di licenze acquistate per un piano di licenze specifico.
    
- **WarningUnits:** Numero di licenze in un piano di licenze non rinnovate e che scadranno dopo il periodo di tolleranza di 30 giorni.
    
- **ConsumedUnits:** Numero di licenze assegnate agli utenti da un piano di licenze specifico.
    
Per visualizzare i dettagli sui Microsoft 365 disponibili in tutti i piani di licenza, eseguire il comando seguente:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Nella tabella seguente vengono illustrati i Microsoft 365 e i relativi nomi descrittivi per i servizi più comuni. L'elenco dei piani di servizio degli utenti potrebbe essere diverso. 
  
|**Piano di servizio**|**Descrizione**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for enterprise *(precedentemente denominato Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online, piano 2  <br/> |
   
Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Per visualizzare i dettagli sui Microsoft 365 disponibili in un piano di gestione delle licenze specifico, utilizzare la sintassi seguente.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

Questo esempio mostra i servizi disponibili nel piano di licenza litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)