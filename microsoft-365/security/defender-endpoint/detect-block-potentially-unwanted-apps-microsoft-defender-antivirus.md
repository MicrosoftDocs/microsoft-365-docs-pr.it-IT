---
title: Bloccare le applicazioni potenzialmente indesiderate con Antivirus Microsoft Defender
description: Abilitare la funzionalità antivirus delle applicazioni potenzialmente indesiderate (PUA) per bloccare il software indesiderato, ad esempio l'adware.
keywords: pua, abilitare, software indesiderato, app indesiderate, adware, barra degli strumenti del browser, rilevare, bloccare, Antivirus Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.openlocfilehash: d7f411c81e839d3929d4aa1a52fda29399c59dca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772378"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Rilevare e bloccare applicazioni potenzialmente indesiderate

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

Le applicazioni potenzialmente indesiderate (PUA) sono una categoria di software che può causare il rallentamento del computer, la visualizzazione di annunci non previsti o, nel peggiore dei casi, l'installazione di altro software che potrebbe risultare indesiderato o imprevisto. Le applicazioni potenzialmente indesiderate non sono considerate virus, malware o minacce di altro tipo, ma potrebbero eseguire azioni che influiscono negativamente sulle prestazioni o sull'uso degli endpoint. Il termine *PUA* può anche fare riferimento a un'applicazione con una reputazione scadente, secondo la valutazione di Microsoft Defender per endpoint, a causa di alcuni tipi di comportamento indesiderato.

Ecco alcuni esempi:

- **Software pubblicitario** che mostra annunci pubblicitari o promozioni, incluso il software che inserisce annunci pubblicitari nelle pagine Web.
- **Software bundler** che offre l'installazione di altro software non firmato digitalmente dalla stessa entità oppure classificato come PUA.
- **Software di evasione**, che tenta attivamente di evadere il rilevamento da parte dei prodotti per la sicurezza, incluso il software che si comporta in modo diverso in presenza di prodotti per la sicurezza.

> [!TIP]
> Per altri esempi e una descrizione dei criteri che usiamo per etichettare le applicazioni per una particolare attenzione da parte delle funzionalità di sicurezza, vedere [Come Microsoft identifica malware e applicazioni potenzialmente indesiderate](/windows/security/threat-protection/intelligence/criteria).

Queste applicazioni possono aumentare il rischio di infezione della rete da parte di malware, possono rendere più difficile l'identificazione di infezioni malware e possono sprecare risorse IT per la pulizia delle applicazioni. La protezione da applicazioni potenzialmente indesiderate è supportata in Windows 10, Windows Server 2019 e Windows Server 2016. In Windows 10 (versione 2004 e successive), Antivirus Microsoft Defender blocca le app considerate PUA per i dispositivi Enterprise (E5) per impostazione predefinita.

## <a name="microsoft-edge"></a>Microsoft Edge

