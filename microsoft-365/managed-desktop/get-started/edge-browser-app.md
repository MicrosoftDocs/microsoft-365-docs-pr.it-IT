---
title: Nuova app Microsoft Edge
description: ''
keywords: browser, Microsoft Managed Desktop, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0602d7c6afef6190578268c78994b43ac60d0d2f
ms.sourcegitcommit: 3119b2246001ba06af8264508785352dfb894166
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44820680"
---
# <a name="new-microsoft-edge-app"></a>Nuova app Microsoft Edge

Il nuovo [browser Microsoft Edge](https://www.microsoft.com/edge) offre prestazioni di livello internazionale con maggiore privacy, maggiore produttività e più valore durante la ricerca. Microsoft Managed Desktop offre un'anteprima pubblica della distribuzione del nuovo browser perimetrale nell'ambiente in uso.

## <a name="initial-deployment"></a>Distribuzione iniziale

Per eseguire la migrazione dei dispositivi Microsoft Managed Desktop al nuovo browser Microsoft Edge, è possibile archiviare un ticket di supporto IT tramite il portale Microsoft Managed Desktop. La distribuzione del canale stable perimetrale nel gruppo di test viene distribuita quando si esegue il file del ticket e quindi viene distribuita in ogni gruppo di distribuzione successivo ogni 24 ore. Per sospendere la distribuzione, eseguire il file di un altro ticket che richiede le operazioni da mantenere.

## <a name="updates-to-microsoft-edge"></a>Aggiornamenti a Microsoft Edge

Microsoft Managed Desktop distribuisce il [canale stabile](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) di Microsoft Edge che viene aggiornato automaticamente circa ogni sei settimane. Gli aggiornamenti sul canale stabile vengono distribuiti [progressivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) dal gruppo di prodotti Microsoft Edge per garantire la migliore esperienza per i clienti. Il canale Microsoft Edge beta non è attualmente disponibile.

Per assicurarsi che Microsoft Edge venga aggiornato correttamente, non modificare i criteri Microsoft Edge [Update](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Impostazioni gestite da Microsoft Managed Desktop

Microsoft Managed Desktop ha creato un set predefinito di criteri per Microsoft Edge per proteggere il browser. Di seguito sono riportate le impostazioni predefinite del browser:

### <a name="microsoft-edge-extensions"></a>Microsoft Edge Extensions

La baseline di sicurezza per Microsoft Edge nei dispositivi Microsoft Managed Desktop imposta due criteri per disabilitare tutte le estensioni Chrome e gli utenti finali sicuri. Per abilitare e distribuire le estensioni nell'ambiente, vedere settings you manage. 

#### <a name="extension-installation-blocklist"></a>Blocco per l'installazione dell'estensione
**Valore predefinito:** Tutti

Microsoft Managed Desktop imposta questo criterio per impedire l'installazione delle estensioni Chrome negli endpoint gestiti. Sono noti risksassociated con il modello di estensione Chromium, tra cui la protezione dalla perdita di dati, la privacy e altri rischi che possono compromettere i dispositivi. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>Consenti host di messaggistica nativa a livello di utente (installati senza autorizzazioni di amministratore)

**Valore predefinito:** Disabili

Disabilitando questo criterio, Microsoft Edge utilizzerà solo host di messaggistica native installati a livello di sistema. Gli host di messaggistica native fanno parte di estensioni di Chrome che consentono al browser di interagire con altre parti dell'endpoint dell'utente, creando una serie di problemi di sicurezza.  

### <a name="secure-sockets-layer-ssl"></a> SSL (Secure Sockets Layer) 

#### <a name="minimum-ssl-version"></a>Versione SSL minima

**Valore predefinito:** Minimo TLS 1,2 supportato

Se si desidera utilizzare il TLS 1,1 meno sicuro, è possibile richiederlo.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>Consente agli utenti di procedere dalla pagina di avviso SSL

**Valore predefinito:** Disabili

Non è consigliabile abilitare questa impostazione poiché consente agli utenti di visitare i siti con errori SSL.

### <a name="microsoft-defender-smart-screen"></a>Smart Screen Microsoft Defender

#### <a name="configure-microsoft-defender-smartscreen"></a>Configurare Microsoft Defender SmartScreen

**Valore predefinito:** Abilitato

Abilitata per impostazione predefinita per garantire la protezione degli utenti finali.

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>Microsoft Defender SmartScreen richiede i siti

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione in quanto consente agli utenti di ignorare gli avvisi e continuare a siti potenzialmente dannosi.

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>Evitare di ignorare gli avvisi di Microsoft Defender SmartScreen sui download

**Valore predefinito:** Abilitato

Non è consigliabile disabilitare questa impostazione in quanto consente agli utenti di ignorare gli avvisi e completare i download non verificati.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>Impostazione predefinita di Adobe Flash

**Valore predefinito:** Disabili

Non è consigliabile utilizzare Flash a causa di rischi per la sicurezza associati. Se si hanno ancora processi che dipendono da Flash, impostare i criteri di **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** per abilitare il flash per i siti che ne hanno bisogno. Se non è possibile mantenere un elenco di siti consentiti per l'utilizzo di Flash, presentare una richiesta di modifica per modificare il valore da **fare clic su per riprodurre**, che consente agli utenti di scegliere quando è opportuno eseguire Flash.

### <a name="password-manager"></a>Gestione password

#### <a name="enable-saving-passwords-to-the-password-manager"></a>Abilitare il salvataggio delle password per il gestore delle password

**Valore predefinito:** Disabili

È consigliabile non consentire agli utenti finali di salvare le password sul proprio dispositivo.

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

È possibile distribuire le impostazioni del server perimetrale di Microsoft non descritte in precedenza utilizzando il profilo dei modelli amministrativi in Microsoft Intune. Per ulteriori informazioni, vedere [configurare le impostazioni dei criteri Microsoft Edge con Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune). Se si desidera valutare un criterio che non è attualmente incluso nei modelli amministrativi Microsoft Edge in Intune, è possibile utilizzare le impostazioni personalizzate per i dispositivi Windows 10 in Intune.

### <a name="enabling-specific-chrome-extensions"></a>Abilitazione di estensioni Chrome specifiche

Il modello amministrativo offre un'impostazione per la distribuzione di specifiche estensioni Chrome con Microsoft Intune. È possibile trovarlo in **Configurazione Computer > Microsoft Edge > extensions > consentire l'installazione di estensioni specifiche**.

### <a name="install-extensions-silently"></a>Installare le estensioni in modo invisibile all'utente

È inoltre possibile utilizzare il modello amministrativo per impostare Microsoft Edge per l'installazione delle estensioni senza avvisare l'utente. È possibile trovarlo in **Configurazione Computer > Microsoft Edge > extensions > controllare quali estensioni vengono installate automaticamente**.

### <a name="other-common-enterprise-policies"></a>Altri criteri dell'organizzazione comuni

Microsoft Edge offre numerosi criteri aggiuntivi. Questi sono alcuni tra quelli più comuni:
 
- [Configurare i siti nell'elenco e la modalità IE del sito dell'organizzazione](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [Configurare le impostazioni di avvio, Home page e nuova scheda pagina](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [Configurare l'impostazione del gioco Surf](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [Configurare le impostazioni del server proxy](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)
