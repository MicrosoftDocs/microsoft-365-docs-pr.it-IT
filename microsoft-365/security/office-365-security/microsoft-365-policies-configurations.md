---
title: Configurazioni di identità e accesso ai dispositivi-Microsoft 365 per Enterprise
description: Vengono descritti i suggerimenti e i concetti di base di Microsoft per la distribuzione di criteri e configurazioni sicure di posta elettronica, documenti e app.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/29/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
ms.openlocfilehash: e07c1455cc2799481bc31871d2c3ee07b10492b9
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446184"
---
# <a name="identity-and-device-access-configurations"></a>Configurazioni di identità e accesso dei dispositivi

Il perimetro di sicurezza moderno dell'organizzazione ora si estende oltre la rete per includere gli utenti che accedono alle app basate su cloud da qualsiasi percorso con una vasta gamma di dispositivi. L'infrastruttura di sicurezza deve determinare se una richiesta di accesso specificata deve essere concessa e in quali condizioni. 

Questa determinazione deve basarsi sull'account utente dell'accesso, sul dispositivo utilizzato, sull'app che l'utente utilizza per accedere, sul percorso da cui viene eseguita la richiesta di accesso e sulla valutazione del rischio della richiesta. Questa funzionalità garantisce che solo gli utenti e i dispositivi autorizzati possano accedere alle risorse cruciali dell'utente.

In questa serie di articoli viene descritto un insieme di configurazioni dei prerequisiti di accesso a identità e dispositivi e un set di accessi condizionali di Azure Active Directory (Azure AD), Microsoft Intune e altri criteri per garantire l'accesso a Microsoft 365 per le app e i servizi cloud aziendali, altri servizi SaaS e applicazioni locali pubblicate con proxy di applicazione Azure AD.

Le impostazioni e i criteri di accesso ai dispositivi e alle identità sono consigliati in tre livelli: protezione di base, protezione riservata e protezione per ambienti con dati altamente regolamentati o classificati. Questi livelli, e le loro configurazioni corrispondenti, offrono livelli costanti di protezione per tutti i dati, le identità e i dispositivi.

Queste funzionalità e i relativi suggerimenti:

- Sono supportate in Microsoft 365 E3 e Microsoft 365 E5.
- Sono allineati con [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) così come il [Punteggio di identità in Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)e aumentano questi punteggi per l'organizzazione.
- Consentirà di implementare questi [cinque passaggi per proteggere l'infrastruttura di identità](https://docs.microsoft.com/azure/security/azure-ad-secure-steps).

Se nell'organizzazione sono presenti requisiti o complessità univoci per l'ambiente, utilizzare questi suggerimenti come punto di partenza. Tuttavia, la maggior parte delle organizzazioni può implementare questi suggerimenti come prescritto.

>[!Note]
>Microsoft vende anche licenze Enterprise Mobility + Security (EMS) per le sottoscrizioni di Office 365. Le funzionalità EMS E3 e EMS E5 sono equivalenti a quelle di Microsoft 365 E3 e Microsoft 365 E5. Vedere i [piani di EMS](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) per i dettagli.
>

## <a name="intended-audience"></a>Pubblico previsto

Tali raccomandazioni sono destinate a Enterprise Architects e ai professionisti IT che hanno familiarità con Microsoft 365 cloud Productivity and Security Services, che include Azure AD (Identity), Microsoft Intune (Device Management) e Azure Information Protection (Data Protection).

### <a name="customer-environment"></a>Ambiente del cliente

I criteri consigliati sono applicabili alle organizzazioni aziendali che operano sia interamente all'interno del cloud Microsoft sia per i clienti con infrastruttura di identità ibrida, che è una foresta di servizi di dominio Active Directory locale che viene sincronizzata con un tenant di Azure AD.

Molte delle raccomandazioni fornite si basano sui servizi disponibili solo con Microsoft 365 E5, Microsoft 365 E3 con l'identità & il componente aggiuntivo di protezione dalle minacce, EMS E5 o le licenze P2 di Azure Premium.

Per le organizzazioni che non dispongono di queste licenze, Microsoft consiglia di implementare almeno le [impostazioni predefinite](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)per la sicurezza, che è inclusa in tutti i piani di Microsoft 365. 

### <a name="caveats"></a>Avvertimenti

L'organizzazione può essere soggetta a requisiti normativi o di altro tipo, tra cui consigli specifici che potrebbero richiedere l'applicazione di criteri che divergono da queste configurazioni consigliate. Tali configurazioni consigliano controlli dell'utilizzo non disponibili in precedenza. Questi controlli sono consigliati perché riteniamo che rappresentino un equilibrio tra sicurezza e produttività.  

In questo modo, è possibile tenere conto di una vasta gamma di requisiti di protezione dell'organizzazione, ma non si è in grado di tenere conto di tutti i requisiti possibili o di tutti gli aspetti univoci della propria azienda.

## <a name="three-tiers-of-protection"></a>Tre livelli di protezione

La maggior parte delle organizzazioni hanno requisiti specifici relativi a sicurezza e protezione dei dati. Tali requisiti variano in base al settore e alle mansioni lavorative all'interno delle organizzazioni. Ad esempio, il reparto legale e gli amministratori possono richiedere ulteriori controlli di sicurezza e protezione delle informazioni attorno alla corrispondenza di posta elettronica non necessari per altre unità aziendali. 

Ogni settore ha anche il proprio set di normative specializzate. Piuttosto che fornire un elenco di tutte le opzioni di sicurezza possibili o una raccomandazione per segmento di settore o funzione del processo, sono state fornite indicazioni per tre diversi livelli di sicurezza e protezione che possono essere applicati in base alla granularità delle proprie esigenze.

- **Protezione di base**: si consiglia di stabilire uno standard minimo per la protezione dei dati, nonché le identità e i dispositivi che accedono ai dati. È possibile seguire questi suggerimenti di base per fornire una protezione predefinita complessa che soddisfi le esigenze di molte organizzazioni.
- **Protezione sensibile**: alcuni clienti dispongono di un sottoinsieme di dati che devono essere protetti a livelli superiori oppure possono richiedere che tutti i dati siano protetti a un livello superiore. È possibile applicare una maggiore protezione a tutti o a set di dati specifici nell'ambiente Microsoft 365. È consigliabile proteggere le identità e i dispositivi che accedono ai dati sensibili con livelli di sicurezza analoghi.  
- **Altamente regolamentato**: alcune organizzazioni potrebbero avere una piccola quantità di dati altamente classificati, costituiti da segreti commerciali o da dati regolamentati. Microsoft offre funzionalità che consentono alle organizzazioni di soddisfare questi requisiti, inclusa la protezione aggiuntiva per identità e dispositivi.

![Cono di sicurezza: tutti i clienti > alcuni clienti > clienti specifici. Applicazione estensiva a un'applicazione specifica](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

In questa guida viene illustrato come implementare la protezione per identità e dispositivi per ognuno di questi livelli di protezione. Utilizzare queste linee guida come punto di partenza per l'organizzazione e regolare i criteri per soddisfare i requisiti specifici dell'organizzazione.

È importante utilizzare livelli di protezione coerenti tra dati, identità e dispositivi. Ad esempio, se si implementano queste linee guida, assicurarsi di proteggere i dati a livelli comparabili. 

Il modello **di architettura di Microsoft 365 per l'identità e la protezione dei dispositivi** indica quali funzionalità sono confrontabili.

[![Immagine del pollice per l'identità e la protezione del dispositivo per il poster di Microsoft 365](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br/>  [Visualizzazione in formato PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Scarica come PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Scaricare come Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Vedere inoltre la soluzione [deploy Information Protection for data privacy Regulations](../../solutions/information-protection-deploy.md) per proteggere le informazioni archiviate in Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Compromesso tra sicurezza e produttività

L'implementazione di qualsiasi strategia di sicurezza richiede compromessi tra la sicurezza e la produttività. È utile valutare il modo in cui ogni decisione influisce sul saldo di sicurezza, funzionalità e facilità d'uso.

![Sicurezza Triad bilanciamento, funzionalità e facilità di utilizzo.](../../media/microsoft-365-policies-configurations/security-triad.png)

Le raccomandazioni fornite si basano sui seguenti principi:

- Conoscere gli utenti ed essere flessibili per la sicurezza e i requisiti funzionali.
- Applicare un criterio di sicurezza appena in tempo e assicurarsi che sia significativo.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Servizi e concetti relativi a identità e protezione dall'accesso ai dispositivi

Microsoft 365 for Enterprise è stato ideato per le organizzazioni di grandi dimensioni per consentire a tutti di essere creativi e di collaborare in modo sicuro.

In questa sezione viene fornita una panoramica dei servizi e delle funzionalità di Microsoft 365 che sono importanti per l'accesso a identità e dispositivi.

### <a name="azure-ad"></a>Azure AD

Azure AD offre una serie completa di funzionalità di gestione delle identità. È consigliabile utilizzare queste funzionalità per garantire l'accesso.

| Capacità o funzionalità | Descrizione | Licenze |
|:-------|:-----|:-------|
| [Autenticazione a più fattori (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks) | L'AMF richiede agli utenti di fornire due forme di verifica, ad esempio una password utente e una notifica dall'app Microsoft Authenticator o da una telefonata. Il Master riduce notevolmente il rischio che le credenziali rubate possano essere utilizzate per accedere all'ambiente. Microsoft 365 utilizza il servizio di autenticazione a più fattori di Azure per gli accessi basati su AMF. | Microsoft 365 E3 o E5 |
| [Accesso condizionale](/azure/active-directory/conditional-access/overview) | Azure AD valuta le condizioni dell'accesso dell'utente e utilizza i criteri di accesso condizionale per determinare gli accessi consentiti. Ad esempio, in questa guida viene illustrato come creare un criterio di accesso condizionale per richiedere la conformità del dispositivo all'accesso ai dati riservati. In questo modo si riduce notevolmente il rischio che un hacker con il proprio dispositivo e le credenziali rubate possano accedere ai dati riservati. Protegge inoltre i dati sensibili nei dispositivi, in quanto i dispositivi devono soddisfare requisiti specifici per la sicurezza e l'integrità. | Microsoft 365 E3 o E5 |
| [Gruppi di Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups) | I criteri di accesso condizionale, la gestione dei dispositivi con Intune e persino le autorizzazioni per i file e i siti dell'organizzazione si basano sull'assegnazione agli account utente o ai gruppi di Azure AD. Si consiglia di creare gruppi di Azure AD che corrispondono ai livelli di protezione che si stanno implementando. Ad esempio, il personale esecutivo è probabilmente un obiettivo di valore superiore per gli hacker. Pertanto, è opportuno aggiungere gli account utente di questi dipendenti a un gruppo di Azure AD e assegnare questo gruppo ai criteri di accesso condizionale e ad altri criteri che applicano un livello di protezione più elevato per l'accesso. | Microsoft 365 E3 o E5 |
| [Registrazione del dispositivo](/azure/active-directory/devices/overview) | La registrazione di un dispositivo in Azure AD per la creazione di un'identità per il dispositivo. Questa identità viene utilizzata per autenticare il dispositivo quando un utente accede e per applicare criteri di accesso condizionale che richiedono PC conformi a un dominio. Per queste linee guida, viene utilizzata la registrazione dei dispositivi per registrare automaticamente i computer Windows con join di dominio. La registrazione del dispositivo è un prerequisito per la gestione dei dispositivi con Intune. | Microsoft 365 E3 o E5 |
| [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview) | Consente di rilevare potenziali vulnerabilità che interessano le identità dell'organizzazione e configurare i criteri di correzione automatici per il rischio di accesso basso, medio e alto e per i rischi dell'utente. Questa guida si basa su questa valutazione dei rischi per applicare criteri di accesso condizionale per l'autenticazione a più fattori. Questa guida include anche un criterio di accesso condizionale che richiede agli utenti di modificare la propria password se viene rilevata un'attività ad alto rischio per il proprio account. | Microsoft 365 E5, Microsoft 365 E3 con il componente aggiuntivo Identity & Threat Protection, EMS E5 o le licenze P2 di Azure Premium |
| [Reimpostazione della password in modalità self-service (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks) | Consente agli utenti di reimpostare le password in modo sicuro e senza l'intervento di supporto tecnico, fornendo la verifica di più metodi di autenticazione che l'amministratore può controllare. | Microsoft 365 E3 o E5 |
| [Protezione delle password di Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Individuare e bloccare le password deboli note e le relative varianti e i termini deboli aggiuntivi specifici per l'organizzazione. Gli elenchi predefiniti di password escluse globalmente sono applicate automaticamente a tutti gli utenti dei tenant di Azure AD. È possibile definire altre voci in un elenco di password escluse personalizzato. Quando gli utenti modificano o reimpostano le loro password, gli elenchi di password escluse sono controllati per applicare l'uso di password sicure. |  Microsoft 365 E3 o E5 |
||||

Di seguito sono inclusi i componenti di accesso alle identità e ai dispositivi, tra cui gli oggetti, le impostazioni e i servizi secondari di Intune e Azure AD.

![Componenti dell'accesso a identità e dispositivi](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) è il servizio di gestione dei dispositivi mobili basato sul cloud di Microsoft. Le linee guida consigliate per la gestione dei dispositivi Windows PC con Intune e consigliate configurazioni di criteri di conformità del dispositivo. Intune determina se i dispositivi sono conformi e li invia a Azure ad per l'applicazione dei criteri di accesso condizionale.

#### <a name="intune-app-protection"></a>Protezione delle app di Intune

I criteri di [protezione delle app di Intune](https://docs.microsoft.com/intune/app-protection-policy) possono essere utilizzati per proteggere i dati dell'organizzazione nelle app per dispositivi mobili, con o senza la registrazione di periferiche in gestione. Intune consente di proteggere le informazioni, assicurandosi che i dipendenti possano continuare a essere produttivi e prevenire la perdita di dati. Se si implementano i criteri a livello di app, è possibile limitare l'accesso alle risorse aziendali e mantenere i dati all'interno del controllo del reparto IT.

In questa guida viene illustrato come creare criteri consigliati per applicare l'utilizzo di app approvate e per determinare in che modo queste app possono essere utilizzate con i dati aziendali.

### <a name="microsoft-365"></a>Microsoft 365

In questa guida viene illustrato come implementare un insieme di criteri per proteggere l'accesso ai servizi cloud di Microsoft 365, tra cui Microsoft teams, Exchange Online, SharePoint Online e OneDrive for business. Oltre all'implementazione di questi criteri, è consigliabile aumentare anche il livello di protezione per il tenant utilizzando queste risorse:

- [Configurare il tenant per una maggiore sicurezza](tenant-wide-setup-for-increased-security.md)

  Consigli che si applicano alla sicurezza di base per il tenant.

- [Roadmap sulla sicurezza: priorità principali per i primi 30 giorni, 90 giorni e oltre](security-roadmap.md)

  Consigli che includono la registrazione, la governance dei dati, l'accesso di amministratore e la protezione dalle minacce.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 e App Microsoft 365 per grandi imprese

Windows 10 con Microsoft 365 Apps for Enterprise è l'ambiente client consigliato per i PC. È consigliabile utilizzare Windows 10 perché Azure è stato creato per offrire un'esperienza più agevole possibile sia per gli ambienti locali che per gli Azure AD. Windows 10 include anche funzionalità di sicurezza avanzate che possono essere gestite tramite Intune. Microsoft 365 Apps for Enterprise include le versioni più recenti delle applicazioni di Office. Questi utilizzano l'autenticazione moderna, che è più sicura e un requisito per l'accesso condizionale. Queste app includono anche strumenti avanzati per la sicurezza e la conformità.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Applicazione di queste funzionalità tra i tre livelli di protezione

Nella tabella seguente vengono riepilogati i suggerimenti per l'utilizzo di queste funzionalità tra i tre livelli di protezione.

|Meccanismo di protezione|Protezione di base|Dati sensibili|Riservatezza elevata|
|:-------------------|:-------|:--------|:---------------|
|**Applicare l'autenticazione a più fattori**|A partire da rischio di accesso medio|A partire da rischio di accesso basso|Per tutte le nuove sessioni|
|**Applicare la modifica della password**|Per gli utenti con rischio elevato|Per gli utenti con rischio elevato|Per gli utenti con rischio elevato|
|**Applicare la protezione delle applicazioni di Intune**|Sì|Sì|Sì|
|**Applicare la registrazione di Intune per il dispositivo di proprietà dell'organizzazione**|Richiedere un PC conforme o aggiunto a un dominio, ma consentire telefoni e Tablet BYOD (Bring-Your-Own Devices)|Richiedere un dispositivo conforme o collegato a un dominio|Richiedere un dispositivo conforme o collegato a un dominio|

## <a name="device-ownership"></a>Proprietà del dispositivo

La tabella di cui sopra riflette l'andamento di molte organizzazioni a supportare una combinazione di dispositivi di proprietà dell'organizzazione, nonché personale o BYODs per consentire la produttività mobile in tutta la forza lavoro. I criteri di protezione delle app di Intune assicurano che la posta elettronica sia protetta da exfiltrating fuori dell'app di Outlook Mobile e di altre app per dispositivi mobili di Office, sia a livello di proprietà dell'organizzazione sia BYODs.  

È consigliabile gestire i dispositivi di proprietà dell'organizzazione da Intune o da un dominio aggiunto per applicare protezioni e controlli aggiuntivi. A seconda della sensibilità dei dati, l'organizzazione può scegliere di non consentire l'utilizzo di BYODs per specifiche popolazioni di utenti o app specifiche.

## <a name="deployment-and-your-apps"></a>Distribuzione e app

Prima di configurare e distribuire la configurazione di identità e accesso ai dispositivi per le app integrate in Azure AD, è necessario eseguire le operazioni seguenti: 

- Decidere quali app utilizzare nell'organizzazione si desidera proteggere. 
- Analizzare questo elenco di app per determinare i gruppi di criteri che offrono livelli di protezione adeguati. 

  Non è consigliabile creare insiemi di criteri distinti per ogni app perché la loro gestione può risultare ingombrante. Microsoft consiglia di raggruppare le app con gli stessi requisiti di protezione per gli stessi utenti. 

  Ad esempio, è possibile disporre di un set di criteri che includa tutte le app Microsoft 365 per tutti gli utenti per la protezione di base e un secondo set di criteri per tutte le app sensibili, ad esempio quelle utilizzate dalle risorse umane o dai reparti finanziari, e applicarle a tali gruppi. 

Dopo aver determinato il set di criteri per le app che si desidera proteggere, eseguire il rollforward dei criteri in modo incrementale, affrontando i problemi lungo il percorso.  

Ad esempio, configurare i criteri che verranno utilizzati per tutte le app Microsoft 365 solo per Exchange Online con le modifiche aggiuntive per Exchange. Eseguire il rollforward dei criteri per gli utenti e risolvere eventuali problemi. Aggiungere quindi i team con le relative modifiche aggiuntive e riportarlo agli utenti. Aggiungere quindi SharePoint con le modifiche aggiuntive. Continuare ad aggiungere le altre app fino a quando non è possibile configurare con sicurezza questi criteri di base per includere tutte le app di Microsoft 365. 

Analogamente, per le app sensibili, creare il set di criteri e aggiungere un'app alla volta e risolvere eventuali problemi finché non sono tutti inclusi nel set di criteri per le app sensibili. 

Microsoft consiglia di non creare set di criteri che si applicano a tutte le app, perché possono verificarsi alcune configurazioni indesiderate. Ad esempio, i criteri che bloccano tutte le app potrebbero bloccare gli amministratori fuori dal portale di Azure e le esclusioni non possono essere configurate per endpoint importanti come Microsoft Graph. 

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Passaggi del processo di configurazione dell'identità e dell'accesso ai dispositivi

![Procedura per configurare l'accesso a identità e dispositivi.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Configurare le funzionalità di identità dei prerequisiti e le relative impostazioni.
2. Configurare i criteri di accesso condizionale e di identità comuni.
3. Configurare i criteri di accesso condizionale per gli utenti guest ed esterni.
4. Configurare i criteri di accesso condizionale per le app cloud di Microsoft 365, ad esempio Microsoft teams, Exchange Online e SharePoint.

## <a name="next-step"></a>Passaggio successivo

[Lavoro prerequisito per l'implementazione dei criteri di identità e accesso ai dispositivi](identity-access-prerequisites.md)
