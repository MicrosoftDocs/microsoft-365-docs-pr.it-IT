---
title: Microsoft Defender Antivirus nell'app Sicurezza di Windows
description: Con Microsoft Defender Antivirus ora incluso nell'app Sicurezza di Windows, puoi esaminare, confrontare ed eseguire attività comuni.
keywords: wdav, antivirus, firewall, sicurezza, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 042bb67c223631ae1759b62a32c2f5713b4d62e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690360"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a>Microsoft Defender Antivirus nell'app Sicurezza di Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In Windows 10, versione 1703 e successive, l Windows Defender app fa parte della sicurezza di Windows.

Le impostazioni che in precedenza erano parte del client Windows Defender e delle impostazioni principali di Windows sono state combinate e spostate nella nuova app, che viene installata per impostazione predefinita come parte di Windows 10 versione 1703.

> [!IMPORTANT]
> La disabilitazione del servizio Centro sicurezza PC Windows non disabilita Microsoft Defender Antivirus [o Windows Defender Firewall.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) Questi vengono disabilitati automaticamente quando viene installato e mantenuto aggiornato un prodotto firewall o antivirus di terze parti.
>
> Se disabiliti il servizio Centro sicurezza PC Windows o configura le impostazioni di Criteri di gruppo associate per impedirne l'avvio o l'esecuzione, l'app Sicurezza di Windows potrebbe visualizzare informazioni non aggiornate o imprecise su eventuali prodotti antivirus o firewall installati nel dispositivo.
> Potrebbe anche impedire a Microsoft Defender Antivirus di abilitarsi se si dispone di un antivirus di terze parti obsoleto o se si disinstallano prodotti antivirus di terze parti che potrebbero essere stati installati in precedenza.
> In questo modo si riduce notevolmente la protezione del dispositivo e potrebbe causare un'infezione da malware.

