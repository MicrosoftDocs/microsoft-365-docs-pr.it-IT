---
title: Blocco comportamentale client
description: Il blocco comportamentale client fa parte delle funzionalità di blocco e contenimento comportamentali in Microsoft Defender ATP
keywords: blocco comportamentale, protezione rapida, comportamento client, Microsoft Defender ATP
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
ms.openlocfilehash: c37a1180f9def51daa4229418b05abe7cf787aa3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165262"
---
# <a name="client-behavioral-blocking"></a>Blocco comportamentale client

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Panoramica

Il blocco comportamentale del client è un componente delle funzionalità di blocco [e contenimento comportamentali](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint. Quando vengono rilevati comportamenti sospetti nei dispositivi (denominati anche client o endpoint), gli artefatti (ad esempio file o applicazioni) vengono bloccati, controllati e corretti automaticamente. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Protezione cloud e client":::

La protezione antivirus funziona meglio se abbinata alla protezione cloud.

## <a name="how-client-behavioral-blocking-works"></a>Funzionamento del blocco comportamentale client

[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) è in grado di rilevare comportamenti sospetti, codice dannoso, attacchi senza file e in memoria e altro ancora in un dispositivo. Quando vengono rilevati comportamenti sospetti, Microsoft Defender Antivirus monitora e invia tali comportamenti sospetti e i relativi alberi di processo al servizio di protezione cloud. L'apprendimento automatico distingue tra applicazioni dannose e comportamenti buoni in pochi millisecondi e classifica ogni artefatto. In tempo quasi reale, non appena un artefatto viene rilevato dannoso, viene bloccato nel dispositivo. 

Ogni volta che viene rilevato un comportamento sospetto, [viene](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) generato un avviso ed è visibile in Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

Il blocco comportamentale del client è efficace perché non solo consente di impedire l'avvio di un attacco, ma può aiutare a interrompere un attacco che ha iniziato l'esecuzione. Inoltre, con [il blocco del ciclo](feedback-loop-blocking.md) di feedback (un'altra funzionalità di blocco e contenimento comportamentale), gli attacchi vengono impediti su altri dispositivi dell'organizzazione.

## <a name="behavior-based-detections"></a>Rilevamenti basati sul comportamento

I rilevamenti basati sul comportamento sono denominati in base [all'ATT MITRE&CK Matrix for Enterprise.](https://attack.mitre.org/matrices/enterprise) La convenzione di denominazione consente di identificare la fase di attacco in cui è stato osservato il comportamento dannoso:


|Tattica |   Nome minaccia di rilevamento |
|----|----|
|Accesso iniziale | Behavior:Win32/InitialAccess.*!ml |
|Esecuzione  | Behavior:Win32/Execution.*!ml |
|Persistenza    | Behavior:Win32/Persistence.*!ml |
|Escalation dei privilegi   | Behavior:Win32/PrivilegeEscalation.*!ml |
|Evasione della difesa    | Behavior:Win32/DefenseEvasion.*!ml |
|Accesso credenziali  | Behavior:Win32/CredentialAccess.*!ml |
|Individuazione  | Behavior:Win32/Discovery.*!ml |
|Movimento laterale | Behavior:Win32/LateralMovement.*!ml |
|Raccolta |   Behavior:Win32/Collection.*!ml |
|Comando e controllo | Behavior:Win32/CommandAndControl.*!ml |
|Exfiltration   | Behavior:Win32/Exfiltration.*!ml |
|Impatto | Behavior:Win32/Impact.*!ml |
|Non classificato  | Behavior:Win32/Generic.*!ml |

> [!TIP]
> Per ulteriori informazioni sulle minacce specifiche, vedere **[Attività di minacce globali recenti.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Configurazione del blocco comportamentale del client

Se l'organizzazione usa Defender per Endpoint, il blocco comportamentale del client è abilitato per impostazione predefinita. Tuttavia, per trarre vantaggio da tutte le funzionalità di Defender for Endpoint, tra cui il blocco comportamentale e il [contenimento,](behavioral-blocking-containment.md)assicurati che le funzionalità e le funzionalità seguenti di Defender for Endpoint siano abilitate e configurate:

- [Linee di base di Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Dispositivi onboarded in Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR in modalità blocco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Riduzione della superficie d'attacco](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Protezione di nuova generazione](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Articoli correlati

- [Blocco comportamentale e contenimento](behavioral-blocking-containment.md)

- [Blocco del ciclo di feedback](feedback-loop-blocking.md)

- [(Blog) Blocco e contenimento comportamentali: trasformazione dell'ottica in protezione](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Defender utile per le risorse endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
