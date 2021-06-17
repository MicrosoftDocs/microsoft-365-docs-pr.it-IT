---
title: Informazioni aggiuntive per i provider di soluzioni cloud
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: informazioni aggiuntive per i provider di soluzioni cloud rilevanti per la migrazione da Microsoft Cloud Deutschland.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984917"
---
# <a name="additional-information-for-cloud-solution-providers"></a>Informazioni aggiuntive per i provider di soluzioni cloud

I provider di soluzioni cloud (CSP) che supportano i clienti devono eseguire ulteriori passaggi durante la migrazione da Microsoft Cloud Deutschland alla nuova area data center tedesca.

## <a name="partner-tenant-migration"></a>Migrazione tenant partner

I tenant di Microsoft Cloud Deutschland partner non verranno migrati. Verrà invece creato un nuovo tenant dei Office 365 per ogni partner Microsoft nella nuova area data center tedesca.

I tenant dei clienti CSP verranno migrati nella nuova area dati tedesca e collegati al nuovo tenant dei servizi di Office 365 dello stesso partner. Dopo la transizione del cliente, il partner può gestire il cliente usando il nuovo tenant dei Office 365 nell'area del datacenter tedesco.

## <a name="missing-subscriptions-in-azure"></a>Sottoscrizioni mancanti in Azure

Dopo il completamento della transizione di sottoscrizione e licenza [(fase 3),](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) i provider di soluzioni cloud non avranno più accesso alla sottoscrizione di Azure.

Per ripristinare l'accesso, eseguire la procedura seguente per [elevare l'accesso per gestire tutte le sottoscrizioni e i gruppi di gestione di Azure.](/azure/role-based-access-control/elevate-access-global-admin)
