---
title: Eseguire il pull dei rilevamenti agli strumenti SIEM da Microsoft Defender per Endpoint
description: Scopri come usare l'API REST e configurare gli strumenti di gestione degli eventi e delle informazioni di sicurezza supportati per ricevere e estrarre i rilevamenti.
keywords: configurare siem, strumenti di gestione delle informazioni di sicurezza ed eventi, splunk, arcsight, indicatori personalizzati, api rest, definizioni di avviso, indicatori di compromissione
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
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222336"
---
# <a name="pull-detections-to-your-siem-tools"></a>Eseguire il pull dei rilevamenti agli strumenti SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>Rilevamento pull tramite strumenti di gestione di eventi e informazioni di sicurezza

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert](alerts.md) è composto da uno o più rilevamenti.
>- [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) è composto dall'evento sospetto che si è verificato nel dispositivo e dai relativi dettagli di avviso.
>-L'API di Microsoft Defender for Endpoint Alert è l'API più recente per il consumo di avvisi e contiene un elenco dettagliato di prove correlate per ogni avviso. Per ulteriori informazioni, vedere [Metodi e proprietà degli](alerts.md) avvisi e Avvisi [elenco.](get-alerts.md)

Defender for Endpoint supporta gli strumenti siem (Security Information and Event Management) per il pull dei rilevamenti. Defender for Endpoint espone gli avvisi tramite un endpoint HTTPS ospitato in Azure. L'endpoint può essere configurato per il pull dei rilevamenti dal tenant aziendale in Azure Active Directory (AAD) utilizzando il protocollo di autenticazione OAuth 2.0 per un'applicazione AAD che rappresenta lo specifico connettore SIEM installato nell'ambiente.

Defender for Endpoint attualmente supporta i seguenti strumenti di soluzione SIEM specifici tramite un modello di integrazione SIEM dedicato:

- IBM QRadar
- Micro Focus ArcSight

Altre soluzioni SIEM (come Splunk, RSA NetWitness) sono supportate tramite un modello di integrazione diverso basato sulla nuova API alert. Per altre informazioni, visualizza la pagina [dell'applicazione partner](https://securitycenter.microsoft.com/interoperability/partners) e seleziona la sezione Analisi e informazioni di sicurezza per i dettagli completi.

Per utilizzare uno di questi strumenti SIEM supportati, è necessario:

- [Abilitare l'integrazione SIEM in Defender for Endpoint](enable-siem-integration.md)
- Configurare lo strumento SIEM supportato:
     - [Configurare Micro Focus ArcSight per eseguire il pull di Defender per i rilevamenti degli endpoint](configure-arcsight.md)
     - Configurare IBM QRadar per il pull defender per i rilevamenti degli endpoint Per ulteriori informazioni, vedere [IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

Per altre informazioni sull'elenco dei campi esposti nell'API di rilevamento, vedi [Defender per i campi di rilevamento degli endpoint.](api-portal-mapping.md)
