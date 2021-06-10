---
title: Esaminare i problemi di integrità dell'agente
description: Informazioni sui valori restituiti quando si esegue il comando di integrità mdatp
keywords: integrità mdatp, comando, integrità, stato, comando, stato di onboarding
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: acc75a931cb14a7aab729c09a7b835fb9f26d1d1
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281177"
---
# <a name="investigate-agent-health-issues"></a>Esaminare i problemi di integrità dell'agente

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Nella tabella seguente vengono fornite informazioni sui valori restituiti quando si esegue il `mdatp health` comando e sulle relative descrizioni.

| Valore | Descrizione |
|-|-|
| automatic_definition_update_enabled | True se gli aggiornamenti automatici delle definizioni antivirus sono abilitati, false in caso contrario. |
|  cloud_automatic_sample_submission_consent | Livello di invio di esempio corrente. Può essere uno dei valori seguenti:     <br><br>  - **Nessuno:** non vengono inviati campioni sospetti a Microsoft.  <br> <br>     - **Sicuro:** solo i campioni sospetti che non contengono informazioni personali vengono inviati automaticamente. Questo è il valore predefinito per questa impostazione.    <br> <br>   - **All**: tutti gli esempi sospetti vengono inviati a Microsoft.   |
| cloud_diagnostic_enabled | True se la raccolta dei dati di diagnostica facoltativa è abilitata, false in caso contrario. Per altre informazioni relative a Defender for Endpoint e ad altri prodotti e servizi come Antivirus Microsoft Defender e Windows 10, vedi Informativa [sulla privacy Microsoft.](https://go.microsoft.com/fwlink/?linkid=827576) |
| cloud_enabled | True se la protezione recapitata nel cloud è abilitata, false in caso contrario. |
| conflicting_applications | Elenco di applicazioni che potrebbero essere in conflitto con Microsoft Defender per Endpoint. Questo elenco include, ma non è limitato a, altri prodotti di sicurezza e altre applicazioni noti per causare problemi di compatibilità. |
| definitions_status | Stato delle definizioni antivirus. |
| definitions_updated | Data e ora dell'ultimo aggiornamento delle definizioni antivirus. |
| definitions_updated_minutes_ago | Numero di minuti dall'ultimo aggiornamento delle definizioni antivirus. |
| definitions_version | Versione della definizione antivirus. |
| edr_client_version | Versione del EDR client in esecuzione nel dispositivo. |
| edr_configuration_version | EDR di configurazione. |
| edr_device_tags | Elenco di tag associati al dispositivo. |
| edr_group_ids | ID gruppo a cui è associato il dispositivo. |
| edr_machine_id | Identificatore del dispositivo usato in Microsoft Defender Security Center. |
| engine_version | Versione del motore antivirus. |
| integro | True se il prodotto è integro, false in caso contrario. |
| concesso in licenza | True se il dispositivo viene onboarded in un tenant, false in caso contrario. |
| log_level | Livello di registrazione corrente per il prodotto. |
| machine_guid | Identificatore univoco del computer utilizzato dal componente antivirus. |
| network_protection_status                 | Stato del componente di protezione di rete (solo macOS). Può essere uno dei valori seguenti:       <br> <br>- **starting** - Protezione di rete in corso  <br> <br>     - **failed_to_start** - Impossibile iniziare la protezione di rete a causa di un errore   <br> <br>    - **started** - Protezione di rete attualmente in esecuzione nel dispositivo     <br> <br>  - **riavvio** - La protezione di rete è attualmente in fase di riavvio   <br> <br>    - **arresto** - Arresto della protezione di rete in corso     <br> <br>  - **arrestato** - Protezione di rete non in esecuzione |
| org_id | Organizzazione in cui è stato onboarded il dispositivo. Se il dispositivo non è ancora stato onboarded in alcuna organizzazione, la stampa non è disponibile. Per altre informazioni sull'onboarding, vedi [Eseguire l'onboarding in Microsoft Defender per Endpoint.](onboarding.md) |
| passive_mode_enabled | True se il componente antivirus è impostato per l'esecuzione in modalità passiva, false in caso contrario. |
| product_expiration | Data e ora in cui la versione corrente del prodotto raggiunge la fine del supporto. |
| real_time_protection_available | True se il componente di protezione in tempo reale è integro, false in caso contrario. |
| real_time_protection_enabled | True se la protezione antivirus in tempo reale è abilitata, false in caso contrario. |
| real_time_protection_subsystem | Sottosistema utilizzato per la protezione in tempo reale. Se la protezione in tempo reale non funziona come previsto, non sarà disponibile. |
| release_ring | Anello di rilascio. Per ulteriori informazioni, vedere   [Anelli di distribuzione](deployment-rings.md). |