---
title: Proteggere la collaborazione con Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Informazioni su come configurare la collaborazione sicura dei contenuti in Teams per proteggere i dati in base alla relativa riservatezza.
ms.openlocfilehash: 88cb3557f1c150a9c9fd68ba362fcc9c424aa73a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906469"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Proteggere la collaborazione con Microsoft 365

La possibilità di condividere facilmente le informazioni con le persone giuste evitando il sovrascivolamento è fondamentale per il successo di un'organizzazione. Ciò include la possibilità di condividere in modo sicuro i dati sensibili solo con coloro che dovrebbero avere accesso ad esso. A seconda del progetto, ciò potrebbe includere la condivisione di dati sensibili con persone esterne all'organizzazione.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Questa guida alla soluzione di collaborazione include due componenti utili:
- Distribuire Microsoft Teams con il livello di protezione giusto per ogni progetto
- Configurare la condivisione esterna con le impostazioni di sicurezza appropriate per ogni progetto

![Distribuire Teams con una protezione appropriata e configurare la condivisione esterna con le impostazioni di sicurezza appropriate](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Se non sono disponibili strumenti di collaborazione del contenuto versatili e facili da usare, gli utenti spesso collaborano inviando tramite posta elettronica i documenti. Si tratta di un metodo di collaborazione noioso e rischioso e può aumentare il rischio di condivisione inappropriata delle informazioni. Se gli utenti trovano troppo difficile condividere le informazioni, potrebbero tornare a usare prodotti di consumo non regolamentati dall'IT. Questo può rappresentare un rischio ancora maggiore.

Con Microsoft 365, è possibile distribuire Teams con un'ampia gamma di configurazioni che consentono di:

- Proteggere la proprietà intellettuale
- Abilitare una facile collaborazione
- Creare un equilibrio tra sicurezza e usabilità che aumenta la soddisfazione degli utenti e riduce il rischio di shadow IT

La maggior parte delle organizzazioni dispone di un'ampia gamma di informazioni, con diversi gradi di riservatezza e diversi gradi di impatto aziendale se le informazioni vengono condivise in modo inappropriato. A seconda della riservatezza di una determinata informazione, è possibile consentire la condivisione con:

- Chiunque (non autenticato)
- Persone all'interno dell'organizzazione
- Persone specifiche all'interno dell'organizzazione
- Persone specifiche all'interno e all'esterno dell'organizzazione

Informazioni come le brochure di marketing sono destinate alla condivisione in generale all'esterno dell'organizzazione. Informazioni come i menu della mensa non sono destinate alla condivisione esterna, ma non avrebbero alcun impatto aziendale se fossero condivise esternamente. Questi tipi di informazioni necessitano di poca o nessuna protezione.

Le stesse brochure di marketing, mentre sono in fase di sviluppo, potrebbero essere condivise solo all'interno dell'organizzazione. In questo caso, le impostazioni di condivisione predefinite in Teams potrebbero essere sufficienti.

Le informazioni su un nuovo prodotto in fase di sviluppo potrebbero essere considerate riservate, anche all'interno dell'organizzazione. In questo caso potrebbe essere appropriato un maggiore livello di protezione. Ad esempio, è possibile limitare l'accesso a queste informazioni ai membri di un team specifico. A seconda del progetto, potrebbe essere necessario collaborare con persone esterne all'organizzazione, ad esempio un fornitore o un'organizzazione partner.

Le informazioni fondamentali per il successo dell'organizzazione o con requisiti di sicurezza o conformità stringenti potrebbero richiedere livelli di protezione ancora maggiori.

![Scala dei rischi da bassa (brochure rilasciata) a alta (dati aziendali sensibili)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Per tutti gli scenari indicati in precedenza, è possibile utilizzare i team in Microsoft Teams per archiviare, condividere e collaborare alle informazioni. 

Per configurare la collaborazione sicura, si usano queste funzionalità e funzionalità di Microsoft 365.

| Prodotto o componente | Capacità o funzionalità | Licenze |
|:-------|:-----|:-------|
| Microsoft Defender per Office 365 | Allegati sicuri per SpO, OneDrive e Teams; Documenti sicuri; Collegamenti sicuri per Teams    | Microsoft 365 E1, E3 ed E5 |
| SharePoint    | Criteri di condivisione di siti e file, autorizzazioni di condivisione del sito, collegamenti di condivisione, richieste di accesso, impostazioni di condivisione guest del sito | Microsoft 365 E1, E3 ed E5 |
| Microsoft Teams   | Accesso guest, team privati, canali privati | Microsoft 365 E1, E3 ed E5 |
| Conformità di Microsoft 365  | Etichette di riservatezza    | Microsoft 365 E3 e E5 |

### <a name="collaboration-governance"></a>Collaborazione di governance

Microsoft 365 offre molte opzioni per la gestione della soluzione di collaborazione. È consigliabile utilizzare questo contenuto di distribuzione insieme al contenuto [di governance](collaboration-governance-overview.md) della collaborazione per creare la soluzione di collaborazione migliore per l'organizzazione.

### <a name="using-teams-for-all-kinds-of-data"></a>Utilizzo di Teams per tutti i tipi di dati

Per gestire l'accesso alle informazioni con sensibilità diverse, sono stati sviluppati tre diversi livelli di [protezione per Teams.](configure-teams-three-tiers-protection.md) È possibile personalizzare uno qualsiasi di questi livelli per soddisfare meglio le esigenze o l'azienda. 

![Immagine di tre livelli di protezione per Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Questi *livelli,* di *base,* sensibili e altamente sensibili, aumentano gradualmente le protezioni che impediscono il sovrascisaggio e la potenziale perdita di informazioni, come illustrato nella tabella seguente. 

|-|**Livello di base**|**Livello sensibile**|**Livello altamente sensibile**|
|:--|:-----------|:------------|:-------------------|
|Team pubblico o privato|Uno dei due|Private|Private|
|Condivisione non autenticata|Bloccato|Bloccato|Bloccato|
|Condivisione di file|Consentito|Consentito|Solo i proprietari del team possono condividere.|
|Appartenenza al team|Chiunque può partecipare a team pubblici.<br>L'approvazione del proprietario del team è necessaria per partecipare a team privati.|L'approvazione del proprietario del team deve essere aggiunta.|L'approvazione del proprietario del team deve essere aggiunta.|
|Crittografia dei documenti|||Disponibile con etichetta di riservatezza|
|Condivisione con gli utenti guest|Consentito|Può essere consentito o bloccato|Può essere consentito o bloccato|
|Dispositivi non gestiti|Nessuna restrizione|Accesso solo Web|Bloccato|

La configurazione di questi livelli implica:

- Configurazione delle impostazioni in Teams per l'accesso guest e i canali privati
- Configurazione delle impostazioni nel sito di SharePoint associato a un team per la condivisione interna e guest, le richieste di accesso e i collegamenti di condivisione
- Per i *livelli sensibili* *e altamente* sensibili, configurare le etichette di riservatezza per classificare i team e controllare la condivisione guest e l'accesso da dispositivi non gestiti
- Per il *livello estremamente sensibile,* configurare un'etichetta di riservatezza per crittografare i documenti a cui viene applicata

Iniziare con il livello di base e  quindi  aggiungere team che utilizzano i livelli sensibili e altamente sensibili in base alle esigenze per proteggere le informazioni nell'organizzazione. Vedi queste risorse per iniziare:

- [Configurare team con la protezione di base](configure-teams-baseline-protection.md)
- [Configurare team con la protezione dei dati sensibili](configure-teams-sensitive-protection.md)
- [Configurare team con la protezione dei dati altamente sensibili](configure-teams-highly-sensitive-protection.md)

Se si dispone di un progetto estremamente sensibile che richiede una protezione aggiuntiva dalla condivisione anche all'interno dell'organizzazione, è possibile configurare un team che utilizza la propria etichetta di riservatezza per crittografare i file in modo che solo i membri del team possano leggerli. Per [informazioni dettagliate, vedere Configure a team with security isolation.](secure-teams-security-isolation.md)

### <a name="sharing-with-people-outside-your-organization"></a>Condivisione con persone esterne all'organizzazione

Potrebbe essere necessario condividere informazioni di qualsiasi riservatezza con persone esterne [all'organizzazione.](collaborate-with-people-outside-your-organization.md) Questo può variare dalla condivisione di un singolo documento con una singola persona alla collaborazione a un progetto principale con un'organizzazione partner di grandi dimensioni o liberi professionisti di tutto il mondo. In Microsoft 365, questa gamma di condivisione esterna può essere eseguita facilmente e con le misure di sicurezza appropriate per proteggere le informazioni riservate.

Queste risorse consentono di iniziare a configurare l'ambiente per collaborare con persone esterne all'organizzazione:

- [Collaborare ai documenti per](collaborate-on-documents.md) la condivisione di singoli file di cartelle.
- [Collaborare in un sito per](collaborate-in-site.md) collaborare con utenti guest in un sito di SharePoint.
- [Collaborare come team per](collaborate-as-team.md) collaborare con gli utenti guest in un team.

A seconda della riservatezza delle informazioni condivise, è possibile aggiungere misure di sicurezza per evitare il sovrascivolmento. Queste risorse consentono di configurare le protezioni necessarie per l'organizzazione:

- [Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)
- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](share-limit-accidental-exposure.md)
- [Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)

Se si dispone di un progetto principale con un'organizzazione partner, è possibile usare Gestione diritti di Azure per gestire gli utenti guest di tale organizzazione in un team configurato per il progetto. Per informazioni dettagliate, vedere Create [a B2B Extranet with managed guests.](b2b-extranet.md)



## <a name="training-for-administrators"></a>Formazione per amministratori

Questi moduli di formazione di Microsoft Learn consentono di apprendere le funzionalità di collaborazione, governance e identità in Teams e SharePoint.

#### <a name="teams"></a>Teams

|Formazione:|Gestione della collaborazione in team con Microsoft Teams|
|:---|:---|
|![Icona formazione sulla collaborazione di Teams](../media/manage-team-collaboration-with-microsoft-teams.svg)|Gestione della collaborazione in team con Microsoft Teams descrive caratteristiche e funzionalità di Microsoft Teams, l'hub centrale per la collaborazione in team di Microsoft 365. Viene spiegato in che modo usare Teams per facilitare il lavoro in team e la comunicazione all'interno dell'organizzazione, in locale e in remoto, su un'ampia gamma di dispositivi, dai PC fissi ai tablet o telefoni, sfruttando al contempo tutte le interessanti funzionalità delle applicazioni di Office 365. Si potrà acquisire una panoramica del modo in cui Teams offre un ambiente completo e flessibile per la collaborazione tra applicazioni e dispositivi. Questo percorso di apprendimento può essere utile per prepararsi per la certificazione Microsoft 365 Certified: Teams Administrator Associate.<br><br>2 ore 17 min - Percorso di apprendimento - 5 moduli|

> [!div class="nextstepaction"]
> [Avviare >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Formazione:|Collaborare con SharePoint in Microsoft 365|
|:---|:---|
|![Icona formazione di SharePoint](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Gestire il contenuto condiviso con Microsoft SharePoint introduce alle funzionalità e caratteristiche di SharePoint e al suo funzionamento con Microsoft 365. Verranno apprese informazioni riguardanti i diversi tipi di siti di SharePoint, inclusi i siti hub, nonché la protezione delle informazioni, la creazione di report e il monitoraggio. Verranno inoltre apprese informazioni su come utilizzare la condivisione di file e cartelle di SharePoint per ottimizzare la collaborazione, su come condividere i file esternamente e come gestire i siti di SharePoint nell'interfaccia di amministrazione di SharePoint. Questo percorso di apprendimento può essere utile per prepararsi per la certificazione Microsoft 365 Certified: Teamwork Administrator Associate.<br><br>1 hr 14 min - Learning Path - 4 Modules|

> [!div class="nextstepaction"]
> [Avviare >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>Protezione delle informazioni

|Formazione:|Proteggere le informazioni aziendali con Microsoft 365|
|:---|:---|
|![Icona formazione sulla protezione delle informazioni di Teams](../media/protect-enterprise-information-microsoft-365.svg)|Proteggere le informazioni dell'organizzazione è più impegnativo che mai. Il percorso di apprendimento Proteggere le informazioni aziendali con Microsoft 365 spiega come proteggere le informazioni sensibili da un elevato numero di condivisioni o da uso improprio, come individuare e classificare i dati, come proteggerli con etichette di riservatezza e come monitorare e analizzare le informazioni sensibili per evitare perdite. Questo percorso di apprendimento può aiutare a prepararsi per le certificazioni Microsoft 365 Certified: Security Administrator Associate e Microsoft 365 Certified: Enterprise Administration Expert certifications..<br><br>1 ora - Percorso di apprendimento - 5 moduli|

> [!div class="nextstepaction"]
> [Avviare >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identità e accesso

|Formazione:|Proteggere l'identità e l'accesso con Azure Active Directory|
|:---|:---|
|![Icona formazione su identità e accesso](../media/protect-identity-and-access-with-microsoft-365.svg)|Il percorso formativo Identità e accesso copre le più recenti tecnologie di identità e accesso, gli strumenti per rafforzare l'autenticazione e le linee guida per la protezione delle identità all'interno dell'organizzazione. Le tecnologie di identità e accesso di Microsoft consentono di proteggere l'identità dell'organizzazione, sia locali che nel cloud, e di offrire agli utenti la possibilità di lavorare in tutta sicurezza da qualsiasi luogo. Questo percorso di apprendimento può essere utile per prepararsi per le certificazioni Microsoft 365 Certified: Security Administrator Associate e Microsoft 365 Certified: Enterprise Administration Expert.<br><br>2 ore 52 min - Percorso di apprendimento - 6 moduli|

> [!div class="nextstepaction"]
> [Avviare >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Formazione per gli utenti finali

Questi moduli di formazione possono aiutare gli utenti a usare Teams, i gruppi e SharePoint per la collaborazione in Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Configurare e personalizzare l'icona di formazione del team](../media/set-up-customize-team-training.png)<br>**[Configurare e personalizzare il team](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![Icona di formazione per la condivisione e la sincronizzazione di SharePoint](../media/sharepoint-share-sync-training.png)<br>**[Condividere e sincronizzare](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Icona di formazione per il caricamento e la ricerca di file in Teams](../media/smc-teams-upload-find-files-training.png)<br>**[Caricare e trovare file](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Icona Collabora in team e canali](../media/teams-collaborate-channels-training.png)<br>**[Collaborare in team e canali](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>Illustrazioni

Queste illustrazioni consentono di comprendere in che modo gruppi e team interagiscono con altri servizi in Microsoft 365 e quali funzionalità di governance e conformità sono disponibili per gestire questi servizi nell'organizzazione.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Gruppi in Microsoft 365 per architetti IT
Cosa devono sapere gli architetti IT sui gruppi di Microsoft 365

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di scorrimento per infografica dei gruppi](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Aggiornato nel giugno 2019|Queste immagini mostrano dettagliatamente i diversi gruppi, come questi vengono creati e gestiti, e alcuni consigli di governance.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams e servizi di produttività correlati in Microsoft 365 per architetti IT
L'architettura logica dei servizi di produttività in Microsoft 365, con Microsoft Teams.

|**Elemento**|**Descrizione**|
|:-----|:-----|
|[![Immagine di scorrimento per poster dell'architettura logica di Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Aggiornato nell'aprile 2019   |Microsoft offre una serie di servizi di produttività che interagiscono tra loro per offrire esperienze di collaborazione con governance dei dati, sicurezza e conformità integrate. <br/> <br/>Questa serie di immagini consente di visualizzare l'architettura logica di servizi di produttività per enterprise architect, con Microsoft Teams.|

## <a name="deploy-the-secure-collaboration-solution"></a>Distribuire la soluzione di collaborazione sicura

Quando si è pronti per distribuire questa soluzione, procedere come segue:
1. Configurare i [tre diversi livelli di protezione per Teams.](configure-teams-three-tiers-protection.md)
2. Configurare le impostazioni per [la condivisione delle informazioni di qualsiasi riservatezza con persone esterne all'organizzazione.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Vedere anche

[Documentazione sulla sicurezza di Microsoft 365](../security/index.yml)

[Documentazione sulla conformità di Microsoft 365](../compliance/index.yml)

[Benvenuto in Microsoft Teams](/MicrosoftTeams/Teams-overview)