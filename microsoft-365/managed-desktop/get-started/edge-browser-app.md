---
title: Nuovo Microsoft Edge
description: Spiega come viene distribuito e aggiornato il nuovo browser Edge
keywords: browser, Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822251"
---
# <a name="new-microsoft-edge-app"></a>Nuova Microsoft Edge app

Il nuovo [browser Microsoft Edge](https://www.microsoft.com/edge) offre prestazioni di livello mondiale con maggiore privacy, maggiore produttività e più valore durante l'esplorazione. Microsoft Managed Desktop offre un'anteprima pubblica della distribuzione del nuovo browser Edge nell'ambiente.

## <a name="initial-deployment"></a>Distribuzione iniziale

Per eseguire la migrazione Microsoft Managed Desktop dispositivi nel nuovo browser Microsoft Edge, è possibile stentarne un ticket di supporto IT tramite Microsoft Managed Desktop Portal. Il canale Edge Stable verrà distribuito al gruppo di test quando si esegue il file del ticket e quindi lo si distribuirà in ogni gruppo di distribuzione successivo ogni 24 ore. Per sospendere la distribuzione, file un altro ticket che richiede operazioni di conservazione.

Il [Canale beta è](/deployedge/microsoft-edge-channels#beta-channel) disponibile anche su richiesta di convalida rappresentativa all'interno dell'organizzazione. Microsoft Managed Desktop distribuirà l'applicazione in base alle esigenze ai gruppi Test e First in modo che tutti gli utenti hanno il Canale Beta oltre al Canale Stable. Per tutti gli altri utenti che necessitano dell'accesso al canale Beta, aggiungerli al gruppo **Modern Workplace - Edge Beta Users** e installarlo dal Portale aziendale

## <a name="updates-to-microsoft-edge"></a>Aggiornamenti a Microsoft Edge

Microsoft Managed Desktop distribuisce il [canale Stable](/deployedge/microsoft-edge-channels#stable-channel) di Microsoft Edge, che viene aggiornato automaticamente circa ogni sei settimane. Gli aggiornamenti nel canale Stable [](/deployedge/microsoft-edge-update-progressive-rollout) vengono evasi progressivamente dal Microsoft Edge per garantire ai clienti la migliore esperienza possibile. 

Il [canale Beta viene](/deployedge/microsoft-edge-channels#beta-channel) distribuito ai dispositivi nei gruppi Test e First per la convalida rappresentativa all'interno dell'organizzazione. Questo canale è completamente supportato e viene aggiornato automaticamente con nuove funzionalità circa ogni sei settimane.

Per assicurarsi che Microsoft Edge aggiornamenti corretti, non modificare i criteri di Microsoft Edge [di aggiornamento.](/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Impostazioni gestito da Microsoft Managed Desktop

Microsoft Managed Desktop ha creato un set predefinito di criteri per Microsoft Edge proteggere il browser. Le impostazioni predefinite del browser sono le seguenti:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge estensioni

La linea di base per la Microsoft Edge nei dispositivi Microsoft Managed Desktop imposta due criteri per disabilitare tutte le estensioni di Chrome e proteggere gli utenti. Per abilitare e distribuire le estensioni nell'ambiente, vedere Impostazioni gestione. 

#### <a name="extension-installation-blocklist"></a>Elenco dei blocchi di installazione delle estensioni
**Valore predefinito:** All

Microsoft Managed Desktop questo criterio per impedire l'installazione delle estensioni di Chrome in endpoint gestiti. Esistono rischi noti associati al modello di estensione Chromium, tra cui protezione della perdita dei dati, privacy e altri rischi che possono compromettere i dispositivi. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Consenti host di messaggistica nativi a livello di utente (installati senza autorizzazioni di amministratore)

**Valore predefinito:** Disabilitato

Disabilitando questo criterio, Microsoft Edge solo gli host di messaggistica nativi installati a livello di sistema. Gli host di messaggistica nativa fanno parte delle estensioni di Chrome, che consentono al browser di interagire con altre parti dell'endpoint dell'utente, creando una serie di problemi di sicurezza.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Versione tls minima

**Valore predefinito:** Tls minimo supportato 1.2

Se vuoi usare TLS 1.1 meno sicuro, puoi determinare una richiesta per farlo.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Consente agli utenti di procedere dalla pagina di avviso SSL

**Valore predefinito:** Disabilitato

Non è consigliabile abilitare questa impostazione poiché consente agli utenti di visitare siti con errori TSL.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Configurare Windows Defender SmartScreen

**Valore predefinito:** Abilitato

Abilitata per impostazione predefinita per proteggere gli utenti.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender Prompt SmartScreen per i siti

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione perché consentirebbe agli utenti di ignorare gli avvisi e continuare a utilizzare siti potenzialmente dannosi.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Impedisci il bypass degli Windows Defender SmartScreen sui download

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione perché consentirebbe agli utenti di ignorare gli avvisi e completare i download nonverificati.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Impostazione predefinita di Adobe Flash

**Valore predefinito:** Disabilitato

Non è consigliabile usare Flash a causa dei rischi di sicurezza associati. Se hai ancora processi che dipendono da Flash, imposta il criterio **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** per abilitare Flash per i siti che ne hanno bisogno. Se non è possibile mantenere un elenco di siti consentiti per l'uso di Flash, determinare una richiesta di modifica per modificare il valore in **Fare** clic per riprodurre , che consente agli utenti di scegliere quando eseguire Flash.

### <a name="password-manager"></a>Gestione password

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Abilitare il salvataggio delle password nel gestore delle password

**Valore predefinito:** Disabilitato

La gestione delle password è disabilitata per impostazione predefinita. Se questa funzionalità è abilitata, determinare una richiesta di supporto e i tecnici del servizio possono abilitare l'impostazione nel proprio ambiente. 

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modalità Internet Explorer in Microsoft Edge
La modalità IE Microsoft Edge consente di usare facilmente tutti i siti di cui l'organizzazione ha bisogno in un unico browser. Usa il motore Chromium integrato per i siti compatibili con il motore di rendering di Chromium e usa il motore MSHTML Trident di Internet Explorer 11 (IE11) per i siti che non sono o hanno dipendenze dalla funzionalità Internet Explorer. [Altre informazioni](/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop la modalità Internet Explorer per i dispositivi per impostazione predefinita 

#### <a name="internet-explorer-mode-integration"></a>Integrazione in modalità Internet Explorer
**Valore predefinito:** Modalità Internet Explorer

Per impostazione predefinita, i dispositivi sono impostati per l'uso della modalità Internet Explorer, ma puoi impostarli per aprire i siti in una finestra autonoma di Internet Explorer 11. Per modificare questo comportamento, stendiamo una richiesta di supporto.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Aggiungere siti all'elenco Enterprise modalità sito
Per l'apertura dei siti in modalità Internet Explorer, è necessario includerli [nell'Enterprise sito.](/DeployEdge/edge-ie-mode-sitelist) La gestione e la distribuzione dell'Enterprise sito è responsabilità dell'utente. Per informazioni dettagliate, vedere [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>Altre impostazioni

#### <a name="enable-site-isolation-for-every-site"></a>Abilitare l'isolamento del sito per ogni sito

**Valore predefinito:** Abilitato

Quando questo criterio è abilitato, gli utenti non possono rifiutare esplicitamente il comportamento predefinito in cui ogni sito viene eseguito nel proprio processo.

#### <a name="supported-authentication-schemes"></a>Schemi di autenticazione supportati

**Valore predefinito:** NTLM, Negozia

Microsoft Managed Desktop non supporta gli schemi di autenticazione di base o digest.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importa automaticamente i dati e le impostazioni di un altro browser alla prima esecuzione

**Valore predefinito:** Importa automaticamente tutti i tipi di dati e le impostazioni supportati dal browser predefinito 

Con questo criterio applicato, la prima esperienza di esecuzione ignora la sezione di importazione, riducendo al minimo l'interazione dell'utente. I dati del browser delle versioni precedenti di Microsoft Edge verranno sempre migrati automaticamente alla prima esecuzione, indipendentemente da questa impostazione. 


## <a name="settings-you-manage"></a>Impostazioni si gestisce

È possibile distribuire qualsiasi impostazione Microsoft Edge non descritta in precedenza utilizzando il profilo Modelli amministrativi in Microsoft Intune. Per informazioni dettagliate, vedere [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune). Se si desidera valutare un criterio attualmente non incluso nei modelli amministrativi di Microsoft Edge in Intune, è possibile usare le impostazioni personalizzate per i dispositivi Windows 10 in Intune.

### <a name="enabling-specific-chrome-extensions"></a>Abilitazione di estensioni di Chrome specifiche

Il modello amministrativo offre un'impostazione per distribuire specifiche estensioni di Chrome con Microsoft Intune. È possibile trovarlo in **Configurazione computer > Microsoft Edge > estensioni > consenti l'installazione di estensioni specifiche**.

### <a name="install-extensions-silently"></a>Installare le estensioni in modo invisibile all'utente

È inoltre possibile utilizzare il modello amministrativo per impostare Microsoft Edge installare le estensioni senza avvisare l'utente. Puoi trovarlo in Configurazione computer > Microsoft Edge > Estensioni > controllare quali **estensioni vengono installate automaticamente.**

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge criteri di aggiornamento
Per assicurarsi che Microsoft Edge aggiornamenti corretti, non modificare i criteri di Microsoft Edge [di aggiornamento.](/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>Altri criteri aziendali comuni

Microsoft Edge offre molti altri criteri. Di seguito sono riportati alcuni dei più comuni:
 
- [Configurare i siti nell'Enterprise siti e in modalità IE](/deployedge/edge-ie-mode-sitelist)
- [Configurare le impostazioni della pagina iniziale, della home page e delle nuove schede](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurare l'impostazione del gioco Surf](/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurare le impostazioni del server proxy](/deployedge/microsoft-edge-policies#proxy-server)
