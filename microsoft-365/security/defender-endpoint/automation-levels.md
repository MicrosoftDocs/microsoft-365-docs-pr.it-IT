---
title: Livelli di automazione nell'indagine e correzione automatizzate
description: Panoramica dei livelli di automazione e del loro funzionamento in Microsoft Defender for Endpoint
keywords: automatizzato, indagine, livello, defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 10/22/2020
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: bb3e8c468983622d780ca185640c2816316bfd48
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165322"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Livelli di automazione nelle funzionalità di analisi e correzione automatizzate

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Le funzionalità di analisi e correzione automatizzate (AIR) in Microsoft Defender for Endpoint possono essere configurate su uno dei diversi livelli di automazione. Il livello di automazione influisce sul fatto che le azioni di correzione dopo le indagini AIR siano intraprese automaticamente o solo dopo l'approvazione.  
- *L'automazione* completa (scelta consigliata) indica che le azioni di correzione vengono eseguite automaticamente sugli artefatti determinati come dannosi.
- *La semiautorizzazione* significa che alcune azioni di correzione vengono eseguite automaticamente, ma altre azioni di correzione attendono l'approvazione prima di essere eseguite. Vedere la tabella in [Livelli di automazione.](#levels-of-automation)
- Tutte le azioni di correzione, in sospeso o completate, vengono rilevate nel Centro notifiche ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 

> [!TIP]
> Per ottenere risultati ottimali, è consigliabile utilizzare l'automazione completa quando [si configura AIR.](configure-automated-investigations-remediation.md) I dati raccolti e analizzati nell'ultimo anno mostrano che i clienti che usano l'automazione completa hanno rimosso il 40% in più di campioni di malware ad alta sicurezza rispetto ai clienti che usano livelli di automazione inferiori. L'automazione completa consente di liberare le risorse operative di sicurezza per concentrarsi di più sulle iniziative strategiche.

## <a name="levels-of-automation"></a>Livelli di automazione

Nella tabella seguente vengono descritti ogni livello di automazione e il suo funzionamento.

|Livello di automazione | Descrizione|
|:---|:---|
|**Completo : correggere automaticamente le minacce** <br/>(noto anche come *automazione completa)*| Con l'automazione completa, le azioni di correzione vengono eseguite automaticamente. Tutte le azioni di correzione eseguite possono essere visualizzate [nel](auto-investigation-action-center.md) Centro notifiche nella **scheda** Cronologia. Se necessario, è possibile annullare un'azione di correzione.<br/><br/>**_L'automazione_* completa è consigliata ed è selezionata per impostazione predefinita per i tenant creati il 16 agosto 2020 con Microsoft Defender for Endpoint, senza ancora definire gruppi di dispositivi.*  |
|**Semi - Richiede l'approvazione per qualsiasi correzione** <br/>(noto anche come *semiautorizzazione)*| Con questo livello di semiautorizzazione, è necessaria l'approvazione per *qualsiasi* azione correttiva. Tali azioni in sospeso possono essere visualizzate e approvate nel [Centro notifiche,](auto-investigation-action-center.md)nella **scheda In** sospeso.<br/><br/>*Questo livello di semiautorizzazione è selezionato per impostazione predefinita per i tenant creati prima del 16 agosto 2020 con Microsoft Defender ATP, senza gruppi di dispositivi definiti.*|
|**Semi - Richiede l'approvazione per la correzione delle cartelle principali** <br/>(anche un tipo di *semiautorizzazione)*  | Con questo livello di semiautorizzazione, è necessaria l'approvazione per tutte le azioni di correzione necessarie per i file o i file eseguibili presenti nelle cartelle principali. Le cartelle principali includono le directory del sistema operativo, ad **esempio Windows** ( `\windows\*` ).<br/><br/>Le azioni di correzione possono essere eseguite automaticamente su file o file eseguibili presenti in altre cartelle (non di base). <br/><br/>Le azioni in sospeso per file o eseguibili nelle cartelle principali possono essere visualizzate e approvate nel Centro [notifiche,](auto-investigation-action-center.md)nella **scheda In** sospeso. <br/><br/>Le azioni eseguite su file o eseguibili in altre cartelle possono essere visualizzate nel Centro notifiche [nella](auto-investigation-action-center.md) **scheda** Cronologia. |
|**Semi - Richiede l'approvazione per la correzione delle cartelle non temporanee** <br/>(anche un tipo di *semiautorizzazione)*| Con questo livello di semiautorizzazione, è necessaria l'approvazione per tutte le azioni di correzione necessarie per i file o i file eseguibili non *presenti* nelle cartelle temporanee. <br/><br/>Le cartelle temporanee possono includere gli esempi seguenti: <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>Le azioni di correzione possono essere eseguite automaticamente su file o file eseguibili presenti in cartelle temporanee. <br/><br/>Le azioni in sospeso per file o eseguibili non presenti in cartelle temporanee possono essere visualizzate e approvate nel Centro notifiche [nella](auto-investigation-action-center.md) **scheda** In sospeso.<br/><br/>Le azioni eseguite su file o eseguibili in cartelle temporanee possono essere visualizzate e approvate nel Centro notifiche [nella](auto-investigation-action-center.md) **scheda** Cronologia.   |
|**Nessuna risposta automatica** <br/>(noto anche come *nessuna automazione)* | Senza automazione, l'indagine automatizzata non viene eseguita nei dispositivi dell'organizzazione. Di conseguenza, non vengono intraprese o in sospeso azioni di correzione a seguito di un'indagine automatizzata. Tuttavia, possono essere effettive [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)altre funzionalità di protezione dalle minacce, ad esempio la protezione da applicazioni potenzialmente indesiderate, a seconda di come sono configurate le funzionalità antivirus e di protezione di nuova generazione.<br/><br/>****L'utilizzo dell'opzione*** no automation non è consigliato perché riduce il livello di sicurezza dei dispositivi dell'organizzazione. [Valuta la possibilità di configurare il livello di automazione per l'automazione completa (o almeno semi-automazione)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups)*. |

## <a name="important-points-about-automation-levels"></a>Punti importanti sui livelli di automazione

- L'automazione completa si è dimostrata affidabile, efficiente e sicura ed è consigliata per tutti i clienti. L'automazione completa libera le risorse di sicurezza critiche in modo che possano concentrarsi di più sulle iniziative strategiche.

- I nuovi tenant (che includono tenant creati il 16 agosto 2020 o dopo) con Microsoft Defender for Endpoint sono impostati sull'automazione completa per impostazione predefinita.

- Se il team di sicurezza ha definito gruppi di dispositivi con un livello di automazione, tali impostazioni non vengono modificate dalle nuove impostazioni predefinite in distribuzione. 

- È possibile mantenere le impostazioni di automazione predefinite o modificarle in base alle esigenze dell'organizzazione. Per modificare le impostazioni, [impostare il livello di automazione](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups).

## <a name="next-steps"></a>Passaggi successivi

- [Configurare le funzionalità di analisi e correzione automatizzate in Microsoft Defender for Endpoint](configure-automated-investigations-remediation.md)

- [Visitare il Centro notifiche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
