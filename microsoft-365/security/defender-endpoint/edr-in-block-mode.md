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
ms.date: 05/08/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 86bb27005365b625ee07feaa067c0ac488c3bb4b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302041"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Rilevamento e risposta degli endpoint (EDR) in modalità blocco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Che cos'EDR in modalità blocco?

[Il rilevamento e la risposta](overview-endpoint-detection-response.md) degli endpoint (EDR) in modalità blocco forniscono protezione da artefatti dannosi, anche quando Antivirus Microsoft Defender in esecuzione in modalità passiva. Quando è attivata, EDR in modalità blocco blocca artefatti o comportamenti dannosi rilevati in un dispositivo. EDR in modalità blocco funziona dietro le quinte per correggere gli artefatti dannosi rilevati dopo la violazione. 

EDR in modalità blocco è integrato anche con l'& gestione delle vulnerabilità [.](next-gen-threat-and-vuln-mgt.md) Il team di sicurezza dell'organizzazione riceverà un consiglio di sicurezza per attivare EDR in modalità blocco se non è già abilitato. [](tvm-security-recommendation.md) 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="è consigliabile attivare EDR in modalità blocco":::

> [!NOTE]
> Per ottenere la protezione migliore, assicurati di distribuire **[Microsoft Defender for Endpoint baselines.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Cosa succede quando viene rilevato un elemento?

Quando EDR in modalità blocco è attivata e viene rilevato un artefatto dannoso, Microsoft Defender for Endpoint blocca e correggere tale artefatto. Il team delle operazioni di sicurezza visualizza lo stato di rilevamento **Bloccato** o **Non** consentito nel centro [notifiche,](respond-machine-alerts.md#check-activity-details-in-action-center)elencato come azioni completate.

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
|Autorizzazioni |Ruolo amministratore globale o amministratore della sicurezza assegnato in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Vedere [Autorizzazioni di base.](basic-permissions.md) |
|Sistema operativo     |Una delle versioni seguenti: <br/>- Windows 10 (tutte le versioni) <br/>- Windows Server, versione 1803 o successiva <br/>- Windows Server 2019 <br/>- Windows Server 2016 (solo quando Antivirus Microsoft Defender in modalità attiva)     |
|Windows Registrazione E5     |Windows E5 è incluso nelle sottoscrizioni seguenti: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 insieme all'offerta Identity & Threat Protection <br/><br/>Vedere [Componenti](/microsoft-365/enterprise/microsoft-365-overview#components) [e funzionalità e funzionalità per ogni piano.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Antivirus Microsoft Defender  |Antivirus Microsoft Defender deve essere installato ed eseguito in modalità attiva o passiva. È possibile utilizzare Antivirus Microsoft Defender una soluzione antivirus non Microsoft. [Verificare Antivirus Microsoft Defender sia attiva o passiva.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Protezione fornita dal cloud |Assicurarsi che Antivirus Microsoft Defender sia configurata in modo che la protezione [recapitata nel cloud sia abilitata.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Antivirus Microsoft Defender client antimalware |Assicurati che il client sia aggiornato. Utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) come amministratore. Nella riga **AMProductVersion** dovrebbe essere visualizzato **4.18.2001.10** o versione successiva. |
|Antivirus Microsoft Defender motore |Assicurati che il motore sia aggiornato. Utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) come amministratore. Nella riga **AMEngineVersion** dovrebbe essere visualizzato **1.1.16700.2** o versione successiva. |

> [!IMPORTANT]
> Per ottenere il miglior valore di protezione, verificare che la soluzione antivirus sia configurata per ricevere aggiornamenti regolari e funzionalità essenziali e che le [esclusioni siano configurate](configure-exclusions-microsoft-defender-antivirus.md). EDR in modalità blocco rispetta le esclusioni definite per Antivirus Microsoft Defender.

## <a name="frequently-asked-questions"></a>Domande frequenti 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>È necessario attivare la EDR in modalità blocco anche se Antivirus Microsoft Defender nei dispositivi?

Ti consigliamo di EDR in modalità blocco attiva, sia che Antivirus Microsoft Defender sia in esecuzione in modalità passiva o in modalità attiva. EDR in modalità blocco offre un altro livello di difesa con Microsoft Defender for Endpoint. Consente a Defender per Endpoint di eseguire azioni in base ai rilevamenti di EDR post-violazione. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>La EDR in modalità blocco avrà un impatto sulla protezione antivirus di un utente? 

EDR in modalità blocco non influisce sulla protezione antivirus di terze parti in esecuzione sui dispositivi degli utenti. EDR in modalità blocco funziona se la soluzione antivirus principale perde qualcosa o se è presente un rilevamento post-violazione. EDR in modalità blocco funziona esattamente come Antivirus Microsoft Defender in modalità passiva, ma blocca e corretti anche artefatti o comportamenti dannosi rilevati.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Perché è necessario mantenere le Antivirus Microsoft Defender aggiornate? 

Poiché Antivirus Microsoft Defender rilevare e correggere gli elementi dannosi, è importante mantenerlo aggiornato. Per EDR in modalità blocco per essere efficace, usa i modelli di apprendimento dei dispositivi più recenti, i rilevamenti comportamentali e l'euristica. Lo [stack di funzionalità](microsoft-defender-endpoint.md) defender per endpoint funziona in modo integrato. Per ottenere un valore di protezione ottimale, è consigliabile Antivirus Microsoft Defender aggiornato. Vedere [Manage Antivirus Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md). 

### <a name="why-do-we-need-cloud-protection-on"></a>Perché è necessaria la protezione cloud? 

La protezione cloud è necessaria per attivare la funzionalità nel dispositivo. La protezione cloud consente a [Defender for Endpoint](microsoft-defender-endpoint.md) di offrire la protezione più recente e massima in base all'ampiezza e alla profondità dell'intelligence per la sicurezza, insieme ai modelli di apprendimento del comportamento e dei dispositivi.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Come si imposta Antivirus Microsoft Defender modalità passiva?

A seconda dei sistemi operativi, quando i dispositivi che eseguono una soluzione antivirus/antimalware non Microsoft vengono onboarded in Defender for Endpoint, Antivirus Microsoft Defender può passare automaticamente in modalità passiva. Per altre informazioni, vedi In che modo [Antivirus Microsoft Defender funzionalità di Defender for Endpoint.](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Come posso verificare se Antivirus Microsoft Defender attiva o passiva?

Per verificare se Antivirus Microsoft Defender è in esecuzione in modalità attiva o passiva, è possibile utilizzare prompt dei comandi o PowerShell in un dispositivo che esegue Windows.


|Metodo  |Procedura  |
|---------|---------|
| PowerShell     | 1. Seleziona il menu Start, inizia a digitare `PowerShell` e quindi apri Windows PowerShell nei risultati. <p>2. Digitare `Get-MpComputerStatus` . <p>3. Nell'elenco dei risultati, nella riga **AMRunningMode** cercare uno dei valori seguenti: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Per ulteriori informazioni, vedere [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)        |
|Prompt dei comandi     | 1. Selezionare il menu Start, iniziare a digitare e quindi `Command Prompt` aprire Windows prompt dei comandi nei risultati. <p>2. Digitare `sc query windefend` . <p>3. Nell'elenco dei risultati, nella riga **STATE,** verificare che il servizio sia in esecuzione.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Quanto tempo è necessario per EDR in modalità blocco per essere disabilitata?

Se hai scelto di disabilitare EDR in modalità blocco, il sistema può richiedere fino a 30 minuti per disabilitare questa funzionalità.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>La EDR in modalità blocco è supportata in Windows Server 2016?

Se Antivirus Microsoft Defender è in esecuzione in modalità attiva o passiva, EDR in modalità blocco è supportato nelle seguenti versioni di Windows:

- Windows 10 (tutte le versioni)
- Windows Server, versione 1803 o successiva 
- Windows Server 2019 

Se Windows Server 2016 è Antivirus Microsoft Defender in esecuzione in modalità attiva e l'endpoint viene onboarded in Defender per Endpoint, la EDR in modalità blocco è tecnicamente supportata. Tuttavia, EDR in modalità blocco deve essere una protezione aggiuntiva quando Antivirus Microsoft Defender non è la soluzione antivirus principale in un endpoint. In questi casi, Antivirus Microsoft Defender in modalità passiva. Attualmente, l'Antivirus Microsoft Defender in modalità passiva non è supportata in Windows Server 2016. Per ulteriori informazioni, [vedere Antivirus Microsoft Defender antivirus/antimalware non Microsoft](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).

## <a name="see-also"></a>Vedere anche

- [Blog Community tech: Introduzione EDR in modalità blocco: Arrestare gli attacchi nelle proprie tracce](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Blocco e contenimento comportamentale](behavioral-blocking-containment.md)

