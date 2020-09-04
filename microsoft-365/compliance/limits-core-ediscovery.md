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
description: In questo articolo vengono descritti i limiti in core eDiscovery case in Microsoft 365.
ms.openlocfilehash: 6224ce5ecb8fc0439e43ab5e1362f8a618194202
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358514"
---
# <a name="limits-in-core-ediscovery"></a>Limiti in eDiscovery di base

Nella tabella seguente sono elencati i limiti per i casi di eDiscovery di base e le esenzioni associate a un caso di eDiscovery di base. Per ulteriori informazioni su eDiscovery di base, vedere [Overview of core eDiscovery](ediscovery-cases.md).
    
  |**Descrizione del limite**|**Tipo di limite**|
  |:-----|:-----|
  |Numero massimo di casi per un'organizzazione  <br/> |Nessun limite  <br/> |
  |Numero massimo di case conservate per un'organizzazione  <br/> |10.000  <br/> |
  |Numero massimo di cassette postali in un singolo blocco maiuscole/minuscole  <br/> |1,000  <br/> |
  |Numero massimo di siti di SharePoint e OneDrive for business in un unico blocco del caso  <br/> |100  <br/> |
  |Numero massimo di casi visualizzati nella Home page di eDiscovery principale e il numero massimo di elementi visualizzati nelle schede esenzioni, ricerche ed esportazione all'interno di un caso. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> per visualizzare un elenco di più di 1.000 casi, esenzioni, ricerche o esportazioni, è possibile utilizzare il cmdlet di PowerShell per la sicurezza & conformità corrispondente di Office 365:<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
