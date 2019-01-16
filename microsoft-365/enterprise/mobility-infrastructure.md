---
title: Fase 5 - gestione dei dispositivi mobili
description: Microsoft Enterprise 365 include la gestione di dispositivi mobili utilizzando Microsoft Intune. Esaminare i requisiti e prerequisiti, impostare Intune mediante le risorse di Azure Active Directory, registrare iOS, Mac OS, Android e Windows dispositivi, distribuire apps, creare un profilo di configurazione, utilizzare criteri di conformità e consentire l'accesso condizionale per dispositivi mobili gestione dei dispositivi con Microsoft 365 Enterprise.
keywords: Documentazione Microsoft 365 Microsoft 365 Microsoft 365 Enterprise, la gestione dei dispositivi mobili, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 3afc28f0d21918c027a6a1622a40318e333f7ab4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868936"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fase 5: Gestione dei dispositivi mobili Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Questa caratteristica è applicabile per le versioni di Microsoft Enterprise 365 E3 ed E5*

Microsoft Enterprise 365 include funzionalità che consentono di gestire i dispositivi e le relative App, all'interno dell'organizzazione. Utilizzando Microsoft Intune, è possibile gestire iOS, Android, Mac OS e dispositivi Windows per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati. Intune si integra con Azure Active Directory (Azure Active Directory) e rende possibili gli scenari di business seguenti per 365 Microsoft:

- Archiviare e condividere file all'interno e all'esterno dell'organizzazione per collaborare facilmente nell'organizzazione
- Lavorare ovunque e in qualsiasi momento in modo sicuro attraverso il proprio dispositivo, per ottenere il massimo risultato pur mantenendo flessibile lo stile di lavoro
- Fornire sicurezza, controlli e visibilità, offrendo conformità verificata nel settore agli standard globali
- Proteggere le informazioni e ridurre il rischio di perdita di dati
- Rileva problemi e protezione contro le minacce esterne
- Monitorare, report e analizzare l'attività per rispondere immediatamente per garantire la sicurezza dell'organizzazione
- Proteggere gli utenti e i relativi account

