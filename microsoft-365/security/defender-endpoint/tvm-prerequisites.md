---
title: Prerequisiti & autorizzazioni - gestione di minacce e vulnerabilità
description: Prima di iniziare a usare gestione di minacce e vulnerabilità, assicurarsi di disporre delle configurazioni e delle autorizzazioni pertinenti.
keywords: prerequisiti & gestione delle vulnerabilità autorizzazioni di protezione, gestione di minacce e vulnerabilità autorizzazioni, prerequisiti per le autorizzazioni di Microsoft Defender for Endpoint TVM, gestione delle vulnerabilità
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843951"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>Prerequisiti & autorizzazioni - gestione di minacce e vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Minaccia e gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Assicurati che i dispositivi:

- Vengono onboarded in Microsoft Defender for Endpoint
- Eseguire [sistemi operativi e piattaforme supportati](tvm-supported-os.md)
- Installare e distribuire nella rete gli aggiornamenti obbligatori seguenti per aumentare la velocità di rilevamento della valutazione delle vulnerabilità:

> Rilascio | Collegamento e numero KB dell'aggiornamento della sicurezza
> :---|:---
> Windows 10 Versione 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) e [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10 Versione 1803 | [KB4493464](https://support.microsoft.com/help/4493464) e [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10 Versione 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10 Versione 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- Vengono onboarded per [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) e [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) per correggere le minacce rilevate da gestione di minacce e vulnerabilità. Se si usa Configuration Manager, aggiornare la console alla versione più recente.
    - **Nota:** se la connessione intune è abilitata, si ottiene un'opzione per creare un'attività di sicurezza di Intune durante la creazione di una richiesta di correzione. Questa opzione non viene visualizzata se la connessione non è impostata.
- Avere almeno un consiglio di sicurezza che può essere visualizzato nella pagina del dispositivo
- Sono contrassegnati o contrassegnati come co-gestiti

## <a name="relevant-permission-options"></a>Opzioni di autorizzazione pertinenti

1. Accedere a Microsoft Defender Security Center con un account con un ruolo amministratore della sicurezza o amministratore globale assegnato.
2. Nel riquadro di spostamento selezionare Impostazioni > **ruoli**.

Per ulteriori informazioni, vedere [Create and manage roles for role-based access control](user-roles.md)

### <a name="view-data"></a>Visualizzare i dati

- **Operazioni di sicurezza** - Visualizzare tutti i dati relativi alle operazioni di sicurezza nel portale
- **Minacce e gestione delle vulnerabilità** - Visualizzare gestione di minacce e vulnerabilità dati nel portale

### <a name="active-remediation-actions"></a>Azioni di correzione attive

- **Operazioni di sicurezza:** eseguire azioni di risposta, approvare o ignorare le azioni di correzione in sospeso, gestire gli elenchi consentiti/bloccati per l'automazione e gli indicatori
- **Minacce e gestione delle vulnerabilità - Gestione delle eccezioni** - Creare nuove eccezioni e gestire le eccezioni attive
- **Minacce e gestione delle vulnerabilità - Gestione** delle correzioni - Inviare nuove richieste di correzione, creare ticket e gestire le attività di correzione esistenti

Per ulteriori informazioni, vedere [Opzioni di autorizzazione RBAC](user-roles.md#permission-options)

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle minacce gestione delle vulnerabilità sicurezza](next-gen-threat-and-vuln-mgt.md)
- [Sistemi operativi e piattaforme supportati](tvm-supported-os.md)
- [Assegnare un valore del dispositivo](tvm-assign-device-value.md)
- [Dashboard delle minacce gestione delle vulnerabilità sicurezza](tvm-dashboard-insights.md)

