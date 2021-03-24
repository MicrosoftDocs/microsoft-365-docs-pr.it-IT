---
title: Microsoft Defender ATP
description: Microsoft Defender for Endpoint è una piattaforma di sicurezza degli endpoint aziendale che aiuta a difendersi dalle minacce persistenti avanzate.
keywords: introduzione a Microsoft Defender for Endpoint, introduzione a Microsoft Defender Advanced Threat Protection, introduzione a Microsoft Defender ATP, cybersecurity, minacce persistenti avanzate, sicurezza aziendale, sensore comportamentale del computer, sicurezza cloud, analisi, intelligence sulle minacce, riduzione della superficie di attacco, protezione di nuova generazione, indagine e correzione automatizzate, esperti di minacce Microsoft, punteggio sicuro, ricerca avanzata, protezione dalle minacce Microsoft, ricerca di minacce informatiche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: b86ec893d61cffa8ca1926779db4d2f3b14eec21
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063957"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Per altre info sulle funzionalità e sulle funzionalità di Windows 10 Enterprise Edition, vedi [Windows 10 Enterprise Edition.](https://www.microsoft.com/WindowsForBusiness/buy)

Microsoft Defender for Endpoint è una piattaforma di sicurezza degli endpoint aziendale progettata per aiutare le reti aziendali a prevenire, rilevare, analizzare e rispondere alle minacce avanzate.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Defender for Endpoint usa la seguente combinazione di tecnologia integrata in Windows 10 e nel solido servizio cloud di Microsoft:

-   **Sensori comportamentali** endpoint: incorporati in Windows 10, questi sensori raccolgono ed elaborano i segnali comportamentali dal sistema operativo e inviano i dati del sensore all'istanza cloud privata, isolata di Microsoft Defender for Endpoint.


-   Analisi della sicurezza **cloud:** utilizzo di big data, apprendimento dei dispositivi e ottica Microsoft univoca nell'ecosistema Windows, prodotti cloud aziendali (come Office 365) e asset online, i segnali comportamentali vengono tradotti in dati analitici, rilevamenti e risposte consigliate alle minacce avanzate.

-   **Intelligence** per le minacce: generata da microsoft, team di sicurezza e aumentata dall'intelligence per le minacce fornita dai partner, l'intelligence per le minacce consente a Defender for Endpoint di identificare strumenti, tecniche e procedure dell'utente malintenzionato e generare avvisi quando vengono osservati nei dati dei sensori raccolti.

<center><h2>Microsoft Defender per Endpoint</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Gestione delle & delle minacce</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Riduzione della superficie di attacco</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Protezione di nuova generazione</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Rilevamento e risposta degli endpoint</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Analisi e correzione automatizzate</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Esperti di microsoft threat</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Configurazione e amministrazione centralizzate, API</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft Threat Protection</a></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Informazioni sui miglioramenti più recenti in Defender for Endpoint: [Novità di Microsoft Defender per Endpoint.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)
> - Microsoft Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

<a name="tvm"></a>

**[Gestione delle & delle minacce](next-gen-threat-and-vuln-mgt.md)**<br>
Questa funzionalità incorporata usa un approccio basato sul rischio che cambia il gioco per l'individuazione, la definizione delle priorità e la correzione delle vulnerabilità degli endpoint e delle configurazioni erre. 

<a name="asr"></a>

