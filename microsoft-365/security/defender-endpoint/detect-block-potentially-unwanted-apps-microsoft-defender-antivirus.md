---
title: Bloccare le applicazioni potenzialmente indesiderate con Microsoft Defender Antivirus
description: Abilita la funzionalità antivirus delle applicazioni potenzialmente indesiderate (PUA) per bloccare software indesiderato come adware.
keywords: pua, abilitare, software indesiderato, app indesiderate, adware, barra degli strumenti del browser, rilevare, bloccare, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bee92dfa998596578c27bda579a86776bc77c07b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691485"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>Rilevare e bloccare applicazioni potenzialmente indesiderate

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> Le applicazioni potenzialmente indesiderate sono una categoria di software che può causare un'esecuzione lenta del computer, visualizzare annunci imprevisti o, nel peggiore dei casi, installare altro software che potrebbe essere imprevisto o indesiderato. Per impostazione predefinita in Windows 10 (versione 2004 e successive), Microsoft Defender Antivirus blocca le app considerate puA per i dispositivi Enterprise (E5).

Le applicazioni potenzialmente indesiderate non sono considerate virus, malware o altri tipi di minacce, ma possono eseguire azioni sugli endpoint che influiscono negativamente sulle prestazioni o sull'uso degli endpoint. _PuA_ può anche fare riferimento a un'applicazione con una reputazione scarsa, come valutato da Microsoft Defender for Endpoint, a causa di alcuni tipi di comportamento indesiderato.

Di seguito vengono descritti alcuni esempi:

- **Software pubblicitario** che visualizza annunci pubblicitari o promozioni, incluso il software che inserisce annunci pubblicitari nelle pagine Web.
- **Software di aggregazione** che offre di installare altro software non firmato digitalmente dalla stessa entità. Inoltre, il software che offre di installare altro software idoneo come PUA.
- **Software di evasione** che tenta attivamente di eludere il rilevamento da parte dei prodotti di sicurezza, incluso il software che si comporta in modo diverso in presenza di prodotti di sicurezza.

> [!TIP]
> Per altri esempi e una descrizione dei criteri che usiamo per etichettare le applicazioni per un'attenzione particolare dalle funzionalità di sicurezza, vedi Come Microsoft identifica malware e [applicazioni potenzialmente indesiderate.](/windows/security/threat-protection/intelligence/criteria)

Le applicazioni potenzialmente indesiderate possono aumentare il rischio che la rete sia infettata da malware effettivo, rendere più difficile identificare le infezioni da malware o sprecare risorse IT per pulirle. La protezione da accesso client è supportata in Windows 10, Windows Server 2019 e Windows Server 2016.

## <a name="microsoft-edge"></a>Microsoft Edge

