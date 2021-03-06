---
title: Blocco del ciclo di feedback
description: Il blocco del ciclo di feedback, denominato anche protezione rapida, fa parte delle funzionalità di blocco e contenimento comportamentali in Microsoft Defender for Endpoint
keywords: behavioral blocking, rapid protection, feedback blocking, Microsoft Defender for Endpoint
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
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842459"
---
# <a name="feedback-loop-blocking"></a>Blocco del ciclo di feedback

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Panoramica

Il blocco del ciclo di feedback, noto anche come protezione rapida, è un componente delle funzionalità di blocco e [contenimento](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) comportamentali in [Microsoft Defender per Endpoint.](/windows/security/threat-protection/) Con il blocco del ciclo di feedback, i dispositivi all'interno dell'organizzazione sono meglio protetti dagli attacchi. 

## <a name="how-feedback-loop-blocking-works"></a>Funzionamento del blocco del ciclo di feedback

Quando viene rilevato un comportamento o un file sospetto, ad esempio da Antivirus Microsoft Defender [,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)le informazioni sull'artefatto vengono inviate a più classificatori. Il motore loop di protezione rapida esamina e correla le informazioni con altri segnali per arrivare a una decisione se bloccare un file. Il controllo e la classificazione degli artefatti avviene rapidamente. Si verifica un rapido blocco del malware confermato e la protezione viene estesa all'intero ecosistema. 

Con la protezione rapida in atto, un attacco può essere arrestato su un dispositivo, altri dispositivi nell'organizzazione e dispositivi in altre organizzazioni, mentre un attacco tenta di ampliare il proprio punto di appoggio.


## <a name="configuring-feedback-loop-blocking"></a>Configurazione del blocco del ciclo di feedback

Se l'organizzazione usa Defender per Endpoint, il blocco del ciclo di feedback è abilitato per impostazione predefinita. Tuttavia, la protezione rapida avviene tramite una combinazione di funzionalità di Defender for Endpoint, funzionalità di protezione di machine learning e condivisione dei segnali tra i servizi di sicurezza Microsoft. Assicurati che le funzionalità e le funzionalità seguenti di Defender for Endpoint siano abilitate e configurate:

- [Linee di base di Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Dispositivi onboarded in Microsoft Defender per Endpoint](/microsoft-365/security/defender-endpoint/onboard-configure)

- [EdR in modalità blocco](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Riduzione della superficie di attacco](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Protezione di nuova generazione](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Articoli correlati

- [Blocco e contenimento comportamentale](behavioral-blocking-containment.md)

- [(Blog) Blocco e contenimento comportamentali: trasformazione dell'ottica in protezione](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Risorse utili per Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/helpful-resources)
