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
ms.date: 05/06/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 78201fd20d689a6774eb5395aa787a2b15147972
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274485"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Rilevamento e risposta degli endpoint (EDR) in modalità blocco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Che cos'è EDR in modalità blocco?

[Il rilevamento e la risposta degli](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) endpoint (EDR) in modalità blocco forniscono protezione da artefatti dannosi, anche quando Microsoft Defender Antivirus è in esecuzione in modalità passiva. Se attivato, EDR in modalità blocco blocca artefatti o comportamenti dannosi rilevati in un dispositivo. EDR in modalità blocco funziona dietro le quinte per correggere gli artefatti dannosi rilevati dopo la violazione. 

EdR in modalità blocco è integrato anche con [la gestione delle & delle vulnerabilità.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Il team di sicurezza dell'organizzazione riceverà un consiglio di sicurezza per attivare edR in modalità blocco se non è già abilitato. [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="consiglio di attivare EDR in modalità blocco":::

> [!NOTE]
> Per ottenere la protezione migliore, assicurati di distribuire **[Microsoft Defender for Endpoint baselines.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>Cosa succede quando viene rilevato un elemento?

Quando la funzione EDR in modalità blocco è attivata e viene rilevato un artefatto dannoso, Microsoft Defender for Endpoint blocca e correggere tale artefatto. Il team delle operazioni di sicurezza visualizza lo stato di rilevamento **Bloccato** o **Non** consentito nel centro [notifiche,](respond-machine-alerts.md#check-activity-details-in-action-center)elencato come azioni completate.

L'immagine seguente mostra un'istanza di software indesiderato rilevato e bloccato tramite EDR in modalità blocco:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR in modalità blocco rilevato qualcosa":::


## <a name="enable-edr-in-block-mode"></a>Abilitare EDR in modalità blocco

> [!IMPORTANT]
> Assicurati che i [requisiti siano](#requirements-for-edr-in-block-mode) soddisfatti prima di attivare EDR in modalità blocco.

1. Vai a Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e accedi. 

2. Scegliere **Impostazioni**  >  **Funzionalità avanzate**.

3. Attivare **EDR in modalità blocco.**

> [!NOTE]
> EdR in modalità blocco può essere attivato solo in Microsoft Defender Security Center. Non è possibile usare chiavi del Registro di sistema, Intune o criteri di gruppo per abilitare o disabilitare EDR in modalità blocco.

## <a name="requirements-for-edr-in-block-mode"></a>Requisiti per EDR in modalità blocco

|Requisito  |Dettagli  |
|---------|---------|
|Autorizzazioni |Ruolo amministratore globale o amministratore della sicurezza assegnato in [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) Vedere [Autorizzazioni di base.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions) |
|Sistema operativo     |Una delle versioni seguenti: <br/>- Windows 10 (tutte le versioni) <br/>- Windows Server, versione 1803 o successiva <br/>- Windows Server 2019 <br/>- Windows Server 2016 (solo quando Microsoft Defender Antivirus è in modalità attiva)     |
|Registrazione di Windows E5     |Windows E5 è incluso nelle sottoscrizioni seguenti: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 insieme all'offerta Identity & Threat Protection <br/><br/>Vedere [Componenti](/microsoft-365/enterprise/microsoft-365-overview#components) [e funzionalità e funzionalità per ogni piano.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Antivirus Microsoft Defender  |Microsoft Defender Antivirus deve essere installato ed eseguito in modalità attiva o passiva. Puoi usare Microsoft Defender Antivirus insieme a una soluzione antivirus non Microsoft. [Verificare che Microsoft Defender Antivirus sia in modalità attiva o passiva.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Protezione fornita dal cloud |Assicurati che Microsoft Defender Antivirus sia configurato in modo che la [protezione recapitata nel cloud sia abilitata.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Client antimalware Microsoft Defender Antivirus |Assicurati che il client sia aggiornato. Utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) come amministratore. Nella riga **AMProductVersion** dovrebbe essere visualizzato **4.18.2001.10** o versione successiva. |
|Motore di Microsoft Defender Antivirus |Assicurati che il motore sia aggiornato. Utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) come amministratore. Nella riga **AMEngineVersion** dovrebbe essere visualizzato **1.1.16700.2** o versione successiva. |

> [!IMPORTANT]
> Per ottenere il miglior valore di protezione, verificare che la soluzione antivirus sia configurata per ricevere aggiornamenti regolari e funzionalità essenziali e che le [esclusioni siano configurate](configure-exclusions-microsoft-defender-antivirus.md). EDR in modalità blocco rispetta le esclusioni definite per Microsoft Defender Antivirus.

## <a name="frequently-asked-questions"></a>Domande frequenti 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>È necessario attivare EDR in modalità blocco anche se Microsoft Defender Antivirus è in esecuzione nei dispositivi?

Ti consigliamo di mantenere attivo EDR in modalità blocco, indipendentemente dal fatto che Microsoft Defender Antivirus sia in esecuzione in modalità passiva o in modalità attiva. EDR in modalità blocco offre un altro livello di difesa con Microsoft Defender for Endpoint. Consente a Defender for Endpoint di eseguire azioni in base ai rilevamenti edR comportamentali post-violazione. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>EdR in modalità blocco avrà un impatto sulla protezione antivirus di un utente? 

EdR in modalità blocco non influisce sulla protezione antivirus di terze parti in esecuzione nei dispositivi degli utenti. EdR in modalità blocco funziona se la soluzione antivirus principale perde qualcosa o se è presente un rilevamento post-violazione. EDR in modalità blocco funziona come [Microsoft Defender Antivirus in](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)modalità passiva, tranne per il fatto che blocca e corretti anche artefatti o comportamenti dannosi rilevati. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Perché è necessario mantenere Microsoft Defender Antivirus aggiornato? 

Poiché Microsoft Defender Antivirus rileva e correggere gli elementi dannosi, è importante mantenerlo aggiornato. Per l'efficacia dell'edR in modalità blocco, usa i modelli di apprendimento dei dispositivi, i rilevamenti comportamentali e l'euristica più recenti. Lo [stack di funzionalità](microsoft-defender-endpoint.md) defender per endpoint funziona in modo integrato. Per ottenere un valore di protezione ottimale, è consigliabile mantenere Microsoft Defender Antivirus aggiornato. Vedi [Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>Perché è necessaria la protezione cloud? 

La protezione cloud è necessaria per attivare la funzionalità nel dispositivo. La protezione cloud consente a [Defender for Endpoint](microsoft-defender-endpoint.md) di offrire la protezione più recente e massima in base all'ampiezza e alla profondità dell'intelligence per la sicurezza, insieme ai modelli di apprendimento del comportamento e dei dispositivi.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Come si imposta Microsoft Defender Antivirus sulla modalità passiva?

A seconda dei sistemi operativi, quando i dispositivi che eseguono una soluzione antivirus/antimalware non Microsoft vengono onboarded in Defender for Endpoint, Microsoft Defender Antivirus può passare automaticamente in modalità passiva. Per altre informazioni, vedi [Antivirus e Microsoft Defender for Endpoint.](microsoft-defender-antivirus-compatibility.md#antivirus-and-microsoft-defender-for-endpoint) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Come posso verificare che Microsoft Defender Antivirus sia in modalità attiva o passiva?

Per verificare se Microsoft Defender Antivirus è in esecuzione in modalità attiva o passiva, puoi usare prompt dei comandi o PowerShell in un dispositivo che esegue Windows.


|Metodo  |Procedura  |
|---------|---------|
| PowerShell     | 1. Seleziona il menu Start, inizia a digitare e quindi apri Windows PowerShell `PowerShell` nei risultati. <p>2. Digitare `Get-MpComputerStatus` . <p>3. Nell'elenco dei risultati, nella riga **AMRunningMode** cercare uno dei valori seguenti: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Per ulteriori informazioni, vedere [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)        |
|Prompt dei comandi     | 1. Seleziona il menu Start, inizia a digitare e quindi apri prompt dei comandi `Command Prompt` di Windows nei risultati. <p>2. Digitare `sc query windefend` . <p>3. Nell'elenco dei risultati, nella riga **STATE,** verificare che il servizio sia in esecuzione.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Quanto tempo è necessario per la disattivazione di EDR in modalità blocco?

Se si è scelto di disabilitare EDR in modalità blocco, il sistema può richiedere fino a 30 minuti per disabilitare questa funzionalità.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>EdR in modalità blocco è supportato in Windows Server 2016?

Se Microsoft Defender Antivirus è in esecuzione in modalità attiva o passiva, EDR in modalità blocco è supportato nelle seguenti versioni di Windows:

- Windows 10 (tutte le versioni)
- Windows Server, versione 1803 o successiva 
- Windows Server 2019 

Se In Windows Server 2016 Microsoft Defender Antivirus è in esecuzione in modalità attiva e l'endpoint viene onboarded in Defender for Endpoint, edR in modalità blocco è supportato. Tuttavia, EDR in modalità blocco è progettato per essere una protezione aggiuntiva quando Microsoft Defender Antivirus non è la soluzione antivirus principale in un endpoint. 

## <a name="see-also"></a>Vedere anche

- [Blog della community tech: Introduzione a EDR in modalità blocco: Arresto degli attacchi nelle proprie tracce](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Blocco e contenimento comportamentale](behavioral-blocking-containment.md)
- [Insieme è meglio: Microsoft Defender Antivirus e Microsoft Defender per Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

