---
title: Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender ATP
description: Informazioni su come modificare le query di Microsoft Defender ATP in modo che sia possibile utilizzarle in Microsoft Threat Protection
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Microsoft Defender ATP, mdatp, Search, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, mapping
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f56360b28a9fe9de4198d97954a64a429d1d99a5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429696"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft Threat Protection

Spostare i flussi di lavoro avanzati di caccia da Microsoft Defender ATP per cercare in modo proattivo le minacce utilizzando un set di dati più ampio. In Microsoft Threat Protection, è possibile accedere ai dati di altre soluzioni di sicurezza di Microsoft 365, tra cui:

- Microsoft Defender Advanced Threat Protection
- Office 365 Advanced Threat Protection
- Microsoft Cloud App Security
- Azure Advanced Threat Protection

>[!NOTE]
>La maggior parte dei clienti Microsoft Defender ATP può [utilizzare Microsoft Threat Protection senza licenze aggiuntive](prerequisites.md#licensing-requirements). Per iniziare a eseguire la transizione dei flussi di lavoro avanzati di caccia da Microsoft Defender ATP, [attivare Microsoft Threat Protection](mtp-enable.md).

È possibile eseguire la transizione senza influire sui flussi di lavoro di Microsoft Defender ATP esistenti. Le query salvate restano intatte e le regole di rilevamento personalizzate continuano a essere eseguite e a generare avvisi. Tuttavia, saranno visibili in Microsoft Threat Protection. 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Tabelle dello schema solo in Microsoft Threat Protection
Lo [schema di protezione avanzata di Microsoft Threat Protection](advanced-hunting-schema-tables.md) fornisce ulteriori tabelle contenenti dati provenienti da varie soluzioni di sicurezza di Microsoft 365. Le tabelle seguenti sono disponibili solo in Microsoft Threat Protection:

| Nome della tabella | Descrizione |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Avvisi di Microsoft Defender ATP, Office 365 ATP, Microsoft cloud app Security e Azure ATP, incluse le informazioni sulla gravità e le categorie di minacce  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Attività correlate ai file nelle app e nei servizi cloud |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informazioni sui file allegati ai messaggi di posta elettronica |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 eventi di posta elettronica, inclusi gli eventi di blocco e recapito della posta elettronica |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventi di sicurezza che si verificano dopo il recapito, dopo che Microsoft 365 ha inviato i messaggi di posta elettronica alla cassetta postale del destinatario |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informazioni sugli URL nei messaggi di posta elettronica |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD). In questa tabella viene illustrata una serie di eventi relativi a identità e eventi di sistema nel controller di dominio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Informazioni sugli account provenienti da origini diverse, tra cui Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventi di autenticazione in Active Directory e nei Microsoft Online Services |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Query per gli oggetti di Active Directory, ad esempio utenti, gruppi, dispositivi e domini |

## <a name="map-devicealertevents-table"></a>Tabella DeviceAlertEvents map
Le `AlertInfo` `AlertEvidence` tabelle e sostituiscono la `DeviceAlertEvents` tabella nello schema ATP Microsoft Defender. Oltre ai dati relativi agli avvisi dei dispositivi, queste due tabelle includono dati relativi agli avvisi relativi a identità, app e messaggi di posta elettronica.

Utilizzare la tabella seguente per controllare in che modo le `DeviceAlertEvents` colonne devono essere mappate alle colonne nelle `AlertInfo` `AlertEvidence` tabelle e.

>[!TIP]
>Oltre alle colonne nella tabella seguente, la `AlertEvidence` tabella include molte altre colonne che forniscono un'immagine più olistica degli avvisi provenienti da varie origini. [Vedere tutte le colonne di AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Colonna DeviceAlertEvents | Dove trovare gli stessi dati in Microsoft Threat Protection |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` e  `AlertEvidence` tabelle |
| `Timestamp` | `AlertInfo` e  `AlertEvidence` tabelle |
| `DeviceId` | `AlertEvidence` tavolo |
| `DeviceName` | `AlertEvidence` tavolo |
| `Severity` | `AlertInfo` tavolo |
| `Category` | `AlertInfo` tavolo |
| `Title` | `AlertInfo` tavolo |
| `FileName` | `AlertEvidence` tavolo |
| `SHA1` | `AlertEvidence` tavolo |
| `RemoteUrl` | `AlertEvidence` tavolo |
| `RemoteIP` | `AlertEvidence` tavolo |
| `AttackTechniques` | `AlertInfo` tavolo |
| `ReportId` | Questa colonna è in genere utilizzata in Microsoft Defender ATP per individuare i record correlati in altre tabelle. In Microsoft Threat Protection, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella. |
| `Table` | Questa colonna è in genere utilizzata in Microsoft Defender ATP per ulteriori informazioni sugli eventi in altre tabelle. In Microsoft Threat Protection, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella. |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>Modificare le query esistenti di Microsoft Defender ATP
Le query di Microsoft Defender ATP funzioneranno così come sono, a meno che non facciano riferimento alla `DeviceAlertEvents` tabella. Per utilizzare queste query in Microsoft Threat Protection, applicare le modifiche seguenti:

- Sostituisci `DeviceAlertEvents` con `AlertInfo` .
- Aggiungere la `AlertInfo` e le `AlertEvidence` tabelle `AlertId` per ottenere dati equivalenti.

### <a name="original-query"></a>Query originale
La query seguente utilizza `DeviceAlertEvents` Microsoft Defender ATP per ottenere gli avvisi che coinvolgono _powershell.exe_:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Query modificata
La query seguente è stata regolata per l'utilizzo in Microsoft Threat Protection. Invece di controllare direttamente il nome del file `DeviceAlertEvents` , si unisce `AlertEvidence` e controlla il nome del file in quella tabella.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Argomenti correlati
- [Attivare Microsoft Threat Protection](advanced-hunting-query-language.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Ricerca avanzata in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)