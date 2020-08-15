---
title: Visualizzare le licenze e i servizi di Microsoft 365 con PowerShell
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
description: Viene illustrato come utilizzare PowerShell per visualizzare informazioni sui piani di licenza, i servizi e le licenze disponibili nell'organizzazione Microsoft 365.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691194"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a>Visualizzare le licenze e i servizi di Microsoft 365 con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Ogni sottoscrizione Microsoft 365 è costituita dai seguenti elementi:

- **Piani di gestione delle licenze** Questi sono noti anche come piani di licenza o Microsoft 365 piani. I piani di gestione delle licenze definiscono i servizi Microsoft 365 che sono disponibili per gli utenti. La sottoscrizione Microsoft 365 potrebbe contenere più piani di gestione delle licenze. Un esempio di piano di gestione delle licenze sarebbe Microsoft 365 E3.
    
- **Servizi offerti** Questi sono noti anche come piani di servizio. Servizi sono i prodotti, le caratteristiche e le funzionalità di Microsoft 365 disponibili in ogni piano di gestione delle licenze, ad esempio, Exchange Online e Microsoft 365 Apps for Enterprise (in precedenza denominato Office 365 ProPlus). Gli utenti possono disporre di più licenze tramite diversi piani di licenza che garantiscono l'accesso ai diversi servizi.
    
- **Licenze** Ogni piano di gestione delle licenze contiene il numero di licenze acquistate. È possibile assegnare licenze agli utenti in modo che possano utilizzare i servizi Microsoft 365 definiti dal piano di gestione delle licenze. Ogni account utente richiede almeno una licenza da un piano di gestione delle licenze, in modo che possano accedere a Microsoft 365 e utilizzare i servizi.
    
È possibile utilizzare PowerShell per Microsoft 365 per visualizzare i dettagli sui piani, le licenze e i servizi di gestione delle licenze disponibili nell'organizzazione Microsoft 365. Per ulteriori informazioni sui prodotti, le caratteristiche e i servizi disponibili in diverse sottoscrizioni di Office 365, vedere [office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Per visualizzare le informazioni di riepilogo sui piani di gestione delle licenze e sulle licenze disponibili per ogni piano, eseguire il comando seguente:
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

I risultati contengono:
  
- **SkuPartNumber:** Visualizza i piani di gestione delle licenze disponibili per l'organizzazione. Ad esempio, `ENTERPRISEPACK` è il nome del piano di licenza per Office 365 Enterprise E3.
    
- **Attivato:** Il numero di licenze acquistate per uno specifico piano di gestione delle licenze.
    
- **ConsumedUnits:** Il numero di licenze assegnate agli utenti da uno specifico piano di gestione delle licenze.
    
Per visualizzare i dettagli sui servizi Microsoft 365 disponibili in tutti i piani di licenza, è necessario innanzitutto visualizzare un elenco dei piani di licenza.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Successivamente, archiviare le informazioni relative ai piani di licenza in una variabile.

```powershell
$licenses = Get-AzureADSubscribedSku
```

Successivamente, visualizzare i servizi in un piano di licenza specifico.

```powershell
$licenses[<index>].ServicePlans
```

\<index> è un valore integer che specifica il numero di riga del piano di licenza dalla visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando (-1).

Ad esempio, se la visualizzazione del `Get-AzureADSubscribedSku | Select SkuPartNumber` comando è la seguente:

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

Successivamente, il comando per visualizzare i servizi per il piano di licenza di ENTERPRISEPREMIUM è il seguente:

```powershell
$licenses[2].ServicePlans
```

ENTERPRISEPREMIUM è la terza riga. Pertanto, il valore di indice è (3-1) oppure 2.

Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), per i piani di servizio inclusi e per i nomi descrittivi corrispondenti, vedere [nomi di prodotti e identificatori di piani di servizio per la gestione delle licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

>[!Note]
>Uno script PowerShell è disponibile per rendere automatiche le procedure descritte in questo argomento. Nello specifico, lo script consente di visualizzare e disabilitare i servizi nell'organizzazione Microsoft 365, tra cui Sway. Per ulteriori informazioni, vedere [disabilitare l'accesso a Sway con PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
>
    
Per visualizzare informazioni di riepilogo sui piani di gestione delle licenze e sulle licenze disponibili per ogni piano, eseguire il comando riportato di seguito:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

I risultati contengono le seguenti informazioni:
  
- **AccountSkuId:** Visualizzare i piani di gestione delle licenze disponibili per l'organizzazione utilizzando la sintassi `<CompanyName>:<LicensingPlan>` .  _\<CompanyName>_ è il valore specificato quando si è registrato Microsoft 365 ed è univoco per l'organizzazione. Il _\<LicensingPlan>_ valore è lo stesso per tutti. Ad esempio, nel valore `litwareinc:ENTERPRISEPACK` , il nome della società è  `litwareinc` e il nome del piano di gestione delle licenze  `ENTERPRISEPACK` , che è il nome di sistema per Office 365 Enterprise E3.
    
- **ActiveUnits:** Il numero di licenze acquistate per uno specifico piano di gestione delle licenze.
    
- **WarningUnits:** Il numero di licenze in un piano di gestione delle licenze che non sono state rinnovate e che scadranno dopo il periodo di tolleranza di 30 giorni.
    
- **ConsumedUnits:** Il numero di licenze assegnate agli utenti da uno specifico piano di gestione delle licenze.
    
Per visualizzare i dettagli sui servizi Microsoft 365 disponibili in tutti i piani di licenza, eseguire il comando riportato di seguito:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Nella tabella seguente vengono illustrati i piani di servizio Microsoft 365 e i relativi nomi descrittivi per i servizi più comuni. L'elenco dei piani di servizio degli utenti potrebbe essere diverso. 
  
|**Piano di servizio**|**Descrizione**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for Enterprise *(in precedenza denominato Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business online  <br/> |
| `SHAREPOINTWAC` <br/> |Ufficio  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online, piano 2  <br/> |
   
Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), per i piani di servizio inclusi e per i nomi descrittivi corrispondenti, vedere [nomi di prodotti e identificatori di piani di servizio per la gestione delle licenze](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Per visualizzare i dettagli sui servizi Microsoft 365 disponibili in uno specifico piano di gestione delle licenze, utilizzare la seguente sintassi.
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

In questo esempio vengono illustrati i servizi disponibili nel piano di gestione delle licenze litwareinc: ENTERPRISEPACK (Office 365 Enterprise E3).
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
