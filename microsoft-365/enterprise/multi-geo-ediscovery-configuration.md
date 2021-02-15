---
title: Configurare eDiscovery per Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Informazioni su come utilizzare il parametro Region per configurare eDiscovery per l'utilizzo nelle posizioni satellite in Microsoft 365 Multi-Geo.
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636806"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Configurazione di eDiscovery per Microsoft 365 Multi-Geo

[Le funzionalità avanzate di eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) consentono a un amministratore di eDiscovery multi-geografico di eseguire ricerche in tutte le aree geografiche senza dover utilizzare un filtro di sicurezza "Area geografica". I dati vengono esportati nell'istanza di Azure della posizione centrale del tenant multi-geografico. 

Senza funzionalità avanzate di eDiscovery, un responsabile o un amministratore di un tenant multi-geografico sarà in grado di condurre eDiscovery solo nella posizione centrale del tenant. Per supportare la possibilità di eseguire eDiscovery per le posizioni satellite, tramite PowerShell è disponibile un nuovo parametro del filtro di sicurezza di conformità denominato "Area geografica". Questo parametro può essere utilizzato dai tenant la cui posizione centrale si trova in Nord America, Europa o Asia Pacifico. Advanced eDiscovery è consigliato per i tenant la cui posizione centrale non si trova in Nord America, Europa o Asia Pacifico e che devono eseguire eDiscovery in posizioni geografiche satellite. 

L'amministratore globale di Microsoft 365 deve assegnare le autorizzazioni di manager di eDiscovery per consentire ad altri di eseguire eDiscovery e assegnare un parametro "Area" nel filtro di sicurezza e conformità applicabile per specificare l'area per l'esecuzione di eDiscovery come posizione satellite, in caso contrario nessuna istanza di eDiscovery verrà eseguita per la posizione geografica satellite.

Quando è impostato il ruolo di manager o amministratore di eDiscovery per una posizione satellite specifica, sarà possibile eseguire operazioni di ricerca eDiscovery solo per i siti di SharePoint e OneDrive che si trovano in tale posizione satellite. Se un manager o amministratore di eDiscovery tenta di cercare siti di SharePoint o OneDrive all'esterno della posizione satellite specificata, non visualizzerà alcun risultato. Inoltre, quando il manager o amministratore di eDiscovery di una posizione satellite attiva un'esportazione, i dati vengono esportati nell'istanza di Azure di quest'area. Ciò consente alle organizzazioni di rimanere conformi, non permettendo di esportare contenuti oltre i confini controllati.

> [!NOTE]
> Tuttavia, se dovesse essere necessario per un manager di eDiscovery effettuare una ricerca in più posizioni satellite di SharePoint, sarà necessario creare un altro account utente per il manager di eDiscovery, specificando la posizione satellite alternativa in cui si trovano i siti di OneDrive o SharePoint.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

Per impostare il filtro di sicurezza di conformità per un'area geografica:

1. [Connettersi a PowerShell per Centro sicurezza e conformità di Microsoft 365](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Utilizzare la sintassi seguente:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Ad esempio:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Vedere l’articolo [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter) per ulteriori parametri e sintassi.
