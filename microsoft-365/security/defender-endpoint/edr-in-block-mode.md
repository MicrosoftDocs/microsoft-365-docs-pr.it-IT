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
ms.date: 07/13/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 1915a57becb1cba14605f4512ff123c1bca846bb
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415600"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Rilevamento e risposta degli endpoint (EDR) in modalità blocco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>Che cos'EDR in modalità blocco?

[Il rilevamento e la](overview-endpoint-detection-response.md) risposta degli endpoint (EDR) in modalità blocco offre una maggiore protezione da artefatti dannosi quando Antivirus Microsoft Defender non è il prodotto antivirus principale ed è in esecuzione in modalità passiva. EDR in modalità blocco consente di correggere gli artefatti dannosi rilevati tramite EDR. Tali artefatti potrebbero essere stati persi dal prodotto antivirus principale non Microsoft. EDR in modalità blocco funziona dietro le quinte per correggere gli artefatti dannosi rilevati, dopo la violazione, in un dispositivo. 

> [!IMPORTANT]
> EDR in modalità blocco non fornisce tutta la protezione disponibile quando Antivirus Microsoft Defender è abilitata la protezione in tempo reale. Tutte le funzionalità che dipendono Antivirus Microsoft Defender essere la soluzione antivirus attiva non funzioneranno, inclusi i seguenti esempi chiave: 
> 
> - La protezione in tempo reale, inclusa la scansione all'accesso, non è disponibile quando Antivirus Microsoft Defender è in modalità passiva. Per ulteriori informazioni sulle impostazioni dei criteri di protezione in tempo reale, vedere **[Enable and configure Antivirus Microsoft Defender always-on protection](configure-real-time-protection-microsoft-defender-antivirus.md)**.
> - Funzionalità come **[la protezione di rete e](network-protection.md)** le regole di **[riduzione](attack-surface-reduction.md)** della superficie di attacco sono disponibili solo quando Antivirus Microsoft Defender è in esecuzione in modalità attiva. 
> 
> Si prevede che la soluzione antivirus non Microsoft fornisce queste funzionalità. 

