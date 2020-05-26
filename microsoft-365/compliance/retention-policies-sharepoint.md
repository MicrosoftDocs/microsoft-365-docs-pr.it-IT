---
title: Informazioni sui criteri di conservazione per SharePoint e OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sui criteri di conservazione applicabili a SharePoint e OneDrive.
ms.openlocfilehash: f3c7d805309a86f05cdea8769693ec6de9c1bf51
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292496"
---
# <a name="learn-about-retention-policies-for-sharepoint-and-onedrive"></a>Informazioni sui criteri di conservazione per SharePoint e OneDrive

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Questo articolo integra [Informazioni sui criteri di conservazione](retention-policies.md) con informazioni specifiche per SharePoint e OneDrive.

## <a name="how-a-retention-policy-works-with-sharepoint-and-onedrive"></a>Funzionamento dei criteri di conservazione con SharePoint e OneDrive

I criteri di conservazione vengono applicati a livello di raccolta siti. Quando si include una raccolta siti di SharePoint o un account OneDrive nei criteri di conservazione viene creata una raccolta di archiviazione, se non esiste già. È possibile visualizzare questa raccolta nella pagina **Contenuto del sito** nel sito principale della raccolta siti. La maggior parte degli utenti non può visualizzare la raccolta di archiviazione poiché è visibile soltanto agli amministratori della raccolta siti.
  
Se un utente tenta di modificare o eliminare i contenuti di un sito soggetto a criteri di conservazione, questi controllano innanzitutto se il contenuto è stato modificato dal momento della sua applicazione. Nel caso della prima modifica dall'applicazione dei criteri di conservazione, questi creano una copia dei contenuti nella raccolta di archiviazione, quindi permettono all'utente di modificare o eliminare i contenuti originali. I contenuti presenti nella raccolta siti possono essere copiati nella raccolta di archiviazione anche se tali contenuti non corrispondono al filtro della query utilizzato dai criteri di conservazione.
  
Un processo timer pulisce periodicamente la raccolta di archiviazione. Questo processo confronta tutti i contenuti della raccolta di archiviazione con tutte le query usate dai criteri di conservazione nel sito. Il contenuto precedente al periodo di conservazione configurato viene eliminato dalla raccolta di archiviazione e dalla posizione originale, se è ancora lì. Questo processo timer viene eseguito ogni 7 giorni, quindi può essere necessario attendere fino a 7 giorni prima che il contenuto venga eliminato.
  
Questo comportamento si applica ai contenuti che esistono al momento dell'applicazione dei criteri di conservazione. Inoltre, i nuovi contenuti creati o aggiunti alla raccolta siti in seguito all'inclusione nei criteri conservazione, verranno conservati dopo l'eliminazione. Tuttavia, i nuovi contenuti non vengono copiati nella raccolta di archiviazione al momento della prima modifica, ma solo quando viene eliminato. Per conservare tutte le versioni di un file, è necessario attivare il [controllo delle versioni](#how-a-retention-policy-works-with-document-versions-in-a-site-collection).
  
Se si prova a eliminare una raccolta, un elenco, una cartella o un sito soggetti a u criteri di conservazione, viene visualizzato un messaggio di errore. Un utente può eliminare una cartella se prima di tutto sposta o elimina gli eventuali file nella cartella soggetta a criteri. Inoltre, la raccolta di archiviazione viene creata in questa fase e non quando si creano i criteri di conservazione. Questo vuol dire che, per testare i criteri, è necessario prima di tutto modificare o eliminare un documento in un sito soggetto ai criteri di conservazione e quindi passare alla raccolta di archiviazione per visualizzare la copia conservata.
  
Dopo che i criteri di conservazione vengono assegnati a un account di OneDrive o a un sito di SharePoint, i percorsi del contenuto variano in base al fatto che il criterio di conservazione sia Conserva ed elimina, Conserva solo o Elimina solo.

Se il criterio di conservazione è Conserva ed elimina:

