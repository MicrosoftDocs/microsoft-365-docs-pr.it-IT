---
title: Informazioni sul criterio predefinito per la prevenzione della perdita di dati in Microsoft Teams (anteprima)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Informazioni sui criteri di prevenzione della perdita di dati predefiniti in Microsoft Teams
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149119"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Informazioni sul criterio predefinito per la prevenzione della perdita di dati in Microsoft Teams (anteprima)

[Le funzionalità di prevenzione della](dlp-learn-about-dlp.md) perdita dei dati sono state estese Microsoft Teams messaggi di chat e canali, inclusi i messaggi del canale privato. Come parte di questa versione, è stato creato un criterio DLP predefinito per Microsoft Teams per i clienti al Centro conformità per la prima volta.

## <a name="applies-to"></a>Si applica a

Qualsiasi tenant concesso in licenza con una o più delle licenze seguenti e con utenti Teams attivi
 
- ME5, 
- MA5, 
- Conformità E5/A5, 
- IP+G, 
- OE5, 
- Conformità avanzata di O365 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>Cosa fa il criterio predefinito?

Il criterio DLP predefinito per Teams tiene traccia di tutti i numeri di carta di credito condivisi internamente ed esternamente all'organizzazione. Questo criterio è in base all'impostazione predefinita per tutti gli utenti del tenant. Non genera suggerimenti per i criteri per gli utenti finali, ma genera un evento Alert e inoltre attiva un messaggio di posta elettronica di bassa gravità per l'amministratore (aggiunto nel criterio). L'amministratore può visualizzare le attività e modificare i dettagli dei criteri accedendo al Centro conformità.

Gli amministratori possono visualizzare questo criterio nel [Centro](https://compliance.microsoft.com/compliancesettings) conformità > criteri di prevenzione della perdita di dati.


> [!div class="mx-imgBorder"]
> ![criterio DLP Teams predefinito](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Modificare o eliminare il criterio predefinito

Per [modificare il criterio predefinito per migliorare le prestazioni](create-test-tune-dlp-policy.md#tune-a-dlp-policy)o eliminarlo, è sufficiente utilizzare un account con autorizzazioni di gestione della conformità **DLP.** Per ulteriori informazioni, vedere [Autorizzazioni](create-test-tune-dlp-policy.md#permissions).