Il [nuovo Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)basato su Chromium, blocca i download di applicazioni potenzialmente indesiderate e gli URL di risorse associati. Questa funzionalità viene fornita tramite [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Abilitare la protezione puA in Microsoft Edge basato su Chromium

Anche se la protezione delle applicazioni potenzialmente indesiderate in Microsoft Edge (basata su Chromium, versione 80.0.361.50) è disattivata per impostazione predefinita, può essere facilmente attivata dal browser.

1. Selezionare i puntini di sospensione e quindi scegliere **Impostazioni.**
2. Seleziona **Privacy, ricerca e servizi.**
3. Nella sezione **Sicurezza** attiva Blocca **app potenzialmente indesiderate.**

> [!TIP]
> Se si esegue Microsoft Edge (basato su Chromium), è possibile esplorare in modo sicuro la funzionalità di blocco degli URL della protezione puA testandolo in una delle pagine demo di [Microsoft Defender SmartScreen.](https://demo.smartscreen.msft.net/)

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>Blocco degli URL con Microsoft Defender SmartScreen

In Edge basato su Chromium con la protezione PUA attivata, Microsoft Defender SmartScreen ti protegge dagli URL associati alla PUA.

Gli amministratori della sicurezza [possono configurare](/DeployEdge/configure-microsoft-edge) il modo in cui Microsoft Edge e Microsoft Defender SmartScreen lavorano insieme per proteggere i gruppi di utenti dagli URL associati alle APPLICAZIONI. Sono disponibili diverse [impostazioni di Criteri di](/DeployEdge/microsoft-edge-policies#smartscreen-settings) gruppo in modo esplicito per Microsoft Defender SmartScreen, tra cui una per bloccare [l'accesso pubblico](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled). Inoltre, gli amministratori possono configurare [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) nel suo complesso, usando le impostazioni di Criteri di gruppo per attivare o disattivare Microsoft Defender SmartScreen.

Anche se Microsoft Defender for Endpoint ha un proprio elenco di blocco basato su un set di dati gestito da Microsoft, puoi personalizzare questo elenco in base alle tue informazioni sulle minacce. Se [crei e gestisci indicatori](/microsoft-365/security/defender-endpoint/manage-indicators) nel portale di Microsoft Defender per endpoint, Microsoft Defender SmartScreen rispetta le nuove impostazioni.

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender Antivirus

La funzionalità di protezione delle applicazioni potenzialmente indesiderate (PUA) in Microsoft Defender Antivirus può rilevare e bloccare le applicazioni potenzialmente indesiderate negli endpoint della rete.

> [!NOTE]
> Questa funzionalità è disponibile in Windows 10, Windows Server 2019 e Windows Server 2016.

Microsoft Defender Antivirus blocca i file PUA rilevati e qualsiasi tentativo di scaricarli, spostarli, eseguirli o installarli. I file PUA bloccati vengono quindi spostati in quarantena. Quando viene rilevato un file PUA in un endpoint, Microsoft Defender Antivirus invia una notifica all'utente[(](configure-notifications-microsoft-defender-antivirus.md)a meno che le notifiche non siano state disabilitate ) nello stesso formato di altri rilevamenti di minacce. La notifica è preceduta da per `PUA:` indicare il relativo contenuto.

La notifica viene visualizzata nel consueto elenco [di quarantena all'interno dell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Configurare la protezione dei criteri di protezione da accesso pubblico in Microsoft Defender Antivirus

È possibile abilitare la protezione dell'applicazione con [Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [Criteri di gruppo](/azure/active-directory-domain-services/manage-group-policy)o tramite i cmdlet [di PowerShell.](/powershell/module/defender/?preserve-view=true&view=win10-ps)

Puoi anche usare la protezione puA in modalità di controllo per rilevare le applicazioni potenzialmente indesiderate senza bloccarle. I rilevamenti vengono acquisiti nel registro eventi di Windows.

> [!TIP]
> Visita il sito Web demo di Microsoft Defender for Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) per verificare che la funzionalità funzioni e visualizzarla in azione.

La protezione delle applicazioni in modalità di controllo è utile se l'azienda esegue un controllo di conformità della sicurezza software interno e si desidera evitare falsi positivi.

#### <a name="use-intune-to-configure-pua-protection"></a>Usare Intune per configurare la protezione delle app di accesso client

Per [altri dettagli, vedi](/intune/device-restrictions-configure) Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune e Microsoft Defender Antivirus per [Windows 10 in Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>Utilizzare Configuration Manager per configurare la protezione dell'applicazione per accesso client

La protezione puA è abilitata per impostazione predefinita in Microsoft Endpoint Manager (Current Branch).

Per informazioni dettagliate sulla configurazione di Microsoft Endpoint Manager (Current Branch), vedere How [to create and deploy antimalware policies: Scheduled scans settings.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)

Per System Center 2012 Configuration Manager, vedere Come distribuire criteri di protezione delle applicazioni potenzialmente indesiderate per [Endpoint Protection in Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)

> [!NOTE]
> Gli eventi puA bloccati da Microsoft Defender Antivirus vengono segnalati nel Visualizzatore eventi di Windows e non in Microsoft Endpoint Configuration Manager.

#### <a name="use-group-policy-to-configure-pua-protection"></a>Utilizzare Criteri di gruppo per configurare la protezione dell'applicazione web

1. Scaricare e installare [modelli amministrativi (admx) per Windows 10 Ottobre 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. Nel computer di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

3. Selezionare l'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

4. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**

5. Espandere l'albero **fino a Componenti di Windows** Microsoft Defender  >  **Antivirus**.

6. Fare doppio clic **su Configura rilevamento per applicazioni potenzialmente indesiderate.**

7. Selezionare **Abilitato** per abilitare la protezione puA.

8. In **Opzioni** seleziona **Blocca per** bloccare le  applicazioni potenzialmente indesiderate oppure seleziona Modalità di controllo per verificare il funzionamento dell'impostazione nell'ambiente. Selezionare **OK**.

9. Distribuisci l'oggetto Criteri di gruppo come di solito.

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>Utilizzare i cmdlet di PowerShell per configurare la protezione delle applicazioni di accesso utente

##### <a name="to-enable-pua-protection"></a>Per abilitare la protezione da accesso alla posta elettronica

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

L'impostazione del valore per questo cmdlet `Enabled` attiva la funzionalità se è stata disabilitata.

##### <a name="to-set-pua-protection-to-audit-mode"></a>Per impostare la protezione delle voci di controllo sulla modalità di controllo

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

`AuditMode`L'impostazione rileva i messaggi di accesso popup senza bloccarli.

##### <a name="to-disable-pua-protection"></a>Per disabilitare la protezione dei criteri di protezione dall'accesso di posta elettronica

È consigliabile mantenere attivata la protezione puA. È tuttavia possibile disattivarlo utilizzando il cmdlet seguente:

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

Se si imposta il valore per questo cmdlet `Disabled` in modo che la funzionalità sia disattivata, se è stata abilitata.

Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/index)

## <a name="view-pua-events"></a>Visualizzare gli eventi puA

Gli eventi puA vengono segnalati nel Visualizzatore eventi di Windows, ma non in Microsoft Endpoint Manager o intune. È inoltre possibile utilizzare il `Get-MpThreat` cmdlet per visualizzare le minacce gestite da Microsoft Defender Antivirus. Di seguito viene riportato un esempio:

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

È possibile attivare le notifiche di posta elettronica per ricevere posta sui rilevamenti di messaggi di posta elettronica.

Vedi [Risolvere i problemi relativi agli ID](troubleshoot-microsoft-defender-antivirus.md) evento per informazioni dettagliate sulla visualizzazione degli eventi di Microsoft Defender Antivirus. Gli eventi puA vengono registrati con ID evento **1160.**

## <a name="excluding-files"></a>Esclusione di file

A volte un file viene erroneamente bloccato dalla protezione PUA oppure è necessaria una funzionalità di un'applicazione per completare un'attività. In questi casi, è possibile aggiungere un file a un elenco di esclusione.

Per ulteriori informazioni, vedere [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

## <a name="see-also"></a>Vedere anche

- [Protezione di nuova generazione](microsoft-defender-antivirus-in-windows-10.md)
- [Configurare la protezione comportamentale, euristica e in tempo reale](configure-protection-features-microsoft-defender-antivirus.md)