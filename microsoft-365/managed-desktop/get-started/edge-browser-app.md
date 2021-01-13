---
title: Nuovo Microsoft Edge
description: Viene illustrato il modo in cui viene distribuito e aggiornato il nuovo browser perimetrale
keywords: browser, Microsoft Managed Desktop, Microsoft 365, Service, Documentation
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

Il nuovo [browser Microsoft Edge](https://www.microsoft.com/edge) offre prestazioni di livello internazionale con maggiore privacy, maggiore produttività e più valore durante la ricerca. Microsoft Managed Desktop offre un'anteprima pubblica della distribuzione del nuovo browser perimetrale nell'ambiente in uso.

## <a name="initial-deployment"></a>Distribuzione iniziale

Per eseguire la migrazione dei dispositivi Microsoft Managed Desktop al nuovo browser Microsoft Edge, è possibile archiviare un ticket di supporto IT tramite il portale Microsoft Managed Desktop. La distribuzione del canale stable perimetrale nel gruppo di test viene distribuita quando si esegue il file del ticket e quindi viene distribuita in ogni gruppo di distribuzione successivo ogni 24 ore. Per sospendere la distribuzione, eseguire il file di un altro ticket che richiede le operazioni da mantenere.

Il [canale Beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) è disponibile anche su richiesta per la convalida rappresentativa all'interno dell'organizzazione. Microsoft Managed Desktop distribuirà l'applicazione in base alle esigenze del test e dei primi gruppi, in modo che tutti gli utenti dispongano del canale beta oltre al canale stabile. Per tutti gli altri utenti che hanno bisogno di accedere al canale beta, aggiungerli al gruppo di **utenti beta sul posto di lavoro moderno** e farli installare dal portale aziendale.

## <a name="updates-to-microsoft-edge"></a>Aggiornamenti a Microsoft Edge

Microsoft Managed Desktop distribuisce il [canale stabile](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) di Microsoft Edge, che viene aggiornato automaticamente circa ogni sei settimane. Gli aggiornamenti sul canale stabile vengono distribuiti [progressivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) dal gruppo di prodotti Microsoft Edge per garantire la migliore esperienza per i clienti. 

Il [canale Beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) viene distribuito ai dispositivi sia nel test che nei primi gruppi per la convalida rappresentativa all'interno dell'organizzazione. Questo canale è completamente supportato e viene aggiornato automaticamente con nuove funzionalità ogni sei settimane.

Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri Microsoft Edge [Update](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).



## <a name="settings-managed-by-microsoft-managed-desktop"></a>Impostazioni gestite da Microsoft Managed Desktop

Microsoft Managed Desktop ha creato un set predefinito di criteri per Microsoft Edge per proteggere il browser. Di seguito sono riportate le impostazioni predefinite del browser:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge Extensions

La previsione di sicurezza per Microsoft Edge nei dispositivi Microsoft Managed Desktop imposta due criteri per disabilitare tutte le estensioni di Chrome e proteggere gli utenti. Per abilitare e distribuire le estensioni nell'ambiente, vedere settings you manage. 

#### <a name="extension-installation-blocklist"></a>Blocco per l'installazione dell'estensione
**Valore predefinito:** Tutti

Microsoft Managed Desktop imposta questo criterio per impedire l'installazione delle estensioni Chrome negli endpoint gestiti. Vi sono rischi noti associati al modello di estensione Chromium, tra cui la protezione dalla perdita di dati, la privacy e altri rischi che possono compromettere i dispositivi. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Consenti host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministratore)

**Valore predefinito:** Disabili

Disabilitando questo criterio, Microsoft Edge utilizzerà solo host di messaggistica native installati a livello di sistema. Gli host di messaggistica nativa fanno parte delle estensioni di Chrome, che consentono al browser di interagire con le altre parti dell'endpoint dell'utente, creando una serie di problemi di sicurezza.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer (TLS/SSL)

#### <a name="minimum-tls-version"></a>Versione TLS minima

**Valore predefinito:** Minimo TLS 1,2 supportato

Se si desidera utilizzare il TLS 1,1 meno sicuro, è possibile presentare una richiesta.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Consente agli utenti di procedere dalla pagina di avviso SSL

**Valore predefinito:** Disabili

Non è consigliabile abilitare questa impostazione poiché consente agli utenti di visitare i siti con errori di TSL.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>Configurare Windows Defender SmartScreen

**Valore predefinito:** Abilitato

Abilitata per impostazione predefinita per garantire la protezione degli utenti.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender SmartScreen richiede i siti

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione in quanto consente agli utenti di ignorare gli avvisi e continuare a siti potenzialmente dannosi.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>Evitare di ignorare gli avvisi di Windows Defender SmartScreen sui download

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione in quanto consente agli utenti di ignorare gli avvisi e completare i download non verificati.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Impostazione predefinita di Adobe Flash

**Valore predefinito:** Disabili

Non è consigliabile utilizzare Flash a causa di rischi per la sicurezza associati. Se si hanno ancora processi che dipendono da Flash, impostare i criteri di **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** per abilitare flash per i siti che ne hanno bisogno. Se non è possibile mantenere un elenco di siti consentiti per l'utilizzo di Flash, presentare una richiesta di modifica per modificare il valore da **fare clic su per riprodurre**, che consente agli utenti di scegliere quando è opportuno eseguire Flash.

### <a name="password-manager"></a>Gestione password

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Abilitare il salvataggio delle password per il gestore delle password

**Valore predefinito:** Disabili

È consigliabile non consentire agli utenti di salvare le password sul proprio dispositivo.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Modalità Internet Explorer in Microsoft Edge
La modalità IE su Microsoft Edge semplifica l'utilizzo di tutti i siti che l'organizzazione ha bisogno in un singolo browser. Utilizza il motore cromo integrato per i siti compatibili con il motore di rendering di cromo e utilizza il motore MSHTML Trident da Internet Explorer 11 (IE11) per i siti che non sono o che hanno dipendenze sulla funzionalità IE. [Ulteriori informazioni] (https://docs.microsoft.com/DeployEdge/edge-ie-mode) 

Microsoft Managed Desktop attiva la modalità Internet Explorer per i propri dispositivi per impostazione predefinita 

#### <a name="internet-explorer-mode-integration"></a>Integrazione della modalità Internet Explorer
**Valore predefinito:** Modalità Internet Explorer

Per impostazione predefinita, i dispositivi sono impostati per l'utilizzo della modalità Internet Explorer, ma è possibile impostarli in modo da aprire i siti in una finestra autonoma di Internet Explorer 11. Per modificare questo comportamento, è necessario presentare una richiesta di supporto.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Aggiungere siti all'elenco del sito in modalità Enterprise
Affinché i siti vengano aperti in modalità Internet Explorer, è necessario includerli nell' [elenco siti organizzazione](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist). La gestione e la distribuzione dell'elenco siti organizzazione è una responsabilità. Per informazioni dettagliate, vedere [Configure using the Configure Enterprise Site List Policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy) .

### <a name="other-settings"></a>Altre impostazioni

#### <a name="enable-site-isolation-for-every-site"></a>Abilitare l'isolamento dei siti per ogni sito

**Valore predefinito:** Abilitato

Quando questo criterio è abilitato, gli utenti non possono escludere il comportamento predefinito in cui ogni sito viene eseguito nel proprio processo.

#### <a name="supported-authentication-schemes"></a>Schemi di autenticazione supportati

**Valore predefinito:** NTLM, negozia

Microsoft Managed Desktop non supporta schemi di autenticazione di base o di digest.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>Importare automaticamente i dati e le impostazioni di un altro browser al primo avvio

**Valore predefinito:** Importare automaticamente tutti i tipi di DataType e le impostazioni supportati dal browser predefinito 

Con questo criterio applicato, la prima operazione di esecuzione ignorerà la sezione Import, riducendo al minimo l'interazione dell'utente. I dati del browser provenienti da versioni precedenti di Microsoft Edge verranno sempre migrati automaticamente al primo avvio, indipendentemente da questa impostazione. 


## <a name="settings-you-manage"></a>Impostazioni gestite

È possibile distribuire le impostazioni di Microsoft Edge non descritte in precedenza utilizzando il profilo dei modelli amministrativi in Microsoft Intune. Per ulteriori informazioni, vedere [configurare le impostazioni dei criteri Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune). Se si desidera valutare un criterio che non è attualmente incluso nei modelli amministrativi di Microsoft Edge in Intune, è possibile utilizzare le impostazioni personalizzate per i dispositivi Windows 10 in Intune.

### <a name="enabling-specific-chrome-extensions"></a>Abilitazione di estensioni Chrome specifiche

Il modello amministrativo offre un'impostazione per la distribuzione di specifiche estensioni Chrome con Microsoft Intune. È possibile trovarlo in **Configurazione Computer > Microsoft Edge > extensions > consentire l'installazione di estensioni specifiche**.

### <a name="install-extensions-silently"></a>Installare le estensioni in modo invisibile all'utente

È inoltre possibile utilizzare il modello amministrativo per impostare Microsoft Edge per l'installazione delle estensioni senza avvisare l'utente. È possibile trovarlo in **Configurazione Computer > Microsoft Edge > extensions > controllare quali estensioni vengono installate automaticamente**.

### <a name="microsoft-edge-update-policies"></a>Criteri di aggiornamento di Microsoft Edge
Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri Microsoft Edge [Update](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).

### <a name="other-common-enterprise-policies"></a>Altri criteri dell'organizzazione comuni

Microsoft Edge offre numerosi altri criteri. Questi sono alcuni tra quelli più comuni:
 
- [Configurare i siti nell'elenco e la modalità IE del sito dell'organizzazione](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Configurare le impostazioni di avvio, Home page e nuova scheda pagina](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurare l'impostazione del gioco Surf](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurare le impostazioni del server proxy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

