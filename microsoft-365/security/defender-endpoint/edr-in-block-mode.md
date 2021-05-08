---
title: Rilevamento e risposta degli endpoint in modalità blocco
description: Informazioni sul rilevamento e la risposta degli endpoint in modalità blocco
keywords: Microsoft Defender for Endpoint, mde, EDR in modalità blocco, blocco in modalità passiva
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 05/05/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: b0fe1da56c34cd0a79e1a41dba2fcb7a79c5a9f6
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259572"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Rilevamento e risposta degli endpoint (EDR) in modalità blocco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Che cos'EDR in modalità blocco?

[Il rilevamento e la risposta](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) degli endpoint (EDR) in modalità blocco forniscono protezione da artefatti dannosi, anche quando Antivirus Microsoft Defender in esecuzione in modalità passiva. Quando è attivata, EDR in modalità blocco blocca artefatti o comportamenti dannosi rilevati in un dispositivo. EDR in modalità blocco funziona dietro le quinte per correggere gli artefatti dannosi rilevati dopo la violazione. 

EDR in modalità blocco è integrato anche con l'& gestione delle vulnerabilità [.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Il team di sicurezza dell'organizzazione riceverà un consiglio di sicurezza per attivare EDR in modalità blocco se non è già abilitato. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="è consigliabile attivare EDR in modalità blocco":::

> [!NOTE]
> Per ottenere la protezione migliore, assicurati di distribuire **[Microsoft Defender for Endpoint baselines.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Cosa succede quando viene rilevato un elemento?

Quando EDR in modalità blocco è attivata e viene rilevato un artefatto dannoso, Microsoft Defender for Endpoint blocca e correggere tale artefatto. Lo stato di rilevamento verrà visualizzato come **Bloccato** o **Non** consentito come azioni completate nel [centro notifiche.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)

L'immagine seguente mostra un'istanza di software indesiderato rilevato e bloccato tramite EDR in modalità blocco:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR in modalità blocco rilevato qualcosa":::


## <a name="enable-edr-in-block-mode"></a>Abilita EDR in modalità blocco

> [!IMPORTANT]
> Assicurati che i [requisiti siano](#requirements-for-edr-in-block-mode) soddisfatti prima di attivare EDR in modalità blocco.

1. Vai al Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e accedi. 

2. Scegliere **Impostazioni**  >  **funzionalità avanzate.**

3. Attivare EDR **in modalità blocco.**

> [!NOTE]
> EDR in modalità blocco può essere attivato solo nella Microsoft Defender Security Center. Non è possibile usare chiavi del Registro di sistema, Intune o criteri di gruppo per abilitare o disabilitare EDR in modalità blocco.

## <a name="requirements-for-edr-in-block-mode"></a>Requisiti per EDR in modalità blocco

|Requisito  |Dettagli  |
|---------|---------|
|Autorizzazioni |Ruolo amministratore globale o amministratore della sicurezza assegnato in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Vedere [Autorizzazioni di base.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions) |
|Sistema operativo     |Una delle versioni seguenti: <br/>- Windows 10 (tutte le versioni) <br/>- Windows Server, versione 1803 o successiva <br/>- Windows Server 2019  <p>**NOTA:** EDR in modalità blocco non è supportata in Windows Server 2016.       |
|Windows Registrazione E5     |Windows E5 è incluso nelle sottoscrizioni seguenti: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 insieme all'offerta Identity & Threat Protection <br/><br/>Vedere [Componenti](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) [e funzionalità e funzionalità per ogni piano.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Antivirus Microsoft Defender  |Antivirus Microsoft Defender deve essere installato ed eseguito in modalità attiva o passiva. È possibile utilizzare Antivirus Microsoft Defender una soluzione antivirus non Microsoft. [Verificare Antivirus Microsoft Defender sia attiva o passiva.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Protezione fornita dal cloud |Assicurarsi che Antivirus Microsoft Defender sia configurata in modo che la protezione [recapitata nel cloud sia abilitata.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) |
|Antivirus Microsoft Defender client antimalware |Assicurati che il client sia aggiornato. Utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) come amministratore. Nella riga **AMProductVersion** dovrebbe essere visualizzato **4.18.2001.10** o versione successiva. |
|Antivirus Microsoft Defender motore |Assicurati che il motore sia aggiornato. Utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) come amministratore. Nella riga **AMEngineVersion** dovrebbe essere visualizzato **1.1.16700.2** o versione successiva. |

> [!IMPORTANT]
> Per ottenere il miglior valore di protezione, verificare che la soluzione antivirus sia configurata per ricevere aggiornamenti regolari e funzionalità essenziali e che le [esclusioni siano configurate](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus). EDR in modalità blocco rispetta le esclusioni definite per Antivirus Microsoft Defender.

