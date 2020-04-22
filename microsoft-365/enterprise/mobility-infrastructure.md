---
title: Fase 5 - Gestione dei dispositivi mobili
description: Microsoft 365 Enterprise include la gestione dei dispositivi mobili tramite Microsoft Intune. Esaminare i requisiti e i prerequisiti, configurare Intune utilizzando la risorsa di Azure Active Directory, registrare i dispositivi iOS, macOS, Android e Windows, distribuire le app, creare un profilo di configurazione, utilizzare criteri di conformità e abilitare l'accesso condizionale per la gestione dei dispositivi mobili con Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, gestione dei dispositivi mobili, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: c90f16bfbdf41f859e13a23fbdaeb0c3480bd191
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631526"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fase 5: gestione dei dispositivi mobili per Microsoft 365 Enterprise

![Fase 5: gestione dei dispositivi mobili](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Questa funzionalità si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

Microsoft 365 Enterprise include funzionalità che consentono di gestire i dispositivi e le loro app all'interno dell'organizzazione. Tramite Microsoft Intune, è possibile gestire i dispositivi iOS, Android, macOS e Windows per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati. 

In questa fase, è necessario registrare i dispositivi in Intune e creare e applicare criteri per garantire la sicurezza e la protezione dei dati. L'intera documentazione della raccolta di Intune è [disponibile online](https://docs.microsoft.com/intune). È inoltre consigliabile esaminare la [Guida alla pianificazione della distribuzione, alla progettazione e all'implementazione di Intune](https://docs.microsoft.com/intune/planning-guide) prima di iniziare.

## <a name="step-1-plan-for-your-scenario"></a>Passaggio 1: pianificare lo scenario

Uno dei motivi principali per la gestione dei dispositivi mobili è la sicurezza e la protezione delle risorse dell'organizzazione. [Metodi comuni per l'utilizzo di Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) elenca alcuni esempi reali, tra cui la protezione dei dati e della posta elettronica Microsoft.

Intune offre opzioni per la gestione dell'accesso all'organizzazione tramite la gestione dei dispositivi mobili (MDM) o la gestione delle applicazioni mobili (MAM). MDM è il momento in cui gli utenti "iscrivono" i propri dispositivi in Intune. Una volta registrati, sono dispositivi gestiti e possono ricevere tutti i criteri, le regole e le impostazioni utilizzate dall'organizzazione. Ad esempio, è possibile installare app specifiche, creare un criterio password, installare una connessione VPN e altro ancora.

Gli utenti che dispongono di dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri. Tuttavia, è comunque necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, è possibile proteggere le app utilizzando MAM. Ad esempio, è possibile utilizzare un criterio MAM che richiede a un utente di immettere un PIN quando si accede a SharePoint nel dispositivo.

