---
title: Microsoft Defender Antivirus su Windows Server
description: Scopri come abilitare e configurare Microsoft Defender Antivirus in Windows Server 2016 e Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269493"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivirus su Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus è disponibile nelle seguenti edizioni/versioni di Windows Server:
- Windows Server 2019
- Windows Server, versione 1803 o successiva
- Windows Server 2016. 

In alcuni casi, Microsoft Defender Antivirus viene definito *Endpoint Protection;* tuttavia, il motore di protezione è lo stesso. Sebbene le funzionalità, la configurazione e la gestione siano in gran parte le stesse per [Microsoft Defender Antivirus in Windows 10,](microsoft-defender-antivirus-in-windows-10.md)esistono alcune differenze chiave in Windows Server:

- In Windows Server, [le esclusioni automatiche](configure-server-exclusions-microsoft-defender-antivirus.md) vengono applicate in base al ruolo del server definito.
 
- In Windows Server, se si esegue una soluzione antivirus/antimalware non Microsoft, Microsoft Defender Antivirus non passa automaticamente alla modalità passiva o disabilitata. Tuttavia, puoi impostare Microsoft Defender Antivirus in modalità passiva o disabilitata manualmente.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Configurazione di Microsoft Defender Antivirus in Windows Server

Il processo di configurazione ed esecuzione di Microsoft Defender Antivirus su una piattaforma server include diversi passaggi:

