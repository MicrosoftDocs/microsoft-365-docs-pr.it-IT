---
title: Cercare contenuto
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Utilizzare lo strumento Ricerca contenuto eDiscovery nel Centro sicurezza & e conformità per trovare rapidamente la posta elettronica nelle cassette postali di Exchange, nei documenti nei siti di SharePoint e nelle posizioni di OneDrive e nelle conversazioni di messaggistica istantanea in Skype for Business.
ms.openlocfilehash: a6aa416768e7910e546b39d5866f884d2d532732
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927592"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Cercare contenuto tramite lo strumento Ricerca contenuto

Utilizzare lo strumento Ricerca contenuto nel Centro sicurezza & conformità per trovare rapidamente la posta elettronica nelle cassette postali di Exchange, nei documenti nei siti di SharePoint e nelle posizioni di OneDrive e nelle conversazioni di messaggistica istantanea in Skype for Business. È possibile utilizzare lo strumento di ricerca contenuto per cercare messaggi di posta elettronica, documenti e conversazioni di messaggistica istantanea in strumenti di collaborazione come Microsoft Teams e Gruppi di Microsoft 365.
  
## <a name="search-for-content"></a>Cercare contenuto

Il primo passaggio consiste nell'iniziare a utilizzare lo strumento Ricerca contenuto per scegliere i percorsi di contenuto in cui eseguire la ricerca e configurare una query con parole chiave per la ricerca di elementi specifici. In caso contrario, è possibile lasciare vuota la query e restituire tutti gli elementi nelle posizioni di destinazione.
  
- [Creare ed eseguire](content-search.md) una ricerca di contenuto 

- [Creare query di ricerca e usare condizioni per](keyword-queries-and-search-conditions.md) restringere la ricerca 

- [Configurare il filtro delle autorizzazioni di ricerca](permissions-filtering-for-content-search.md) in modo che un responsabile di eDiscovery possa cercare solo sottoinsiemi di cassette postali o siti nell'organizzazione 

- [Eseguire una ricerca nell'elenco id](csv-file-for-an-id-list-content-search.md) per cercare messaggi di posta elettronica specifici 

- [Cercare cassette postali basate sul cloud ](search-cloud-based-mailboxes-for-on-premises-users.md) per gli utenti locali in Microsoft 365

- [Visualizzare le statistiche sulle](view-keyword-statistics-for-content-search.md) parole chiave per i risultati di una ricerca e quindi perfezionare la query, se necessario

- [Cercare dati di terze parti](use-content-search-to-search-third-party-data-that-was-imported.md) importati dall'organizzazione in Microsoft 365

- [Modificare in blocco](bulk-edit-content-searches.md) la query e i percorsi del contenuto per più ricerche

- [Ritentare una ricerca di contenuto per](retry-failed-content-search.md) risolvere un errore di percorso del contenuto

- [Conservare i destinatari Ccn](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) in modo da poterli cercare 

## <a name="perform-actions-on-content-you-find"></a>Eseguire azioni sul contenuto trovato

Dopo aver eseguito una ricerca e affinarla in base alle esigenze, il passaggio successivo consiste nell'eseguire un'operazione con i risultati restituiti dalla ricerca. È possibile esportare e scaricare i risultati nel computer locale o in caso di attacco tramite posta elettronica all'organizzazione, è possibile eliminare i risultati di una ricerca dalle cassette postali degli utenti.
  
- [Esportare i risultati di una ricerca di contenuto](export-search-results.md) e scaricarli nel computer locale 

- [Cercare ed eliminare messaggi di posta](search-for-and-delete-messages-in-your-organization.md) elettronica, ad esempio messaggi che contenutino un virus, allegati pericolosi o messaggi di phishing

- [Esportare un report](export-a-content-search-report.md) sui risultati di una ricerca di contenuto, senza esportare i risultati effettivi 

## <a name="learn-more-about-content-search"></a>Ulteriori informazioni sulla ricerca di contenuto

Ricerca contenuto è facile da usare, ma è anche uno strumento potente. Dietro le quinte, c'è molto da fare. Più si conosce e si comprende il comportamento e le limitazioni, maggiore sarà il successo con cui verrà utilizzato per le esigenze di ricerca e indagine dell'organizzazione. Informazioni su:
  
- [Elementi parzialmente indicizzati in Exchange e SharePoint](partially-indexed-items-in-content-search.md) e come includerli o escluderli quando si esportano e scaricano i risultati della ricerca

- [Analizzare gli elementi parzialmente indicizzati e](investigating-partially-indexed-items-in-ediscovery.md) determinare l'esposizione dell'organizzazione a questi elementi

- [Limiti dello strumento Ricerca contenuto,](limits-for-content-search.md)ad esempio il numero massimo di ricerche che è possibile eseguire contemporaneamente e il numero massimo di percorsi di contenuto che è possibile includere in una singola ricerca

- [Risultati di ricerca stimati ed](differences-between-estimated-and-actual-ediscovery-search-results.md) effettivi e i motivi per cui potrebbero esservi differenze durante l'esportazione e il download dei risultati della ricerca

- [Deduplicazione nei risultati della ricerca](de-duplication-in-ediscovery-search-results.md) che è possibile abilitare quando si esportano messaggi di posta elettronica che sono i risultati di una ricerca

## <a name="use-scripts-for-advanced-scenarios"></a>Usare script per scenari avanzati

A volte è necessario eseguire attività di ricerca del contenuto più avanzate, complesse e ripetitive. In questi casi, è più semplice e veloce usare i comandi di PowerShell nel Centro sicurezza & conformità. Per semplificare questa operazione &, sono stati creati diversi script di PowerShell del Centro sicurezza e conformità per completare attività complesse correlate alla ricerca di contenuto.
  
- [Cercare cartelle specifiche di cassette](use-content-search-for-targeted-collections.md) postali e siti (denominate *raccolta di destinazione) quando si è certi che gli elementi che responsavano a un caso si trovino in tale cartella

- [Cercare un elenco di](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) utenti nella cassetta postale e nel percorso di OneDrive 

- [Creare, creare report ed eliminare più](create-report-on-and-delete-multiple-content-searches.md) ricerche per identificare ed eliminare in modo rapido ed efficiente i dati di ricerca 

- [Clonare una ricerca di contenuto](clone-a-content-search.md) e confrontare rapidamente i risultati di query di ricerca con parole chiave diverse eseguite nelle stesse posizioni di contenuto. oppure utilizzare lo script per risparmiare tempo senza dover immettere di nuovo un numero elevato di percorsi di contenuto quando si crea una nuova ricerca