Per ulteriori informazioni, vedere [Trasformazione digitale tramite Microsoft 365](http://transform.microsoft.com). 

In questa fase, registrare i dispositivi in Intune e creare e applicare i criteri che consentono di proteggere i dati. L'intera raccolta di documentazione Intune è [disponibili online](https://docs.microsoft.com/intune). È inoltre consigliabile controllare la [pianificazione della distribuzione Intune, progettazione e implementazione Guida](https://docs.microsoft.com/intune/planning-guide) prima di iniziare.

## <a name="step-1-plan-for-your-scenario"></a>Passaggio 1: Pianificare il proprio scenario

Uno dei motivi principali per la gestione dei dispositivi mobili è sicuro e proteggere le risorse dell'organizzazione. [Metodi comuni per utilizzare Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) sono elencati alcuni esempi di pratiche, tra cui la protezione dei dati e posta elettronica di Office 365.

Intune permette di utilizzare le opzioni per gestire l'accesso all'organizzazione tramite [Mobile Device Management (MDM) o Gestione applicazione Mobile (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions). MDM è quando gli utenti di dispositivi in Intune "registrare". Dopo aver registrato, vengono gestiti i dispositivi e possono ricevere eventuali criteri, regole e impostazioni utilizzate dall'organizzazione. Ad esempio, possono installare App specifiche, creare un criterio di password, installare una connessione VPN e altro ancora.

Gli utenti con i propri dispositivi personali non possibile registrare i dispositivi o gestito da Intune e i criteri. Tuttavia, è necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, è possibile proteggere le app utilizzando MAM. Ad esempio, è possibile utilizzare un criterio MAM che richiede all'utente di immettere un PIN per l'accesso di SharePoint nel dispositivo.

È inoltre sarà determinare la modalità che si desidera gestire i dispositivi personali o proprietà dell'organizzazione. È consigliabile considerare i dispositivi in modo diverso a seconda della loro utilizzo. Ad esempio, è possibile diversi piani per gli utenti nel reparto risorse umane (HR) o utenti del reparto vendite. [Gli scenari in caso di utilizzo di gestione di identità dispositivi mobili](https://docs.microsoft.com/intune/planning-guide-scenarios) possono iniziare e sono inclusi alcuni consigli su come i diversi scenari.

## <a name="step-2-get-your-prerequisites"></a>Passaggio 2: Ottenere i prerequisiti

Successivamente, ottenere i prerequisiti in base alle esigenze e gli scenari creati nel passaggio precedente. [Implementare il piano](https://docs.microsoft.com/intune/planning-guide-onboarding) vengono elencati tutti i requisiti. Di seguito sono contenuti gli elementi significativi che necessari per Intune con Microsoft 365:

- **Sottoscrizione Intune**: incluso in Microsoft 365 e consente di accedere a Microsoft Intune nel [portale di Azure](https://portal.azure.com)
- **Sottoscrizione a Office 365**: incluso in Microsoft 365 e viene utilizzato per le applicazioni di Office, inclusa la posta elettronica
- **Premium di Azure Active Directory (AD)**: incluso in Microsoft 365 e viene utilizzato per creare gruppi di sicurezza o utente. Questi gruppi ricevono criteri Intune creati, ad esempio forzare una lunghezza della password per sbloccare un dispositivo. I gruppi creati in [fase 2: identità](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) può essere utilizzato.

È possibile alcuni requisiti aggiuntivi, in base alle esigenze della propria organizzazione. Ad esempio, se sarà Gestione dispositivi iOS, è necessario un certificato Push di Apple MDM. Se si utilizza Exchange in locale, quindi è necessario il connettore di Exchange locale. Quando si arriva a questi passaggi e vengono descritti i requisiti aggiuntivi.

## <a name="step-3-set-up-intune"></a>Passaggio 3: Impostare Intune

Intune utilizza numerose funzionalità disponibili in Azure Active Directory, tra cui il dominio, gli utenti e gruppi. È inoltre possibile creare nuovi utenti e gruppi nuovi adatta a specifiche esigenze dell'organizzazione. Ad esempio, è possibile creare un gruppo denominato **iOS dispositivi**o **utenti di tutte le risorse Umane**.  Trai vantaggio [Gruppi dinamici](https://docs.microsoft.com/intune/groups-add) che consente di creare utenti o gruppi di dispositivi basati sulle regole semplici o avanzate.

Questo passaggio è incentrata su impostazione Intune e operazioni preliminari per gestire i dispositivi.

1. **[Conferma i dispositivi sono supportati](https://docs.microsoft.com/intune/supported-devices-browsers)**. Verificare l'iOS, Mac OS, dispositivi Android, viene e Windows sono supportati da Intune. Se nell'organizzazione sono dispositivi che non sono supportati, i criteri non vengono applicati a tali dispositivi.

2. **[Personalizzare il nome di dominio](https://docs.microsoft.com/intune/custom-domain-name-configure)**. Per impostazione predefinita, un dominio denominato qualcosa di simile **your domain.onmicrosoft.com** viene creato automaticamente in Azure Active Directory. **onmicrosoft.com** può essere personalizzato per l'organizzazione. Quando si personalizza, offre inoltre agli utenti un dominio familiarità quando ci si connette a Intune e utilizzo delle risorse.

3. **[Accedere a Intune](https://docs.microsoft.com/intune/account-sign-up)**. Quando si accede, è possibile che venga chiesto di immettere le informazioni sull'organizzazione. Intune è incluso in Microsoft 365 e può essere aperto direttamente dal [portale di amministrazione di Office 365](https://portal.office.com/). È inoltre possibile aprire Intune direttamente dal [portale di Azure](https://portal.azure.com).

4. **[Scegliere la configurazione di gestione di dispositivi mobili](https://docs.microsoft.com/intune/mdm-authority-set)**. La prima volta che si utilizza Intune, è necessario abilitare la gestione dei dispositivi. Intune può essere utilizzato come servizio solo cloud, ibride con Intune e System Center Configuration Manager o utilizzo di gestione dei dispositivi mobili per Office 365. È possibile scegliere quale programma di installazione è più appropriata per l'organizzazione.

5. **[Aggiungere utenti](https://docs.microsoft.com/intune/users-add)** e **[aggiungere gruppi](https://docs.microsoft.com/intune/groups-add)**. 

   Manualmente è possibile aggiungere utenti o connettersi a Azure Active Directory per gli utenti di sincronizzazione con Intune. È inoltre possibile assegnare ruoli amministrativi a utenti specifici. Gli utenti sono necessari a meno che i dispositivi sono dispositivi "userless", ad esempio dispositivi chiosco multimediale.

   Gruppi di Azure Active Directory vengono utilizzati per semplificare la modalità di gestione di dispositivi e gli utenti in Intune. Utilizzo dei gruppi, è possibile eseguire numerose attività. Ad esempio, l'organizzazione desidera richiedono un'app specifica nei dispositivi Android. È possibile creare un gruppo di dispositivi Android e distribuire un criterio con questa applicazione al gruppo.

    Intune, è possibile aggiungere utenti o gruppi creati in [fase 2: identità](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Assegnare licenze](https://docs.microsoft.com/intune/licenses-assign)**. Per gli utenti o dispositivi per effettuare la registrazione Intune, è necessaria una licenza del dispositivo. Ogni utente o dispositivo userless richiede una licenza Intune per accedere al servizio Intune. Queste licenze sono incluse in Microsoft 365 e devono essere assegnate Intune.

## <a name="step-4-enroll-devices"></a>Passaggio 4: Registrare i dispositivi

Per gestire i dispositivi, i dispositivi devono essere iscritti Intune. In qualità di amministratore, sarà impostare restrizioni di registrazione e i criteri per gli utenti e i dispositivi. Ogni piattaforma del dispositivo (iOS, Android, Mac OS e Windows) con una serie di opzioni. È possibile avere gli utenti di registrare se stessi. In alternativa, è possibile automatizzare la registrazione in modo che gli utenti semplicemente accedere al dispositivo.

La registrazione è fondamentale quando si utilizza Intune. [Dispositivi di registrazione](https://docs.microsoft.com/intune/device-enrollment) sono elencati i passaggi necessari per i dispositivi diversi.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: iOS e registrazione dei dispositivi Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Passaggio 5: Aggiungere e distribuire applicazioni

Apps nei dispositivi mobili sono spesso più rapido modo gli utenti di ottenere l'accesso alle risorse aziendali. 

Esistono problemi affrontati dalle quando si utilizzano App, come sono disponibili diversi dispositivi, inclusi dispositivi di personali e aziendale. E che si desidera proteggere le risorse dell'organizzazione e i relativi dati garantendo che gli utenti siano produttivi.

Intune può gestire le app, tra cui aggiungere applicazioni, assegnarli a utenti o gruppi diversi ed esaminare altri dettagli principali. Ad esempio, è possibile visualizzare quali App errori di installazione, controllare la versione di un'app e altro ancora.

Quando gli utenti ricevono un dispositivo mobile, è una delle prime attività per accedere ai documenti e posta elettronica. Utilizza Intune, è possibile [creare e distribuire impostazioni della posta elettronica](https://docs.microsoft.com/intune/email-settings-configure) mediante app di posta elettronica che sono già installati nei dispositivi. 

[Aggiungi App](https://docs.microsoft.com/intune/app-management) viene illustrata la procedura per aggiungere, distribuire, monitorare, configurare e proteggere apps nei dispositivi all'interno del org.

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Test Lab Guide: Criteri di conformità di dispositivi](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Passaggio 6: Attivare la conformità e l'accesso condizionale

Nei passaggi precedenti, impostare l'ambiente e abilitato Intune. A questo punto, si è pronti creare alcuni criteri utilizzando la conformità e l'accesso condizionale.

Conformità e l'accesso condizionale sono importanti per la gestione dei dispositivi. **[Criteri di conformità](https://docs.microsoft.com/intune/device-compliance-get-started)** vengono creati per proteggere le risorse dell'organizzazione. Quando si crea un criterio di conformità, si definisce lo standard o "previsto" di un dispositivo necessario. Ad esempio, è possibile scegliere un livello di rischio accettabile (o inaccettabili), bloccare i dispositivi jailbroken, richiedono una lunghezza delle password e altro ancora. Se questi dispositivi non soddisfano le regole, il che significa che non è compatibile con, è possibile bloccare l'accesso alle risorse.

Questo "bloccare" introduce **[accesso condizionale](https://docs.microsoft.com/intune/conditional-access)**. Se un dispositivo è considerato non conforme, è possibile bloccare l'accesso alla posta elettronica, SharePoint e altro ancora.

Intune nel [portale Azure](https://portal.azure.com) consente di creare questi criteri e applicarle a utenti e i dispositivi. È consigliabile, avviare piccolo e utilizzare un approccio in più fasi. Ad esempio, creare un criterio di iOS che blocca jailbroken dispositivi. Applicare il criterio (denominato "assegna" Intune) a un gruppo pilota o di testing. Al termine del test iniziali, aggiungere più utenti al gruppo pilota. In modo graduale, è possibile ottenere commenti e suggerimenti da una vasta gamma di tipi di utente.

[Guida introduttiva a criteri di conformità di dispositivi](https://docs.microsoft.com/intune/device-compliance-get-started) e [che cos'è access condizionale?](https://docs.microsoft.com/intune/conditional-access) consentono di iniziare.

## <a name="step-7-apply-features-and-settings"></a>Passaggio 7: Applicare impostazioni e caratteristiche

Queste impostazioni e le funzionalità sono considerate spesso la parte del Intune "interessante" e sono molto potenti. Dopo aver correttamente applicati alcuni criteri di conformità utilizzando access condizionale, si è pronti creare **profili del dispositivo**.

Intune nel [portale Azure](https://portal.azure.com) consente di creare profili diversi in base alla piattaforma del dispositivo - iOS, Mac OS, Android e Windows. Ad esempio, è possibile:

- Utilizzare Endpoint protection nei dispositivi Windows 10 per abilitare diverse opzioni di BitLocker, tra cui la crittografia.
- Utilizzare la funzionalità di App con restrizioni nei dispositivi iOS per creare un elenco di applicazioni approvate che può essere installato. In alternativa, è possibile creare un elenco di applicazioni non consentiti.
- Utilizzare le impostazioni di chioschi multimediali per scegliere quali App può essere utilizzato su dispositivi Android in esecuzione in modalità schermo intero.
- Applicare una connessione Wi-Fi e le impostazioni, incluso il tipo di protezione, su dispositivi che eseguono Mac OS.
- E altro ancora

[Che cosa sono i profili del dispositivo Microsoft Intune?](https://docs.microsoft.com/intune/device-profiles) è un ottimo esempio in lettura sui profili, vedere creare un profilo e altro ancora.

Memorizza, avviare piccolo e utilizzare un approccio in più fasi. Assegnare il profilo a un gruppo pilota o di testing. Quindi, assegnare il profilo a più gruppi pilota.

## <a name="step-8-get-to-know-the-other-features"></a>Passaggio 8: Imparare a conoscere le altre caratteristiche

Intune è un servizio potente e sono incluse numerose caratteristiche. Ecco alcune altre attività che è possibile eseguire utilizzando Intune:

- Gestione di aggiornamenti software e dei [dispositivi](https://docs.microsoft.com/intune/windows-update-for-business-configure)di Windows & [PC](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)e dispositivi [iOS](https://docs.microsoft.com/intune/software-updates-ios)
- Attivare [Windows Defender avanzate Threat Protection (degli strumenti di analisi)](https://docs.microsoft.com/intune/advanced-threat-protection) nei dispositivi Windows 10 e utilizzare accesso condizionato e conformità per la protezione dell'accesso alle risorse aziendali, ad esempio SharePoint o Exchange Online
- Utilizzare [attenzione](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)e altri partner di rischio di difesa per dispositivi mobili
- Aggiungere un [partner certificato autorità di certificazione](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) per emettere e rinnovare i certificati
- [Specificare informazioni aggiuntive per gli utenti finali](https://docs.microsoft.com/intune/end-user-educate) per l'app portale della società, introduzione App e altro ancora
- Monitorare le [App](https://docs.microsoft.com/intune/apps-monitor), monitorare [la conformità di dispositivi](https://docs.microsoft.com/intune/compliance-policy-monitor), monitor [profili di configurazione](https://docs.microsoft.com/intune/compliance-policy-monitor)e ulteriori telemetria utilizzando i registri di controllo. È anche possibile connettersi al [Intune Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) e utilizzare Power BI per esigenze di report ancora più.


## <a name="identity-and-device-access-recommendations"></a>Consigli sull’identità e sull’accesso dei dispositivi

Microsoft offre una serie di suggerimenti per l' [accesso di dispositivi e identità](microsoft-365-policies-configurations.md) garantire una forza lavoro protetta e produttività. Accesso di dispositivi, utilizzare i suggerimenti e le impostazioni negli articoli seguenti con i passaggi descritti in questa fase:

- [Prerequisiti](identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni su come parte di esperti IT presso Microsoft pianificate per e distribuito gestione EMS e dei dispositivi con queste risorse:

- [Gestire la produttività mobile moderna con Enterprise Mobility + Security](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [Lavorare dal proprio dispositivo Windows 10 con Microsoft Intune](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [Abilitare la produttività mobile per i dispositivi iOS, OS X e Android in Microsoft](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come servizi cloud di Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa [distribuito infrastruttura di gestione proprio dispositivo mobile](contoso-mdm.md) con Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

[Criteri di uscita del dispositivo mobile management dell'infrastruttura](mobility-infrastructure-exit-criteria.md)

