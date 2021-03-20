---
title: Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint
description: Informazioni su come modificare le query di Microsoft Defender for Endpoint in modo da poterle usare in Microsoft 365 Defender
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, microsoft defender atp, mdatp, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, mapping
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
ms.openlocfilehash: 5f356c5861586d4435a619a056a6fa1a0afc53f0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904139"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Sposta i flussi di lavoro di ricerca avanzati da Microsoft Defender for Endpoint per cercare in modo proattivo le minacce usando un set più ampio di dati. In Microsoft 365 Defender, si ottiene l'accesso ai dati da altre soluzioni di sicurezza di Microsoft 365, tra cui:

- Microsoft Defender per endpoint
- Microsoft Defender per Office 365
- Microsoft Cloud App Security
- Che cosa è Microsoft Defender per identità?

>[!NOTE]
>La maggior parte dei clienti di Microsoft Defender per Endpoint [può usare Microsoft 365 Defender senza licenze aggiuntive.](prerequisites.md#licensing-requirements) Per avviare la transizione dei flussi di lavoro di ricerca avanzata da Defender for Endpoint, [attiva Microsoft 365 Defender.](mtp-enable.md)

Puoi eseguire la transizione senza influire sui flussi di lavoro esistenti di Defender for Endpoint. Le query salvate rimangono intatte e le regole di rilevamento personalizzate continuano a essere eseguite e a generare avvisi. Saranno tuttavia visibili in Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tabelle dello schema solo in Microsoft 365 Defender
Lo schema di ricerca avanzata di [Microsoft 365 Defender](advanced-hunting-schema-tables.md) fornisce tabelle aggiuntive contenenti dati di varie soluzioni di sicurezza di Microsoft 365. Le tabelle seguenti sono disponibili solo in Microsoft 365 Defender:

| Nome della tabella | Descrizione |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | File, indirizzi IP, URL, utenti o dispositivi associati agli avvisi |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Avvisi da Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity, incluse le informazioni sulla gravità e le categorie di minacce  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Attività correlate ai file in app e servizi cloud |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informazioni sui file allegati ai messaggi di posta elettronica |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventi di posta elettronica di Microsoft 365, inclusi il recapito della posta elettronica e gli eventi di blocco |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventi di sicurezza che si verificano dopo il recapito, dopo che Microsoft 365 ha recapitato i messaggi di posta elettronica alla cassetta postale del destinatario |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informazioni sugli URL nei messaggi di posta elettronica |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventi che coinvolgono un controller di dominio locale che esegue Active Directory (AD). In questa tabella viene illustrata una serie di eventi correlati all'identità ed eventi di sistema nel controller di dominio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Informazioni sull'account da varie origini, tra cui Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventi di autenticazione in Active Directory e Microsoft online Services |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Query per oggetti Active Directory, ad esempio utenti, gruppi, dispositivi e domini |

>[!IMPORTANT]
> Le query e i rilevamenti personalizzati che utilizzano tabelle dello schema disponibili solo in Microsoft 365 Defender possono essere visualizzati solo in Microsoft 365 Defender.

## <a name="map-devicealertevents-table"></a>Tabella Map DeviceAlertEvents
Le `AlertInfo` tabelle e `AlertEvidence` sostituiscono la tabella nello schema di Microsoft `DeviceAlertEvents` Defender for Endpoint. Oltre ai dati sugli avvisi per i dispositivi, queste due tabelle includono i dati sugli avvisi per identità, app e messaggi di posta elettronica.

Utilizzare la tabella seguente per verificare il mapping `DeviceAlertEvents` delle colonne alle colonne nelle tabelle e `AlertInfo` `AlertEvidence` .

>[!TIP]
>Oltre alle colonne della tabella seguente, la tabella include molte altre colonne che forniscono un'immagine più olistica degli avvisi `AlertEvidence` provenienti da varie origini. [Vedi tutte le colonne AlertEvidence](advanced-hunting-alertevidence-table.md) 

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
| `ReportId` | Questa colonna viene in genere utilizzata in Microsoft Defender for Endpoint per individuare i record correlati in altre tabelle. In Microsoft 365 Defender puoi ottenere i dati correlati direttamente dalla `AlertEvidence` tabella. |
| `Table` | Questa colonna viene in genere usata in Microsoft Defender for Endpoint per ulteriori informazioni sugli eventi in altre tabelle. In Microsoft 365 Defender puoi ottenere i dati correlati direttamente dalla `AlertEvidence` tabella. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Modificare le query esistenti di Microsoft Defender for Endpoint
Le query di Microsoft Defender for Endpoint funzionano così come sono, a meno che non fanno riferimento alla `DeviceAlertEvents` tabella. Per usare queste query in Microsoft 365 Defender, applicare queste modifiche:

- Sostituire `DeviceAlertEvents` con `AlertInfo` .
- Unire le `AlertInfo` tabelle e le tabelle per ottenere dati `AlertEvidence` `AlertId` equivalenti.

### <a name="original-query"></a>Query originale
La query seguente usa `DeviceAlertEvents` Microsoft Defender for Endpoint per ottenere gli avvisi che coinvolgono _powershell.exe:_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Query modificata
La query seguente è stata modificata per l'utilizzo in Microsoft 365 Defender. Invece di controllare il nome del file direttamente da , viene aggiunta e verificata la `DeviceAlertEvents` presenza del nome del file nella `AlertEvidence` tabella.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Eseguire la migrazione di regole di rilevamento personalizzate

Quando le regole di Microsoft Defender for Endpoint vengono modificate in Microsoft 365 Defender, continuano a funzionare come prima se la query risultante esamina solo le tabelle dei dispositivi. 

Ad esempio, gli avvisi generati da regole di rilevamento personalizzate che eseguono query solo sulle tabelle dei dispositivi continueranno a essere recapitati al SIEM e genereranno notifiche di posta elettronica, a seconda di come sono stati configurati in Microsoft Defender for Endpoint. Anche le regole di eliminazione esistenti in Defender for Endpoint continueranno ad essere applicate.

Dopo aver modificato una regola di Defender for Endpoint in modo che eseere query sulle tabelle di identità e posta elettronica, disponibili solo in Microsoft 365 Defender, la regola viene spostata automaticamente in Microsoft 365 Defender. 

Avvisi generati dalla regola migrata:

- Non sono più visibili nel portale di Defender for Endpoint (Microsoft Defender Security Center)
- Smettere di essere recapitati al SIEM o generare notifiche di posta elettronica. Per risolvere questo problema, configurare le notifiche tramite Microsoft 365 Defender per ottenere gli avvisi. Puoi usare [l'API di Microsoft 365 Defender per](api-incident.md) ricevere notifiche per avvisi di rilevamento dei clienti o eventi imprevisti correlati.
- Non verrà eliminato da Microsoft Defender per le regole di eliminazione degli endpoint. Per impedire la generazione di avvisi per determinati utenti, dispositivi o cassette postali, modificare le query corrispondenti per escludere tali entità in modo esplicito.

Se si modifica una regola in questo modo, verrà richiesta una conferma prima dell'applicazione di tali modifiche.

I nuovi avvisi generati dalle regole di rilevamento personalizzate nel portale di Microsoft 365 Defender vengono visualizzati in una pagina di avviso che fornisce le informazioni seguenti:

- Titolo e descrizione dell'avviso 
- Asset influenzati
- Azioni eseguite in risposta all'avviso
- Risultati della query che hanno attivato l'avviso 
- Informazioni sulla regola di rilevamento personalizzata 
 
![Immagine della pagina del nuovo avviso](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>Scrivere query senza DeviceAlertEvents

Nello schema di Microsoft 365 Defender, le tabelle e vengono fornite per supportare il set diversificato di informazioni che accompagnano `AlertInfo` gli avvisi provenienti da diverse `AlertEvidence` origini. 

Per ottenere le stesse informazioni di avviso che hai usato per ottenere dalla tabella nello schema di Microsoft Defender for Endpoint, filtra la tabella in base a e quindi unisci ogni ID univoco alla tabella, che fornisce informazioni dettagliate sull'evento e `DeviceAlertEvents` `AlertInfo` sull'entità. `ServiceSource` `AlertEvidence` 

Vedi la query di esempio seguente:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Questa query restituisce molte più colonne rispetto `DeviceAlertEvents` allo schema di Microsoft Defender for Endpoint. Per mantenere gestibili i risultati, utilizzare per ottenere solo le colonne `project` a cui si è interessati. L'esempio seguente proietta colonne che potrebbero interessarti quando l'indagine ha rilevato l'attività di PowerShell:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Se vuoi filtrare per entità specifiche coinvolte negli avvisi, puoi farlo specificando il tipo di entità e il valore per cui vuoi `EntityType` filtrare. Nell'esempio seguente viene ricercato un indirizzo IP specifico:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>Vedere anche
- [Attivare Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Ricerca avanzata in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)