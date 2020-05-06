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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integrare il server SIEM dell'organizzazione con Office 365 Advanced Threat Protection e gli eventi relativi alle minacce correlati nell'API di gestione delle attività di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035273"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Integrazione di SIEM con Advanced Threat Protection

Se l'organizzazione utilizza un server di gestione eventi e incidenti di sicurezza (SIEM), è possibile integrare Office 365 Advanced Threat Protection con il server SIEM. L'integrazione di SIEM consente di visualizzare le informazioni, ad esempio malware o phishing rilevate da Office 365 Advanced Protection, nei report di SIEM server. Per configurare l'integrazione di SIEM, è possibile utilizzare l' [API di gestione delle attività di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

L'API di gestione delle attività di Office 365 recupera informazioni sulle azioni e sugli eventi degli utenti, dell'amministratore, del sistema e dei criteri dai registri delle attività di Microsoft 365 per le aziende e di Azure Active Directory dell'organizzazione. Lo [schema office 365 Advanced Threat Protection](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) è compatibile con Advanced Threat Protection, quindi se l'organizzazione dispone di Office 365 Advanced Threat Protection Plan 1 o Plan 2 o Office 365 E5, è comunque possibile utilizzare la stessa API per l'integrazione del server Siem. 

Come parte degli aggiornamenti più recenti, sono stati aggiunti anche eventi provenienti da funzionalità di analisi e risposta automatizzate in Office 365 ATP Plan 2 all'interno dell'API di gestione di Office 365 Management. Oltre a includere i dati relativi ai dettagli relativi alle indagini di base, quali ID, nome e stato, contiene anche informazioni di alto livello sulle azioni e sulle entità di indagine.   

Il server SIEM o un altro sistema analogo deve eseguire il polling del carico di lavoro **generale** per accedere agli eventi di rilevamento. Per ulteriori informazioni, vedere [Introduzione alle API di gestione di Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Inoltre, i seguenti valori di **AuditLogRecordType** sono rilevanti per gli eventi ATP di Office 365:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-Type: EDM. Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Valore|Nome membro|Descrizione|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Eventi di phishing e malware da Exchange Online Protection e Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|Collegamenti sicuri ATP gli eventi Time-of-Block e Block override di Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Eventi di phishing e malware per i file in SharePoint Online, OneDrive for business e Microsoft teams dalla protezione avanzata dalle minacce di Office 365.|
|64|Indagine|Eventi di ricerca e di risposta automatizzati, ad esempio i dettagli dell'indagine e gli elementi rilevanti di Office 365 Advanced Threat Protection Plan 2.|


> [!IMPORTANT]
> È necessario essere un amministratore globale o disporre del ruolo di amministratore della sicurezza assegnato per il Centro sicurezza & Compliance per configurare l'integrazione di SIEM con Office 365 Advanced Threat Protection.<br/>La registrazione di controllo deve essere attivata per l'ambiente Microsoft 365. Per ottenere assistenza, vedere [attivazione o disattivazione della ricerca dei log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Argomenti correlati

[Analisi delle minacce e risposta alle minacce in Office 365](office-365-ti.md)

[Indagine automatizzata e risposta (AIR) in Office 365](automated-investigation-response-office.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Smart report e informazioni dettagliate nel centro sicurezza &amp; e conformità](reports-and-insights-in-security-and-compliance.md)
  
[Autorizzazioni nel centro sicurezza &amp; e conformità](permissions-in-the-security-and-compliance-center.md)
  
