---
title: Antivirus Microsoft Defender compatibilità con altri prodotti di sicurezza
description: Informazioni sulle Antivirus Microsoft Defender con altri prodotti di sicurezza e i sistemi operativi.
keywords: windows defender, defender per endpoint, di nuova generazione, antivirus, compatibilità, modalità passiva
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: aac84d2e957809d1c9579f25c01006798af2c0a9
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322414"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Antivirus Microsoft Defender compatibilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>Riepilogo

Antivirus Microsoft Defender viene abilitato e installato automaticamente in endpoint e dispositivi che eseguono Windows 10. Ma cosa succede quando viene utilizzata un'altra soluzione antivirus/antimalware (non Microsoft) ? È possibile eseguire Antivirus Microsoft Defender insieme a un altro prodotto antivirus? Le risposte dipendono da diversi fattori, ad esempio il sistema operativo e l'uso di [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) insieme alla protezione antivirus. 

## <a name="important-points-to-keep-in-mind"></a>Punti importanti da tenere presenti

- In modalità attiva, Antivirus Microsoft Defender viene usata come app antivirus nel computer. Impostazioni configurazione tramite Configuration Manager, Criteri di gruppo, Microsoft Intune o altri prodotti di gestione. I file vengono analizzati, le minacce vengono corretti e le informazioni di rilevamento vengono segnalate nello strumento di configurazione (ad esempio Configuration Manager o l'app Antivirus Microsoft Defender nell'endpoint stesso).

- In modalità passiva, Antivirus Microsoft Defender non viene usato come app  antivirus e le minacce non vengono corretti da Antivirus Microsoft Defender. I file vengono analizzati e vengono forniti report per i rilevamenti delle minacce condivisi con il servizio Microsoft Defender for Endpoint. Nel Centro sicurezza [](microsoft-defender-security-center.md) potrebbero essere visualizzati avvisi che Antivirus Microsoft Defender come origine, anche Antivirus Microsoft Defender in modalità passiva.

- Quando [EDR in](edr-in-block-mode.md) modalità blocco è attivato e Antivirus Microsoft Defender non è la soluzione antivirus principale, EDR in modalità blocco rileva e correggere gli elementi dannosi trovati nel dispositivo (dopo la violazione). EDR in modalità blocco è necessario Antivirus Microsoft Defender in modalità attiva o passiva.

- Se disabilitata, Antivirus Microsoft Defender non viene usata come app antivirus. I file non vengono analizzati e le minacce non vengono corretti. La disabilitazione o la Antivirus Microsoft Defender non è consigliata in generale. se possibile, mantenere Antivirus Microsoft Defender in modalità passiva se si utilizza una soluzione antimalware/antivirus non Microsoft.

- Se sei registrato in Microsoft Defender per Endpoint e stai usando un prodotto antivirus/antimalware non Microsoft, la Antivirus Microsoft Defender è abilitata in modalità passiva. Defender for Endpoint richiede la condivisione delle informazioni comuni da Antivirus Microsoft Defender per monitorare correttamente i dispositivi e la rete per i tentativi di intrusione e gli attacchi. Per altre informazioni, vedi [Antivirus Microsoft Defender compatibilità con Microsoft Defender per Endpoint.](defender-compatibility.md) 

- Quando Antivirus Microsoft Defender è in modalità passiva, è comunque possibile [gestire gli aggiornamenti per Antivirus Microsoft Defender;](manage-updates-baselines-microsoft-defender-antivirus.md) Tuttavia, non è possibile spostare Antivirus Microsoft Defender in modalità attiva se i dispositivi dispongono di un prodotto antivirus non Microsoft che fornisce protezione in tempo reale dal malware. Per un'efficacia ottimale della protezione e del rilevamento a più livelli, assicurati di ottenere gli aggiornamenti antivirus e antimwalware, anche se Antivirus Microsoft Defender è in esecuzione in modalità passiva. Vedere [Manage Antivirus Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

- Quando Antivirus Microsoft Defender viene disabilitato automaticamente, può essere ri-abilitato automaticamente se il prodotto antivirus/antimalware non Microsoft scade o in altro modo smette di fornire protezione in tempo reale da virus, malware o altre minacce. La ri-abilitazione automatica Antivirus Microsoft Defender consente di garantire che la protezione antivirus sia mantenuta sugli endpoint. Puoi anche abilitare un'analisi [periodica](limited-periodic-scanning-microsoft-defender-antivirus.md)limitata, che usa il motore di Antivirus Microsoft Defender per controllare periodicamente la presenza di minacce se usi un'app antivirus non Microsoft.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Antivirus Microsoft Defender e non Microsoft antivirus/antimalware

Il sistema operativo, il prodotto antivirus e Defender for Endpoint influiscono sulla modalità Antivirus Microsoft Defender attiva, passiva o disabilitata. Nella tabella seguente vengono riepilogati gli Antivirus Microsoft Defender quando le soluzioni antivirus/antimalware non Microsoft vengono utilizzate insieme o senza Microsoft Defender for Endpoint. 

