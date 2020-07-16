---
title: Informazioni sulla conservazione per SharePoint e OneDrive
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
description: Informazioni sul funzionamento della conservazione per SharePoint e OneDrive.
ms.openlocfilehash: f19f452a01c093d08dbeed38a34756dcaf7a4e95
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127403"
---
# <a name="learn-about-retention-for-sharepoint-and-onedrive"></a>Informazioni sulla conservazione per SharePoint e OneDrive

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Questo articolo integra [Informazioni sulla conservazione](retention.md) con informazioni specifiche per SharePoint e OneDrive.

## <a name="how-retention-works-for-sharepoint-and-onedrive"></a>Funzionamento della conservazione per SharePoint e OneDrive

Per supportare la conservazione, SharePoint e OneDrive creano una raccolta di archiviazione se non è presente. È possibile visualizzare questa raccolta nella pagina **Contenuto del sito** nel sito principale della raccolta siti. La maggior parte degli utenti non può visualizzare la raccolta di archiviazione poiché è visibile soltanto agli amministratori della raccolta siti.
  
Se si tenta di modificare o eliminare un documento soggetto a impostazioni di conservazione, viene eseguita una verifica del contenuto per stabilire se è stato modificato dopo l'applicazione delle impostazioni di conservazione. Nel caso della prima modifica dell’applicazione delle impostazioni di conservazione, il contenuto viene copiato nella raccolta di archiviazione che permette all'utente di modificare o eliminare i contenuti originali. Il contenuto di una raccolta siti può essere copiato nella raccolta di archiviazione, indipendentemente dalle impostazioni di conservazione.
  
Un processo timer pulisce periodicamente la raccolta di archiviazione. Questo processo confronta tutti i contenuti della raccolta di archiviazione con tutte le query usate dalle impostazioni di conservazione per tali contenuti. Il contenuto precedente al periodo di conservazione configurato viene eliminato dalla raccolta di archiviazione e dalla posizione originale, se è ancora lì. Questo processo timer viene eseguito ogni 7 giorni, quindi può essere necessario attendere fino a 7 giorni prima che il contenuto venga eliminato.
  
Questo comportamento si applica ai contenuti che esistono al momento dell'applicazione delle impostazioni di conservazione. Inoltre, per i criteri di conservazione, i nuovi contenuti creati o aggiunti alla raccolta siti in seguito all'inclusione nei criteri conservazione, verranno conservati dopo l'eliminazione. Tuttavia, i nuovi contenuti non vengono copiati nella raccolta di archiviazione al momento della prima modifica, ma solo quando viene eliminato. Per conservare tutte le versioni di un file, è necessario attivare il [controllo delle versioni](#how-retention-works-with-document-versions-in-a-site-collection).
  
Se si prova a eliminare una raccolta, un elenco, una cartella o un sito soggetti a u criteri di conservazione, viene visualizzato un messaggio di errore. Un utente può eliminare una cartella se prima di tutto sposta o elimina gli eventuali file nella cartella soggetta a criteri. Inoltre, la raccolta di archiviazione viene creata in questa fase e non quando si creano i criteri di conservazione o si applica un’etichetta di conservazione. Questo vuol dire che, per testare la conservazione, è necessario prima di tutto modificare o eliminare un documento in un sito soggetto ai criteri di conservazione o con un’etichetta di conservazione applicata, e quindi passare alla raccolta di archiviazione per visualizzare la copia conservata.
  
Dopo che le impostazioni di conservazione vengono assegnate ai contenuti di OneDrive o a un sito di SharePoint, i percorsi del contenuto variano in base al fatto che le impostazioni di conservazione siano Conserva ed elimina, Conserva solo o Elimina solo.

Se l'impostazione di conservazione è Conserva ed elimina:

![Diagramma del ciclo di vita dei contenuti in SharePoint e OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Se il contenuto viene modificato o eliminato** durante il periodo di conservazione, una copia del contenuto originale al momento dell'assegnazione dei criteri di conservazione viene creata nella raccolta di archiviazione. Nella raccolta, un processo timer identifica gli elementi il cui periodo di conservazione è scaduto. Questi elementi vengono poi spostati nel cestino di secondo livello, dove vengono eliminati definitivamente dopo 93 giorni. Il Cestino di secondo livello non è visibile agli utenti finali come il Cestino di primo livello, tuttavia gli amministratori della raccolta siti possono visualizzare e ripristinare il contenuto da tale posizione.

    > [!NOTE]
    > Per evitare perdite accidentali di dati, non eliminiamo più definitivamente il contenuto dalla raccolta di archiviazione. Eliminiamo invece definitivamente il contenuto solo dal Cestino in modo che tutto il contenuto della raccolta di archiviazione passi al Cestino di secondo livello.
    
2. **Se il contenuto non viene modificato o eliminato** durante il periodo di conservazione, il processo timer lo sposta nel Cestino di primo livello alla fine del periodo di conservazione. Se un utente elimina il contenuto da questa posizione o svuota questo Cestino, il documento viene spostato nel Cestino di secondo livello. Il periodo di conservazione per i Cestini di primo e secondo livello è di 93 giorni. Al termine di questi 93 giorni, il documento viene eliminato definitivamente dal Cestino di primo o di secondo livello. Il Cestino non è indicizzato e quindi non è disponibile per la ricerca. Di conseguenza, una ricerca eDiscovery non può trovare alcun contenuto nel Cestino a cui applicare un blocco.

Quando l'impostazione di conservazione è Conserva solo o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed elimina:

### <a name="content-paths-for-retain-only-retention-settings"></a>Percorsi di contenuto per l'impostazione di conservazione Conserva solo

1. **Se il contenuto viene modificato o eliminato** durante il periodo di conservazione: una copia del documento originale viene creata nella raccolta di archiviazione e conservata fino al termine del periodo di conservazione, quindi la copia nella raccolta di archiviazione viene spostata nel cestino di secondo livello e viene eliminata definitivamente dopo 93 giorni.

2. **Se il contenuto non viene modificato o eliminato** durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. Il documento rimane nella posizione originale.

### <a name="content-paths-for-delete-only-retention-settings"></a>Percorsi di contenuto per l'impostazione di conservazione Elimina solo

1. **Se il contenuto viene eliminato** durante il periodo configurato: il documento viene spostato nel Cestino di primo livello. Se un utente elimina il documento da questa posizione o svuota questo Cestino, il documento viene spostato nel Cestino di secondo livello. Il periodo di conservazione per i Cestini di primo e secondo livello è di 93 giorni, dopo i quali il documento viene eliminato definitivamente dal Cestino, sia di primo che di secondo livello. Se il contenuto viene modificato durante il periodo configurato, segue lo stesso percorso di eliminazione dopo il periodo configurato.

2. **Se il contenuto non viene eliminato** durante il periodo configurato: alla fine del periodo configurato nel criterio di conservazione, il documento viene spostato nel Cestino di primo livello. Se un utente elimina il documento da questa posizione o svuota questo Cestino, il documento viene spostato nel Cestino di secondo livello. Il periodo di conservazione per i Cestini di primo e secondo livello è di 93 giorni, dopo i quali il documento viene eliminato definitivamente dal Cestino, sia di primo che di secondo livello. Il Cestino non è indicizzato e quindi non è disponibile per la ricerca. Di conseguenza, una ricerca eDiscovery non può trovare alcun contenuto nel Cestino a cui applicare un blocco.

## <a name="how-retention-works-with-document-versions-in-a-site-collection"></a>Funzionamento della conservazione con le versioni del documento in una raccolta siti

Il controllo delle versioni è una caratteristica di tutte le raccolte documenti di SharePoint e OneDrive. Per impostazione predefinita, il controllo delle versioni conserva almeno 500 versioni principali, limite che è possibile aumentare. Per altre informazioni, vedere [Abilitare e configurare il controllo delle versioni per un elenco o una raccolta](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
Le impostazioni di sola conservazione mantengono tutte le versioni di un documento in una raccolta siti di SharePoint o in un account OneDrive. Quando si modifica per la prima volta un documento soggetto a impostazioni di blocco o di sola conservazione, una versione dell'originale viene copiata nella raccolta di archiviazione. Quando si elimina un documento soggetto a impostazioni di blocco o di sola conservazione, vengono copiate tutte le versioni nella raccolta di archiviazione, se è attivato il controllo delle versioni. Ogni versione di un documento nella raccolta di conservazione è un elemento separato con un periodo di conservazione specifico:
  
- Se il periodo di conservazione si basa sulla data di creazione del contenuto, ciascuna versione ha la stessa data di scadenza del documento originale.  Il documento originale e le sue versioni scadono tutti allo stesso tempo.

- Se il periodo di conservazione si basa sulla data dell'ultima modifica del contenuto, ciascuna versione ha la propria data di scadenza in base a quando il documento originale è stato modificato per creare quella versione.  I documenti originali e le relative versioni scadono indipendentemente l'uno dall'altro.

> [!NOTE]
> Le versioni conservate dei documenti di SharePoint e OneDrive non sono disponibili per la ricerca da parte degli strumenti di eDiscovery.

## <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l'organizzazione

**SharePoint**:

Se un utente abbandona l'organizzazione, tutti i contenuti creati da quest'ultimo non subiranno alcuna modifica in quanto SharePoint è considerato un ambiente di collaborazione, al contrario di una cassetta postale o di un account OneDrive dell'utente.

**OneDrive**:

Se un utente abbandona l'organizzazione, i file soggetti a un criterio di conservazione o con etichette di conservazione verranno mantenuti per l'intera durata dell'etichetta o del criterio. Durante questo periodo di tempo, tutti gli accessi di condivisione continueranno a funzionare. Quando il periodo di conservazione scade, il contenuto viene spostato nel Cestino della raccolta siti e solo gli amministratori possono accedervi. Se un documento viene contrassegnato come record da un’etichetta di conservazione, il documento viene mantenuto fino allo scadere del periodo di conservazione, al termine del quale il contenuto verrà eliminato definitivamente.

## <a name="configuration-guidance"></a>Linee guida per la configurazione

Se è tutto pronto per configurare la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).