![Diagramma del ciclo di vita dei contenuti in SharePoint e OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Se il contenuto viene modificato o eliminato** durante il periodo di conservazione, una copia del contenuto originale al momento dell'assegnazione dei criteri di conservazione viene creata nella raccolta di archiviazione. Nella raccolta, un processo timer identifica gli elementi il cui periodo di conservazione è scaduto. Questi elementi vengono poi spostati nel cestino di secondo livello, dove vengono eliminati definitivamente dopo 93 giorni. Il Cestino di secondo livello non è visibile agli utenti finali come il Cestino di primo livello, tuttavia gli amministratori della raccolta siti possono visualizzare e ripristinare il contenuto da tale posizione.

    > [!NOTE]
    > Per evitare perdite accidentali di dati, non eliminiamo più definitivamente il contenuto dalla raccolta di archiviazione. Eliminiamo invece definitivamente il contenuto solo dal Cestino in modo che tutto il contenuto della raccolta di archiviazione passi al Cestino di secondo livello.
    
2. **Se il contenuto non viene modificato o eliminato** durante il periodo di conservazione, il processo timer lo sposta nel Cestino di primo livello alla fine del periodo di conservazione. Se un utente elimina il contenuto da questa posizione o svuota questo Cestino, il documento viene spostato nel Cestino di secondo livello. Il periodo di conservazione per i Cestini di primo e secondo livello è di 93 giorni, dopo i quali il documento viene eliminato definitivamente dal Cestino, sia di primo che di secondo livello. Il Cestino non è indicizzato e quindi non è disponibile per la ricerca. Di conseguenza, una ricerca eDiscovery non può trovare alcun contenuto nel Cestino a cui applicare un blocco.

Quando il criterio di conservazione è Conserva solo, o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed elimina:

#### <a name="content-paths-for-retain-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Conserva solo

1. **Se il contenuto viene modificato o eliminato** durante il periodo di conservazione: una copia del documento originale viene creata nella raccolta di archiviazione e conservata fino al termine del periodo di conservazione, quindi la copia nella raccolta di archiviazione viene spostata nel cestino di secondo livello e viene eliminata definitivamente dopo 93 giorni.

2. **Se il contenuto non viene modificato o eliminato** durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. Il documento rimane nella posizione originale.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Elimina solo

1. **Se il contenuto viene eliminato** durante il periodo configurato: il documento viene spostato nel Cestino di primo livello. Se un utente elimina il documento da questa posizione o svuota questo Cestino, il documento viene spostato nel Cestino di secondo livello. Il periodo di conservazione per i Cestini di primo e secondo livello è di 93 giorni, dopo i quali il documento viene eliminato definitivamente dal Cestino, sia di primo che di secondo livello. Se il contenuto viene modificato durante il periodo configurato, segue lo stesso percorso di eliminazione dopo il periodo configurato.

2. **Se il contenuto non viene eliminato** durante il periodo configurato: alla fine del periodo configurato nel criterio di conservazione, il documento viene spostato nel Cestino di primo livello. Se un utente elimina il documento da questa posizione o svuota questo Cestino, il documento viene spostato nel Cestino di secondo livello. Il periodo di conservazione per i Cestini di primo e secondo livello è di 93 giorni, dopo i quali il documento viene eliminato definitivamente dal Cestino, sia di primo che di secondo livello. Il Cestino non è indicizzato e quindi non è disponibile per la ricerca. Di conseguenza, una ricerca eDiscovery non può trovare alcun contenuto nel Cestino a cui applicare un blocco.
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>Funzionamento dei criteri di conservazione con le versioni del documento in una raccolta siti

Il controllo delle versioni è una caratteristica di tutte le raccolte documenti di SharePoint e OneDrive. Per impostazione predefinita, il controllo delle versioni conserva almeno 500 versioni principali, limite che è possibile aumentare. Per altre informazioni, vedere [Abilitare e configurare il controllo delle versioni per un elenco o una raccolta](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
Un criterio di sola conservazione mantiene tutte le versioni di un documento in una raccolta siti di SharePoint o in un account OneDrive. Quando si modifica per la prima volta un documento soggetto a un criterio di blocco o di sola conservazione, una versione dell'originale viene copiata nella raccolta di archiviazione. Quando si elimina un documento soggetto a un criterio di blocco o di sola conservazione, vengono copiate tutte le versioni nella raccolta di archiviazione, se è attivato il controllo delle versioni. Ogni versione di un documento nella Raccolta blocchi per conservazione è un elemento separato con un periodo di conservazione specifico:
  
- Se i criteri di conservazione si basano sulla data di creazione del contenuto, ciascuna versione ha la stessa data di scadenza del documento originale. Il documento originale e le sue versioni scadono tutti allo stesso tempo.
    
- Se i criteri di conservazione si basano sulla data dell'ultima modifica del contenuto, ciascuna versione ha la propria data di scadenza in base a quando il documento originale è stato modificato per creare quella versione. I documenti originali e le relative versioni scadono indipendentemente l'uno dall'altro.

> [!NOTE]
> Le versioni conservate dei documenti di SharePoint e OneDrive non sono disponibili per la ricerca da parte degli strumenti di eDiscovery.

### <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l'organizzazione 

**SharePoint**:

Se un utente abbandona l'organizzazione, tutti i contenuti creati da quest'ultimo non subiranno alcuna modifica in quanto SharePoint è considerato un ambiente di collaborazione, al contrario di una cassetta postale o di un account OneDrive dell'utente.

**OneDrive**:

Se un utente abbandona l'organizzazione, i file soggetti a un criterio di conservazione o con etichette di conservazione verranno mantenuti per l'intera durata dell'etichetta o del criterio. Durante questo periodo di tempo, tutti gli accessi di condivisione continueranno a funzionare. Quando il periodo di conservazione scade, il contenuto viene spostato nel Cestino della raccolta siti e solo gli amministratori possono accedervi. Se un documento viene contrassegnato come record da un criterio di conservazione, viene mantenuto fino allo scadere del periodo di conservazione, al termine del quale il contenuto verrà eliminato definitivamente. 

## <a name="how-to-configure-a-retention-policy-for-sharepoint-and-onedrive"></a>Come configurare un criterio di conservazione per SharePoint e OneDrive

Vedere [Creare e configurare criteri di conservazione](create-retention-policies.md).

Per la pagina **Seleziona posizioni** della procedura guidata, selezionare una delle opzioni seguenti:

- **Applica il criterio solo al contenuto dei messaggi di posta elettronica di Exchange, alle cartelle pubbliche, ai gruppi di Office 365 e ai documenti di OneDrive e di SharePoint**

- **Consenti la scelta di posizioni specifiche** > **Siti di SharePoint** o **Account di OneDrive**

### <a name="sharepoint-locations"></a>Posizioni di SharePoint 

I criteri di conservazione possono conservare il contenuto di siti di comunicazione di SharePoint, siti del team non collegati a gruppi di Office 365 e siti classici. I siti del team collegati a gruppi di Office 365 non sono supportati con questa opzione. In alternativa, usare le posizioni dei **gruppi di Office 365**. 

Se si specificano siti non supportati, i criteri di conservazione li ignoreranno. 

Quando si specificano le posizioni dei siti di SharePoint, non è necessario disporre delle autorizzazioni per accedere al sito e non viene eseguita alcuna convalida quando si specifica l'URL nella pagina **Modifica delle posizioni**. Tuttavia, i siti devono essere indicizzati e viene verificata l'esistenza dei siti specificati al termine della procedura guidata. 

Se la verifica dell'URL immesso fallisce, verrà visualizzato un messaggio di errore e la procedura guidata non creerà il criterio di conservazione fino al successo della verifica. Se si visualizza il messaggio di errore, tornare alla procedura guidata per cambiare l'URL o rimuovere il sito.
