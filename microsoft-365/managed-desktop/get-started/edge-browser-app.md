---
title: Nuovo Microsoft Edge
description: Spiega come distribuire e aggiornare il nuovo browser Edge
keywords: browser, Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 42ff665e8ba9c369e29eeeafd27affff04b40966
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841340"
---
# <a name="new-microsoft-edge-app"></a>Nuova app Microsoft Edge

Il nuovo [browser Microsoft Edge](https://www.microsoft.com/edge) offre prestazioni di livello mondiale con maggiore privacy, maggiore produttività e più valore durante l'esplorazione. Microsoft Managed Desktop offre un'anteprima pubblica della distribuzione del nuovo browser Edge nell'ambiente.

## <a name="initial-deployment"></a>Distribuzione iniziale

Per eseguire la migrazione dei dispositivi Microsoft Managed Desktop nel nuovo browser Microsoft Edge, creare un ticket di supporto IT tramite microsoft Managed Desktop Portal. Il canale Stable di Edge verrà distribuito al gruppo di test quando si esegue il file del ticket e quindi verrà distribuito in ogni gruppo di distribuzione successivo ogni 24 ore. Per sospendere la distribuzione, creare un altro ticket per richiedere il blocco a Operations.

Il [Canale Beta è](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) disponibile anche su richiesta di una convalida rappresentativa all'interno dell'organizzazione. Microsoft Managed Desktop distribuirà l'applicazione in base alle esigenze ai gruppi Test e First, in modo che tutti gli utenti hanno il Canale Beta oltre al Canale Stable. Per tutti gli altri utenti che hanno bisogno di accedere al Canale beta, aggiungerli al gruppo **Modern Workplace - Edge Beta Users** e installarlo dal portale aziendale

## <a name="updates-to-microsoft-edge"></a>Aggiornamenti a Microsoft Edge

Microsoft Managed Desktop distribuisce il [canale Stable](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) di Microsoft Edge, che viene aggiornato automaticamente ogni sei settimane. Gli aggiornamenti nel canale Stable [](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) vengono gradualmente installati dal gruppo di prodotti Microsoft Edge per garantire la migliore esperienza per i clienti. 

Il [canale Beta viene](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) distribuito ai dispositivi sia nei gruppi Test che First per la convalida rappresentativa all'interno dell'organizzazione. Questo canale è completamente supportato e viene aggiornato automaticamente con nuove funzionalità circa ogni sei settimane.

Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri di aggiornamento [di](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Impostazioni gestite da Microsoft Managed Desktop

Microsoft Managed Desktop ha creato un set predefinito di criteri per Microsoft Edge per proteggere il browser. Le impostazioni predefinite del browser sono le seguenti:

### <a name="microsoft-edge-extensions"></a>Estensioni di Microsoft Edge

La linea di base della sicurezza per Microsoft Edge nei dispositivi Microsoft Managed Desktop imposta due criteri per disabilitare tutte le estensioni di Chrome e proteggere gli utenti. Per abilitare e distribuire le estensioni nell'ambiente, vedere Impostazioni gestite. 

#### <a name="extension-installation-blocklist"></a>Elenco di indirizzi di installazione delle estensioni
**Valore predefinito:** All

Microsoft Managed Desktop imposta questo criterio per impedire l'installazione delle estensioni di Chrome in endpoint gestiti. Esistono rischi noti associati al modello di estensione Chromium, tra cui la protezione della perdita di dati, la privacy e altri rischi che possono compromettere i dispositivi. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Consenti host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministratore)

**Valore predefinito:** Disabilitato

Disabilitando questo criterio, Microsoft Edge utilizzerà solo gli host di messaggistica nativa installati a livello di sistema. Gli host di messaggistica nativa fanno parte delle estensioni di Chrome, che consentono al browser di interagire con altre parti dell'endpoint dell'utente, creando una serie di problemi di sicurezza.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Versione tls minima

**Valore predefinito:** Tls 1.2 minimo supportato

Se si desidera utilizzare TLS 1.1 meno sicuro, è possibile determinare una richiesta per farlo.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Consente agli utenti di procedere dalla pagina di avviso SSL

**Valore predefinito:** Disabilitato

Non è consigliabile abilitare questa impostazione perché consente agli utenti di visitare siti con errori TSL.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Configurare Windows Defender SmartScreen

**Valore predefinito:** Abilitato

Abilitata per impostazione predefinita per proteggere gli utenti.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender prompt di SmartScreen per i siti

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione perché consentirebbe agli utenti di ignorare gli avvisi e continuare con siti potenzialmente dannosi.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Impedisci il bypass Windows Defender avvisi di SmartScreen sui download

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione perché consentirebbe agli utenti di ignorare gli avvisi e completare i download nonverificati.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Impostazione predefinita di Adobe Flash

**Valore predefinito:** Disabilitato

Non è consigliabile usare Flash a causa dei rischi per la sicurezza associati. Se hai ancora processi che dipendono da Flash, imposta il criterio **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** per abilitare Flash per i siti che ne hanno bisogno. Se non riesci a mantenere un elenco di siti consentiti per l'uso di Flash, crea una richiesta di modifica per modificare il valore in **Click to Play,** che consente agli utenti di scegliere quando è appropriato eseguire Flash.

### <a name="password-manager"></a>Gestione password

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Abilitare il salvataggio delle password nel gestore delle password

**Valore predefinito:** Disabilitato

Non è consigliabile consentire agli utenti di salvare le password nel dispositivo.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modalità Internet Explorer in Microsoft Edge
La modalità IE in Microsoft Edge semplifica l'uso di tutti i siti di cui l'organizzazione ha bisogno in un unico browser. Usa il motore Chromium integrato per i siti compatibili con il motore di rendering Chromium e usa il motore TRIDENT MSHTML di Internet Explorer 11 (IE11) per i siti che non sono o hanno dipendenze dalla funzionalità di Internet Explorer. [Altre informazioni] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop abilita la modalità Internet Explorer per i dispositivi per impostazione predefinita 

#### <a name="internet-explorer-mode-integration"></a>Integrazione della modalità Internet Explorer
**Valore predefinito:** Modalità Internet Explorer

Per impostazione predefinita, i dispositivi sono impostati per l'uso della modalità Internet Explorer, ma puoi impostarli per aprire i siti in una finestra autonoma di Internet Explorer 11. Per modificare questo comportamento, stenta una richiesta di supporto.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Aggiungere siti all'elenco dei siti per la modalità Enterprise
Per l'apertura dei siti in modalità Internet Explorer, è necessario includerli [nell'elenco Dei siti aziendali.](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist) La gestione e la distribuzione dell'elenco di siti aziendali sono di responsabilità dell'utente. Per informazioni dettagliate, vedere [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Altre impostazioni

#### <a name="enable-site-isolation-for-every-site"></a>Abilitare l'isolamento del sito per ogni sito

**Valore predefinito:** Abilitato

Quando questo criterio è abilitato, gli utenti non possono rifiutare esplicitamente il comportamento predefinito in cui ogni sito viene eseguito nel proprio processo.

#### <a name="supported-authentication-schemes"></a>Schemi di autenticazione supportati

**Valore predefinito:** NTLM, Negotiate

Microsoft Managed Desktop non supporta gli schemi di autenticazione di base o digest.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importare automaticamente i dati e le impostazioni di un altro browser alla prima esecuzione

**Valore predefinito:** Importa automaticamente tutti i tipi di dati e le impostazioni supportati dal browser predefinito 

Con questo criterio applicato, la first-run experience ignora la sezione di importazione, riducendo al minimo l'interazione dell'utente. I dati del browser delle versioni precedenti di Microsoft Edge verranno sempre migrati automaticamente alla prima esecuzione, indipendentemente da questa impostazione. 


## <a name="settings-you-manage"></a>Impostazioni gestite

Puoi distribuire qualsiasi impostazione di Microsoft Edge non descritta in precedenza usando il profilo Modelli amministrativi in Microsoft Intune. Per informazioni dettagliate, vedere [Configurare le impostazioni dei criteri di Microsoft Edge con Microsoft Intune.](https://docs.microsoft.com/deployedge/configure-edge-with-intune) Se vuoi valutare un criterio attualmente non incluso nei modelli amministrativi di Microsoft Edge in Intune, puoi usare impostazioni personalizzate per i dispositivi Windows 10 in Intune.

### <a name="enabling-specific-chrome-extensions"></a>Abilitazione di estensioni di Chrome specifiche

Il modello amministrativo offre un'impostazione per distribuire specifiche estensioni di Chrome con Microsoft Intune. È possibile trovarlo in Configurazione computer > Microsoft Edge > Estensioni > consenti l'installazione **di estensioni specifiche.**

### <a name="install-extensions-silently"></a>Installare le estensioni in modo invisibile all'utente

Puoi anche usare il modello amministrativo per impostare Microsoft Edge in modo che installi le estensioni senza avvisare l'utente. È possibile trovarlo in Configurazione computer > Microsoft Edge > estensioni > controllare quali estensioni vengono installate in **modo invisibile all'utente.**

### <a name="microsoft-edge-update-policies"></a>Criteri di aggiornamento di Microsoft Edge
Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri di aggiornamento [di](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)Microsoft Edge.

### <a name="other-common-enterprise-policies"></a>Altri criteri aziendali comuni

Microsoft Edge offre molti altri criteri. Di seguito sono riportati alcuni dei più comuni:
 
- [Configurare i siti nell'elenco di siti enterprise e nella modalità IE](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Configurare le impostazioni di avvio, home page e pagina nuova scheda](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurare l'impostazione del gioco Surf](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurare le impostazioni del server proxy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

