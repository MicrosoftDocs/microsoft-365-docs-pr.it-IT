---
title: Esaminare i requisiti di architettura e la struttura Microsoft Cloud App Security, pianificare la configurazione e la progettazione conoscendo il framework di Cloud App Security in Microsoft 365 Defender
description: Microsoft Cloud App Security diagrammi tecnici illustrano l'architettura in Microsoft 365 Defender, che consente di creare un ambiente pilota.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a3fa9670262b90d1566c375680946a131bb9c78a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458015"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-cloud-app-security"></a>Esaminare i requisiti di architettura e i concetti chiave per Microsoft Cloud App Security


**Si applica a:**

- Microsoft 365 Defender

Questo articolo è [il passaggio 1 di 3 nel](eval-defender-mcas-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Cloud App Security insieme Microsoft 365 Defender. Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-identity-overview.md).

Prima di Microsoft Cloud App Security, assicurarsi di conoscere l'architettura e di soddisfare i requisiti. 

## <a name="understand-the-architecture"></a>Informazioni sull'architettura

Microsoft Cloud App Security è un Cloud Access Security Broker (CASB). I casb agiscono da gatekeeper per mediare l'accesso in tempo reale tra gli utenti aziendali e le risorse cloud che usano, ovunque gli utenti si trovino e indipendentemente dal dispositivo in uso. Microsoft Cloud App Security si integra in modo nativo con le funzionalità di sicurezza Microsoft, tra cui Microsoft 365 Defender. 

Senza Cloud App Security, le app cloud usate dall'organizzazione sono non gestite e non protette, come illustrato.

![Architettura per Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-architecture-a.png)

Nella figura:
- L'uso di app cloud da parte di un'organizzazione non è monitorato e non protetto. 
- Questo utilizzo non rientra nelle protezioni ottenute all'interno di un'organizzazione gestita. 

#### <a name="discovering-cloud-apps"></a>Individuazione delle app cloud

Il primo passaggio per gestire l'uso delle app cloud consiste nell'individuare le app cloud usate dall'organizzazione. Questo diagramma successivo illustra il funzionamento dell'individuazione cloud con Cloud App Security.

![Architettura per Microsoft Cloud App Security - Individuazione cloud](../../media/defender/m365-defender-mcas-architecture-b.png)

In questa figura sono disponibili due metodi che possono essere usati per monitorare il traffico di rete e individuare le app cloud utilizzate dall'organizzazione.
- R. Cloud App Discovery si integra con Microsoft Defender for Endpoint in modo nativo. Defender for Endpoint segnala l'accesso alle app e ai servizi cloud da dispositivi Windows 10 IT. 
- B. Per la copertura su tutti i dispositivi connessi a una rete, l'Cloud App Security di log viene installato nei firewall e in altri proxy per raccogliere dati dagli endpoint. Questi dati vengono inviati a Cloud App Security per l'analisi.

#### <a name="managing-cloud-apps"></a>Gestione delle app cloud

Dopo aver scoperto le app cloud e aver analizzato il comportamento di queste app usate dall'organizzazione, puoi iniziare a gestire le app cloud che scegli. 

![Architettura per Microsoft Cloud App Security - Gestione delle app cloud](../../media/defender/m365-defender-mcas-architecture-c.png)

In questa illustrazione:
- Alcune app sono sanzionate per l'uso. Questo è un modo semplice per iniziare a gestire le app.
- Puoi abilitare maggiore visibilità e controllo connettendo le app con i connettori dell'app. I connettori di app usano le API dei provider di app.


#### <a name="applying-session-controls-to-cloud-apps"></a>Applicazione di controlli di sessione alle app cloud

Microsoft Cloud App Security funge da proxy inverso, fornendo l'accesso proxy alle app cloud sanzionate. Ciò consente Cloud App Security di applicare i controlli di sessione che si configurano. 

![Architettura per Microsoft Cloud App Security - Controllo della sessione di accesso proxy](../../media/defender/m365-defender-mcas-architecture-d.png)

