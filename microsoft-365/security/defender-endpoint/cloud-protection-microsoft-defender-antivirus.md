---
title: Protezione con distribuzione cloud e Microsoft Defender Antivirus
description: Informazioni sulla protezione basata sul cloud e Microsoft Defender Antivirus
keywords: Microsoft Defender Antivirus, tecnologie di nuova generazione, av di nuova generazione, apprendimento automatico, antimalware, sicurezza, defender, cloud, protezione basata sul cloud
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: e967cb9efe03fc180bda531f192f3143c311796d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764760"
---
# <a name="use-next-generation-technologies-in-microsoft-defender-antivirus-through-cloud-delivered-protection"></a>Usare tecnologie di nuova generazione in Microsoft Defender Antivirus tramite la protezione basata sul cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Le tecnologie microsoft di nuova generazione in Microsoft Defender Antivirus offrono una protezione automatizzata quasi istantanea dalle minacce nuove ed emergenti. Per identificare in modo dinamico nuove minacce, queste tecnologie analizzano grandi quantità di dati interconnessi nei sistemi Microsoft Intelligent Security Graph e nei potenti strumenti di intelligenza artificiale (AI) basati su modelli di machine learning avanzati.  

Microsoft Defender Antivirus usa più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente. [Informazioni sulle tecnologie avanzate alla base di Microsoft Defender for Endpoint di nuova generazione.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)
![Elenco dei motori Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Per sfruttare la potenza e la velocità di queste tecnologie di nuova generazione, Microsoft Defender Antivirus funziona senza problemi con i servizi cloud Microsoft. Questi servizi di protezione cloud, denominati anche Microsoft Advanced Protection Service (MAPS), migliorano la protezione standard in tempo reale, offrendo probabilmente la migliore difesa antivirus. 

>[!NOTE]
>Il servizio cloud Microsoft Defender Antivirus è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Anche se viene chiamato servizio cloud, non si tratta semplicemente di protezione per i file archiviati nel cloud, bensì di risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di Security intelligence.

Grazie alla protezione basata sul cloud, le tecnologie di nuova generazione forniscono una rapida identificazione delle nuove minacce, a volte anche prima che un singolo computer venga infettato. Guarda il video seguente su Microsoft AI e Microsoft Defender Antivirus in azione: 
 
<iframe 
src="https://www.microsoft.com/videoplayer/embed/RE1Yu4B" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

Per comprendere in che modo le tecnologie di nuova generazione riducono i tempi di recapito della protezione attraverso il cloud, guardare il video seguente: 
 
<iframe 
src="https://videoplayercdn.osi.office.net/embed/c2f20f59-ca56-4a7b-ba23-44c60bc62c59" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

Leggere i post di blog seguenti per informazioni dettagliate sulla protezione del cloud e sull'intelligenza artificiale Microsoft: 

- [Perché Microsoft Defender Antivirus è il più distribuito nell'azienda](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [Il monitoraggio del comportamento combinato con l'apprendimento automatico guasta una campagna di estrazione di monete Dofoil di massa](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Come l'intelligenza artificiale ha arrestato un'epidemia di Emotet](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonazione di un bruttissimo coniglio: Microsoft Defender Antivirus e difese di apprendimento automatico a più livelli](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Servizio di protezione cloud Microsoft Defender Antivirus: difesa avanzata in tempo reale da malware mai visto prima](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="get-cloud-delivered-protection"></a>Ottenere la protezione basata sul cloud 

La protezione con distribuzione cloud è abilitata per impostazione predefinita. Tuttavia, potrebbe essere necessario ri abilitarlo se è stato disabilitato come parte dei criteri organizzativi precedenti.

Le organizzazioni che eseguono Windows 10 E5 possono anche sfruttare gli aggiornamenti di intelligence dinamica di emergenza, che forniscono una protezione quasi in tempo reale dalle minacce emergenti. Quando si attiva la protezione con distribuzione cloud, le correzioni per i problemi di malware possono essere recapitate tramite il cloud in pochi minuti, invece di attendere l'aggiornamento successivo.

>[!TIP]
>Puoi anche visitare il sito Web Windows Defender Testground all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.

Nella tabella seguente vengono descritte le differenze nella protezione basata sul cloud tra le versioni recenti di Windows e Configuration Manager.

|Versione del sistema operativo o applicazione di servizio |Etichetta del servizio di protezione cloud  |Livello di report (livello di appartenenza MAPS)  |Periodo di timeout blocco cloud  |
|---------|---------|---------|---------|
|Windows 8.1 (Criteri di gruppo)     |Microsoft Advanced Protection Service   |Basic, Advanced   |No         |
|Windows 10 versione 1607 (Criteri di gruppo)  |Microsoft Advanced Protection Service      |Impostazioni avanzate         |No         |
|Windows 10 versione 1703 o successiva (Criteri di gruppo)      |Protezione basata su cloud      |Impostazioni avanzate         |Configurabile         |
|System Center 2012 Configuration Manager  |      N/D         |Dipendente dalla versione di Windows         |Non configurabile |
|Microsoft Endpoint Manager (Current Branch)         |Servizio di protezione cloud         |Dipendente dalla versione di Windows          |Configurabile         |
|Microsoft Intune     |Microsoft Advanced Protection Service         |Dipendente dalla versione di Windows         |Configurabile         |

Puoi anche configurare [Microsoft Defender Antivirus per ricevere automaticamente nuovi](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)aggiornamenti della protezione in base ai report del nostro servizio cloud.


## <a name="tasks"></a>Tasks

- [Abilitare la protezione basata sul cloud.](enable-cloud-protection-microsoft-defender-antivirus.md) È possibile abilitare la protezione basata sul cloud con Microsoft Endpoint Configuration Manager, Criteri di gruppo, Microsoft Intune e cmdlet di PowerShell.

- [Specificare il livello di protezione fornito dal cloud.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Puoi specificare il livello di protezione offerto dal cloud con Criteri di gruppo e Microsoft Endpoint Configuration Manager. Il livello di protezione influisce sulla quantità di informazioni condivise con il cloud e sulla modalità di blocco aggressivo dei nuovi file.

- [Configurare e convalidare le connessioni di rete per Microsoft Defender Antivirus.](configure-network-connections-microsoft-defender-antivirus.md) Esistono alcuni URL Microsoft a cui la rete e gli endpoint devono essere in grado di connettersi per garantire un funzionamento efficace della protezione basata sul cloud. In questo articolo vengono elencati gli URL che devono essere consentiti tramite le regole di filtro di rete o firewall e le istruzioni per verificare che la rete sia correttamente registrato nella protezione con distribuzione cloud.

- [Configurare la funzionalità blocco al primo avvistamento](configure-block-at-first-sight-microsoft-defender-antivirus.md). La funzionalità "blocco al primo rilevamento" può bloccare il nuovo malware in pochi secondi, senza dover attendere ore per la tradizionale intelligence di sicurezza. Puoi abilitarlo e configurarlo con Microsoft Endpoint Manager e Criteri di gruppo.

- [Configurare il periodo di timeout del blocco cloud](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md). Microsoft Defender Antivirus può impedire l'esecuzione di file sospetti durante le query sul servizio di protezione fornito dal cloud. Puoi configurare la quantità di tempo per cui il file non verrà eseguito con Microsoft Endpoint Manager e Criteri di gruppo.