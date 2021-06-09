---
title: Threat Protection (Windows 10)
description: Microsoft Defender per endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta.
keywords: protezione dalle minacce, Microsoft Defender for Endpoint, riduzione della superficie di attacco, protezione di nuova generazione, rilevamento e risposta degli endpoint, analisi e risposta automatizzate, esperti delle minacce Microsoft, Punteggio microsoft sicuro per i dispositivi, ricerca avanzata, ricerca di minacce informatiche, protezione dalle minacce Web
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 3db1517d87a47aae254d36cfb28f6c057830ef3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840995"
---
# <a name="threat-protection"></a>Protezione dalle minacce
[Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. Defender for Endpoint protegge gli endpoint dalle minacce informatiche, rileva attacchi avanzati e violazioni dei dati, automatizza gli incidenti di sicurezza e migliora la sicurezza.

> [!TIP]
> Consentire agli utenti di accedere ai servizi cloud e alle applicazioni locali con facilità e abilitare funzionalità di gestione moderne per tutti i dispositivi. Per ulteriori informazioni, vedere [Proteggere la forza lavoro remota.](/enterprise-mobility-security/remote-work/) 

<center><h2>Microsoft Defender per Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Minaccia & gestione delle vulnerabilità</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Riduzione della superficie di attacco</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Protezione di nuova generazione</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Rilevamento e risposta degli endpoint</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Analisi e correzione automatizzate</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Microsoft Threat Experts</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Configurazione e amministrazione centralizzate, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Gestione di minacce e vulnerabilità.](next-gen-threat-and-vuln-mgt.md)**<br>
Questa funzionalità incorporata usa un approccio basato sul rischio che cambia il gioco per l'individuazione, la definizione delle priorità e la correzione delle vulnerabilità degli endpoint e delle configurazioni erre.

- [Panoramica & gestione delle vulnerabilità minacce](next-gen-threat-and-vuln-mgt.md)
- [Introduzione](tvm-prerequisites.md)
- [Accedere al proprio ruolo di sicurezza](tvm-dashboard-insights.md)
- [Migliorare la sicurezza e ridurre i rischi](tvm-security-recommendation.md)
- [Capire le vulnerabilità nei dispositivi](tvm-software-inventory.md)

<a name="asr"></a>

**[Riduzione della superficie di attacco](overview-attack-surface-reduction.md)**<br>
Il set di funzionalità di riduzione della superficie di attacco fornisce la prima linea di difesa nello stack. Assicurandosi che le impostazioni di configurazione siano impostate correttamente e che le tecniche di mitigazione degli exploit siano applicate, questo set di funzionalità resiste agli attacchi e allo sfruttamento.

- [Isolamento basato su hardware](overview-hardware-based-isolation.md)
- [Controllo delle applicazioni](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Controllo dispositivo](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Protezione dagli exploit](exploit-protection.md)
- [Protezione di rete](network-protection.md), [protezione Web](web-protection-overview.md)
- [Accesso controllato alle cartelle](controlled-folders.md)
- [Firewall di rete](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Regole per la riduzione della superficie di attacco](attack-surface-reduction.md)

<a name="ngp"></a>

**[Protezione di nuova generazione](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Per rafforzare ulteriormente il perimetro di sicurezza della rete, Microsoft Defender for Endpoint usa una protezione di nuova generazione progettata per rilevare tutti i tipi di minacce emergenti.

- [Monitoraggio del comportamento](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Protezione basata su cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Apprendimento automatico](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [Protezione URL](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Servizio sandbox automatizzato](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[Rilevamento e risposta di endpoint](overview-endpoint-detection-response.md)**<br>
Vengono messe in atto funzionalità di rilevamento e risposta degli endpoint per rilevare, analizzare e rispondere ai tentativi di intrusione e alle violazioni attive. Con ricerca avanzata, hai uno strumento di ricerca delle minacce basato su query che consente all'utente di individuare in modo proattivo le violazioni e creare rilevamenti personalizzati.

- [Avvisi](alerts-queue.md)
- [Dati cronologici degli endpoint](investigate-machines.md#timeline)
- [Orchestrazione della risposta](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Raccolta forense](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Intelligence per le minacce](threat-indicator-concepts.md)
- [Servizio di detonazione e analisi avanzato](respond-file-alerts.md#deep-analysis)
- [Rilevazione avanzata](advanced-hunting-overview.md)
    - [Rilevamenti personalizzati](overview-custom-detections.md)

<a name="ai"></a>

**[Analisi e correzione automatizzate](automated-investigations.md)**<br>
Oltre a rispondere rapidamente agli attacchi avanzati, Microsoft Defender for Endpoint offre funzionalità di analisi e correzione automatiche che consentono di ridurre il volume di avvisi in minuti su larga scala.

- [Analisi e correzione automatizzate](automated-investigations.md)
- [Visualizzare dettagli e risultati delle indagini automatizzate](auto-investigation-action-center.md)
- [Visualizzare e approvare le azioni correttive](manage-auto-investigation.md)

<a name="mte"></a>

**[Microsoft Threat Experts](microsoft-threat-experts.md)**<br>
Il nuovo servizio di ricerca delle minacce gestite di Microsoft Defender for Endpoint fornisce la ricerca proattiva, la definizione delle priorità e ulteriori informazioni e contesto. Microsoft Threat Experts consente inoltre ai Security Operation Center (SOC) di identificare e rispondere alle minacce in modo rapido e accurato.

- [Notifica di attacco mirato](microsoft-threat-experts.md)
- [Esperti su richiesta](microsoft-threat-experts.md)
- [Configurare il servizio Microsoft 365 di ricerca gestita di Microsoft 365 Defender](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Configurazione e amministrazione centralizzate, API](management-apis.md)**<br>
Integrare Microsoft Defender for Endpoint nei flussi di lavoro esistenti.
- [Onboarding](onboard-configure.md)
- [Integrazione API e SIEM](configure-siem.md)
- [API esposte](apis-intro.md)
- [Controllo degli accessi in base al ruolo](rbac.md)
- [Report e tendenze](threat-protection-reports.md)

<a name="integration"></a>
**[Integrazione con soluzioni Microsoft](threat-protection-integration.md)** <br>
 Microsoft Defender for Endpoint si integra direttamente con varie soluzioni Microsoft, tra cui:
- Intune
- Microsoft Defender per Office 365
- Microsoft Defender per identità
- Azure Defender
- Skype for Business
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Con Microsoft 365 Defender, Microsoft Defender for Endpoint e varie soluzioni di sicurezza Microsoft formano una famiglia di prodotti di difesa aziendale unificata pre e post-violazione che si integra in modo nativo tra endpoint, identità, posta elettronica e applicazioni per rilevare, prevenire, analizzare e rispondere automaticamente ad attacchi sofisticati.