In questa illustrazione:
- L'accesso alle app cloud sanzionate da utenti e dispositivi dell'organizzazione viene instradato attraverso Cloud App Security.
- Questo accesso proxy consente di applicare i controlli della sessione.
- Le app cloud non sanzionate o esplicitamente non sanzionate non sono interessate.

I controlli di sessione consentono di applicare parametri al modo in cui le app cloud vengono usate dall'organizzazione. Ad esempio, se l'organizzazione usa Salesforce, è possibile configurare un criterio di sessione che consenta solo ai dispositivi gestiti di accedere ai dati dell'organizzazione in Salesforce. Un esempio più semplice potrebbe essere la configurazione di un criterio per monitorare il traffico da dispositivi non gestiti in modo da poter analizzare il rischio di questo traffico prima di applicare criteri più rigidi.

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>Integrazione con Azure AD con il controllo dell'app con accesso condizionale

Potresti già aggiungere app SaaS al tenant di Azure AD per applicare l'autenticazione a più fattori e altri criteri di accesso condizionale. Microsoft Cloud App Security si integra in modo nativo con Azure AD. Tutto ciò che devi fare è configurare un criterio in Azure AD per usare il controllo dell'app di accesso condizionale in Cloud App Security. In questo modo il traffico di rete per queste app SaaS gestite viene instradato tramite Cloud App Security come proxy, che consente a Cloud App Security di monitorare questo traffico e di applicare i controlli della sessione. 

![Architettura per Microsoft Cloud App Security - App SaaS](../../media/defender/m365-defender-mcas-architecture-e.png)

In questa illustrazione:
- Le app SaaS sono integrate con il tenant di Azure AD. Ciò consente ad Azure AD di applicare criteri di accesso condizionale, inclusa l'autenticazione a più fattori.
- Viene aggiunto un criterio per Azure Active Directory indirizzare il traffico per le app SaaS a Cloud App Security. Il criterio specifica a quali app SaaS applicare questo criterio. Di conseguenza, dopo che Azure AD applica i criteri di accesso condizionale che si applicano a queste app SaaS, Azure AD indirizza (proxy) il traffico della sessione attraverso Cloud App Security.
- Cloud App Security questo traffico e applica tutti i criteri di controllo della sessione configurati dagli amministratori. 

Potresti aver individuato e sanzionato app cloud usando Cloud App Security che non sono state aggiunte ad Azure AD. Puoi sfruttare il controllo delle app di accesso condizionale aggiungendo queste app cloud al tenant di Azure AD e l'ambito delle regole di accesso condizionale.

#### <a name="protecting-your-organization-from-hackers"></a>Protezione dell'organizzazione da hacker

Cloud App Security offre una protezione efficace. Tuttavia, se combinato con le altre funzionalità di Microsoft 365 Defender, Cloud App Security fornisce dati nei segnali condivisi che, insieme, aiutano a bloccare gli attacchi.

Vale la pena ripetere questa illustrazione dalla panoramica a questa guida Microsoft 365 Defender e pilota. 

![Come Microsoft 365 Defender una catena di minacce](../../media/defender/m365-defender-eval-threat-chain.png)

Concentrandosi sul lato destro di questa illustrazione, Microsoft Cloud App Security rileva comportamenti anomali come viaggi impossibili, accesso alle credenziali e attività insolite di download, condivisione file o inoltro della posta e le segnala al team di sicurezza. Di conseguenza, Cloud App Security impedisce lo spostamento laterale da parte di hacker e l'esfiltrazione di dati sensibili. Microsoft 356 Defender correla i segnali di tutti i componenti per fornire la storia di attacco completa.

## <a name="understand-key-concepts"></a>Comprendere i concetti chiave

Nella tabella seguente sono stati identificati i concetti chiave importanti da comprendere durante la valutazione, la configurazione e la Microsoft Cloud App Security.


