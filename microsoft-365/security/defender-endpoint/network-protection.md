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
ms.topic: how-to
ms.openlocfilehash: 95c87330eec3cb557e5fea96148d626b7e0ee4b3
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768915"
---
# <a name="protect-your-network"></a>Proteggere la rete

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

La protezione di rete consente di ridurre la superficie di attacco dei dispositivi da eventi basati su Internet. Impedisce ai dipendenti di utilizzare qualsiasi applicazione per accedere a domini pericolosi che potrebbero ospitare tentativi di phishing, exploit e altri contenuti dannosi su Internet. La protezione di rete espande l'ambito di [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) per bloccare tutto il traffico HTTP in uscita che tenta di connettersi a origini con reputazione scarsa (in base al dominio o al nome host).

La protezione di rete è supportata in Windows, a partire da Windows 10 versione 1709. La protezione di rete non è ancora supportata in altri sistemi operativi, ma la protezione Web è supportata tramite il nuovo Microsoft Edge basato su Chromium. Per ulteriori informazioni, vedere [Protezione Web.](web-protection-overview.md)

La protezione di rete estende la protezione della [protezione Web](web-protection-overview.md) al livello del sistema operativo. Fornisce funzionalità di protezione Web in Edge ad altri browser supportati e applicazioni non browser. Inoltre, la protezione di rete fornisce visibilità e blocco degli indicatori di compromissione (I/O) se usati con il rilevamento [e la risposta degli endpoint.](overview-endpoint-detection-response.md) Ad esempio, la protezione di rete funziona con [gli indicatori personalizzati](manage-indicators.md).

Per ulteriori informazioni su come abilitare la protezione di rete, vedere [Enable network protection](enable-network-protection.md). Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.

> [!TIP]
> Per informazioni sul funzionamento della protezione di rete, vedere il sito di test di Microsoft Defender ATP [all'indirizzo demo.wd.microsoft.com.](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

La protezione di rete funziona in modo ottimale [con Microsoft Defender for Endpoint,](microsoft-defender-endpoint.md)che fornisce report dettagliati sugli eventi e i blocchi di protezione da exploit come parte degli scenari di analisi degli [avvisi.](investigate-alerts.md)

Quando la protezione di rete blocca una connessione, viene visualizzata una notifica dal Centro notifiche. Il team delle operazioni di sicurezza [può personalizzare la notifica](customize-attack-surface-reduction.md#customize-the-notification) con i dettagli e le informazioni di contatto dell'organizzazione. Inoltre, le singole regole di riduzione della superficie di attacco possono essere abilitate e personalizzate in base a determinate tecniche da monitorare.

È inoltre possibile utilizzare la [modalità di controllo](audit-windows-defender.md) per valutare l'impatto della protezione di rete sull'organizzazione se fosse abilitata.

## <a name="requirements"></a>Requisiti

La protezione di rete richiede Windows 10 Pro o Enterprise e microsoft Defender Antivirus in tempo reale.

| Versione di Windows | Microsoft Defender Antivirus |
|:---|:---|
| Windows 10 versione 1709 o successiva <p>Windows Server 1803 o versione successiva | [La protezione in tempo reale](configure-real-time-protection-microsoft-defender-antivirus.md) di Microsoft Defender Antivirus e la protezione con distribuzione [cloud](enable-cloud-protection-microsoft-defender-antivirus.md) devono essere abilitate |

Dopo aver abilitato i servizi, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni tra i servizi e i dispositivi (denominati anche endpoint).  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Esaminare gli eventi di protezione di rete in Microsoft Defender for Endpoint Security Center

Microsoft Defender for Endpoint fornisce report dettagliati su eventi e blocchi nell'ambito degli scenari di analisi [degli avvisi.](investigate-alerts.md)

Puoi eseguire query su Microsoft Defender per i dati dell'endpoint usando [la ricerca avanzata.](advanced-hunting-overview.md) Se usi la modalità [di](audit-windows-defender.md)controllo, puoi usare la ricerca avanzata per vedere in che modo le impostazioni di protezione di rete influirebbero sull'ambiente se fossero abilitate.

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

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>Considerazioni sul desktop virtuale Windows che esegue Windows 10 Enterprise Multi-Session

A causa della natura multi-utente di Windows 10 Enterprise, tenere presenti i punti seguenti:

1. La protezione di rete è una funzionalità a livello di dispositivo e non può essere destinata a sessioni utente specifiche.

2. Anche i criteri di filtro del contenuto Web sono a livello di dispositivo.

3. Se è necessario distinguere i gruppi di utenti, prendere in considerazione la creazione di pool host Desktop virtuale Windows e assegnazioni separati.

4. Testare la protezione di rete in modalità di controllo per valutarne il comportamento prima dell'implementazione. 

5. È consigliabile ridimensionare la distribuzione se si dispone di un numero elevato di utenti o di un numero elevato di sessioni multi-utente.

### <a name="alternative-option-for-network-protection"></a>Opzione alternativa per la protezione di rete

Per Windows 10 Enterprise Multi-Session 1909 e versione successiva, usata in Desktop virtuale Windows in Azure, la protezione di rete per Microsoft Edge può essere abilitata usando il metodo seguente:

1. Usa [Attiva protezione di rete](enable-network-protection.md) e segui le istruzioni per applicare i criteri.

2. Eseguire il comando di PowerShell seguente: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>Risoluzione dei problemi di protezione di rete

A causa dell'ambiente in cui viene eseguito Protezione di rete, Microsoft potrebbe non essere in grado di rilevare le impostazioni proxy del sistema operativo. In alcuni casi, i client di protezione di rete non sono in grado di raggiungere il servizio cloud. Per risolvere il problema di connettività, i clienti con licenze E5 devono configurare una delle seguenti chiavi del Registro di sistema defender:

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>Articoli correlati

- [Valutare i criteri di protezione](evaluate-network-protection.md) | Eseguire uno scenario rapido che illustra il funzionamento della funzionalità e gli eventi che in genere verrebbero creati.

- [Abilitare la protezione di](enable-network-protection.md) rete | Usa Criteri di gruppo, PowerShell o CSP MDM per abilitare e gestire la protezione di rete nella rete.
