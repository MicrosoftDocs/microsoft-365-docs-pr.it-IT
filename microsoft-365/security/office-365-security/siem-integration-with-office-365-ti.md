---
title: Integrazione di SIEM con Advanced Threat Protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Office 365 Advanced Threat Protection e gli eventi relativi alle minacce correlati nell'API di gestione delle attività di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cfb76485fec8eca2f2b62da59fa2d18a56177bba
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203653"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Integrazione di SIEM con Advanced Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se l'organizzazione utilizza un server di gestione eventi e incidenti di sicurezza (SIEM), è possibile integrare Office 365 Advanced Threat Protection (Office 365 ATP) con il server SIEM. È possibile configurare questa integrazione utilizzando l'API di [gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio malware o phishing rilevate da Office 365 ATP, nei report di SIEM server. 

- Per visualizzare un esempio di integrazione di SIEM con Office 365 ATP, vedere [Tech Community Blog: migliorare l'efficacia del SOC con office 365 ATP e l'API di gestione di O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Per ulteriori informazioni sulle API di gestione di Office 365, vedere [Panoramica delle API di gestione](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)di Office 365.

## <a name="how-siem-integration-works"></a>Funzionamento dell'integrazione di SIEM

L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 e Azure Active Directory dell'organizzazione. Se l'organizzazione dispone di Office 365 ATP piano 1 o 2 oppure Office 365 E5, è possibile utilizzare lo [schema ATP di office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Recentemente, gli eventi provenienti da indagini automatizzate e funzionalità di risposta in [office 365 ATP piano 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) sono stati aggiunti all'API di attività di gestione di Office 365. Oltre a includere i dati relativi ai dettagli dell'analisi di base, quali ID, nome e stato, l'API contiene anche informazioni di alto livello sulle azioni e sulle entità di indagine.

Il server SIEM o un altro sistema analogo esegue il polling del **controllo.** carico di lavoro generale per accedere agli eventi di rilevamento. Per ulteriori informazioni, vedere [Introduzione a Office 365 Management Apis](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-Type: EDM. Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

Nella tabella seguente sono riepilogati i valori di **AuditLogRecordType** rilevanti per gli eventi ATP di Office 365:

|Valore|Nome membro|Descrizione|
|---|---|---|
|28|ThreatIntelligence|Eventi di phishing e malware da Exchange Online Protection e Office 365 ATP.|
|41|ThreatIntelligenceUrl|Collegamenti sicuri ATP Time-of-Block e Block override Events from Office 365 ATP.|
|47|ThreatIntelligenceAtpContent|Eventi di phishing e malware per i file in SharePoint Online, OneDrive for business e Microsoft teams, da Office 365 ATP.|
|64|Indagine|Eventi di analisi e di risposta automatizzati, ad esempio i dettagli dell'indagine e gli elementi rilevanti, da Office 365 ATP piano 2.|
|

> [!IMPORTANT]
> È necessario essere un amministratore globale o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Office 365 Advanced Threat Protection.<br/>La registrazione di controllo deve essere attivata per l'ambiente Microsoft 365. Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Vedere anche

[Analisi delle minacce e risposta alle minacce in Office 365](office-365-ti.md)

[Indagine automatizzata e risposta (AIR) in Office 365](automated-investigation-response-office.md)