EDR in modalità blocco è integrato con [l'& gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md). Il team di sicurezza dell'organizzazione riceverà un consiglio di sicurezza per attivare EDR in modalità blocco se non è già abilitato. [](tvm-security-recommendation.md) 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="è consigliabile attivare EDR in modalità blocco":::

> [!TIP]
> Per ottenere la protezione migliore, assicurati di distribuire **[Microsoft Defender for Endpoint baselines.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>Cosa succede quando viene rilevato un elemento?

Quando EDR in modalità blocco è attivata e viene rilevato un artefatto dannoso, Microsoft Defender for Endpoint blocca e correggere tale artefatto. Il team delle operazioni di sicurezza visualizza lo stato di rilevamento **Bloccato** o **Non** consentito nel centro [notifiche,](respond-machine-alerts.md#check-activity-details-in-action-center)elencato come azioni completate.

L'immagine seguente mostra un'istanza di software indesiderato rilevato e bloccato tramite EDR in modalità blocco:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR in modalità blocco rilevato qualcosa":::


## <a name="enable-edr-in-block-mode"></a>Abilita EDR in modalità blocco

> [!TIP]
> Assicurati che i [requisiti siano](#requirements-for-edr-in-block-mode) soddisfatti prima di attivare EDR in modalità blocco.

1. Accedere al portale Microsoft 365 Defender ( [https://security.microsoft.com/](https://security.microsoft.com/) ) ed eseguire l'accesso. 

2. Scegliere **Impostazioni**  >  **Endpoint**  >  **generali**  >  **Funzionalità avanzate**.

3. Scorrere verso il basso e quindi urn su **Abilita EDR in modalità blocco.**

> [!NOTE]
> EDR in modalità blocco può essere attivato solo nel portale di Microsoft 365 Defender ( ) o nel precedente [https://security.microsoft.com](https://security.microsoft.com) Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). Non è possibile utilizzare chiavi del Registro di sistema, Microsoft Intune o Criteri di gruppo per abilitare o disabilitare EDR in modalità blocco.

## <a name="requirements-for-edr-in-block-mode"></a>Requisiti per EDR in modalità blocco

| Requisito  | Dettagli  |
|---------|---------|
| Autorizzazioni | È necessario disporre del ruolo Amministratore globale o Amministratore sicurezza assegnato in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Per ulteriori informazioni, vedere [Autorizzazioni di base.](basic-permissions.md) |
| Sistema operativo     | I dispositivi devono eseguire una delle seguenti versioni di Windows: <br/>- Windows 10 (tutte le versioni) <br/>- Windows Server, versione 1803 o successiva <br/>- Windows Server 2019 <br/>- Windows Server 2016 (solo quando Antivirus Microsoft Defender in modalità attiva)     |
| Microsoft Defender per endpoint     | I dispositivi devono essere onboarded in Defender for Endpoint. Vedi [Requisiti minimi per Microsoft Defender per Endpoint.](minimum-requirements.md)       |
| Antivirus Microsoft Defender  | I dispositivi devono avere Antivirus Microsoft Defender e in esecuzione in modalità attiva o passiva. [Verificare Antivirus Microsoft Defender sia attiva o passiva.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
| Protezione fornita dal cloud | Antivirus Microsoft Defender deve essere configurata in modo che sia abilitata la [protezione recapitata nel cloud.](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Antivirus Microsoft Defender piattaforma | I dispositivi devono essere aggiornati. Per confermare, utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) come amministratore. Nella riga **AMProductVersion** dovrebbe essere visualizzato **4.18.2001.10** o versione successiva. <p> Per ulteriori informazioni, vedere [Gestire gli aggiornamenti in Antivirus Microsoft Defender e applicare i valori di riferimento](manage-updates-baselines-microsoft-defender-antivirus.md). |
| Antivirus Microsoft Defender motore | I dispositivi devono essere aggiornati. Per confermare, utilizzando PowerShell, eseguire il cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) come amministratore. Nella riga **AMEngineVersion** dovrebbe essere visualizzato **1.1.16700.2** o versione successiva. <p> Per ulteriori informazioni, vedere [Gestire gli aggiornamenti in Antivirus Microsoft Defender e applicare i valori di riferimento](manage-updates-baselines-microsoft-defender-antivirus.md). |

> [!IMPORTANT]
> Per ottenere il miglior valore di protezione, verificare che la soluzione antivirus sia configurata per ricevere aggiornamenti regolari e funzionalità essenziali e che le [esclusioni siano configurate](configure-exclusions-microsoft-defender-antivirus.md). EDR in modalità blocco rispetta le esclusioni definite per Antivirus Microsoft Defender, [](manage-indicators.md) ma non gli indicatori definiti per Microsoft Defender for Endpoint.

## <a name="frequently-asked-questions"></a>Domande frequenti 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-if-i-have-microsoft-defender-antivirus-running-on-devices"></a>È necessario attivare la EDR in modalità blocco se si Antivirus Microsoft Defender nei dispositivi?

Lo scopo principale di EDR in modalità blocco è quello di correggere i rilevamenti post-violazione che sono stati persi da un prodotto antivirus non Microsoft. Tuttavia, ti consigliamo di EDR in modalità blocco attivata, sia che Antivirus Microsoft Defender sia in esecuzione in modalità passiva o in modalità attiva. 

- Quando Antivirus Microsoft Defender è in modalità passiva, EDR in modalità blocco fornisce un altro livello di difesa insieme a Microsoft Defender for Endpoint. 
- Quando Antivirus Microsoft Defender è in modalità attiva, EDR in modalità blocco non fornisce un'analisi aggiuntiva, ma consente a Defender for Endpoint di eseguire azioni automatiche sui rilevamenti di EDR post-violazione.

### <a name="will-edr-in-block-mode-affect-a-users-antivirus-protection"></a>La EDR in modalità blocco influisce sulla protezione antivirus di un utente? 

EDR in modalità blocco non influisce sulla protezione antivirus di terze parti in esecuzione sui dispositivi degli utenti. EDR in modalità blocco funziona se la soluzione antivirus principale perde qualcosa o se è presente un rilevamento post-violazione. EDR in modalità blocco funziona come Antivirus Microsoft Defender in modalità passiva, con la differenza che EDR in modalità blocco blocca anche gli artefatti o i comportamenti dannosi rilevati.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Perché è necessario mantenere le Antivirus Microsoft Defender aggiornate? 

Poiché Antivirus Microsoft Defender rilevare e correggere gli elementi dannosi, è importante mantenerlo aggiornato. Per EDR in modalità blocco per essere efficace, usa i modelli di apprendimento dei dispositivi più recenti, i rilevamenti comportamentali e l'euristica. Lo [stack di funzionalità](microsoft-defender-endpoint.md) defender per endpoint funziona in modo integrato. Per ottenere un valore di protezione ottimale, è consigliabile Antivirus Microsoft Defender aggiornato. Vedere [Manage Antivirus Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md). 

### <a name="why-do-we-need-cloud-protection-maps-on"></a>Perché è necessaria la protezione cloud (MAPS) su? 

La protezione cloud è necessaria per attivare la funzionalità nel dispositivo. La protezione cloud consente a [Defender for Endpoint](microsoft-defender-endpoint.md) di offrire la protezione più recente e massima in base all'ampiezza e alla profondità dell'intelligence per la sicurezza, insieme ai modelli di apprendimento del comportamento e dei dispositivi.

### <a name="what-is-the-difference-between-active-and-passive-mode"></a>Qual è la differenza tra modalità attiva e passiva?

Per gli endpoint che eseguono Windows 10, Windows Server, versione 1803 o successiva o Windows Server 2019, quando Antivirus Microsoft Defender è in modalità attiva, viene utilizzato come antivirus principale nel dispositivo. Quando viene eseguito in modalità passiva, Antivirus Microsoft Defender non è il prodotto antivirus principale. In questo caso, le minacce non vengono corretti da Antivirus Microsoft Defender in tempo reale.

> [!NOTE]
> Antivirus Microsoft Defender può essere eseguito in modalità passiva solo quando il dispositivo viene onboarded in Microsoft Defender per Endpoint.

Per ulteriori informazioni, vedere [Antivirus Microsoft Defender compatibilità.](microsoft-defender-antivirus-compatibility.md)

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Come posso verificare se Antivirus Microsoft Defender attiva o passiva?

Per verificare se Antivirus Microsoft Defender è in esecuzione in modalità attiva o passiva, è possibile utilizzare prompt dei comandi o PowerShell in un dispositivo che esegue Windows.

|Metodo  |Procedura  |
|---------|---------|
| PowerShell     | 1. Selezionare il menu Start, iniziare a digitare e quindi aprire Windows PowerShell `PowerShell` nei risultati. <p>2. Digitare `Get-MpComputerStatus` . <p>3. Nell'elenco dei risultati, nella riga **AMRunningMode** cercare uno dei valori seguenti: <br/>- `Normal` <br/>- `Passive Mode` <p>Per ulteriori informazioni, vedere [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)        |
|Prompt dei comandi     | 1. Selezionare il menu Start, iniziare a digitare e quindi `Command Prompt` aprire Windows prompt dei comandi nei risultati. <p>2. Digitare `sc query windefend` . <p>3. Nell'elenco dei risultati, nella riga **STATE,** verificare che il servizio sia in esecuzione.         |

### <a name="how-do-i-confirm-that-edr-in-block-mode-is-turned-on-with-microsoft-defender-antivirus-in-passive-mode"></a>Come verificare che l'EDR in modalità blocco sia attivato con Antivirus Microsoft Defender in modalità passiva?

È possibile usare PowerShell per verificare che l'EDR in modalità blocco sia attivata con Antivirus Microsoft Defender in esecuzione in modalità passiva.

1. Selezionare il menu Start, iniziare a digitare e quindi `PowerShell` aprire Windows PowerShell nei risultati. 

2. Tipo `Get-MPComputerStatus | select AMRunningMode`.

3. Verificare che il risultato, `EDR Block Mode` , sia visualizzato.

   > [!TIP]
   > Se Antivirus Microsoft Defender è in modalità attiva, verrà visualizzato `Normal` invece `EDR Block Mode` di . Per ulteriori informazioni, vedere [Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus)

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>La EDR in modalità blocco è supportata in Windows Server 2016?

Se Antivirus Microsoft Defender è in esecuzione in modalità attiva o passiva, EDR in modalità blocco è supportato nelle seguenti versioni di Windows:

- Windows 10 (tutte le versioni)
- Windows Server, versione 1803 o successiva 
- Windows Server 2019 

#### <a name="what-about-windows-server-2016"></a>Che dire di Windows Server 2016? 

Se Windows Server 2016 è Antivirus Microsoft Defender in esecuzione in modalità attiva e l'endpoint viene onboarded in Defender per Endpoint, la EDR in modalità blocco è tecnicamente supportata. Tuttavia, EDR in modalità blocco deve essere una protezione aggiuntiva quando Antivirus Microsoft Defender non è la soluzione antivirus principale in un endpoint. In questi casi, Antivirus Microsoft Defender in modalità passiva. 

Attualmente, l'Antivirus Microsoft Defender in modalità passiva non è supportata in Windows Server 2016. Per ulteriori informazioni, [vedere Antivirus Microsoft Defender antivirus/antimalware non Microsoft](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions).

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Quanto tempo è necessario per EDR in modalità blocco per essere disabilitata?

Se si sceglie di disabilitare EDR in modalità blocco, il sistema può richiedere fino a 30 minuti per disabilitare questa funzionalità.

## <a name="see-also"></a>Vedere anche

- [Blog Community tech: Introduzione EDR in modalità blocco: Arrestare gli attacchi nelle proprie tracce](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Blocco e contenimento comportamentale](behavioral-blocking-containment.md)

