---
title: Usare indagini automatizzate per analizzare e correggere le minacce
description: Comprendere il flusso di indagine automatizzato in Microsoft Defender for Endpoint.
keywords: automatizzato, indagine, rilevamento, defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: d2effb44c145a4fbf1006446685dbcd703754e6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166210"
---
# <a name="overview-of-automated-investigations"></a>Panoramica delle indagini automatizzate

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Vuoi vedere come funziona? Guarda il video seguente: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

La tecnologia nell'indagine automatizzata utilizza vari algoritmi di ispezione ed è basata sui processi utilizzati dagli analisti della sicurezza. Le funzionalità AIR sono progettate per esaminare gli avvisi e intervenire immediatamente per risolvere le violazioni. Le funzionalità AIR riducono significativamente il volume degli avvisi, consentendo alle operazioni di sicurezza di concentrarsi su minacce più sofisticate e altre iniziative di alto valore. Tutte le azioni di correzione, in sospeso o completate, vengono rilevate nel [centro notifiche.](auto-investigation-action-center.md) Nel centro notifiche le azioni in sospeso vengono approvate (o rifiutate) e le azioni completate possono essere annullate se necessario.

In questo articolo viene fornita una panoramica di AIR e vengono forniti collegamenti ai passaggi successivi e a risorse aggiuntive.

> [!TIP]
> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)

## <a name="how-the-automated-investigation-starts"></a>Inizio dell'indagine automatizzata

Un'indagine automatizzata può iniziare quando viene attivato un avviso o quando un operatore di sicurezza avvia l'indagine.

|Situazione  |Effetto  |
|---------|---------|
|Viene attivato un avviso     | In generale, un'indagine automatizzata viene avviata [quando](review-alerts.md) viene attivato un avviso e viene [creato](view-incidents-queue.md) un evento imprevisto. Si supponga ad esempio che un file dannoso si trovi in un dispositivo. Quando viene rilevato il file, viene attivato un avviso e viene creato un evento imprevisto. Nel dispositivo viene avviato un processo di indagine automatizzato. Poiché altri avvisi vengono generati a causa dello stesso file in altri dispositivi, vengono aggiunti all'evento imprevisto associato e all'indagine automatizzata.         |
|Un'indagine viene avviata manualmente     | Un'indagine automatizzata può essere avviata manualmente dal team delle operazioni di sicurezza. Ad esempio, si supponga che un operatore di sicurezza riveda un elenco di dispositivi e noti che un dispositivo ha un livello di rischio elevato. L'operatore di sicurezza può selezionare il dispositivo nell'elenco per aprire il riquadro a comparsa e quindi selezionare **Avvia indagine automatizzata.** |

## <a name="how-an-automated-investigation-expands-its-scope"></a>Come un'indagine automatizzata espande il suo ambito

Durante l'esecuzione di un'indagine, tutti gli altri avvisi generati dal dispositivo vengono aggiunti a un'indagine automatizzata in corso fino al completamento dell'indagine. Inoltre, se la stessa minaccia viene vista su altri dispositivi, questi dispositivi vengono aggiunti all'indagine.

Se un'entità incriminata viene visualizzata in un altro dispositivo, il processo di indagine automatizzata espande il suo ambito per includere tale dispositivo e un playbook di sicurezza generale viene avviato su tale dispositivo. Se durante questo processo di espansione vengono trovati 10 o più dispositivi dalla stessa entità, l'azione di espansione richiede un'approvazione ed è visibile nella **scheda Azioni in** sospeso.

## <a name="how-threats-are-remediated"></a>Modalità di correzione delle minacce

Quando vengono attivati avvisi e viene eseguita un'indagine automatizzata, viene generato un verdetto per ogni prova esaminata. I verdetti possono essere 
- *Dannoso*;
- *Sospetto;* o 
- *Nessuna minaccia trovata.* 

Una volta raggiunti i verdetti, le indagini automatizzate possono comportare una o più azioni di correzione. Esempi di azioni di correzione includono l'invio di un file in quarantena, l'arresto di un servizio, la rimozione di un'attività pianificata e altro ancora. Per ulteriori informazioni, vedere [Azioni di correzione.](manage-auto-investigation.md#remediation-actions)  

A seconda del [livello di automazione](automation-levels.md) impostato per l'organizzazione, nonché di altre impostazioni di sicurezza, le azioni di correzione possono verificarsi automaticamente o solo dopo l'approvazione da parte del team delle operazioni di sicurezza. Altre impostazioni di sicurezza che possono influire sulla correzione automatica includono la protezione da applicazioni potenzialmente [indesiderate.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) 

Tutte le azioni di correzione, in sospeso o completate, vengono rilevate nel [centro notifiche.](auto-investigation-action-center.md) Se necessario, il team delle operazioni di sicurezza può annullare un'azione di correzione. Per ulteriori informazioni, vedere [Review and approve remediation actions following an automated investigation.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

> [!TIP]
> Vedere la nuova pagina di indagine unificata nel Centro sicurezza Microsoft 365. Per ulteriori informazioni, vedere [(NEW!) Pagina di indagine unificata](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).


## <a name="requirements-for-air"></a>Requisiti per AIR

L'organizzazione deve disporre di Defender per Endpoint (vedere [Requisiti minimi per Microsoft Defender per Endpoint](minimum-requirements.md)).

Attualmente, AIR supporta solo le seguenti versioni del sistema operativo:
- Windows Server 2019
- Windows 10, versione 1709 (OS Build 16299.1085 con [KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)o versione successiva
- Windows 10 versione 1803 (OS Build 17134.704 con [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) o versione successiva
- Windows 10, versione [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) o successiva

## <a name="next-steps"></a>Passaggi successivi

- [Ulteriori informazioni sui livelli di automazione](automation-levels.md)
- [Vedere la guida interattiva: Analizzare e correggere le minacce con Microsoft Defender for Endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Configurare le funzionalità di analisi e correzione automatizzate in Microsoft Defender for Endpoint](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Vedere anche

- [Protezione puA](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Analisi e risposta automatizzate in Microsoft Defender per Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-air)
- [Analisi e risposta automatizzate in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
