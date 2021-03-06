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
ms.openlocfilehash: 263dc319d7e7d3ee5f12ebe374e8f5bd44c4cc8c
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341677"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Creare notifiche per attività di corrispondenza esatta dei dati

Quando si [creano tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) nel [log di audit](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log) vengono create diverse attività. È possibile usare il cmdlet [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) di PowerShell per creare notifiche che consentono di sapere quando si verificano queste attività:

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

La classificazione basata su EDM è inclusa negli abbonamenti seguenti:

- Office 365 E5
- Microsoft 365 E5
- Conformità Microsoft 365 E5
- Microsoft E5/A5 Information Protection and Governance

Per altre informazioni sulle licenze DLP, vedere [Indicazioni sulla gestione delle licenze di Microsoft 365 per la sicurezza e la conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>Configurare le notifiche per le attività EDM

1. Connettersi a [PowerShell nel Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).

2. Eseguire il cmdlet `New-ProtectionAlert` usando l'attività per cui si vuole creare la notifica.  Ad esempio, se si vuole ricevere una notifica quando si verifica l'azione **UploadDataCompleted**, eseguire:

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    per l'azione **UploadDataFailed** è possibile eseguire:
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>Articoli correlati

- [Creare tipi di informazioni sensibili personalizzate con corrispondenza esatta dei dati (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)