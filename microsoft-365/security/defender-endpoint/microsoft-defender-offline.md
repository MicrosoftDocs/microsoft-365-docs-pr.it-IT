---
title: Microsoft Defender Offline in Windows 10
description: Puoi usare Microsoft Defender Offline direttamente dall'app Windows Defender Antivirus app. È inoltre possibile gestire la modalità di distribuzione nella rete.
keywords: analisi, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275145"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Eseguire e rivedere i risultati di un’analisi Microsoft Defender Offline

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline è uno strumento di analisi antimalware che consente di avviare ed eseguire un'analisi da un ambiente attendibile. L'analisi viene eseguita dall'esterno del normale kernel di Windows in modo che possa essere mirato al malware che tenta di ignorare la shell di Windows, ad esempio virus e rootkit che infettano o sovrascrivono il record di avvio master (MBR).

È possibile utilizzare Microsoft Defender Offline se si sospetta un'infezione da malware o si desidera confermare una pulizia completa dell'endpoint dopo un'epidemia di malware.

In Windows 10, Microsoft Defender Offline può essere eseguito con un solo clic direttamente [dall'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md) Nelle versioni precedenti di Windows, un utente doveva installare Microsoft Defender Offline su supporti di avvio, riavviare l'endpoint e caricare il supporto di avvio.

## <a name="prerequisites-and-requirements"></a>prerequisiti e requisiti

Microsoft Defender Offline in Windows 10 ha gli stessi requisiti hardware di Windows 10. 

Per ulteriori informazioni sui Windows 10, vedere i seguenti argomenti:

- [Requisiti hardware minimi](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Linee guida per i componenti hardware](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline non è supportato nei computer con processori ARM o Windows Server Stock Keeping Units.

Per eseguire Microsoft Defender Offline dall'endpoint, l'utente deve essere connesso con privilegi di amministratore.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender Offline aggiornamenti

Microsoft Defender Offline vengono utilizzati gli aggiornamenti di protezione più recenti disponibili nell'endpoint. viene aggiornato ogni volta Windows Defender Antivirus viene aggiornato. 

> [!NOTE]
> Prima di eseguire un'analisi offline, è consigliabile tentare di aggiornare la protezione di Microsoft Defender AV. È possibile forzare un aggiornamento con Criteri di gruppo o, in genere, distribuire gli aggiornamenti agli endpoint oppure scaricare e installare manualmente gli aggiornamenti di protezione più recenti [dal Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Per ulteriori [informazioni, vedere l'argomento Manage Antivirus Microsoft Defender Security intelligence updates.](manage-protection-updates-microsoft-defender-antivirus.md)

## <a name="usage-scenarios"></a>Scenari di utilizzo

In Windows 10 versione 1607, è possibile forzare manualmente un'analisi offline. In alternativa, se Windows Defender che Microsoft Defender Offline necessario eseguire, verrà richiesto all'utente nell'endpoint. 

La necessità di eseguire un'analisi offline verrà inoltre rivelata Microsoft Endpoint Manager se si usa per gestire gli endpoint.

Il prompt può verificarsi tramite una notifica, simile alla seguente:

![Windows notifica che mostra il requisito per l'esecuzione Microsoft Defender Offline](images/defender/notification.png)

L'utente riceverà anche una notifica all'interno del client Windows Defender client.

In Configuration Manager è possibile identificare lo stato degli endpoint accedendo a Monitoraggio > Panoramica > Sicurezza > Endpoint Protection stato > System Center Endpoint Protection **Stato**. 

Microsoft Defender Offline analisi sono indicate in **Stato** correzione malware come **Analisi offline necessaria.**

![Microsoft Endpoint Manager che indica che è necessaria Microsoft Defender Offline'analisi](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Configurare le notifiche

Microsoft Defender Offline le notifiche vengono configurate nella stessa impostazione dei criteri di altre notifiche di Microsoft Defender AV.

Per altre informazioni sulle notifiche in Windows Defender, vedi l'argomento [Configurare le notifiche visualizzate negli endpoint.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Eseguire un'analisi 

> [!IMPORTANT]
> Prima di utilizzare Microsoft Defender Offline, assicurarsi di salvare i file e arrestare i programmi in esecuzione. L Microsoft Defender Offline intervaio richiede circa 15 minuti. L'endpoint verrà riavviato al termine dell'analisi. L'analisi viene eseguita al di fuori dell'ambiente Windows normale. L'interfaccia utente sarà diversa da una normale analisi eseguita da Windows Defender. Al termine dell'analisi, l'endpoint verrà riavviato e Windows verrà caricato normalmente.

È possibile eseguire un'Microsoft Defender Offline di analisi con le opzioni seguenti:

- PowerShell
- Strumentazione gestione Windows (WMI)
- L Sicurezza di Windows app



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Utilizzare i cmdlet di PowerShell per eseguire un'analisi offline

Utilizzare i cmdlet seguenti:

```PowerShell
Start-MpWDOScan
```

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Utilizzare Windows Management Instruction (WMI) per eseguire un'analisi offline

Utilizzare la [**classe MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per eseguire un'analisi offline.

Il frammento di script WMI seguente eseguirà immediatamente un'analisi Microsoft Defender Offline, che causerà il riavvio dell'endpoint, l'esecuzione dell'analisi offline e quindi il riavvio e l'avvio in Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Per ulteriori informazioni, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Usare l'app Windows Defender Security per eseguire un'analisi offline

1. Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando Defender nel menu **Start.**

2. Fai clic **sul riquadro Protezione da &** virus (o sull'icona scudo sulla barra dei menu sinistra) e quindi sull'etichetta **Analisi** avanzata:
    
3. Selezionare **Microsoft Defender Offline analisi e** fare clic su Analizza **ora.**

    > [!NOTE]
    > In Windows 10 versione 1607, l'analisi offline potrebbe essere eseguita da **Windows Impostazioni** Update & security Windows Defender o dal  >    >   client Windows Defender.


## <a name="review-scan-results"></a>Esaminare i risultati dell'analisi

Microsoft Defender Offline risultati dell'analisi verranno elencati nella sezione [Cronologia analisi dell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Articoli correlati

- [Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)