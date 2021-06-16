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
ms.openlocfilehash: 7a7c377d8e0b72a0179ff28a93018f88d22a5325
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52931050"
---
# <a name="additional-information-for-cloud-solution-providers"></a>Informazioni aggiuntive per i provider di soluzioni cloud

I provider di soluzioni cloud (CSP) che supportano i clienti devono eseguire ulteriori passaggi durante la migrazione da Microsoft Cloud Deutschland alla nuova area data center tedesca.

## <a name="partner-tenant-migration"></a>Migrazione tenant partner

I tenant di Microsoft Cloud Deutschland partner non verranno migrati. Verrà invece creato un nuovo tenant dei Office 365 per ogni partner Microsoft nella nuova area data center tedesca.

I tenant dei clienti CSP verranno migrati nella nuova area dati tedesca e collegati al nuovo tenant dei servizi di Office 365 dello stesso partner. Dopo la transizione del cliente, il partner può gestire il cliente usando il nuovo tenant dei Office 365 nell'area del datacenter tedesco.

## <a name="missing-subscriptions-in-azure"></a>Sottoscrizioni mancanti in Azure

Dopo il completamento della transizione di sottoscrizione e licenza [(fase 3),](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) i provider di soluzioni cloud non avranno più accesso alla sottoscrizione di Azure.

Per ripristinare l'accesso, eseguire la procedura seguente per [elevare l'accesso per gestire tutte le sottoscrizioni e i gruppi di gestione di Azure.](/azure/role-based-access-control/elevate-access-global-admin)
