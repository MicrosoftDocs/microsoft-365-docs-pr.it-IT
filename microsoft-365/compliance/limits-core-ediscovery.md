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
description: In questo articolo vengono descritti i limiti nel caso di eDiscovery di base in Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311425"
---
# <a name="limits-in-core-ediscovery"></a>Limiti in Core eDiscovery

Nella tabella seguente sono elencati i limiti per i casi principali di eDiscovery e i blocchi associati a un caso di eDiscovery di base. Per ulteriori informazioni su Core eDiscovery, vedere [Overview of Core eDiscovery.](./get-started-core-ediscovery.md)
    
  | Descrizione del limite | Limite |
  |:-----|:-----|
  |Numero massimo di casi per un'organizzazione.  <br/> |Nessun limite  <br/> |
  |Numero massimo di blocchi di maiuscole e minuscole per un'organizzazione.  <br/> |10.000  <br/> |
  |Numero massimo di cassette postali in un singolo caso di blocco. Questo limite include il totale combinato delle cassette postali degli utenti e le cassette postali associate Microsoft 365 gruppi, Microsoft Teams e Yammer gruppi.  <br/> |1.000  <br/> |
  |Numero massimo di siti in un singolo caso di blocco. Questo limite include il totale combinato di OneDrive for Business, siti SharePoint e siti associati a Microsoft 365 Groups, Microsoft Teams e Yammer Groups.  <br/> |100  <br/> |
  |Numero massimo di casi visualizzati nella home page principale di eDiscovery e numero massimo di elementi visualizzati nelle schede Esenzioni, Ricerche ed Esportazione all'interno di un caso. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Per visualizzare un elenco di più di 1.000 casi, blocchi, ricerche o esportazioni, è possibile utilizzare i cmdlet di PowerShell Office 365 Security & Compliance corrispondenti:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Per ulteriori informazioni sui limiti relativi alle ricerche e alle esportazioni associate a un caso di eDiscovery di base, vedere [Limits for Content search e Core eDiscovery.](limits-for-content-search.md)