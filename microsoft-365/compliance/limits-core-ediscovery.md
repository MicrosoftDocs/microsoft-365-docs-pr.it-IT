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
description: Questo articolo descrive i limiti del caso principale di eDiscovery in Microsoft 365.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799663"
---
# <a name="limits-in-core-ediscovery"></a>Limiti in Core eDiscovery

Nella tabella seguente sono elencati i limiti per i casi principali di eDiscovery e i blocchi associati a un caso di eDiscovery di base. Per ulteriori informazioni su Core eDiscovery, vedere [Panoramica di Core eDiscovery.](ediscovery-cases.md)
    
  | Descrizione del limite | Limite |
  |:-----|:-----|
  |Numero massimo di casi per un'organizzazione  <br/> |Nessun limite  <br/> |
  |Numero massimo di blocchi dei casi per un'organizzazione  <br/> |10.000  <br/> |
  |Numero massimo di cassette postali in un blocco caso singolo  <br/> |1.000  <br/> |
  |Numero massimo di siti di SharePoint e OneDrive for Business in un blocco caso singolo  <br/> |100  <br/> |
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