Il [nuovo Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), basato su Chromium, blocca i download di applicazioni potenzialmente indesiderate e gli URL di risorse associati. Questa funzionalità viene fornita tramite [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Abilitare la protezione da applicazioni potenzialmente indesiderate in Microsoft Edge basato su Chromium

Anche se la protezione da applicazioni potenzialmente indesiderate in Microsoft Edge (basato su Chromium, versione 80.0.361.50) è disattivata per impostazione predefinita, può essere attivata facilmente dall'interno del browser.

1. Nel browser Microsoft Edge selezionare i puntini di sospensione e quindi **Impostazioni**.

2. Selezionare **Privacy, ricerca e servizi**.

3. Nella sezione **Sicurezza** attivare **Blocca app potenzialmente indesiderate**.

> [!TIP]
> Se si usa Microsoft Edge (basato su Chromium), si può esplorare in sicurezza la funzionalità di blocco degli URL della protezione PUA, testandola in una delle [pagine demo di Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/).

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Bloccare gli URL con Microsoft Defender SmartScreen

In Microsoft Edge basato su Chromium con protezione PUA attivata, Microsoft Defender SmartScreen protegge dagli URL associati alle applicazioni potenzialmente indesiderate.

Gli amministratori della sicurezza possono [configurare](/DeployEdge/configure-microsoft-edge) il modo in cui Microsoft Edge e Microsoft Defender SmartScreen interagiscono per proteggere gruppi di utenti dagli URL associati alle applicazioni potenzialmente indesiderate. Sono disponibili diverse [impostazioni di Criteri di gruppo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) esplicitamente destinate a Microsoft Defender SmartScreen, tra cui [una per bloccare le PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Gli amministratori possono inoltre [configurare Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) nel suo insieme, usando le impostazioni di Criteri di gruppo per attivare o disattivare la funzionalità.

Anche se Microsoft Defender per endpoint ha un proprio elenco di blocco basato su un set di dati gestito da Microsoft, è possibile personalizzare questo elenco in base alla propria intelligence per le minacce. Se si [creano e gestiscono indicatori](manage-indicators.md) nel portale di Microsoft Defender per endpoint, Microsoft Defender SmartScreen rispetta le nuove impostazioni.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Antivirus Microsoft Defender e protezione PUA

La funzionalità di protezione PUA in Antivirus Microsoft Defender può rilevare e bloccare le applicazioni potenzialmente indesiderate negli endpoint della rete.

> [!NOTE]
> Questa funzionalità è disponibile in Windows 10, Windows Server 2019 e Windows Server 2016.

Antivirus Microsoft Defender blocca i file di PUA rilevati e gli eventuali tentativi di scaricarli, spostarli, eseguirli o installarli. I file di PUA bloccati vengono quindi spostati in quarantena. Quando viene rilevato un file PUA in un endpoint, Antivirus Microsoft Defender invia una notifica all'utente ([a meno che le notifiche non siano state disabilitate](configure-notifications-microsoft-defender-antivirus.md)) nello stesso formato degli altri rilevamenti delle minacce. La notifica è preceduta da `PUA:` per indicarne il contenuto.

La notifica viene visualizzata nel normale [elenco di quarantena nell'app Sicurezza di Windows](microsoft-defender-security-center-antivirus.md).

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Configurare la protezione PUA in Antivirus Microsoft Defender

È possibile abilitare la protezione da applicazioni potenzialmente indesiderate con [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Criteri di gruppo](/azure/active-directory-domain-services/manage-group-policy) o tramite [cmdlet di PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).

SI può anche usare la protezione PUA in modalità di controllo per rilevare le applicazioni potenzialmente indesiderate senza bloccarle. I rilevamenti vengono acquisiti nel registro eventi di Windows.

> [!TIP]
> Visitare il sito Web con le demo di Microsoft Defender per endpoint all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) per verificare se la funzionalità è operativa e vederla in azione.

La protezione PUA in modalità di controllo è utile se l'azienda sta esegue un controllo di conformità interno sulla sicurezza del software e si desidera evitare falsi positivi.

### <a name="use-intune-to-configure-pua-protection"></a>Usare Intune per configurare la protezione PUA

Per altre informazioni, vedere [Configurare le impostazioni relative alle restrizioni dei dispositivi in Microsoft Intune](/intune/device-restrictions-configure) e [Impostazioni relative alle restrizioni dei dispositivi di Antivirus Microsoft Defender per Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Usare Configuration Manager per configurare la protezione PUA

La protezione PUA è abilitata per impostazione predefinita in Microsoft Endpoint Manager (Current Branch).

Vedere la [sezione Impostazioni per le analisi pianificate in Come creare e distribuire criteri antimalware](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) per informazioni dettagliate sulla configurazione di Microsoft Endpoint Manager (Current Branch).

Per System Center Configuration Manager 2012, vedere [Come distribuire criteri di protezione delle applicazioni potenzialmente indesiderate per Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).

> [!NOTE]
> Gli eventi PUA bloccati da Antivirus Microsoft Defender vengono segnalati nel Visualizzatore eventi di Windows e non in Microsoft Endpoint Configuration Manager.

### <a name="use-group-policy-to-configure-pua-protection"></a>Usare Criteri di gruppo per configurare la protezione PUA

1. Scaricare e installare i [modelli amministrativi (.admx) per Windows 10 aggiornamento dell'ottobre 2020 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

3. Selezionare l'oggetto Criteri di gruppo da configurare e quindi scegliere **Modifica**.

4. Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.

5. Espandere l'albero fino a **Componenti di Windows** > **Antivirus Microsoft Defender**.

6. Fare doppio clic su **Configura il rilevamento di applicazioni potenzialmente indesiderate**.

7. Selezionare **Abilitata** per abilitare la protezione PUA.

8. In **Opzioni** selezionare **Blocca** per bloccare le applicazioni potenzialmente indesiderate oppure selezionare **Modalità di controllo** per testare il funzionamento dell'impostazione nel proprio ambiente. Selezionare **OK**.

9. Distribuire l'oggetto Criteri di gruppo come di consueto.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Usare i cmdlet di PowerShell per configurare la protezione PUA

#### <a name="to-enable-pua-protection"></a>Per abilitare la protezione PUA

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

Impostando il valore di questo cmdlet su `Enabled` è possibile attivare la funzionalità, se è stata disabilitata.

#### <a name="to-set-pua-protection-to-audit-mode"></a>Per impostare la protezione PUA sulla modalità di controllo

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

L'impostazione `AuditMode` consente di rilevare le applicazioni potenzialmente indesiderate senza bloccarle.

#### <a name="to-disable-pua-protection"></a>Per disabilitare la protezione PUA

È consigliabile mantenere la protezione PUA attivata. Tuttavia, è possibile disattivarla usando il cmdlet seguente:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Impostando il valore di questo cmdlet su `Disabled` è possibile disattivare la funzionalità, se è stata disabilitata.

Per altre informazioni, vedere [Usare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [Cmdlet di Defender](/powershell/module/defender/index).

## <a name="view-pua-events-using-powershell"></a>Visualizzare gli eventi PUA con PowerShell

Gli eventi PUA vengono segnalati nel Visualizzatore eventi di Windows, ma non in Microsoft Endpoint Manager o in Intune. È anche possibile usare il cmdlet `Get-MpThreat` per visualizzare le minacce gestite da Antivirus Microsoft Defender. Ecco un esempio:

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a>Ricevere notifiche tramite posta elettronica sui rilevamenti di applicazioni potenzialmente indesiderate

È possibile attivare le notifiche tramite posta elettronica per ricevere messaggi relativi al rilevamento di PUA.

Vedere l'articolo su come [risolvere i problemi relativi agli ID evento](troubleshoot-microsoft-defender-antivirus.md) per informazioni dettagliate sulla visualizzazione degli eventi di Antivirus Microsoft Defender. Gli eventi PUA vengono registrati con l'ID evento **1160**.

## <a name="view-pua-events-using-advanced-hunting"></a>Visualizzare gli eventi PUA con la rilevazione avanzata

Se si usa [Microsoft Defender per endpoint](microsoft-defender-endpoint.md), è possibile usare una query di rilevazione avanzata per visualizzare gli eventi PUA. Ecco una query di esempio:

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

Per altre informazioni sulla rilevazione avanzata, vedere [Rilevare in modo proattivo le minacce con la rilevazione avanzata](advanced-hunting-overview.md).

## <a name="exclude-files-from-pua-protection"></a>Escludere file dalla protezione PUA

A volte un file viene erroneamente bloccato dalla protezione PUA oppure per completare un'attività è necessaria una funzionalità di un'applicazione potenzialmente indesiderata. In questi casi, è possibile aggiungere un file a un elenco di esclusione.

Per altre informazioni, vedere [Configurare e convalidare le esclusioni in base all'estensione di file e al percorso della cartella](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Vedere anche

- [Protezione di nuova generazione](microsoft-defender-antivirus-in-windows-10.md)
- [Configurare la protezione comportamentale, euristica e in tempo reale](configure-protection-features-microsoft-defender-antivirus.md)