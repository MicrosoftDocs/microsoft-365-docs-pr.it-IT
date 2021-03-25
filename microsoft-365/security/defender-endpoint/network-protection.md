---
title: Utilizzare la protezione di rete per impedire connessioni a siti non consentiti
description: Proteggere la rete impedendo agli utenti di accedere a indirizzi di rete sospetti e dannosi noti
keywords: Protezione di rete, exploit, sito Web dannoso, ip, dominio, domini
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.openlocfilehash: 29844d72f4a081db18ab56941fec53eeaf76dd12
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186978"
---
# <a name="protect-your-network"></a>Proteggere la rete

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

La protezione di rete consente di ridurre la superficie di attacco dei dispositivi da eventi basati su Internet. Impedisce ai dipendenti di utilizzare qualsiasi applicazione per accedere a domini pericolosi che potrebbero ospitare tentativi di phishing, exploit e altri contenuti dannosi su Internet. La protezione di rete espande l'ambito di [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) per bloccare tutto il traffico HTTP in uscita che tenta di connettersi a origini con reputazione scarsa (in base al dominio o al nome host).

La protezione di rete è supportata in Windows, a partire da Windows 10 versione 1709. 

Per ulteriori informazioni su come abilitare la protezione di rete, vedere [Enable network protection](enable-network-protection.md). Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.

> [!TIP]
> Per informazioni sul funzionamento della protezione di rete, vedere il sito di test di Microsoft Defender ATP [all'indirizzo demo.wd.microsoft.com.](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

La protezione di rete funziona in modo ottimale [con Microsoft Defender for Endpoint,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)che fornisce report dettagliati sugli eventi e i blocchi di protezione da exploit come parte degli scenari di analisi degli [avvisi.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Quando la protezione di rete blocca una connessione, viene visualizzata una notifica dal Centro notifiche. Il team delle operazioni di sicurezza [può personalizzare la notifica](customize-attack-surface-reduction.md#customize-the-notification) con i dettagli e le informazioni di contatto dell'organizzazione. Inoltre, le singole regole di riduzione della superficie di attacco possono essere abilitate e personalizzate in base a determinate tecniche da monitorare.

È inoltre possibile utilizzare la [modalità di controllo](audit-windows-defender.md) per valutare l'impatto della protezione di rete sull'organizzazione se fosse abilitata.

## <a name="requirements"></a>Requisiti

La protezione di rete richiede Windows 10 Pro o Enterprise e microsoft Defender Antivirus in tempo reale.

| Versione di Windows | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 versione 1709 o successiva <p>Windows Server 1803 o versione successiva | [La protezione in tempo reale](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) di Microsoft Defender Antivirus e la protezione con distribuzione [cloud](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) devono essere abilitate |

Dopo aver abilitato i servizi, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni tra i servizi e i dispositivi (denominati anche endpoint).  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Esaminare gli eventi di protezione di rete in Microsoft Defender for Endpoint Security Center

Microsoft Defender for Endpoint fornisce report dettagliati su eventi e blocchi nell'ambito degli scenari di analisi [degli avvisi.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

Puoi eseguire una query su Microsoft Defender per i dati dell'endpoint usando [Ricerca avanzata.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection) Se usi la modalità [di](audit-windows-defender.md)controllo, puoi usare la ricerca avanzata per vedere in che modo le impostazioni di protezione di rete influirebbero sull'ambiente se fossero abilitate.

Ecco una query di esempio

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Esaminare gli eventi di protezione di rete nel Visualizzatore eventi di Windows

È possibile esaminare il registro eventi di Windows per visualizzare gli eventi creati quando la protezione di rete blocca (o controlla) l'accesso a un IP o a un dominio dannoso:

1. [Copiare il codice XML direttamente](event-views.md).

2. Selezionare **OK**.

Questa procedura crea una visualizzazione personalizzata che filtra in modo da visualizzare solo gli eventi seguenti correlati alla protezione di rete:

| ID evento | Descrizione |
|:---|:---|
| 5007 | Evento quando vengono modificate le impostazioni |
| 1125 | Evento quando viene attivata la protezione di rete in modalità di controllo |
| 1126 | Evento quando viene attivata la protezione di rete in modalità blocco |

## <a name="related-articles"></a>Articoli correlati

- [Valutare i criteri di protezione](evaluate-network-protection.md) | Eseguire uno scenario rapido che illustra il funzionamento della funzionalità e gli eventi che in genere verrebbero creati.

- [Abilitare la protezione di](enable-network-protection.md) rete | Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.
