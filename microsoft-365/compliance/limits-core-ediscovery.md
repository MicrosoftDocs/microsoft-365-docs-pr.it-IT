---
title: Limiti nel caso di eDiscovery di base
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Questo articolo descrive i limiti nel caso di eDiscovery di base in Microsoft 365.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423447"
---
# <a name="limits-in-core-ediscovery"></a>Limiti in Core eDiscovery

Nella tabella seguente sono elencati i limiti per i casi principali di eDiscovery e i blocchi associati a un caso di eDiscovery di base. Per ulteriori informazioni su Core eDiscovery, vedere [Panoramica di Core eDiscovery.](ediscovery-cases.md)
    
  | Descrizione del limite | Limite |
  |:-----|:-----|
  |Numero massimo di casi per un'organizzazione.  <br/> |Nessun limite  <br/> |
  |Numero massimo di blocchi dei casi per un'organizzazione.  <br/> |10.000  <br/> |
  |Numero massimo di cassette postali in un singolo blocco caso. Questo limite include il totale combinato delle cassette postali degli utenti e le cassette postali associate ai gruppi di Microsoft 365, Microsoft Teams e Gruppi di Yammer.  <br/> |1.000  <br/> |
  |Numero massimo di siti in un blocco caso singolo. Questo limite include il totale combinato dei siti di OneDrive for Business, dei siti di SharePoint e dei siti associati a Gruppi di Microsoft 365, Microsoft Teams e Gruppi di Yammer.  <br/> |100  <br/> |
  |Numero massimo di casi visualizzati nella home page principale di eDiscovery e numero massimo di elementi visualizzati nelle schede Esenzioni, Ricerche ed Esportazione all'interno di un caso. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Per visualizzare un elenco di più di 1.000 casi, blocchi, ricerche o esportazioni, è possibile utilizzare i cmdlet di PowerShell per la sicurezza & e la conformità di Office 365:
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Per ulteriori informazioni sui limiti relativi alle ricerche di contenuto e alle esportazioni associate a un caso di eDiscovery di base, vedere [Limits for Content Search and Core eDiscovery.](limits-for-content-search.md)