|Concetti  |Descrizione |Ulteriori informazioni  |
|---------|---------|---------|
| Cloud App Security Dashboard | Presenta una panoramica delle informazioni più importanti sull'organizzazione e fornisce collegamenti a un'indagine più approfondita.        | [Utilizzo del dashboard ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| Controllo app per l'accesso condizionale    | Architettura del proxy inverso che si integra con il provider di identità (IdP) per fornire criteri di accesso condizionale di Azure AD e applicare in modo selettivo i controlli della sessione.        |  [Proteggere le app con Microsoft Cloud App Security controllo dell'app con accesso condizionale](/cloud-app-security/proxy-intro-aad)       |
|  Catalogo app cloud   | Il Catalogo app cloud offre un'immagine completa rispetto al catalogo Microsoft di oltre 16.000 app cloud classificate e classificate in base a più di 80 fattori di rischio.    |  [Utilizzo dei punteggi di rischio delle app](/cloud-app-security/risk-score)       |
| Cloud Discovery Dashboard    | Cloud Discovery analizza i log del traffico ed è progettato per fornire maggiori informazioni su come vengono usate le app cloud nell'organizzazione, nonché per fornire avvisi e livelli di rischio.     |  [Uso delle app individuate   ](/cloud-app-security/discovered-apps)    |
|App connesse |Cloud App Security offre protezione end-to-end per le app connesse tramite l'integrazione da cloud a cloud, connettori API e controlli di accesso e sessione in tempo reale sfruttando i controlli di accesso condizionale alle app. |[Protezione delle app connesse](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>Esaminare i requisiti dell'architettura

### <a name="discovering-cloud-apps"></a>Individuazione delle app cloud

Per individuare le app cloud usate nell'ambiente, è possibile eseguire una o entrambe le operazioni seguenti:

- Iniziare rapidamente a utilizzare Cloud Discovery integrandosi con Microsoft Defender for Endpoint. Questa integrazione nativa consente di avviare immediatamente la raccolta di dati sul traffico cloud nei dispositivi Windows 10, all'interno e all'uscita dalla rete.
- Per individuare tutte le app cloud accessibili da tutti i dispositivi connessi alla rete, distribuire l'Cloud App Security di log nei firewall e in altri proxy. In questo modo vengono raccolti i dati dagli endpoint e inviati a Cloud App Security per l'analisi. Cloud App Security si integra in modo nativo con alcuni proxy di terze parti per altre funzionalità.

Queste opzioni sono incluse nel [passaggio 2. Abilitare l'ambiente di valutazione](eval-defender-mcas-enable-eval.md). 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>Applicazione dei criteri di accesso condizionale di Azure AD alle app cloud

Il controllo delle app di accesso condizionale (la possibilità di applicare criteri di accesso condizionale alle app cloud) richiede l'integrazione con Azure AD. Questo non è un requisito per iniziare a usare Cloud App Security. È un passaggio che ti invitiamo a provare durante la fase pilota, [passaggio 3. Progetto pilota Microsoft Cloud App Security](eval-defender-mcas-pilot.md).

## <a name="siem-integration"></a>Integrazione SIEM

È possibile integrare Microsoft Cloud App Security con il server SIEM generico o con Azure Sentinel per abilitare il monitoraggio centralizzato di avvisi e attività da app connesse. 

Azure Sentinel include inoltre un connettore Microsoft Cloud App Security per fornire un'integrazione più approfondita con Azure Sentinel. Ciò consente non solo di ottenere visibilità nelle app cloud, ma anche di ottenere analisi sofisticate per identificare e contrastare le minacce informatiche e controllare il modo in cui viaggiano i dati.

- [Integrazione SIEM generica](/cloud-app-security/siem)
- [Stream alerts and Cloud Discovery logs from MCAS into Azure Sentinel](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>Passaggi successivi

Passaggio 2 di 3: [Abilitare l'ambiente di valutazione per Microsoft Cloud App Security](eval-defender-mcas-enable-eval.md)

Tornare alla panoramica di [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)