**[Riduzione della superficie d'attacco](overview-attack-surface-reduction.md)**<br>
Il set di funzionalità di riduzione della superficie di attacco fornisce la prima linea di difesa nello stack. Garantendo che le impostazioni di configurazione siano impostate correttamente e che le tecniche di mitigazione degli exploit siano applicate, le funzionalità resistono agli attacchi e allo sfruttamento. Questo set di [](network-protection.md) funzionalità include anche la protezione di rete e la protezione [Web,](web-protection-overview.md)che regolano l'accesso a indirizzi IP, domini e URL dannosi. 

<a name="ngp"></a>

**[Protezione di nuova generazione](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Per rafforzare ulteriormente il perimetro di sicurezza della rete, Microsoft Defender for Endpoint usa una protezione di nuova generazione progettata per rilevare tutti i tipi di minacce emergenti.

<a name="edr"></a>

**[Rilevamento endpoint e risposta](overview-endpoint-detection-response.md)**<br>
Le funzionalità di rilevamento e risposta degli endpoint vengono messe in atto per rilevare, analizzare e rispondere alle minacce avanzate che potrebbero aver fatto superare i primi due pilastri della sicurezza. [La ricerca avanzata](advanced-hunting-overview.md) offre uno strumento di ricerca delle minacce basato su query che consente di individuare in modo proattivo le violazioni e creare rilevamenti personalizzati.

<a name="ai"></a>

**[Indagine e correzione automatizzate](automated-investigations.md)**<br>
Oltre a essere in grado di rispondere rapidamente agli attacchi avanzati, Microsoft Defender for Endpoint offre funzionalità di analisi e correzione automatiche che consentono di ridurre il volume di avvisi in minuti su larga scala. 

<a name="ss"></a>

**[Microsoft Secure Score per i dispositivi](tvm-microsoft-secure-score-devices.md)**<br>

Defender for Endpoint include Microsoft Secure Score for Devices per aiutarti a valutare in modo dinamico lo stato di sicurezza della rete aziendale, identificare i sistemi non protetti ed eseguire azioni consigliate per migliorare la sicurezza complessiva dell'organizzazione.

<a name="mte"></a>

**[Microsoft Threat Experts](microsoft-threat-experts.md)**<br>
Il nuovo servizio di ricerca delle minacce gestite di Microsoft Defender for Endpoint fornisce la ricerca proattiva, la definizione delle priorità e ulteriori informazioni e contesto che consentono ai Centri operazioni di sicurezza (SOC) di identificare e rispondere alle minacce in modo rapido e accurato.

>[!IMPORTANT]
>I clienti di Defender for Endpoint devono richiedere il servizio di ricerca delle minacce gestito da Microsoft Threat Experts per ricevere notifiche di attacco mirato proattive e collaborare con esperti su richiesta. Experts on Demand è un servizio di componenti aggiuntivi. Le notifiche di attacco mirato vengono sempre incluse dopo l'accettazione nel servizio di ricerca delle minacce gestito da Microsoft Threat Experts.<p>
><p>Se non si è ancora registrati e si desidera sperimentarne i vantaggi, passare <b>a</b> Impostazioni > <b>Funzionalità</b> > <b></b> avanzate generali > <b>Microsoft Threat Experts</b> da applicare. Una volta accettato, potrai ottenere i vantaggi delle notifiche di attacco mirato e avviare una versione di valutazione di 90 giorni di Experts on Demand. Contattare il rappresentante Microsoft per ottenere un abbonamento completo a Experts on Demand.

<a name="apis"></a>

**[Configurazione e amministrazione centralizzate, API](management-apis.md)**<br>
Integrare Microsoft Defender for Endpoint nei flussi di lavoro esistenti.

<a name="mtp"></a>

**[Integrazione con soluzioni Microsoft](threat-protection-integration.md)** <br>
Defender for Endpoint si integra direttamente con varie soluzioni Microsoft, tra cui:
- Centro sicurezza di Azure
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender per identità
- Microsoft Defender per Office
- Skype for Business

**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Con Microsoft 365 Defender, Defender for Endpoint e varie soluzioni di sicurezza Microsoft formano una famiglia di prodotti di difesa aziendale unificata pre e post-violazione che si integra in modo nativo tra endpoint, identità, posta elettronica e applicazioni per rilevare, prevenire, analizzare e rispondere automaticamente ad attacchi sofisticati.


## <a name="related-topic"></a>Argomento correlato
[Microsoft Defender for Endpoint consente di rilevare minacce sofisticate](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
