---
title: Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender per Endpoint
description: Informazioni su come modificare le query di Microsoft Defender for Endpoint in modo da poterle usare in Microsoft 365 Defender
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, microsoft defender atp, mdatp, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, mapping
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094808"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender per Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender for Endpoint per cercare in modo proattivo le minacce usando un set più ampio di dati. In Microsoft 365 Defender, si ottiene l'accesso ai dati da altre soluzioni di sicurezza di Microsoft 365, tra cui:

- Microsoft Defender per endpoint
- Microsoft Defender per Office 365
- Microsoft Cloud App Security
- Che cosa è Microsoft Defender per identità?

>[!NOTE]
>La maggior parte dei clienti di Microsoft Defender per endpoint [può usare Microsoft 365 Defender senza licenze aggiuntive.](prerequisites.md#licensing-requirements) Per avviare la transizione dei flussi di lavoro di ricerca avanzata da Defender per Endpoint, [attivare Microsoft 365 Defender.](mtp-enable.md)

È possibile eseguire la transizione senza influire sui flussi di lavoro di Defender for Endpoint esistenti. Le query salvate rimangono intatte e le regole di rilevamento personalizzate continuano a essere eseguite e a generare avvisi. Tuttavia, saranno visibili in Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tabelle dello schema solo in Microsoft 365 Defender
Lo schema di ricerca avanzata di [Microsoft 365 Defender](advanced-hunting-schema-tables.md) fornisce tabelle aggiuntive contenenti i dati di varie soluzioni di sicurezza di Microsoft 365. Le tabelle seguenti sono disponibili solo in Microsoft 365 Defender:

| Nome della tabella | Descrizione |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Avvisi di Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity, incluse le informazioni sulla gravità e le categorie di minacce  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Attività relative ai file nelle app e nei servizi cloud |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informazioni sui file allegati ai messaggi di posta elettronica |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventi di posta elettronica di Microsoft 365, inclusi gli eventi di recapito e blocco della posta elettronica |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventi di sicurezza che si verificano dopo il recapito, dopo che Microsoft 365 ha recapitato i messaggi di posta elettronica alla cassetta postale del destinatario |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informazioni sugli URL nei messaggi di posta elettronica |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD). In questa tabella viene illustrata una serie di eventi correlati all'identità e di eventi di sistema nel controller di dominio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Informazioni sull'account da varie origini, tra cui Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventi di autenticazione in Active Directory e Nei servizi online Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Query per oggetti Active Directory, ad esempio utenti, gruppi, dispositivi e domini |

## <a name="map-devicealertevents-table"></a>Tabella Map DeviceAlertEvents
Le `AlertInfo` tabelle `AlertEvidence` e `DeviceAlertEvents` sostituiscono la tabella nello schema di Microsoft Defender per endpoint. Oltre ai dati relativi agli avvisi per i dispositivi, queste due tabelle includono dati sugli avvisi per identità, app e messaggi di posta elettronica.

Utilizzare la tabella seguente per verificare il mapping `DeviceAlertEvents` delle colonne alle colonne nelle tabelle e nelle `AlertInfo` `AlertEvidence` colonne.

>[!TIP]
>Oltre alle colonne della tabella seguente, la tabella include molte altre colonne che forniscono un quadro più olistico degli avvisi `AlertEvidence` provenienti da varie origini. [Visualizzare tutte le colonne AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Colonna DeviceAlertEvents | Dove trovare gli stessi dati in Microsoft 365 Defender |
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
| `ReportId` | Questa colonna viene in genere usata in Microsoft Defender for Endpoint per individuare i record correlati in altre tabelle. In Microsoft 365 Defender, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella. |
| `Table` | Questa colonna viene in genere usata in Microsoft Defender per Endpoint per ulteriori informazioni sugli eventi in altre tabelle. In Microsoft 365 Defender, è possibile ottenere i dati correlati direttamente dalla `AlertEvidence` tabella. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Modificare le query esistenti di Microsoft Defender per endpoint
Le query di Microsoft Defender per endpoint funzionano così come sono, a meno che non fanno riferimento alla `DeviceAlertEvents` tabella. Per usare queste query in Microsoft 365 Defender, applicare queste modifiche:

- Sostituire `DeviceAlertEvents` con `AlertInfo` .
- Unire le `AlertInfo` tabelle e le tabelle per ottenere dati `AlertEvidence` `AlertId` equivalenti.

### <a name="original-query"></a>Query originale
La query seguente usa `DeviceAlertEvents` Microsoft Defender per Endpoint per ottenere gli avvisi che coinvolgono _powershell.exe:_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Query modificata
La query seguente è stata modificata per l'uso in Microsoft 365 Defender. Invece di controllare il nome del file direttamente da , esegue il join e verifica il `DeviceAlertEvents` nome del file nella `AlertEvidence` tabella.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a>Vedere anche
- [Attivare Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Ricerca avanzata in Microsoft Defender per Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)