---
title: Compatibilità di Microsoft Defender Antivirus con altri prodotti di sicurezza
description: Cosa aspettarsi da Microsoft Defender Antivirus con altri prodotti di sicurezza e i sistemi operativi in uso.
keywords: windows defender, di nuova generazione, antivirus, compatibilità, modalità passiva
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8eb52e277f7987477114db9333c3f90bb581ebb5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690390"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Compatibilità con Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Panoramica

Microsoft Defender Antivirus viene abilitato e installato automaticamente in endpoint e dispositivi che eseguono Windows 10. Ma cosa succede quando viene utilizzata un'altra soluzione antivirus/antimalware? Dipende dal fatto che si utilizzi [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) insieme alla protezione antivirus.
- Se gli endpoint e i dispositivi dell'organizzazione sono protetti con una soluzione antivirus/antimalware non Microsoft e Microsoft Defender for Endpoint non viene utilizzato, Microsoft Defender Antivirus passa automaticamente alla modalità disabilitata.
- Se l'organizzazione usa Microsoft Defender for Endpoint insieme a una soluzione antivirus/antimalware non Microsoft, Microsoft Defender Antivirus passa automaticamente in modalità passiva. La protezione e le minacce in tempo reale non vengono corretti da Microsoft Defender Antivirus.
- Se l'organizzazione usa Microsoft Defender for Endpoint con una soluzione antivirus/antimalware non Microsoft e hai [edR abilitato in](/microsoft-365/security/defender-endpoint/edr-in-block-mode) modalità blocco, ogni volta che viene rilevato un artefatto dannoso, Microsoft Defender for Endpoint si attiva per bloccare e correggere l'artefatto.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivirus e Microsoft Defender per Endpoint

La tabella seguente riepiloga cosa accade con Microsoft Defender Antivirus quando i prodotti antivirus di terze parti vengono usati insieme o senza Microsoft Defender per Endpoint. 


| Versione di Windows   | Protezione antimalware  | Registrazione di Microsoft Defender per endpoint | Stato di Microsoft Defender Antivirus     |
|------|------|-------|-------|
| Windows 10  | Un prodotto di terze parti non offerto o sviluppato da Microsoft | Sì  | Modalità passiva  |
| Windows 10  | Un prodotto di terze parti non offerto o sviluppato da Microsoft | No   | Modalità disabilitata automaticamente     |
| Windows 10  | Microsoft Defender Antivirus | Sì  | Modalità attiva | 
| Windows 10  | Microsoft Defender Antivirus | No   | Modalità attiva |
| Windows Server, versione 1803 o successiva o Windows Server 2019 | Un prodotto di terze parti non offerto o sviluppato da Microsoft | Sì  | Deve essere impostato sulla modalità passiva (manualmente) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, versione 1803 o successiva o Windows Server 2019 | Un prodotto di terze parti non offerto o sviluppato da Microsoft | No  | Deve essere disabilitato (manualmente) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, versione 1803 o successiva o Windows Server 2019 | Microsoft Defender Antivirus  | Sì |         Modalità attiva  |
| Windows Server, versione 1803 o successiva o Windows Server 2019 | Microsoft Defender Antivirus | No  | Modalità attiva |
| Windows Server 2016 | Microsoft Defender Antivirus | Sì | Modalità attiva |
| Windows Server 2016 | Microsoft Defender Antivirus | No | Modalità attiva |
| Windows Server 2016 | Un prodotto di terze parti non offerto o sviluppato da Microsoft | Sì | Deve essere disabilitato (manualmente) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Un prodotto di terze parti non offerto o sviluppato da Microsoft | No | Deve essere disabilitato (manualmente) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) In Windows Server, versione 1803 o successiva o Windows Server 2019, Microsoft Defender Antivirus non entra automaticamente in modalità passiva quando si installa un prodotto antivirus non Microsoft. In questi casi, impostare Microsoft Defender Antivirus sulla modalità [passiva](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) per evitare problemi causati dall'installazione di più prodotti antivirus in un server.

Se si usa Windows Server, versione 1803 o successiva o Windows Server 2019, è possibile impostare Microsoft Defender Antivirus sulla modalità passiva impostando la chiave del Registro di sistema seguente:
- Percorso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nome: `ForcePassiveMode`
- Digitare: `REG_DWORD`
- Valore: `1`