| Versione di Windows   | Soluzione antivirus/antimalware  | Onboarded in <br/> Defender for Endpoint? | Antivirus Microsoft Defender stato     |
|------|------|-------|-------|
| Windows 10  | Antivirus Microsoft Defender | Sì  | Modalità attiva | 
| Windows 10  | Antivirus Microsoft Defender | No   | Modalità attiva |
| Windows 10  | Una soluzione antivirus/antimalware non Microsoft | Sì  | Modalità passiva (automaticamente) |
| Windows 10  | Una soluzione antivirus/antimalware non Microsoft | No   | Modalità disabilitata (automaticamente)    |
| Windows Server, versione 1803 o successiva <p> Windows Server 2019 | Antivirus Microsoft Defender  | Sì |         Modalità attiva  |
| Windows Server, versione 1803 o successiva <p> Windows Server 2019 | Antivirus Microsoft Defender | No  | Modalità attiva |
| Windows Server, versione 1803 o successiva <p> Windows Server 2019 | Una soluzione antivirus/antimalware non Microsoft | Sì  | Antivirus Microsoft Defender deve essere impostata sulla modalità passiva (manualmente) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, versione 1803 o successiva <p> Windows Server 2019 | Una soluzione antivirus/antimalware non Microsoft | No  | Antivirus Microsoft Defender deve essere disabilitato (manualmente) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Antivirus Microsoft Defender | Sì | Modalità attiva |
| Windows Server 2016 | Antivirus Microsoft Defender | No | Modalità attiva |
| Windows Server 2016 | Una soluzione antivirus/antimalware non Microsoft | Sì | Antivirus Microsoft Defender deve essere disabilitato (manualmente) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Una soluzione antivirus/antimalware non Microsoft | No | Antivirus Microsoft Defender deve essere disabilitato (manualmente) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) In Windows Server, versione 1803 o successiva o Windows Server 2019, Antivirus Microsoft Defender non entra automaticamente in modalità passiva quando si installa un prodotto antivirus non Microsoft. In questi casi, [impostare Antivirus Microsoft Defender modalità passiva](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) per evitare problemi causati dall'installazione di più prodotti antivirus in un server. Puoi impostare la Antivirus Microsoft Defender in modalità passiva usando PowerShell, Criteri di gruppo o una chiave del Registro di sistema.

Se si utilizza Windows Server, versione 1803 o successiva o Windows Server 2019, è possibile impostare Antivirus Microsoft Defender sulla modalità passiva impostando la chiave del Registro di sistema seguente:
- Percorso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nome: `ForceDefenderPassiveMode`
- Digitare: `REG_DWORD`
- Valore: `1`

> [!NOTE]
> La modalità passiva non è supportata Windows Server 2016. La chiave del Registro di sistema può essere utilizzata in Windows Server, versione 1803 o successiva o `ForceDefenderPassiveMode` Windows Server 2019, ma non Windows Server 2016. 

(<a id="fn2">2</a>) In Windows Server 2016, se si utilizza un prodotto antivirus non Microsoft, non è possibile eseguire Antivirus Microsoft Defender in modalità passiva o attiva. In questi casi, [disabilitare/disinstallare Antivirus Microsoft Defender manualmente](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) per evitare problemi causati dall'installazione di più prodotti antivirus in un server.

Vedere [Antivirus Microsoft Defender in Windows Server per](microsoft-defender-antivirus-on-windows-server.md) le principali differenze e opzioni di gestione per le Windows Server.

