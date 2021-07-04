---
title: Distribuire Microsoft Defender per Endpoint negli anelli
description: Informazioni su come distribuire Microsoft Defender per Endpoint negli anelli
keywords: distribuire, anelli, valutare, pilota, insider fast, insider slow, setup, onboard, phase, deployment, deploying, adoption, configuring
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4fffbbb519f9c31b5343e665958bcb47436a2d50
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289344"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>Distribuire Microsoft Defender per Endpoint negli anelli

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

La distribuzione di Microsoft Defender per Endpoint può essere eseguita usando un approccio di distribuzione basato su anello. 

I ring di distribuzione possono essere applicati negli scenari seguenti:
- [Nuove distribuzioni](#new-deployments)
- [Distribuzioni esistenti](#existing-deployments)

## <a name="new-deployments"></a>Nuove distribuzioni

![Immagine dei ring di distribuzione](images/deployment-rings.png)


Un approccio basato su anello è un metodo per identificare un set di endpoint da eseguire l'onboarding e verificare che determinati criteri siano soddisfatti prima di procedere alla distribuzione del servizio in un set di dispositivi più ampio. Puoi definire i criteri di uscita per ogni anello e assicurarti che siano soddisfatti prima di passare all'anello successivo.

L'adozione di una distribuzione basata su anello consente di ridurre i potenziali problemi che potrebbero verificarsi durante l'implementazione del servizio. Pilotando prima un determinato numero di dispositivi, è possibile identificare potenziali problemi e ridurre i potenziali rischi che potrebbero verificarsi. 

Nella tabella 1 viene fornito un esempio dei ring di distribuzione che è possibile utilizzare.

**Tabella 1**

|Anello di distribuzione|Descrizione
|---|---|
Valutazione | Anello 1: identificare 50 sistemi per i test pilota
Distribuzione pilota | Anello 2: identificare i successivi 50-100 endpoint nell'ambiente di produzione
Distribuzione completa | Anello 3: Implementare il servizio nel resto dell'ambiente con incrementi maggiori

### <a name="exit-criteria"></a>Criteri di uscita

Un esempio di set di criteri di uscita per questi anelli può includere:

- I dispositivi vengono visualizzati nell'elenco di inventario dei dispositivi
- Gli avvisi vengono visualizzati nel dashboard
- [Eseguire un test di rilevamento](run-detection-test.md)
- [Eseguire un attacco simulato su un dispositivo](attack-simulations.md)

### <a name="evaluate"></a>Valutazione

Identificare un numero limitato di computer di test nell'ambiente da eseguire l'onboard nel servizio. Idealmente, questi computer sarebbero meno di 50 endpoint.

### <a name="pilot"></a>Distribuzione pilota

Microsoft Defender for Endpoint supporta un'ampia gamma di endpoint che è possibile eseguire l'onboard nel servizio. In questo anello, identificare diversi dispositivi da eseguire l'onboard e in base ai criteri di uscita definiti, decidere di passare al successivo anello di distribuzione.

La tabella seguente mostra gli endpoint supportati e lo strumento corrispondente che puoi usare per eseguire l'onboardboard dei dispositivi nel servizio. 

| Endpoint     | Strumento di distribuzione                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script locale (fino a 10 dispositivi)](configure-endpoints-script.md) <br> NOTA: se vuoi distribuire più di 10 dispositivi in un ambiente di produzione, usa il metodo Criteri di gruppo o gli altri strumenti supportati elencati di seguito.<br>  [Criteri di gruppo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Gestione dispositivi mobili](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Script VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Script locale](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Gestione di dispositivi mobili](mac-install-with-other-mdm.md) |
| **Linux Server** | [Script locale](linux-install-manually.md) <br> [Pupazzo](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Basato su app](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               |

### <a name="full-deployment"></a>Distribuzione completa

In questa fase, è possibile utilizzare il [materiale di](deployment-strategy.md) pianificazione della distribuzione per pianificare la distribuzione. 

Usa il materiale seguente per selezionare l'architettura appropriata di Microsoft Defender for Endpoint che meglio si adatta alla tua organizzazione.

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di scorrimento per la strategia di distribuzione di Microsoft Defender for Endpoint](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | Il materiale sull'architettura consente di pianificare la distribuzione per le architetture seguenti: <ul><li> Nativa del cloud </li><li> Co-gestione </li><li> Locale</li><li>Valutazione e onboarding locale</li></ul>

## <a name="existing-deployments"></a>Distribuzioni esistenti

### <a name="windows-endpoints"></a>Windows endpoint

Per Windows e/o Windows Server, è possibile selezionare più computer da testare in anticipo (prima della patch di martedì) utilizzando il programma Di convalida degli aggiornamenti della sicurezza **(SUVP).**

Per altre informazioni, vedere:

- [Che cos'è il programma di convalida degli aggiornamenti della sicurezza](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>Endpoint non Windows

Con macOS e Linux, puoi prendere un paio di sistemi ed eseguirti nel canale Beta.

> [!NOTE]
> Idealmente almeno un amministratore della sicurezza e uno sviluppatore in modo da poter trovare problemi di compatibilità, prestazioni e affidabilità prima che la build la relazioni nel canale Corrente.

La scelta del canale determina il tipo e la frequenza degli aggiornamenti offerti al dispositivo. I dispositivi nella versione Beta sono i primi a ricevere aggiornamenti e nuove funzionalità, seguiti successivamente da Anteprima e infine da Current.

![Immagine degli anelli insider](images/insider-rings.png)

Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi dell'organizzazione per l'uso della versione Beta o dell'anteprima.

> [!WARNING]
> Il cambio di canale dopo l'installazione iniziale richiede la reinstallazione del prodotto. Per cambiare il canale del prodotto: disinstalla il pacchetto esistente, ri-configura il dispositivo per l'uso del nuovo canale e segui i passaggi in questo documento per installare il pacchetto dal nuovo percorso.
