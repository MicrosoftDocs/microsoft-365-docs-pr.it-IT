---
title: Creare notifiche per attività di corrispondenza esatta dei dati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come creare notifiche per le attività di corrispondenza esatta dei dati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15aa8f2bda76d56d3e35af8e884193193bb78d40
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007562"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Creare notifiche per attività di corrispondenza esatta dei dati

Quando si [creano tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) nel [log di audit](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log) vengono create diverse attività. È possibile usare il cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) di PowerShell per creare notifiche che consentono di sapere quando si verificano queste attività:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

## <a name="pre-requisites"></a>Prerequisiti

L'account da usare deve essere uno dei seguenti:

- Amministratore globale
- Amministratore di conformità
- Amministratore di Exchange Online

Per ulteriori informazioni sulle autorizzazioni DLP, vedere [Autorizzazioni](data-loss-prevention-policies.md#permissions).

La classificazione basata su EDM è inclusa negli abbonamenti

- Office 365 E5
- Microsoft 365 E5
- Conformità Microsoft 365 E5
- Microsoft E5/A5 Information Protection and Governance

Per altre informazioni sulle licenze DLP, vedere [Indicazioni sulla gestione delle licenze di Microsoft 365 per la sicurezza e la conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>Configurare le notifiche per le attività EDM

1. Connettersi a [PowerShell nel Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps) 

2. Eseguire il cmdlet `New-ProtectionAlert` usando l'attività per cui si vuole creare la notifica.  Ad esempio, se si vuole ricevere una notifica quando si verifica l’azione **UploadDataCompleted**, eseguire

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

per l’azione **UploadDataFailed** è possibile eseguire

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>Articoli correlati

- [Creare tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)