> [!NOTE]
> La `ForcePassiveMode` chiave del Registro di sistema non è supportata in Windows Server 2016.

(<a id="fn2">2</a>) In Windows Server 2016, Microsoft Defender Antivirus non entra automaticamente in modalità passiva quando si installa un prodotto antivirus non Microsoft. Inoltre, Microsoft Defender Antivirus non è supportato in modalità passiva. In questi casi, [disabilitare/disinstallare manualmente Microsoft Defender Antivirus](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) per evitare problemi causati dall'installazione di più prodotti antivirus in un server.

Vedi [Microsoft Defender Antivirus in Windows Server per](microsoft-defender-antivirus-on-windows-server.md) le principali differenze e opzioni di gestione per le installazioni di Windows Server.

> [!IMPORTANT]
> Microsoft Defender Antivirus è disponibile solo nei dispositivi che eseguono Windows 10, Windows Server 2016, Windows Server, versione 1803 o successiva e Windows Server 2019.
>
> In Windows 8.1 e Windows Server 2012, la protezione antivirus degli endpoint a livello aziendale è disponibile come [System Center Endpoint Protection,](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))gestito tramite Microsoft Endpoint Configuration Manager.
>
> Windows Defender è disponibile anche per i dispositivi [consumer in Windows 8.1 e Windows Server 2012,](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)anche se non fornisce una gestione a livello aziendale (o un'interfaccia nelle installazioni di Windows Server 2012 Server Core).

## <a name="functionality-and-features-available-in-each-state"></a>Funzionalità e funzionalità disponibili in ogni stato

Nella tabella di questa sezione sono riepilogate le funzionalità e le funzionalità disponibili in ogni stato. La tabella è progettata per essere solo informativo. È progettato per descrivere le funzionalità & che funzionano attivamente o meno, a seconda che Microsoft Defender Antivirus sia in modalità attiva, in modalità passiva o sia disabilitato/disinstallato. 

> [!IMPORTANT]
> Non disattivare le funzionalità, ad esempio la protezione in tempo reale, la protezione offerta dal cloud o l'analisi periodica limitata, se si usa Microsoft Defender Antivirus in modalità passiva o si usa EDR in modalità blocco. 

|Protezione |Modalità attiva |Modalità passiva |EdR in modalità blocco |Disabilitato o disinstallato |
|:---|:---|:---|:---|:---|
| [Protezione in tempo reale](./configure-real-time-protection-microsoft-defender-antivirus.md) e [protezione basata sul cloud](./enable-cloud-protection-microsoft-defender-antivirus.md) | Sì | No <sup> [[3](#fn3)]<sup> | No | No |
| [Disponibilità di analisi periodica limitata](./limited-periodic-scanning-microsoft-defender-antivirus.md) | No | No | No | Sì |
| [Informazioni di analisi e rilevamento dei file](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Sì | Sì | Sì | No |
|  [Correzione delle minacce](./configure-remediation-microsoft-defender-antivirus.md) | Sì | Vedere nota <sup> [[4](#fn4)]<sup> | Sì | No |
| [Aggiornamenti delle funzionalità di intelligence per la sicurezza](./manage-updates-baselines-microsoft-defender-antivirus.md) | Sì | Sì | Sì | No |

(<a id="fn3">3</a>) In generale, quando Microsoft Defender Antivirus è in modalità passiva, la protezione in tempo reale non fornisce alcun blocco o imposizione, anche se è abilitato e in modalità passiva. 

(<a id="fn4">4</a>) Quando Microsoft Defender Antivirus è in modalità passiva, le funzionalità di correzione delle minacce sono attive solo durante le analisi pianificate o su richiesta.

> [!NOTE]
> La protezione della prevenzione della perdita dei dati di [Microsoft 365 Endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about) continua a funzionare normalmente quando Microsoft Defender Antivirus è in modalità attiva o passiva.

## <a name="keep-the-following-points-in-mind"></a>Tenere presenti i punti seguenti

- In modalità attiva, Microsoft Defender Antivirus viene usato come app antivirus nel computer. Verranno applicate tutte le configurazioni effettuate con Configuration Manager, Criteri di gruppo, Intune o altri prodotti di gestione. I file vengono analizzati e le minacce vengono corretti e le informazioni di rilevamento vengono segnalate nello strumento di configurazione (ad esempio Configuration Manager o l'app Microsoft Defender Antivirus nel computer stesso).

- In modalità passiva, Microsoft Defender Antivirus non viene usato come app antivirus e le minacce non vengono corretti da Microsoft Defender Antivirus. I file vengono analizzati e vengono forniti report per i rilevamenti delle minacce condivisi con il servizio Microsoft Defender for Endpoint. Pertanto, potresti riscontrare avvisi nella console del Centro sicurezza con Microsoft Defender Antivirus come origine, anche quando Microsoft Defender Antivirus è in modalità passiva.

- Quando [EDR in modalità](/microsoft-365/security/defender-endpoint/edr-in-block-mode) blocco è attivato e Microsoft Defender Antivirus non è la soluzione antivirus principale, può comunque rilevare e correggere gli elementi dannosi.

- Se disabilitato, Microsoft Defender Antivirus non viene usato come app antivirus. I file non vengono analizzati e le minacce non vengono corretti. La disabilitazione/disinstallazione di Microsoft Defender Antivirus non è consigliata in generale. se possibile, mantenere Microsoft Defender Antivirus in modalità passiva se si utilizza una soluzione antimalware/antivirus non Microsoft.

- Se sei registrato in Microsoft Defender per Endpoint e stai usando un prodotto antimalware di terze parti, la modalità passiva è abilitata. [Il servizio richiede la condivisione delle informazioni comuni](/microsoft-365/security/defender-endpoint/defender-compatibility) dal servizio Microsoft Defender Antivirus per monitorare correttamente i dispositivi e la rete per i tentativi di intrusione e gli attacchi.

- Quando Microsoft Defender Antivirus viene disabilitato automaticamente, può essere ri-abilitato automaticamente se la protezione offerta da un prodotto antivirus non Microsoft scade o in altro modo smette di fornire protezione in tempo reale da virus, malware o altre minacce. La ri-abilitazione automatica garantisce che la protezione antivirus sia mantenuta nei dispositivi. Consente inoltre di abilitare l'analisi [periodica](limited-periodic-scanning-microsoft-defender-antivirus.md)limitata, che usa il motore Microsoft Defender Antivirus per controllare periodicamente la presenza di minacce oltre all'app antivirus principale.

- Quando Microsoft Defender Antivirus è in modalità passiva, puoi comunque [gestire gli aggiornamenti per Microsoft Defender Antivirus;](manage-updates-baselines-microsoft-defender-antivirus.md) Tuttavia, non è possibile spostare Microsoft Defender Antivirus in modalità attiva se i dispositivi dispongono di un prodotto antivirus aggiornato e non Microsoft che fornisce protezione in tempo reale dal malware. Per garantire un'efficacia ottimale per la difesa e il rilevamento a più livelli di sicurezza, assicurati di aggiornare la protezione [microsoft Defender Antivirus (aggiornamento dell'intelligence](./manage-updates-baselines-microsoft-defender-antivirus.md) per la sicurezza, motore e piattaforma) anche se Microsoft Defender Antivirus è in esecuzione in modalità passiva.

   Se disinstalli il prodotto antivirus non Microsoft e usi Microsoft Defender Antivirus per fornire protezione ai dispositivi, Microsoft Defender Antivirus tornerà automaticamente alla normale modalità attiva.

> [!WARNING]
> Non disabilitare, arrestare o modificare i servizi associati usati da Microsoft Defender Antivirus, Microsoft Defender for Endpoint o dall'app Windows Security. Questa raccomandazione include i servizi e i processi *wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* o *MsMpEng.* La modifica manuale di questi servizi può causare gravi instabilità nei dispositivi e può rendere vulnerabile la rete. La disabilitazione, l'arresto o la modifica di tali servizi può causare problemi anche quando si utilizzano soluzioni antivirus non Microsoft e la modalità di visualizzazione delle informazioni [nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Vedere anche

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus in Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EdR in modalità blocco](edr-in-block-mode.md)
- [Configurare Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Risolvere i falsi positivi/negativi in Microsoft Defender per endpoint](defender-endpoint-false-positives-negatives.md)
- [Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)