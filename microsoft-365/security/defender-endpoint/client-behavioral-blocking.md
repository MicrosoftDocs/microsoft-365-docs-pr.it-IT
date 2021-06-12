---
title: Blocco comportamentale client
description: Il blocco comportamentale client fa parte delle funzionalità di blocco e contenimento comportamentali in Microsoft Defender for Endpoint
keywords: blocco comportamentale, protezione rapida, comportamento client, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b85c0c63cc7c72ad555d80bd8ce6c07c95b4b97b
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908078"
---
# <a name="client-behavioral-blocking"></a>Blocco comportamentale client

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Panoramica

Il blocco comportamentale del client è un componente delle funzionalità di blocco [e contenimento comportamentali](behavioral-blocking-containment.md) in Defender for Endpoint. Quando vengono rilevati comportamenti sospetti nei dispositivi (denominati anche client o endpoint), gli artefatti (ad esempio file o applicazioni) vengono bloccati, controllati e corretti automaticamente. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protezione cloud e client":::

La protezione antivirus funziona meglio se abbinata alla protezione cloud.

## <a name="how-client-behavioral-blocking-works"></a>Funzionamento del blocco comportamentale client

[Antivirus Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) in grado di rilevare comportamenti sospetti, codice dannoso, attacchi senza file e in memoria e altro ancora in un dispositivo. Quando vengono rilevati comportamenti sospetti, Antivirus Microsoft Defender questi comportamenti sospetti e i relativi alberi di processo vengono monitorati e inviati al servizio di protezione cloud. L'apprendimento automatico distingue tra applicazioni dannose e comportamenti buoni in pochi millisecondi e classifica ogni artefatto. In tempo quasi reale, non appena un artefatto viene rilevato dannoso, viene bloccato nel dispositivo. 

Ogni volta che viene [](alerts-queue.md) rilevato un comportamento sospetto, viene generato un avviso ed è visibile nel portale [di Microsoft 365 Defender](microsoft-defender-security-center.md) (in precedenza Microsoft Defender Security Center).

Il blocco comportamentale del client è efficace perché non solo consente di impedire l'avvio di un attacco, ma può aiutare a interrompere un attacco che ha iniziato l'esecuzione. Inoltre, con [il blocco del ciclo](feedback-loop-blocking.md) di feedback (un'altra funzionalità di blocco e contenimento comportamentale), gli attacchi vengono impediti su altri dispositivi dell'organizzazione.

## <a name="behavior-based-detections"></a>Rilevamenti basati sul comportamento

I rilevamenti basati sul comportamento sono denominati in base alla matrice [MITRE ATT&CK per Enterprise](https://attack.mitre.org/matrices/enterprise). La convenzione di denominazione consente di identificare la fase di attacco in cui è stato osservato il comportamento dannoso:


|Tattica |   Nome minaccia di rilevamento |
|----|----|
|Accesso iniziale | `Behavior:Win32/InitialAccess.*!ml` |
|Esecuzione  | `Behavior:Win32/Execution.*!ml` |
|Persistenza    | `Behavior:Win32/Persistence.*!ml` |
|Escalation dei privilegi   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|Evasione della difesa    | `Behavior:Win32/DefenseEvasion.*!ml` |
|Accesso credenziali  | `Behavior:Win32/CredentialAccess.*!ml` |
|Individuazione  | `Behavior:Win32/Discovery.*!ml` |
|Movimento laterale | `Behavior:Win32/LateralMovement.*!ml` |
|Raccolta |   `Behavior:Win32/Collection.*!ml` |
|Comando e controllo | `Behavior:Win32/CommandAndControl.*!ml` |
|Exfiltration   | `Behavior:Win32/Exfiltration.*!ml` |
|Impatto | `Behavior:Win32/Impact.*!ml` |
|Non classificato  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> Per ulteriori informazioni sulle minacce specifiche, vedere **[Attività di minacce globali recenti.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Configurazione del blocco comportamentale del client

Se l'organizzazione usa Defender per Endpoint, il blocco comportamentale del client è abilitato per impostazione predefinita. Tuttavia, per trarre vantaggio da tutte le funzionalità di Defender for Endpoint, tra cui il blocco comportamentale e il [contenimento,](behavioral-blocking-containment.md)assicurati che le funzionalità e le funzionalità seguenti di Defender for Endpoint siano abilitate e configurate:

- [Linee di base di Defender for Endpoint](configure-machines-security-baseline.md)

- [Dispositivi onboarded in Defender for Endpoint](onboard-configure.md)

- [EdR in modalità blocco](edr-in-block-mode.md)

- [Riduzione della superficie di attacco](attack-surface-reduction.md)

- [Protezione di nuova generazione](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware e altre funzionalità di protezione dalle minacce)