Vedi [l'articolo Sicurezza di Windows](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) per altre informazioni sulle altre funzionalità di sicurezza di Windows che possono essere monitorate nell'app.

L'app Sicurezza di Windows è un'interfaccia client in Windows 10, versione 1703 e successive. Non è il portale Web di Microsoft Defender Security Center che viene usato per esaminare e gestire [Microsoft Defender for Endpoint.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a>Esaminare le impostazioni di protezione da virus e minacce nell'app Sicurezza di Windows

![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

1. Apri l'app Sicurezza di Windows facendo clic sull'icona scudo nella barra delle applicazioni o cercando **Defender** nel menu Start.

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).
   
Le sezioni seguenti descrivono come eseguire alcune delle attività più comuni durante la revisione o l'interazione con la protezione dalle minacce fornita da Microsoft Defender Antivirus nell'app Windows Security.

> [!NOTE]
> Se queste impostazioni vengono configurate e distribuite tramite Criteri di gruppo, le impostazioni descritte in questa sezione saranno disattivate e non saranno disponibili per l'utilizzo nei singoli endpoint. Le modifiche apportate tramite un oggetto Criteri di gruppo devono prima essere distribuite a singoli endpoint prima che l'impostazione venga aggiornata in Impostazioni di Windows. [L'argomento Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) descrive come configurare le impostazioni di sostituzione dei criteri locali.

## <a name="run-a-scan-with-the-windows-security-app"></a>Eseguire un'analisi con l'app Sicurezza di Windows

1. Apri l'app Sicurezza di Windows cercando Sicurezza nel menu Start **e** quindi selezionando Sicurezza **di Windows.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).

3. Selezionare **Analisi rapida**. In caso contrario, per eseguire un'analisi completa, selezionare **Opzioni di** analisi e quindi selezionare un'opzione, ad esempio **Analisi completa.**

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a>Esaminare la versione dell'aggiornamento della sicurezza intelligence e scaricare gli aggiornamenti più recenti nell'app Sicurezza di Windows

![Informazioni sul numero di versione dell'intelligence per la sicurezza](images/defender/wdav-wdsc-defs.png)

1. Apri l'app Sicurezza di Windows cercando Sicurezza nel menu Start *e* quindi selezionando Sicurezza **di Windows.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).

3. Selezionare **Virus & threat protection updates**. La versione attualmente installata viene visualizzata insieme ad alcune informazioni sul momento in cui è stata scaricata. È possibile verificare la versione corrente rispetto alla versione più recente disponibile per il download manuale oppure esaminare il registro delle modifiche per tale versione. Vedi [Aggiornamenti dell'intelligence per la sicurezza per Microsoft Defender Antivirus e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

4. Selezionare **Controlla disponibilità aggiornamenti** per scaricare nuovi aggiornamenti di protezione (se disponibili).

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a>Verificare che Microsoft Defender Antivirus sia abilitato nell'app Sicurezza di Windows

1. Apri l'app Sicurezza di Windows cercando Sicurezza nel menu Start *e* quindi selezionando Sicurezza **di Windows.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).

3. Selezionare **Impostazioni protezione da & virus**.

4. Attiva **l'opzione Protezione in tempo** **reale.**

    > [!NOTE]
    > Se si disattiva **la protezione in tempo** reale, la protezione verrà automaticamente attivata dopo un breve ritardo. Ciò consente di garantire la protezione da malware e minacce.
    > Se installi un altro prodotto antivirus, Microsoft Defender Antivirus si disabilita automaticamente e viene indicato come tale nell'app Sicurezza di Windows. Verrà visualizzata un'impostazione che consente di abilitare [l'analisi periodica limitata.](limited-periodic-scanning-microsoft-defender-antivirus.md)

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a>Aggiungere esclusioni per Microsoft Defender Antivirus nell'app Sicurezza di Windows

1. Apri l'app Sicurezza di Windows cercando Sicurezza nel menu Start *e* quindi selezionando Sicurezza **di Windows.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).

3. In **Gestisci impostazioni selezionare** Impostazioni protezione da **& virus**.

4. **Nell'impostazione Esclusioni** seleziona **Aggiungi o rimuovi esclusioni.** 

5. Selezionare l'icona più ( **+** ) per scegliere il tipo e impostare le opzioni per ogni esclusione. 

Nella tabella seguente sono riepilogati i tipi di esclusione e cosa accade:

|Tipo di esclusione  |Definito da  |Effetto  |
|---------|---------|---------|
|**File** |Posizione <br/>Esempio: `c:\sample\sample.test` |Il file specifico viene ignorato da Microsoft Defender Antivirus. |
|**Cartella**    |Posizione <br/>Esempio: `c:\test\sample`       |Tutti gli elementi nella cartella specificata vengono ignorati da Microsoft Defender Antivirus.         |
|**Tipo file**   |Estensione del file <br/>Esempio: `.test` |Tutti i file con `.test` estensione in qualsiasi punto del dispositivo vengono ignorati da Microsoft Defender Antivirus.         |
|**Procedura**     |Percorso file eseguibile <br>Esempio: `c:\test\process.exe`         |Il processo specifico e tutti i file aperti da tale processo vengono ignorati da Microsoft Defender Antivirus.         |

Per altre informazioni, vedere le risorse seguenti:
- [Configurare e convalidare le esclusioni in base all'estensione di file e al percorso della cartella](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [Configurare le esclusioni per i file aperti dai processi](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a>Esaminare la cronologia del rilevamento delle minacce nell'app Centro sicurezza Windows Defender sicurezza

1. Apri l'app Sicurezza di Windows cercando Sicurezza nel menu Start *e* quindi selezionando Sicurezza **di Windows.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).

3. Selezionare **Cronologia protezione**. Vengono elencati tutti gli elementi recenti.

## <a name="set-ransomware-protection-and-recovery-options"></a>Impostare le opzioni di protezione e ripristino ransomware

1. Apri l'app Sicurezza di Windows cercando Sicurezza nel menu Start *e* quindi selezionando Sicurezza **di Windows.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).

3. In **Protezione ransomware** seleziona Gestisci protezione **ransomware.**

4. Per modificare le **impostazioni di accesso controllato** alle cartelle, vedere Protect important folders with Controlled folder [access](/microsoft-365/security/defender-endpoint/controlled-folders).

5. Per configurare le opzioni di ripristino ransomware, selezionare Configura **in** Ripristino dati **ransomware** e seguire le istruzioni per il collegamento o la configurazione dell'account OneDrive in modo da poter eseguire facilmente il ripristino da un attacco ransomware.

## <a name="see-also"></a>Vedere anche
- [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md)