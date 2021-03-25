---
title: Integrazione SIEM con Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Microsoft Defender per Office 365 e gli eventi di minaccia correlati nell'API di gestione delle attività di Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8f86c831df16568ae569e7b21c7e0a33475948
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205175"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integrazione SIEM con Microsoft Defender per Office 365

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se l'organizzazione usa un server SIEM (Security Information and Event Management), è possibile integrare Microsoft Defender per Office 365 con il server SIEM. È possibile configurare questa integrazione usando l'API di gestione delle attività di [Office 365.](/office/office-365-management-api/office-365-management-activity-api-reference)

L'integrazione SIEM consente di visualizzare informazioni, ad esempio malware o phish rilevati da Microsoft Defender per Office 365, nei report del server SIEM.

- Per un esempio di integrazione SIEM con Microsoft Defender per Office 365, vedere blog della community tech: migliorare l'efficacia del SOC con [Defender per Office 365 e l'API di gestione di O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Per ulteriori informazioni sulle API di gestione di Office 365, vedere Panoramica delle API di gestione di [Office 365.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Funzionamento dell'integrazione SIEM

L'API di gestione delle attività di Office 365 recupera informazioni su azioni ed eventi di utenti, amministratori, sistema e criteri dai log attività di Microsoft 365 e Azure Active Directory dell'organizzazione. Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 1 o 2 o Office 365 E5, è possibile usare [lo schema di Microsoft Defender per Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Di recente, gli eventi delle funzionalità di analisi e risposta automatizzate in [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) sono stati aggiunti all'API di attività di gestione di Office 365. Oltre a includere dati sui dettagli dell'indagine di base, ad esempio ID, nome e stato, l'API contiene anche informazioni di alto livello sulle azioni ed entità di indagine.

Il server SIEM o un altro sistema simile esegue il polling del **carico di lavoro audit.general** per accedere agli eventi di rilevamento. Per altre informazioni, vedere Introduzione alle API di gestione di [Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enumerazione: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

Nella tabella seguente sono riepilogati i valori di **AuditLogRecordType** rilevanti per gli eventi di Microsoft Defender per Office 365:

|Valore|Nome membro|Descrizione|
|---|---|---|
|28|ThreatIntelligence|Eventi di phishing e malware da Exchange Online Protection e Microsoft Defender per Office 365.|
|41|ThreatIntelligenceUrl|Safe Links time-of-block and block override events from Microsoft Defender for Office 365.|
|47|ThreatIntelligenceAtpContent|Eventi di phishing e malware per i file in SharePoint Online, OneDrive for Business e Microsoft Teams, da Microsoft Defender per Office 365.|
|64|AirInvestigation|Eventi di indagine e risposta automatizzati, ad esempio dettagli dell'indagine e artefatti rilevanti, da Microsoft Defender per Office 365 Piano 2.|
|

> [!IMPORTANT]
> Per configurare l &'integrazione di SIEM con Microsoft Defender per Office 365, è necessario essere un amministratore globale o disporre del ruolo di amministratore della sicurezza per il Centro sicurezza e conformità.
>
> La registrazione di controllo deve essere attivata per l'ambiente Microsoft 365. Per informazioni su questo argomento, vedere Attivare o disattivare la ricerca nel [log di controllo.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Vedere anche

[Analisi delle minacce e risposta alle minacce in Office 365](office-365-ti.md)

[Analisi e risposta automatizzate (AIR) in Office 365](automated-investigation-response-office.md)