## <a name="frequently-asked-questions"></a>Domande frequenti 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>È necessario attivare la EDR in modalità blocco anche se Antivirus Microsoft Defender nei dispositivi?

Ti consigliamo di EDR in modalità blocco attiva, sia che Antivirus Microsoft Defender sia in esecuzione in modalità passiva o in modalità attiva. EDR in modalità blocco offre un altro livello di difesa con Microsoft Defender for Endpoint. Consente a Defender per Endpoint di eseguire azioni in base ai rilevamenti di EDR post-violazione. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>La EDR in modalità blocco avrà un impatto sulla protezione antivirus di un utente? 

EDR in modalità blocco non influisce sulla protezione antivirus di terze parti in esecuzione sui dispositivi degli utenti. EDR in modalità blocco funziona se la soluzione antivirus principale perde qualcosa o se è presente un rilevamento post-violazione. EDR in modalità blocco funziona come Antivirus Microsoft Defender in modalità [passiva,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)ma blocca e correda anche artefatti o comportamenti dannosi rilevati. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Perché è necessario mantenere le Antivirus Microsoft Defender aggiornate? 

Poiché Antivirus Microsoft Defender rilevare e correggere gli elementi dannosi, è importante mantenerlo aggiornato. Per EDR in modalità blocco per essere efficace, usa i modelli di apprendimento dei dispositivi più recenti, i rilevamenti comportamentali e l'euristica. Lo [stack di funzionalità](https://docs.microsoft.com/windows/security/threat-protection) defender per endpoint funziona in modo integrato. Per ottenere un valore di protezione ottimale, è consigliabile Antivirus Microsoft Defender aggiornato.  

### <a name="why-do-we-need-cloud-protection-on"></a>Perché è necessaria la protezione cloud? 

La protezione cloud è necessaria per attivare la funzionalità nel dispositivo. La protezione cloud consente a [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) di offrire la protezione più recente e massima in base all'ampiezza e alla profondità dell'intelligence per la sicurezza, insieme ai modelli di apprendimento del comportamento e dei dispositivi.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Come si imposta Antivirus Microsoft Defender modalità passiva?

Vedi [Abilitare Antivirus Microsoft Defender e verificare che sia in modalità passiva.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Come posso verificare se Antivirus Microsoft Defender attiva o passiva?

Per verificare se Antivirus Microsoft Defender è in esecuzione in modalità attiva o passiva, è possibile utilizzare prompt dei comandi o PowerShell in un dispositivo che esegue Windows.

#### <a name="use-powershell"></a>Usare PowerShell.

1. Seleziona il menu Start, inizia a digitare `PowerShell` e quindi apri Windows PowerShell nei risultati.

2. Digitare `Get-MpComputerStatus`.

3. Nell'elenco dei risultati, nella **riga AMRunningMode** cercare uno dei valori seguenti:
   - `Normal` - Servizio Defender in esecuzione normalmente. Non sono abilitate modalità speciali.
   - `Passive Mode`- Se l'organizzazione usa Microsoft Defender for Endpoint insieme a una soluzione antivirus/antimalware non Microsoft, Antivirus Microsoft Defender automaticamente passa alla modalità passiva. La protezione e le minacce in tempo reale non vengono corretti da Antivirus Microsoft Defender.
   - `SxS Passive Mode`- Simile alla modalità passiva, ma con la possibilità di attivare un'analisi periodica limitata.
   
Per ulteriori informazioni, vedere [Get-MpComputerStatus.](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus)

#### <a name="use-command-prompt"></a>Utilizzare il prompt dei comandi

1. Seleziona il menu Start, inizia a digitare `Command Prompt` e quindi apri Windows prompt dei comandi nei risultati.

2. Digitare `sc query windefend`.

3. Nella riga **STATE** dell'elenco dei risultati verificare che il servizio sia in esecuzione.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Quanto tempo è necessario per EDR in modalità blocco per essere disabilitata?

Se hai scelto di disabilitare EDR in modalità blocco, il sistema può richiedere fino a 30 minuti per disabilitare questa funzionalità.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>La EDR in modalità blocco è supportata in Windows Server 2016?

No. EDR in modalità blocco è supportato nelle seguenti versioni di Windows:

- Windows 10 (tutte le versioni)
- Windows Server, versione 1803 o successiva 
- Windows Server 2019 

## <a name="see-also"></a>Vedere anche

- [Blog Community tech: Introduzione EDR in modalità blocco: Arrestare gli attacchi nelle proprie tracce](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Blocco e contenimento comportamentale](behavioral-blocking-containment.md)
- [Insieme è meglio: Microsoft Defender Antivirus e Microsoft Defender per Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

