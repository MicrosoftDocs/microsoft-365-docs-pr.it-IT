---
title: Ottimizzare la distribuzione e i rilevamenti delle regole asr
description: Ottimizzare le regole di riduzione della superficie di attacco (ASR) per identificare e impedire exploit di malware tipici.
keywords: onboard, gestione di Intune, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, riduzione della superficie di attacco, ASR, baseline di sicurezza
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932848"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Ottimizzare la distribuzione e i rilevamenti delle regole asr

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Le regole di riduzione della superficie di](./attack-surface-reduction.md) attacco identificano e impediscono exploit di malware tipici. Controllano quando e come può essere eseguito codice potenzialmente dannoso. Ad esempio, possono impedire a JavaScript o VBScript di avviare un file eseguibile scaricato, bloccare le chiamate API Win32 dalle macro di Office e bloccare i processi eseguiti da unità USB.

![Scheda di gestione della superficie di attacco](images/secconmgmt_asr_card.png)<br>
*Scheda di gestione della superficie di attacco*

La *scheda di gestione della superficie* di attacco è un punto di ingresso agli strumenti nel Centro sicurezza Microsoft 365 che è possibile usare per:

* Comprendere in che modo le regole DISR sono attualmente distribuite nell'organizzazione.
* Esaminare i rilevamenti asr e identificare possibili rilevamenti non corretti.
* Analizzare l'impatto delle esclusioni e generare l'elenco dei percorsi di file da escludere.

Seleziona **Vai a gestione della superficie di** attacco Monitoraggio & report > regole di riduzione della superficie di attacco > Aggiungi  >  **esclusioni.** Da qui è possibile passare ad altre sezioni del Centro sicurezza Microsoft 365.

![Aggiungere la scheda esclusioni nella pagina Regole di riduzione della superficie di attacco nel Centro sicurezza Microsoft 365](images/secconmgmt_asr_m365exlusions.png)<br>
Scheda Aggiungi esclusioni nella pagina Regole di riduzione della superficie di attacco nel Centro sicurezza *Microsoft 365*

> [!NOTE]
> Per accedere al Centro sicurezza Microsoft 365, è necessaria una licenza di Microsoft 365 E3 o E5 e un account con determinati ruoli in Azure Active Directory. [Leggere le licenze e le autorizzazioni necessarie.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)

Per ulteriori informazioni sulla distribuzione delle regole asr nel Centro sicurezza Microsoft 365, vedere Monitorare e gestire la distribuzione e i rilevamenti delle regole [ASR.](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)

**Argomenti correlati**

* [Verificare che i dispositivi siano configurati correttamente](configure-machines.md)
* [Eseguire l'onboarded dei dispositivi in Microsoft Defender per Endpoint](configure-machines-onboarding.md)
* [Monitorare la conformità alla linea di base di sicurezza di Microsoft Defender for Endpoint](configure-machines-security-baseline.md)
