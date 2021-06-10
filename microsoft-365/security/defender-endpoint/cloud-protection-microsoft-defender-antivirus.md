---
title: Protezione fornita dal cloud e Windows Defender Antivirus
description: Informazioni sulla protezione e l'Antivirus Microsoft Defender
keywords: Antivirus Microsoft Defender, tecnologie di nuova generazione, av di nuova generazione, apprendimento automatico, antimalware, sicurezza, defender, cloud, protezione basata sul cloud
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 06/03/2021
ms.openlocfilehash: ce54f8205e62b953022fd2518caac058f4f9bab2
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788800"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>Protezione fornita dal cloud e Windows Defender Antivirus

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)
- Antivirus Microsoft Defender

Le tecnologie di nuova Antivirus Microsoft Defender offrono una protezione automatizzata quasi istantanea dalle minacce nuove ed emergenti. Per identificare dinamicamente le nuove minacce, le tecnologie di nuova generazione funzionano con grandi set di dati interconnessi nel Graph Microsoft Intelligent Security e con potenti sistemi di intelligenza artificiale (AI) guidati da modelli avanzati di machine learning. Antivirus Microsoft Defender più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente. 

> [!TIP]
> Ulteriori informazioni Vedi il post di blog, [Informazioni sulle tecnologie avanzate alla base di Microsoft Defender per la protezione di nuova generazione dell'endpoint.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Antivirus Microsoft Defender funziona senza problemi con i servizi cloud Microsoft. Questi servizi di protezione cloud, denominati anche Microsoft Advanced Protection Service (MAPS), migliorano la protezione standard in tempo reale, offrendo probabilmente la migliore difesa antivirus. 

> [!NOTE]
> Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Come servizio cloud, non si tratta semplicemente di protezione per i file archiviati nel cloud; al contrario, il servizio cloud usa risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di intelligence per la sicurezza.

Grazie alla protezione basata sul cloud, le tecnologie di nuova generazione forniscono una rapida identificazione delle nuove minacce, a volte anche prima che un singolo computer venga infettato. I post di blog seguenti illustrano il funzionamento della protezione basata sul cloud:

- [Perché Antivirus Microsoft Defender è il più distribuito nell'organizzazione](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [Il monitoraggio del comportamento combinato con l'apprendimento automatico intasa una campagna di estrazione di monete di massa](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Come l'intelligenza artificiale ha arrestato un'epidemia di "Emotet"](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonazione di un maso: Antivirus Microsoft Defender di machine learning a più livelli](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Antivirus Microsoft Defender di protezione cloud: difesa avanzata in tempo reale da malware mai visto prima](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>Come ottenere la protezione basata sul cloud 

La protezione con distribuzione cloud è abilitata per impostazione predefinita. Tuttavia, potrebbe essere necessario ri abilitarlo se è stato disabilitato come parte dei criteri organizzativi precedenti. Per ulteriori informazioni, vedere [Attivare la protezione con distribuzione cloud.](enable-cloud-protection-microsoft-defender-antivirus.md)

Le organizzazioni che eseguono Windows 10 E5 possono anche sfruttare gli aggiornamenti di intelligence dinamica di emergenza, che forniscono una protezione quasi in tempo reale dalle minacce emergenti. Quando si attiva la protezione con distribuzione cloud, le correzioni per i problemi di malware possono essere recapitate tramite il cloud in pochi minuti, invece di attendere l'aggiornamento successivo. [Configurare Antivirus Microsoft Defender ricevere automaticamente nuovi aggiornamenti della](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)protezione in base ai report del servizio cloud.

> [!TIP]
> Visitare il Windows Defender Testground [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) verificare che la funzionalità funzioni e vedere come funziona.

## <a name="next-steps"></a>Passaggi successivi

1. [Abilitare la protezione basata sul cloud.](enable-cloud-protection-microsoft-defender-antivirus.md) È possibile abilitare la protezione basata sul cloud con Microsoft Endpoint Manager (che ora include Microsoft Endpoint Configuration Manager e Microsoft Intune), Criteri di gruppo o cmdlet di PowerShell.

2. [Specificare il livello di protezione fornito dal cloud.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Puoi specificare il livello di protezione offerto dal cloud usando Microsoft Endpoint Manager o Criteri di gruppo. Il livello di protezione influisce sulla quantità di informazioni condivise con il cloud e sulla modalità di blocco aggressivo dei nuovi file.

3. [Configurare e convalidare le connessioni di rete per Antivirus Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md). Esistono alcuni URL Microsoft a cui la rete e gli endpoint devono essere in grado di connettersi per garantire un funzionamento efficace della protezione basata sul cloud. In questo articolo vengono elencati gli URL che devono essere consentiti tramite le regole di filtro di rete o firewall e le istruzioni per verificare che la rete sia correttamente registrato nella protezione con distribuzione cloud.

4. [Configurare la funzionalità "blocco al primo sguardo".](configure-block-at-first-sight-microsoft-defender-antivirus.md) La funzionalità "blocco al primo rilevamento" può bloccare il nuovo malware in pochi secondi, senza dover attendere ore per la tradizionale intelligence di sicurezza. È possibile abilitarlo e configurarlo utilizzando Microsoft Endpoint Manager o Criteri di gruppo.

5. [Configurare il periodo di timeout del blocco cloud](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md). Antivirus Microsoft Defender possibile bloccare l'esecuzione di file sospetti durante le query sul servizio di protezione fornito dal cloud. È possibile configurare la quantità di tempo per cui il file non verrà eseguito utilizzando Microsoft Endpoint Manager o Criteri di gruppo.