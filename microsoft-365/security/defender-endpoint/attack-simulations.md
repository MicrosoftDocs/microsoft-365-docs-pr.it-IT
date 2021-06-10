---
title: Esperienza di Microsoft Defender per Endpoint tramite attacchi simulati
description: Esegui le simulazioni dello scenario di attacco fornite per scoprire in che modo Microsoft Defender for Endpoint può rilevare, analizzare e rispondere alle violazioni.
keywords: test, scenario, attacco, simulazione, simulato, diy, Microsoft Defender per Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 6ecbf98c81b1f68e42f39269809592fb446e6036
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934382"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Esperienza di Microsoft Defender per Endpoint tramite attacchi simulati 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Informazioni sugli ultimi miglioramenti in Microsoft Defender for Endpoint: [Novità di Defender per Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Potresti voler provare Defender for Endpoint prima di eseguire l'onboardboard di più di alcuni dispositivi nel servizio. A tale scopo, è possibile eseguire simulazioni di attacco controllate su alcuni dispositivi di test. Dopo aver eseguito gli attacchi simulati, puoi esaminare il modo in cui Defender for Endpoint mostra attività dannose ed esplorare il modo in cui consente una risposta efficiente.

## <a name="before-you-begin"></a>Prima di iniziare

Per eseguire una delle simulazioni fornite, è necessario almeno [un dispositivo onboarded.](onboard-configure.md) 

Leggere il documento della procedura dettagliata fornito con ogni scenario di attacco. Ogni documento include i requisiti del sistema operativo e delle applicazioni, nonché istruzioni dettagliate specifiche per uno scenario di attacco.

## <a name="run-a-simulation"></a>Eseguire una simulazione

1. In   >  **Simulazioni guida & esercitazioni** selezionare quali degli scenari di attacco disponibili si desidera simulare:

   - **Scenario 1: la backdoor** del documento viene simulare la consegna di un documento di esca socialmente progettato. Il documento avvia una backdoor appositamente predisposta che consente agli utenti malintenzionati di controllare.

   - **Scenario 2: script di PowerShell in** attacco senza file - Simula un attacco senza file che si basa su PowerShell, che mostra la riduzione della superficie di attacco e il rilevamento di dispositivi di apprendimento di attività di memoria dannose.
    
   - **Scenario 3: risposta** automatica agli eventi imprevisti : attiva un'indagine automatizzata, che cerca e correda automaticamente gli artefatti di violazione per ridimensionare la capacità di risposta agli incidenti.

2. Scaricare e leggere il documento della procedura dettagliata corrispondente fornito con lo scenario selezionato.

3. Scarica il file di simulazione o copia lo script di simulazione accedendo alla **Guida**  >  **Simulazioni & esercitazioni**. Puoi scegliere di scaricare il file o lo script nel dispositivo di test, ma non è obbligatorio.

4. Eseguire il file o lo script di simulazione nel dispositivo di test come indicato nel documento della procedura dettagliata.

> [!NOTE]
> I file o gli script di simulazione simulano l'attività di attacco, ma sono in realtà benigni e non danneggiano o comprometteranno il dispositivo di test.
> 
> 
> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Argomenti correlati

- [Eseguire l'onboarding dei dispositivi](onboard-configure.md)
- [Aggiungere di dispositivi Windows 10](configure-endpoints.md)
