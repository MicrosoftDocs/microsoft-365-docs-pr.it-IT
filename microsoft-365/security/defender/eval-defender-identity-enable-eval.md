---
title: Abilitare l'ambiente di valutazione per Microsoft Defender for Identity, configurare l'istanza MDI, installare e configurare il sensore MDI, consentire al sensore MDI di rilevare gli amministratori locali
description: Configurare Microsoft Defender per l'identità Microsoft 365 Defender laboratorio di valutazione o ambiente pilota installando & configurando il sensore e individuando gli amministratori locali in altri computer.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458074"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>Abilitare l'ambiente di valutazione per Microsoft Defender for Identity

**Si applica a:**
- Microsoft 365 Defender

Questo articolo è [il passaggio 2 di 2](eval-defender-identity-overview.md) nel processo di configurazione dell'ambiente di valutazione per Microsoft Defender for Identity. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-identity-overview.md).

Usa la procedura seguente per configurare l'ambiente Microsoft Defender for Identity. 

![Passaggi per abilitare Microsoft Defender for Identity nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [Passaggio 1. Configurare Defender per l'istanza di identità](#step-1-set-up-the-defender-for-identity-instance)
- [Passaggio 2. Installare e configurare il sensore](#step-2-install-and-configure-the-sensor)
- [Passaggio 3. Configurare le impostazioni del registro eventi e del proxy nei computer con il sensore](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [Passaggio 4. Consenti a Defender for Identity di identificare gli amministratori locali in altri computer](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>Passaggio 1. Configurare Defender per l'istanza di identità

Accedi al portale defender per l'identità per creare l'istanza e quindi connetti questa istanza all'ambiente Active Directory. 

|  |Passaggio     |Altre informazioni  |
|---------|---------|---------|
|1      | Creare l'istanza defender per l'identità        | [Guida introduttiva: Creare l'istanza di Microsoft Defender for Identity](/defender-for-identity/install-step1)        |
|2      | Connessione'istanza di Defender for Identity nella foresta di Active Directory   | [Guida introduttiva: Connessione alla foresta di Active Directory](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>Passaggio 2. Installare e configurare il sensore

Successivamente, scaricare, installare e configurare il sensore Defender for Identity nei controller di dominio e nei server AD FS nell'ambiente locale.

|  |Passaggio     |Altre informazioni  |
|---------|---------|---------|
|1      | Determinare quanti sensori di Microsoft Defender for Identity sono necessari.        | [Pianificare la capacità di Microsoft Defender per l'identità](/defender-for-identity/capacity-planning)   |
|2      | Scaricare il pacchetto di installazione del sensore  |  [Guida introduttiva: Scaricare il pacchetto di installazione del sensore di identità di Microsoft Defender for Identity](/defender-for-identity/install-step3)   |
|3      | Installare il sensore Defender for Identity    |  [Guida introduttiva: Installare il sensore Microsoft Defender for Identity](/defender-for-identity/install-step4)       |
|4      | Configurare il sensore       |  [Configurare le impostazioni del sensore di identità per Microsoft Defender ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>Passaggio 3. Configurare le impostazioni del registro eventi e del proxy nei computer con il sensore

Nei computer in cui è installato il sensore, configurare Windows registro eventi e le impostazioni proxy Internet per abilitare e migliorare le funzionalità di rilevamento.

|  |Passaggio     |Altre informazioni  |
|---------|---------|---------|
|1      | Configurare Windows del registro eventi         | [Configurare Windows event](/defender-for-identity/configure-windows-event-collection)        |
|2      | Configurare le impostazioni proxy Internet        | [Configurare le impostazioni di connettività Internet e proxy endpoint per Il sensore di identità di Microsoft Defender](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>Passaggio 4. Consenti a Defender for Identity di identificare gli amministratori locali in altri computer

Il rilevamento del percorso di spostamento laterale di Microsoft Defender for Identity si basa su query che identificano gli amministratori locali in computer specifici. Queste query vengono eseguite con il protocollo SAM-R, utilizzando l'account Defender for Identity Service. 

Per garantire che i client e i server di Windows consentano all'account Defender for Identity di eseguire SAM-R, è necessario apportare una modifica a Criteri di gruppo per aggiungere l'account del servizio Defender per l'identità oltre agli account configurati elencati nei criteri di accesso di rete. Assicurarsi di applicare criteri di gruppo a tutti i computer ad **eccezione dei controller di dominio**.

Per istruzioni su come eseguire questa operazione, vedi Configurare Microsoft Defender per l'identità per [effettuare chiamate remote a SAM.](/defender-for-identity/install-step8-samr) 

## <a name="next-steps"></a>Passaggi successivi

Passaggio 3 di 3: [Pilotare Microsoft Defender per l'identità](eval-defender-identity-pilot.md)

Tornare alla panoramica per [valutare Microsoft Defender for Identity](eval-defender-identity-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)