1. [Abilitare l'interfaccia](#enable-the-user-interface-on-windows-server).
2. [Installare Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).
3. [Verificare che Microsoft Defender Antivirus sia in esecuzione](#verify-microsoft-defender-antivirus-is-running).
4. [Aggiornare l'antimalware Security intelligence](#update-antimalware-security-intelligence).
5. (In base alle esigenze) [Inviare esempi](#submit-samples).
6. (In base alle esigenze) [Configurare le esclusioni automatiche](#configure-automatic-exclusions).
7. (Solo se necessario) [Imposta Microsoft Defender Antivirus sulla modalità passiva.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)

## <a name="enable-the-user-interface-on-windows-server"></a>Abilitare l'interfaccia utente in Windows Server

Per impostazione predefinita, Microsoft Defender Antivirus è installato e funzionante in Windows Server. A volte, l'interfaccia utente (GUI) viene installata per impostazione predefinita, ma l'interfaccia utente grafica non è necessaria. Puoi usare PowerShell, Criteri di gruppo o altri metodi per gestire Microsoft Defender Antivirus. 

Se l'interfaccia utente grafica non è installata nel server  e si desidera installarla, la procedura guidata Aggiungi ruoli e funzionalità o i cmdlet di PowerShell.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Attivare l'interfaccia utente grafica tramite l'Aggiunta guidata ruoli e funzionalità

1. Vedere [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e use the Add Roles and Features **Wizard.**

2. Quando si arriva al passaggio **Funzionalità** della procedura guidata, in Windows Defender **funzionalità** selezionare l'opzione **GUI per Windows Defender** funzionalità.

   In Windows Server 2016, **l'Aggiunta guidata ruoli e funzionalità** è simile alla seguente:

   ![Aggiunta guidata ruoli e funzionalità che mostra l'opzione GUI per Windows Defender funzionalità](images/server-add-gui.png)

   In Windows Server 2019, **l'Aggiunta guidata ruoli e funzionalità** è simile.

### <a name="turn-on-the-gui-using-powershell"></a>Attivare l'interfaccia utente grafica con PowerShell

Il cmdlet PowerShell seguente abiliterà l'interfaccia: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Installare Microsoft Defender Antivirus in Windows Server

Se è necessario installare o reinstallare Microsoft Defender Antivirus in Windows Server, è possibile farlo utilizzando l'Aggiunta guidata ruoli **e** funzionalità o PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Usare l'Aggiunta guidata ruoli e funzionalità per installare Microsoft Defender Antivirus

1. Fare riferimento [a questo articolo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e utilizzare l'Aggiunta guidata ruoli e **funzionalità.**

2. Quando si arriva al passaggio **Funzionalità** della procedura guidata, selezionare l'opzione Microsoft Defender Antivirus. Selezionare anche **l'opzione GUI per Windows Defender.**

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Usare PowerShell per installare Microsoft Defender Antivirus

Per utilizzare PowerShell per installare Microsoft Defender Antivirus, eseguire il cmdlet seguente:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

I messaggi di evento per il motore antimalware incluso in Microsoft Defender Antivirus sono disponibili in [Microsoft Defender AV Events.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Verificare che Microsoft Defender Antivirus sia in esecuzione

Dopo aver installato Microsoft Defender Antivirus, il passaggio successivo consiste nel verificare che sia in esecuzione. Nell'endpoint di Windows Server, eseguire il cmdlet PowerShell seguente:

```PowerShell
Get-Service -Name windefend
```

Per verificare che la protezione firewall sia attivata, eseguire il cmdlet PowerShell seguente:

```PowerShell 
Get-Service -Name mpssvc
```

In alternativa a PowerShell, è possibile utilizzare il prompt dei comandi per verificare che Microsoft Defender Antivirus sia in esecuzione. A tale scopo, eseguire il comando seguente da un prompt dei comandi: 

```console
sc query Windefend
```

Il `sc query` comando restituisce informazioni sul servizio Microsoft Defender Antivirus. Quando Microsoft Defender Antivirus è in esecuzione, il `STATE` valore visualizza `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Aggiornare antimalware Security intelligence 

Per ottenere informazioni aggiornate sulla sicurezza antimalware, è necessario che il servizio Windows Update sia in esecuzione. Se usi un servizio di gestione degli aggiornamenti, come Windows Server Update Services (WSUS), assicurati che gli aggiornamenti per Microsoft Defender Antivirus Security intelligence siano approvati per i computer gestiti.

Per impostazione predefinita, Windows Update non scarica e installa automaticamente gli aggiornamenti in Windows Server 2019 o Windows Server 2016. È possibile modificare questa configurazione utilizzando uno dei metodi seguenti:


|Metodo  |Descrizione  |
|---------|---------|
|**Windows Update** nel Pannello di controllo     |- **L'installazione automatica** degli aggiornamenti comporta l'installazione automatica di tutti gli aggiornamenti, Windows Defender aggiornamenti di Security intelligence. <br/>- **Scaricare gli aggiornamenti ma consentirmi** di scegliere se installarli consente Windows Defender scaricare e installare automaticamente gli aggiornamenti di Security Intelligence, ma altri aggiornamenti non vengono installati automaticamente.       |
|**Criteri di gruppo**     | Puoi configurare e gestire Windows Update usando le impostazioni disponibili in Criteri di gruppo nel percorso seguente: **Modelli amministrativi\Componenti di Windows\Windows Update\Configura aggiornamenti automatici**         |
|Chiave **del Registro di sistema AUOptions**     |I due valori seguenti consentono a Windows Update di scaricare e installare automaticamente gli aggiornamenti di Security Intelligence: <br/>- **4**  -  **Installare automaticamente gli aggiornamenti**. Questo valore determina l'installazione automatica di tutti gli aggiornamenti, Windows Defender aggiornamenti di Security intelligence. <br/>- **3**  -  **Scarica gli aggiornamenti ma consentimi di scegliere se installarli**.  Questo valore consente Windows Defender scaricare e installare automaticamente gli aggiornamenti di Security Intelligence, ma altri aggiornamenti non vengono installati automaticamente.         |

Per garantire che la protezione da malware sia mantenuta, è consigliabile abilitare i servizi seguenti:

- Servizio Segnalazione errori Windows

- Servizio Windows Update

Nella tabella seguente sono elencati i servizi per Microsoft Defender Antivirus e i servizi dipendenti.

|Nome servizio|Percorso file|Descrizione|
|--------|---------|--------|
|Windows Defender Service (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Questo è il principale servizio Microsoft Defender Antivirus che deve essere sempre in esecuzione.|
|Servizio Segnalazione errori Windows (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Questo servizio invia le segnalazioni errori a Microsoft.|
|Windows Defender firewall (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|È consigliabile lasciare abilitato il Windows Defender firewall.|
|Windows Update (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows Update è necessario per ottenere gli aggiornamenti di Intelligence per la sicurezza e gli aggiornamenti del motore antimalware|

## <a name="submit-samples"></a>Inviare esempi

L'invio di esempio consente a Microsoft di raccogliere campioni di software potenzialmente dannoso. Per garantire una protezione continua e aggiornata, i ricercatori Microsoft usano questi esempi per analizzare le attività sospette e produrre informazioni aggiornate sulla sicurezza antimalware. Raccogliamo file eseguibili di programma, ad esempio .exe file e .dll file. Non vengono raccolti file contenenti dati personali, ad esempio documenti di Microsoft Word e file PDF.

### <a name="submit-a-file"></a>Inviare un file

1. Consultare la [guida all'invio](/windows/security/threat-protection/intelligence/submission-guide).

2. Visita il [portale di invio di esempio](https://www.microsoft.com/wdsi/filesubmission)e invia il file.


### <a name="enable-automatic-sample-submission"></a>Abilitare l'invio automatico di esempi

Per abilitare l'invio automatico di esempi, avviare una console di Windows PowerShell come amministratore e impostare i dati del valore **SubmitSamplesConsent** in base a una delle impostazioni seguenti:

|Impostazione  |Descrizione  |
|---------|---------|
|**0**  -  **Chiedi sempre conferma**     |Il Antivirus Microsoft Defender richiede di confermare l'invio di tutti i file necessari. Questa è l'impostazione predefinita per Antivirus Microsoft Defender, ma non è consigliata per le installazioni in Windows Server 2016 o 2019 senza gui.         |
|**1**   -  **Inviare automaticamente campioni sicuri**     |Il Antivirus Microsoft Defender invia tutti i file contrassegnati come "sicuri" e richiede il resto dei file.         |
|**2**  -  **Non inviare mai**      |Il Antivirus Microsoft Defender non richiede conferma e non invia alcun file.         |
|**3**  -  **Inviare automaticamente tutti i campioni**     |Il Antivirus Microsoft Defender invia tutti i file senza una richiesta di conferma.         |

## <a name="configure-automatic-exclusions"></a>Configurare le esclusioni automatiche

Per garantire sicurezza e prestazioni, alcune esclusioni vengono aggiunte automaticamente in base ai ruoli e alle funzionalità installate quando si usa Antivirus Microsoft Defender in Windows Server 2016 o 2019.

Vedere [Configure exclusions in Antivirus Microsoft Defender on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md). 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>È necessario impostare Antivirus Microsoft Defender modalità passiva?

Se si utilizza un prodotto antivirus non Microsoft come soluzione antivirus principale in Windows Server, è necessario impostare Antivirus Microsoft Defender modalità passiva o disabilitata.

- In Windows Server, versione 1803 o successiva o Windows Server 2019, è possibile impostare Antivirus Microsoft Defender modalità passiva.  

- In Windows Server 2016, Antivirus Microsoft Defender non è supportato insieme a un prodotto antivirus/antimalware non Microsoft. In questi casi, devi impostare Antivirus Microsoft Defender modalità disabilitata.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a>Impostare Antivirus Microsoft Defender modalità passiva tramite PowerShell

Se si utilizza Windows Server, versione 1803 o Windows Server 2019, è possibile impostare Antivirus Microsoft Defender sulla modalità passiva utilizzando il cmdlet PowerShell seguente:

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a>Impostare Antivirus Microsoft Defender modalità passiva tramite Criteri di gruppo

PROCEDURA NECESSARIA

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Impostare Antivirus Microsoft Defender modalità passiva usando una chiave del Registro di sistema

Se si utilizza Windows Server versione 1803 o Windows Server 2019, è possibile impostare Antivirus Microsoft Defender sulla modalità passiva impostando la chiave del Registro di sistema seguente:
- Percorso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nome: `ForceDefenderPassiveMode`
- Digitare: `REG_DWORD`
- Valore: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Disabilitare Antivirus Microsoft Defender tramite la procedura guidata Rimuovi ruoli e funzionalità

1. Vedere [Installare o disinstallare ruoli, servizi ruolo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)o funzionalità e utilizzare la Rimozione guidata ruoli e **funzionalità.** 

2. Quando si arriva al passaggio **Funzionalità** della procedura guidata, deselezionare l'opzione **Windows Defender funzionalità.** 

    Se si deseleziona **Windows Defender** nella sezione Funzionalità di **Windows Defender,** verrà richiesto di rimuovere l'opzione gui dell'interfaccia per **Windows Defender**. 
    
    Antivirus Microsoft Defender verrà comunque eseguita normalmente senza l'interfaccia utente, ma l'interfaccia utente non può essere abilitata se si disabilita la funzionalità di Windows Defender **di** base.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Disattivare l'Antivirus Microsoft Defender utente con PowerShell

Per disattivare l'Antivirus Microsoft Defender gui, utilizzare il cmdlet PowerShell seguente:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Si sta usando Windows Server 2016?

Se si utilizza Windows Server 2016 e un prodotto antimalware/antivirus di terze parti non offerto o sviluppato da Microsoft, è necessario disabilitare/disinstallare Antivirus Microsoft Defender. 

> [!NOTE]
> Non puoi disinstallare l'app Sicurezza di Windows, ma puoi disabilitare l'interfaccia con queste istruzioni.

Il cmdlet PowerShell seguente disinstalla Antivirus Microsoft Defender in Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Per disabilitare Antivirus Microsoft Defender in Windows Server 2016, utilizzare il cmdlet PowerShell seguente:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>Vedere anche

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus Microsoft Defender compatibilità](microsoft-defender-antivirus-compatibility.md)