> [!IMPORTANT]
> Antivirus Microsoft Defender è disponibile solo nei dispositivi che eseguono Windows 10, Windows Server 2016, Windows Server, versione 1803 o successiva e Windows Server 2019.
>
> In Windows 8.1 e Windows Server 2012, la protezione antivirus degli endpoint a livello aziendale viene offerta come [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), che viene gestita tramite Microsoft Endpoint Configuration Manager.
>
> Windows Defender è disponibile anche per i dispositivi consumer in Windows 8.1 e [Windows Server 2012](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender), anche se non fornisce una gestione a livello aziendale (o un'interfaccia nelle installazioni di Windows Server 2012 Server Core).

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Impatto Antivirus Microsoft Defender funzionalità di Defender for Endpoint

Nella tabella di questa sezione sono riepilogate le funzionalità e le funzionalità disponibili in ogni stato. La tabella è progettata per essere solo informativo. È progettato per descrivere le funzionalità & che funzionano attivamente o meno, a seconda che Antivirus Microsoft Defender sia in modalità attiva, passiva o disabilitata/disinstallata. 

> [!IMPORTANT]
> Non disattivare le funzionalità, ad esempio la protezione in tempo reale, la protezione offerta dal cloud o l'analisi periodica limitata, se si usa Antivirus Microsoft Defender in modalità passiva o si usa EDR in modalità blocco. 

|Protezione |Modalità attiva |Modalità passiva |EDR in modalità blocco |Disabilitato o disinstallato |
|:---|:---|:---|:---|:---|
| [Protezione in tempo reale](configure-real-time-protection-microsoft-defender-antivirus.md) e [protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md) | Sì | No <sup> [[3](#fn3)]<sup> | No | No |
| [Disponibilità di analisi periodica limitata](limited-periodic-scanning-microsoft-defender-antivirus.md) | No | No | No | Sì |
| [Informazioni di analisi e rilevamento dei file](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Sì | Sì | Sì | No |
|  [Correzione delle minacce](configure-remediation-microsoft-defender-antivirus.md) | Sì | Vedere nota <sup> [[4](#fn4)]<sup> | Sì | No |
| [Aggiornamenti delle funzionalità di intelligence per la sicurezza](manage-updates-baselines-microsoft-defender-antivirus.md) | Sì | Sì | Sì | No |

(<a id="fn3">3</a>) In generale, quando Antivirus Microsoft Defender è in modalità passiva, la protezione in tempo reale non fornisce alcun blocco o applicazione, anche se è abilitata e in modalità passiva. 

(<a id="fn4">4</a>) Quando Antivirus Microsoft Defender è in modalità passiva, le funzionalità di correzione delle minacce sono attive solo durante le analisi pianificate o su richiesta.

> [!NOTE]
> [Microsoft 365 protezione della prevenzione della perdita](/microsoft-365/compliance/endpoint-dlp-learn-about) dei dati dell'endpoint continua a funzionare normalmente quando Antivirus Microsoft Defender in modalità attiva o passiva.

## <a name="why-defender-for-endpoint-matters"></a>Perché Defender for Endpoint è importante

Prendi in considerazione l'onboarding degli endpoint in Defender for Endpoint, anche se stai usando una soluzione antivirus/antimalware non Microsoft. Nella maggior parte dei casi, quando onboard i dispositivi a Defender for Endpoint, puoi usare Antivirus Microsoft Defender insieme alla soluzione antivirus non Microsoft per una maggiore protezione. Ad esempio, è possibile usare EDR [in](edr-in-block-mode.md)modalità blocco, che blocca e correggi gli artefatti dannosi che la soluzione antivirus principale potrebbe aver perso. 

Tenere presente quanto segue:

- Se i dispositivi client dell'organizzazione sono protetti da una soluzione antivirus/antimwalware non Microsoft, quando questi dispositivi vengono onboarded in Defender for Endpoint, Antivirus Microsoft Defender passa automaticamente in modalità passiva. In questo caso, si verificano rilevamenti di minacce, ma la protezione e le minacce in tempo reale non vengono corretti da Antivirus Microsoft Defender.
   
   > [!NOTE]
   > Questo scenario specifico non si applica agli endpoint che eseguono Windows Server.

- Se i dispositivi client dell'organizzazione sono protetti da una soluzione antivirus/antimalware non Microsoft e tali dispositivi non vengono onboarded in Microsoft Defender for Endpoint, Antivirus Microsoft Defender passa automaticamente alla modalità disabilitata. In questo caso, le minacce non vengono rilevate o corretti da Antivirus Microsoft Defender.
   
   > [!NOTE]
   > Questo scenario specifico non si applica agli endpoint che eseguono Windows Server.

- Se gli endpoint dell'organizzazione eseguono Windows Server e tali endpoint sono protetti da una soluzione antivirus/antimalware non Microsoft, quando tali endpoint vengono onboarded in Defender for Endpoint, Antivirus Microsoft Defender non passa automaticamente alla modalità passiva o disabilitata. In questo scenario specifico, è necessario configurare gli endpoint Windows Server in modo appropriato. 

   - In Windows Server, versione 1803 o successiva e Windows Server 2019, è possibile impostare Antivirus Microsoft Defender per l'esecuzione in modalità passiva. 
   - In Windows Server 2016, Antivirus Microsoft Defender deve essere disabilitata (la modalità passiva non è supportata in Windows Server 2016).

- Se gli endpoint dell'organizzazione sono protetti da una soluzione antivirus/antimalware non Microsoft, quando questi dispositivi vengono onboarded in Defender for Endpoint con [EDR in](/microsoft-365/security/defender-endpoint/edr-in-block-mode) modalità blocco abilitata, Defender for Endpoint blocca e correma gli artefatti dannosi.
   
   > [!NOTE]
   > Questo scenario specifico non si applica a Windows Server 2016. EDR in modalità blocco è necessario Antivirus Microsoft Defender in modalità attiva o passiva.


> [!WARNING]
> Non disabilitare, arrestare o modificare i servizi associati usati da Antivirus Microsoft Defender, Microsoft Defender per Endpoint o l'app Sicurezza di Windows. Questa raccomandazione include i servizi e i processi *wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* o *MsMpEng.* La modifica manuale di questi servizi può causare gravi instabilità nei dispositivi e può rendere vulnerabile la rete. La disabilitazione, l'arresto o la modifica di tali servizi può causare problemi anche quando si utilizzano soluzioni antivirus non Microsoft e la modalità di visualizzazione delle informazioni [nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Vedere anche

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus su Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EdR in modalità blocco](edr-in-block-mode.md)
- [Configurare Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint](defender-endpoint-false-positives-negatives.md)
- [Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
