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
description: Informazioni su come configurare una collaborazione sicura sui contenuti in Teams per proteggere i dati in base alla riservatezza.
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233857"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Proteggere la collaborazione con Microsoft 365

La possibilità di condividere facilmente le informazioni con le persone giuste, evitando il sovrastono, è fondamentale per il successo di un'organizzazione. Ciò include la possibilità di condividere i dati sensibili in modo sicuro solo con gli utenti che devono accedervi. A seconda del progetto, potrebbe essere incluso la condivisione di dati sensibili con persone esterne all'organizzazione.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Questa guida alla soluzione di collaborazione include due componenti che consentono di:
- Distribuire Microsoft Teams con il giusto livello di protezione per ogni progetto
- Configurare la condivisione esterna con le impostazioni di sicurezza appropriate per ogni progetto

![Distribuire Teams con una protezione appropriata e configurare la condivisione esterna con le impostazioni di sicurezza appropriate](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Se gli strumenti di collaborazione sul contenuto versatili e facili da usare non sono disponibili, gli utenti spesso collaborano inviando tramite posta elettronica i documenti. Si tratta di un metodo di collaborazione noioso e rischioso per gli errori e può aumentare il rischio di una condivisione inappropriata delle informazioni. Se gli utenti trovano troppo difficile condividere le informazioni, potrebbero tornare a usare prodotti consumer non regolamentati dall'IT. Questo può rappresentare un rischio ancora maggiore.

Con Microsoft 365, è possibile distribuire Teams con un'ampia gamma di configurazioni che consentono di:

- Proteggere la proprietà intellettuale
- Abilitare una collaborazione semplice
- Creare un equilibrio tra sicurezza e usabilità che aumenta la soddisfazione degli utenti e riduce il rischio di shadow IT

La maggior parte delle organizzazioni dispone di una vasta gamma di informazioni, con diversi gradi di riservatezza e diversi gradi di impatto aziendale se le informazioni vengono condivise in modo inappropriato. A seconda della riservatezza di una determinata informazione, è possibile consentire la condivisione con:

- Chiunque (non autenticato)
- Persone all'interno dell'organizzazione
- Persone specifiche all'interno dell'organizzazione
- Persone specifiche all'interno e all'esterno dell'organizzazione

Le informazioni, ad esempio le opuscoli di marketing, sono destinate alla condivisione su vasta base all'esterno dell'organizzazione. Informazioni come i menu della mensa non sono destinate alla condivisione esterna, ma non avrebbero alcun impatto aziendale se fossero condivise esternamente. Questi tipi di informazioni non necessitano di alcuna protezione.

Le stesse depliant marketing, mentre sono in fase di sviluppo, potrebbero essere condivise solo all'interno dell'organizzazione. In questo caso, le impostazioni di condivisione predefinite in Teams potrebbero essere sufficienti.

Le informazioni su un nuovo prodotto in fase di sviluppo potrebbero essere considerate sensibili, anche all'interno dell'organizzazione. In questo caso potrebbe essere appropriato un livello di protezione maggiore. Ad esempio, è possibile limitare l'accesso a queste informazioni ai membri di un team specifico. A seconda del progetto, potrebbe essere necessario collaborare con persone esterne all'organizzazione, ad esempio un fornitore o un'organizzazione partner.

Le informazioni fondamentali per il successo dell'organizzazione o con requisiti di sicurezza o conformità stringenti potrebbero richiedere livelli di protezione ancora più elevati.

![Scala dei rischi da bassa (pubblicazione di opuscoli) a elevata (dati aziendali sensibili)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Per tutti gli scenari indicati in precedenza, è possibile usare i team in Microsoft Teams per archiviare, condividere e collaborare alle informazioni. 

Per configurare la collaborazione sicura, usare queste funzionalità e funzionalità di Microsoft 365.

| Prodotto o componente | Capacità o funzionalità | Licenze |
|:-------|:-----|:-------|
| Microsoft Defender per Office 365 | Allegati sicuri per SpO, OneDrive e Teams; Documenti sicuri; Collegamenti sicuri per Teams    | Microsoft 365 E1, E3 ed E5 |
| SharePoint    | Criteri di condivisione di siti e file, autorizzazioni di condivisione del sito, collegamenti di condivisione, richieste di accesso, impostazioni di condivisione guest del sito | Microsoft 365 E1, E3 ed E5 |
| Microsoft Teams   | Accesso guest, team privati, canali privati | Microsoft 365 E1, E3 ed E5 |
| Conformità di Microsoft 365  | Etichette di riservatezza    | Microsoft 365 E3 e E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Uso di Teams per tutti i tipi di dati

Per gestire l'accesso alle informazioni con sensibilità diverse, sono stati sviluppati tre [diversi livelli di protezione per Teams.](configure-teams-three-tiers-protection.md) È possibile personalizzare uno qualsiasi di questi livelli per soddisfare meglio le esigenze o l'azienda. 

![Immagine di scorrimento per poster dell'architettura logica di Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Questi *livelli,* di *base,* sensibili e altamente sensibili, aumentano gradualmente le protezioni che impediscono la sovrascrittura e la potenziale perdita di informazioni, come illustrato nella tabella seguente. 

|-|**Livello di base**|**Livello Dati sensibili**|**Livello altamente sensibile**|
|:--|:-----------|:------------|:-------------------|
|Team pubblico o privato|Uno dei due|Private|Private|
|Condivisione non autenticata|Bloccato|Bloccato|Bloccato|
|Condivisione di file|Consentito|Consentito|Solo i proprietari del team possono condividere.|
|Appartenenza al team|Chiunque può partecipare a team pubblici.<br>L'approvazione del proprietario del team è necessaria per entrare a far parte di team privati.|Approvazione del proprietario del team necessaria per partecipare.|Approvazione del proprietario del team necessaria per partecipare.|
|Crittografia dei documenti|||Disponibile con etichetta di riservatezza|
|Condivisione con gli utenti guest|Consentito|Può essere consentito o bloccato|Può essere consentito o bloccato|
|Dispositivi non gestiti|Nessuna restrizione|Accesso solo Web|Bloccato|

La configurazione di questi livelli implica:

- Configurazione delle impostazioni in Teams per l'accesso guest e i canali privati
- Configurazione delle impostazioni nel sito di SharePoint associato di un team per la condivisione interna e guest, le richieste di accesso e i collegamenti di condivisione
- Per i *livelli sensibili* ed estremamente *sensibili,* configurare le etichette di riservatezza per classificare i team e controllare la condivisione guest e l'accesso da dispositivi non gestiti
- Per il *livello estremamente sensibile,* configurare un'etichetta di riservatezza per crittografare i documenti a cui viene applicata

Iniziare con il livello di base e  quindi  aggiungere team che usano i livelli sensibili ed estremamente sensibili in base alle esigenze per proteggere le informazioni nell'organizzazione. Vedi queste risorse per iniziare:

- [Configurare team con la protezione di base](configure-teams-baseline-protection.md)
- [Configurare team con la protezione dei dati sensibili](configure-teams-sensitive-protection.md)
- [Configurare team con la protezione dei dati altamente sensibili](configure-teams-highly-sensitive-protection.md)

Se si dispone di un progetto altamente sensibile che richiede una protezione aggiuntiva dalla condivisione anche all'interno dell'organizzazione, è possibile configurare un team che utilizza una propria etichetta di riservatezza per crittografare i file in modo che solo i membri del team possano leggerli. Per [informazioni dettagliate, vedere Configurare un team con isolamento](secure-teams-security-isolation.md) di sicurezza.

### <a name="sharing-with-people-outside-your-organization"></a>Condivisione con persone esterne all'organizzazione

Potrebbe essere necessario condividere informazioni di riservatezza con persone esterne [all'organizzazione.](collaborate-with-people-outside-your-organization.md) Questo può variare dalla condivisione di un singolo documento con una sola persona alla collaborazione a un progetto principale con un'organizzazione partner di grandi dimensioni o con professionisti di tutto il mondo. In Microsoft 365, questa gamma di condivisione esterna può essere eseguita facilmente e con le misure di sicurezza appropriate per proteggere le informazioni riservate.

Queste risorse consentono di iniziare a configurare l'ambiente per collaborare con persone esterne all'organizzazione:

- [Collaborare ai documenti per](collaborate-on-documents.md) la condivisione di singoli file di cartelle.
- [Collaborare in un sito per](collaborate-in-site.md) collaborare con gli utenti guest in un sito di SharePoint.
- [Collaborare come team per](collaborate-as-team.md) collaborare con gli utenti guest in un team.

A seconda della riservatezza delle informazioni condivise, è possibile aggiungere misure di sicurezza per evitare la sovrascrittura. Queste risorse ti aiuteranno a configurare le protezioni necessarie per la tua organizzazione:

- [Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)
- [Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione](share-limit-accidental-exposure.md)
- [Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)

Se si ha un progetto principale con un'organizzazione partner, è possibile utilizzare Azure Entitlement Management per gestire gli utenti guest di tale organizzazione in un team configurato per il progetto. Per informazioni dettagliate, vedere Creare una [extranet B2B con utenti guest](b2b-extranet.md) gestiti.

## <a name="deploy-the-secure-collaboration-solution"></a>Distribuire la soluzione di collaborazione sicura

Quando si è pronti per distribuire questa soluzione, procedere come segue:
1. Configurare i [tre diversi livelli di protezione per Teams.](configure-teams-three-tiers-protection.md)
2. Configurare le impostazioni per [la condivisione delle informazioni di qualsiasi riservatezza con persone esterne all'organizzazione.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Vedere anche

[Documentazione sulla sicurezza di Microsoft 365](https://docs.microsoft.com/microsoft-365/security)

[Documentazione sulla conformità di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance)

[Benvenuto in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