È inoltre possibile determinare come gestire i dispositivi personali o di proprietà dell'organizzazione. È possibile che si desideri gestire i dispositivi in modo diverso, a seconda dell'utilizzo. Ad esempio, è possibile che si desiderino piani diversi per gli utenti delle risorse umane (HR) o degli utenti nelle vendite. [Identificare gli scenari di utilizzo della gestione dei dispositivi mobili](https://docs.microsoft.com/intune/planning-guide-scenarios) consente di iniziare e include alcune linee guida su questi diversi scenari.

## <a name="step-2-get-your-prerequisites"></a>Passaggio 2: ottenere i prerequisiti

Successivamente, ottenere i prerequisiti in base alle proprie esigenze e agli scenari creati nel passaggio precedente. [Implementare il piano](https://docs.microsoft.com/intune/planning-guide-onboarding) elenca tutti i requisiti. Di seguito sono riprodotti gli elementi significativi necessari per Intune con Microsoft 365:

- **Sottoscrizione a Intune**: inclusa in Microsoft 365 e fornisce l'accesso a Microsoft Intune nel [portale di Azure](https://portal.azure.com)
- **Sottoscrizione microsoft 365**: incluso in Microsoft 365 ed è utilizzato per le app di Office, incluso il messaggio di posta elettronica
- **Azure Active Directory (Azure ad) Premium**: incluso in Microsoft 365 e viene utilizzato per creare gruppi di utenti o di sicurezza. Questi gruppi ricevono i criteri di Intune creati, ad esempio forzando la lunghezza della password per sbloccare un dispositivo. I gruppi creati nella [fase 2:](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) è possibile utilizzare l'identità.

Potrebbe essere necessario disporre di alcuni requisiti aggiuntivi, a seconda delle esigenze dell'organizzazione. Ad esempio, se si intende gestire i dispositivi iOS, è necessario un certificato push di Apple MDM. Se si utilizza Exchange locale, è necessario disporre del connettore di Exchange locale. Questi requisiti aggiuntivi vengono delineati quando si arriva a tali passaggi.

## <a name="step-3-set-up-intune"></a>Passaggio 3: configurare Intune

Intune utilizza molte funzionalità in Azure AD, tra cui il dominio, gli utenti e i gruppi. È inoltre possibile creare nuovi utenti e nuovi gruppi per soddisfare le esigenze aziendali. Ad esempio, è possibile creare un gruppo denominato **dispositivi iOS**o **tutti gli utenti HR**.  Avvalersi di [gruppi dinamici](https://docs.microsoft.com/intune/groups-add) che consentono di creare gruppi di utenti o dispositivi basati su regole semplici o avanzate.

Questo passaggio si concentra sulla configurazione di Intune e sulla sua preparazione per la gestione dei dispositivi.

1. **[Confermare che i dispositivi siano supportati](https://docs.microsoft.com/intune/supported-devices-browsers)**. Conferma che i dispositivi iOS, macOS, Android, Galaxy e Windows sono supportati da Intune. Se l'organizzazione include dispositivi che non sono supportati, i criteri non vengono applicati a tali dispositivi.

2. **[Personalizzare il nome di dominio](https://docs.microsoft.com/intune/custom-domain-name-configure)**. Per impostazione predefinita, in Azure AD viene creato automaticamente un dominio denominato qualcosa di simile a **Your-Domain.onmicrosoft.com** . **onmicrosoft.com** può essere personalizzato per l'organizzazione. Quando si Personalizza, fornisce agli utenti anche un dominio familiare per la connessione a Intune e l'utilizzo delle risorse.

3. **[Accedere a Intune](https://docs.microsoft.com/intune/account-sign-up)**. Quando si esegue l'accesso, è possibile che venga richiesto di immettere le informazioni sull'organizzazione. Intune è incluso in Microsoft 365 e può essere aperto direttamente dall'interfaccia di [amministrazione di microsoft 365](https://admin.microsoft.com). È inoltre possibile aprire Intune direttamente dal [portale di Azure](https://portal.azure.com).

4. **[Scegliere la configurazione di gestione dei dispositivi mobili](https://docs.microsoft.com/intune/mdm-authority-set)**. La prima volta che si utilizza Intune, è necessario abilitare la gestione dei dispositivi. Intune può essere utilizzato come servizio solo cloud, ibrido con Intune e Microsoft endpoint Configuration Manager oppure tramite la gestione dei dispositivi mobili per Office 365. È possibile scegliere quale installazione funziona meglio per l'organizzazione.

5. **[Aggiungere utenti](https://docs.microsoft.com/intune/users-add)** e **[aggiungere gruppi](https://docs.microsoft.com/intune/groups-add)**. 

   È possibile aggiungere manualmente gli utenti o utilizzare l'identità ibrida e Azure AD Connect per sincronizzare gli account utente locali con Intune. È inoltre possibile assegnare ruoli di amministratore a utenti specifici. Gli utenti sono obbligatori, a meno che i dispositivi non siano dispositivi "senza utenti", ad esempio i dispositivi Kiosk.

   I gruppi di Azure AD vengono utilizzati per semplificare la gestione dei dispositivi e degli utenti in Intune. Se si utilizzano i gruppi, è possibile eseguire molte attività diverse. Ad esempio, l'organizzazione vuole richiedere un'app specifica nei dispositivi Android. È possibile creare un gruppo di dispositivi Android e distribuire un criterio con questa app al gruppo.

    In Intune, è possibile aggiungere utenti o gruppi creati nella [fase 2: identità](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Assegnare le licenze](https://docs.microsoft.com/intune/licenses-assign)**. Per gli utenti o i dispositivi da registrare in Intune, è necessaria una licenza Microsoft 365 con il servizio Intune abilitato per accedere al servizio Intune. Assegnare le licenze Microsoft 365, che dispongono del servizio Microsoft Intune abilitato per impostazione predefinita, nell'interfaccia di amministrazione di Microsoft 365 o con PowerShell.

## <a name="step-4-enroll-devices"></a>Passaggio 4: registrare i dispositivi

Per gestire i dispositivi, è necessario che i dispositivi siano registrati in Intune. In qualità di amministratore, verranno configurate le restrizioni di registrazione e i criteri per gli utenti e i dispositivi. Ogni piattaforma del dispositivo (iOS, Android, macOS e Windows) dispone di una vasta gamma di opzioni. Gli utenti possono registrarsi autonomamente. In alternativa, è possibile automatizzare la registrazione in modo che gli utenti eseguano semplicemente l'accesso al dispositivo.

La registrazione è un passaggio fondamentale quando si utilizza Intune. I [dispositivi di registrazione](https://docs.microsoft.com/intune/device-enrollment) elencano i passaggi per i diversi dispositivi.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: registrazione di dispositivi iOS e Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Passaggio 5: aggiungere e distribuire app

Le app sui dispositivi mobili spesso sono il modo più rapido per accedere alle risorse aziendali. 

Sono presenti problemi quando si utilizzano le app, in quanto esistono diversi dispositivi, inclusi i dispositivi personali e i dispositivi aziendali. Inoltre, si desidera proteggere le risorse e i dati dell'organizzazione anche assicurandosi che gli utenti siano produttivi.

Intune è in grado di gestire le app, incluse le app, di assegnarle a utenti o gruppi diversi e di esaminare altre informazioni chiave. Ad esempio, è possibile visualizzare le app che non sono in grado di installare, controllare la versione di un'app e altro ancora.

Quando gli utenti ottengono un dispositivo mobile, una delle prime attività consiste nell'accedere alla posta elettronica e ai documenti dell'organizzazione. Utilizzando Intune, è possibile [creare e distribuire le impostazioni di posta elettronica](https://docs.microsoft.com/intune/email-settings-configure) utilizzando le app di posta elettronica preinstallate nei dispositivi. 

L'articolo [Add Apps](https://docs.microsoft.com/intune/apps/apps-add) elenca i passaggi da eseguire per aggiungere, distribuire, monitorare, configurare e proteggere le app nei dispositivi all'interno dell'organizzazione.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: criteri di conformità del dispositivo](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Passaggio 6: abilitare la conformità e l'accesso condizionale

Nei passaggi precedenti è stato configurato l'ambiente e è stato abilitato Intune. A questo punto, è possibile creare alcuni criteri utilizzando la conformità e l'accesso condizionale.

La conformità e l'accesso condizionale sono importanti per la gestione dei dispositivi. Sono stati creati [criteri di conformità](https://docs.microsoft.com/intune/device-compliance-get-started) che consentono di proteggere le risorse dell'organizzazione. Quando si crea un criterio di conformità, si sta definendo lo standard o la "linea di base" di ciò che un dispositivo deve disporre. Ad esempio, è possibile scegliere un livello di rischio accettabile (o inaccettabile), bloccare i dispositivi jailbroken, richiedere una lunghezza della password e altro ancora. Se questi dispositivi non soddisfano le regole, il che significa che non sono conformi, quindi è possibile bloccare l'accesso alle risorse.

Questo "blocco" introduce [l'accesso condizionale](https://docs.microsoft.com/intune/conditional-access). Se un dispositivo viene considerato non conforme, è possibile bloccare l'accesso alla posta elettronica, a SharePoint e altro ancora.

Intune nel [portale di Azure](https://portal.azure.com) consente di creare questi criteri e di applicarli agli utenti e ai dispositivi. Come procedura consigliata, avviare Small e utilizzare un approccio a fasi. Ad esempio, creare un criterio iOS che blocchi i dispositivi jailbroken. Apply (denominato "Assign" in Intune) il criterio a un gruppo pilota o di test. Dopo il test iniziale, aggiungere altri utenti al gruppo pilota. Se si utilizza un approccio a fasi, è possibile ottenere commenti e suggerimenti da una vasta gamma di tipi di utenti.

Vedere [Introduzione ai criteri di conformità dei dispositivi](https://docs.microsoft.com/intune/device-compliance-get-started) e informazioni [sull'accesso condizionale e Intune?](https://docs.microsoft.com/intune/conditional-access) per iniziare.

## <a name="step-7-apply-features-and-settings"></a>Passaggio 7: applicare caratteristiche e impostazioni

Queste caratteristiche e impostazioni sono spesso considerate la parte "cool" di Intune e sono molto potenti. Dopo aver applicato correttamente alcuni criteri di conformità utilizzando l'accesso condizionale, è possibile creare **profili dispositivo**.

Intune nel [portale di Azure](https://portal.azure.com) consente di creare profili diversi in base alla piattaforma del dispositivo: iOS, MacOS, Android e Windows. Ad esempio, è possibile:

- Utilizzare Endpoint Protection nei dispositivi Windows 10 per abilitare diverse opzioni di BitLocker, inclusa la crittografia.
- Utilizzare la caratteristica delle app limitate nei dispositivi iOS per creare un elenco di applicazioni approvate che possono essere installate. In alternativa, creare un elenco di app vietate.
- Utilizzare le impostazioni del chiosco per scegliere quali app possono essere utilizzate nei dispositivi Android in esecuzione in modalità Kiosk.
- Applicazione di una connessione Wi-Fi e delle relative impostazioni, incluso il tipo di sicurezza, nei dispositivi che eseguono macOS.

[Applicare le caratteristiche e le impostazioni sui dispositivi utilizzando i profili dispositivo](https://docs.microsoft.com/intune/device-profiles) è un ottimo posto per leggere i profili, vedere come creare un profilo e altro ancora.

Tenere presente che è necessario avviare Small e utilizzare un approccio a fasi. Assegnare il profilo a un gruppo pilota o di testing. Assegnare quindi il profilo a più gruppi pilota.

## <a name="step-8-get-to-know-the-other-features"></a>Passaggio 8: conoscere le altre caratteristiche

Intune è un servizio potente e include numerose funzionalità. Di seguito sono riportate alcune altre attività che è possibile eseguire tramite Intune:

- Gestire software e aggiornamenti nei[PC](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)Windows [Devices](https://docs.microsoft.com/intune/windows-update-for-business-configure) & e nei dispositivi [iOS](https://docs.microsoft.com/intune/software-updates-ios)
- Attiva [Microsoft Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) nei dispositivi Windows 10 e utilizza la conformità e l'accesso condizionale per proteggere l'accesso alle risorse aziendali, ad esempio SharePoint o Exchange Online
- Utilizzo di [Lookout](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)e di altri partner per la difesa delle minacce per dispositivi mobili
- Aggiungere un' [autorità di certificazione (CA) partner](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) per emettere e rinnovare i certificati
- [Fornire indicazioni per gli utenti finali](https://docs.microsoft.com/intune/end-user-educate) nell'app portale aziendale, per ottenere app e altro ancora.
- Monitorare le [app](https://docs.microsoft.com/intune/apps-monitor) e i [profili di configurazione e conformità del dispositivo](https://docs.microsoft.com/intune/compliance-policy-monitor)e una maggiore telemetria utilizzando i registri di controllo. È inoltre possibile connettersi al [data warehouse di Intune](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) e utilizzare Power BI per altre esigenze di creazione di report.


## <a name="identity-and-device-access-recommendations"></a>Consigli sull’identità e sull’accesso dei dispositivi

Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l'accesso ai dispositivi, utilizzare i suggerimenti e le impostazioni negli articoli seguenti insieme ai passaggi in questa fase:

- [Prerequisiti](identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni su come gli esperti IT di Microsoft [gestiscono i dispositivi con EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha [distribuito l'infrastruttura di gestione dei dispositivi mobili](contoso-mdm.md) con i servizi cloud di Microsoft 365.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura per la gestione dei dispositivi mobili](mobility-infrastructure-exit-criteria.md)

