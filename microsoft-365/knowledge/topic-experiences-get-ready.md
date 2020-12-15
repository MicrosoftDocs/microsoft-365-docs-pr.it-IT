---
title: Preparare l'ambiente per le esperienze di argomento (anteprima)
description: Prepara l'ambiente in modo che sia possibile fornire il massimo contenuto possibile per gli utenti con esperienze di argomento (anteprima).
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX
ms.openlocfilehash: 19112b222be328eb75b7eea807bea94e524fd56d
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683437"
---
# <a name="get-your-environment-ready-for-topic-experiences-preview"></a>Preparare l'ambiente per le esperienze di argomento (anteprima)

> [!Note]
> Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex. [Altre informazioni su Project Cortex](https://aka.ms/projectcortex).

Per sfruttare al meglio le esperienze degli argomenti, si desidera includere il contenuto più possibile incluso nell'argomento Discovery, in modo che sia possibile disporre di un set di temi completo per gli utenti. Tuttavia, quali contenuti devono essere utilizzati per l'individuazione degli argomenti? In che modo è possibile massimizzare il contenuto indicizzato, mantenendo il controllo? Maggiore è il contenuto nell'ambito, maggiore è la comprensione dell'intelligenza artificiale. In questo articolo vengono illustrati i passaggi per la pianificazione per garantire che si includa il contenuto appropriato e che siano disponibili le persone e le risorse appropriate per creare una buona esperienza per gli utenti.

Per pianificare le esperienze sugli argomenti (anteprima), è necessario:

![Eseguire la migrazione, la connessione, la modernizzazione, la sicurezza e l'identificazione dei passaggi per l'onboarding per la gestione delle informazioni](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Eseguire la migrazione del contenuto a SharePoint](#1-migrate-content-to-microsoft-365)
    - Nell'argomento data mining è incluso solo il contenuto nei siti di SharePoint.
      - Se possibile, eseguire la migrazione di contenuto prezioso in SharePoint Online da origini esterne.
      - Definire la priorità delle origini di contenuto con un elevato potenziale di conoscenza tacita.
      - Evidenziare i vantaggi offerti dalla Knowledge Management per incoraggiare gli utenti a spostare contenuto da OneDrive a siti di SharePoint.

2. [Connettere informazioni a Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In futuro, il contenuto esterno può essere introdotto nel grafico delle informazioni e diventare disponibile.
    - Per i contenuti che non possono essere spostati, è consigliabile utilizzare i connettori grafico per migliorare la ricerca e prepararsi per l'inclusione futura.

3. [Modernizzare le pagine di SharePoint](#3-modernize-sharepoint-pages)
    - Le schede degli argomenti possono essere riemerse solo nelle pagine moderne.
    - Identificare le pagine classiche di alto profilo che sono candidati alla modernizzazione.

4. [Proteggere il contenuto in modo appropriato](#4-secure-content-appropriately)
    - Le risorse dell'argomento sono rimosse dalla sicurezza in base alle autorizzazioni di un utente.
    - Identificare qualsiasi contenuto che potrebbe presentare autorizzazioni non corrette per la larghezza o la limitazione:
      - Incoraggiare i proprietari dei siti a utilizzare i report di condivisione per esaminare le autorizzazioni
      - Gli amministratori devono controllare il contenuto condiviso in senso lato tramite la ricerca
      - Incoraggiare i proprietari di contenuti a condividere il contenuto che non è sensibile e che potrebbero avere un vantaggio più ampio per l'organizzazione.
    - Esaminare la configurazione di Microsoft Graph su utenti e contenuti:
      - Argomento data mining la configurazione che esclude il contenuto dalla ricerca o dall'approfondimento. Controllare se queste configurazioni sono ancora rilevanti.

5. [Identificare i responsabili della conoscenza e gli argomenti](#5-identify-knowledge-managers-and-topics)
    - Utilizzare le tassonomie esistenti per creare manualmente gli argomenti.
    - Identificare gli esperti in materia (PMI) per gli argomenti previsti o con seeding.
    - Identificare i siti che coprono un corpo di dati di valore elevato che è possibile utilizzare per l'estrazione degli argomenti pilota.
    - Coinvolgere i Knowledge Manager e le community di pratica.

## <a name="1-migrate-content-to-microsoft-365"></a>1. eseguire la migrazione del contenuto a Microsoft 365

Sono disponibili diversi strumenti e servizi per la migrazione: è possibile ottenere una panoramica e informazioni su come eseguire la migrazione [per eseguire la migrazione del contenuto a Microsoft 365](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online). Gli strumenti di migrazione includono:

- [Gestione migrazione](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Strumento di migrazione di SharePoint](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Strumenti e servizi di migrazione dei partner](https://www.microsoft.com/solution-providers)

Sfruttare al massimo la migrazione:

- Eseguire la migrazione a un sito moderno che include Microsoft teams. Durante l'indicizzazione può verificarsi su qualsiasi sito di SharePoint (classico o moderno), la visualizzazione di argomenti per gli utenti tramite evidenziazioni e le schede si verifica solo nelle pagine moderne.
- Maintain usernames-la maggior parte degli strumenti di migrazione consente di eseguire il mapping delle identità degli utenti nella migrazione, in modo che le proprietà create o modificate da vengano mantenute dopo la migrazione. Questo è importante per gli argomenti, poiché la paternità dei file viene utilizzata per identificare gli esperti che vengono aggiunti a una pagina o a una scheda di argomento. 
- Rendere descrittivo i nomi degli account di servizio-ci saranno alcuni casi in cui non è possibile mantenere il nome utente. Ad esempio, se si sta eseguendo la migrazione di contenuto creato da un utente che non è più un dipendente dell'organizzazione. In questa istanza, la maggior parte degli strumenti di migrazione sposterà un file come se fosse stato creato da un account di amministratore o da un account di servizio. In caso contrario, l'account di servizio potrebbe essere elencato in base a argomenti come esperti. Questo è il luogo in cui la denominazione di quell'account diventa molto importante. Se lo si rende descrittivo, la presenza di questi account non umani sarà comprensibile per gli utenti che utilizzano gli argomenti.

## <a name="2-connect-information-to-microsoft-graph"></a>2. connettere informazioni a Microsoft Graph

Se non è possibile eseguire la migrazione di contenuto, collegarlo al grafico Microsoft:

- Prendere in considerazione l'implementazione di [connettori del contenuto grafico](https://docs.microsoft.com/microsoftsearch/connectors-overview). Utilizzando i connettori, il contenuto esterno può essere indicizzato in Microsoft Graph, in cui gli utenti possono quindi scoprirlo tramite Microsoft Search.
- Gli sviluppi futuri porteranno i dati esterni in esperienze di argomento.

## <a name="3-modernize-sharepoint-pages"></a>3. modernizzare le pagine di SharePoint

Poiché le schede e i punti salienti degli argomenti possono essere visualizzati solo nelle pagine moderne, aggiornare tutte le pagine che si desidera includere nelle esperienze di argomento da classico a moderno. Vedere [modernizzare i siti di SharePoint classici](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites). È possibile utilizzare lo [scanner di modernizzazione di SharePoint](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) per preparare i siti classici per la modernizzazione.

Se si dispone di un gran quantità di siti classici, assegnare la priorità alle pagine di alto profilo per la conversione in versione moderna.

## <a name="4-secure-content-appropriately"></a>4. proteggere il contenuto in modo appropriato

Quando gli utenti interagiscono con una scheda di argomento o una pagina di argomento, possono visualizzare risorse diverse. Ciò è dovuto al fatto che hanno accesso a diversi file associati all'argomento. Se le autorizzazioni sottostanti sono troppo rigorose, gli aspetti fortuiti dell'individuazione delle informazioni tramite gli argomenti potrebbero essere diminuiti. D'altra parte, se sono troppo larghe, un argomento potrebbe esporre il contenuto a un utente che non si intende visualizzare.
La gestione delle autorizzazioni valide è critica qui. And good Permissions Management si basa su una partnership continua tra amministratori e proprietari di contenuti. Anche se potrebbe essere un'attività in corso, è possibile eseguire alcuni passaggi pratici per la preparazione degli argomenti:

- Incoraggiare i proprietari dei siti a esaminare la condivisione e le autorizzazioni.

  I proprietari dei siti di SharePoint possono esaminare un report di condivisione per il sito in cui sono visualizzati tutti i dettagli di tutte le autorizzazioni e i collegamenti di condivisione configurati nel sito, vedere [condivisione di report](https://docs.microsoft.com/sharepoint/sharing-reports). In questo elenco vengono elencati gli utenti interni ed esterni.

  I proprietari dei siti possono anche vedere chi ha le autorizzazioni per il sito accedendo alle pagine delle impostazioni per le autorizzazioni per il **sito** e le **autorizzazioni avanzate** .

  1. Nel sito scegliere **Impostazioni**  >  **sito autorizzazioni**. Controllare se sono elencati i proprietari dei siti, i membri del sito e i visitatori del sito. Controllare gli utenti guest.
  2. Nella pagina **autorizzazioni** scegliere **Impostazioni avanzate autorizzazioni**. È possibile controllare le autorizzazioni esclusive e vedere chi ha accesso limitato a qualsiasi elemento del sito.

- Controllare i gruppi e i team di Microsoft 365 per assicurarsi che siano impostati in modo appropriato come gruppi o team pubblici o privati. I nuovi team e i gruppi di Microsoft 365 sono impostati come privati per impostazione predefinita, ma quando sono stati rilasciati per la prima volta come pubblico Se si è in precedenza adottanti queste tecnologie, potrebbe essere necessario esaminare. Inoltre, la funzione di un team si evolve spesso nel ciclo di vita e potrebbe essere necessario aggiornare l'impostazione in modo da riflettere l'utilizzo corrente del team.
- Esaminare l'utilizzo di "tutti", "tutti tranne gli utenti esterni" o gruppi di sicurezza di grandi dimensioni. Il contenuto può essere condiviso erroneamente con questi valori. Per esaminare l'utilizzo di questi gruppi, è possibile eseguire le operazioni seguenti:
  - Creare un account privo di appartenenze a gruppi
  - Utilizzare la ricerca con questo account per individuare il contenuto ampiamente condiviso.
  - Se il contenuto inappropriato è visibile per questo account tramite la ricerca, è possibile collaborare con i proprietari dei siti per correggere la configurazione delle autorizzazioni.

Oltre alle autorizzazioni, è anche possibile controllare l'ambito di ciò che è individuabile tramite gli argomenti. Si è sempre in controllo di ciò che è indicizzato.

Gli amministratori possono configurare l'indicizzazione nell'interfaccia di amministrazione di Microsoft 365. Quando si configura la [gestione delle informazioni](set-up-topic-experiences.md), è possibile:

- Consenti l'individuazione in tutti i siti di SharePoint o specifica i siti da includere o escludere come origini degli argomenti.
- Se si dispone di termini riservati, è possibile escludere anche gli argomenti per nome. Ad esempio, se si ha il nome di un progetto sensibile, in cui non si desidera che venga visualizzata un'evidenziazione o una scheda, indipendentemente dalle autorizzazioni dell'utente, è possibile escludere il nome del progetto.

A livello di contenuto, è anche possibile controllare gli elementi individuabili. Tutte le configurazioni eseguite per escludere il contenuto dalla ricerca verranno utilizzate anche dall'individuazione del contenuto. Ad esempio, se è stata esclusa una raccolta documenti specifica che viene visualizzata nei risultati di ricerca, questa raccolta documenti non verrà utilizzata per l'individuazione degli argomenti.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. identificare Knowledge Manager e argomenti

La gestione degli argomenti prevede tre ruoli chiave, tra cui due nuovi ruoli di Azure Active Directory (AAD): Knowledge Administrator e Knowledge Manager:

- L'amministratore della Knowledge base (KA) è un ruolo tecnico, in genere in esso. Questo ruolo consente la configurazione dell'argomento experiences nell'interfaccia di amministrazione di M365, nonché la configurazione dell'argomento Discovery and Visibility.
- Il Knowledge Manager (KM) è compatibile con gli argomenti stessi e supervisiona la qualità e la completezza.
- Gli argomenti contributori (TCs) non si basano su un ruolo AAD, bensì sulle autorizzazioni nell'interfaccia di amministrazione. Sono esperti in grado di curare il contenuto degli argomenti, l'aggiunta di risorse e persone.

A seconda dell'organizzazione, è possibile che si disponga di poche o numerose persone che agiscono in questi ruoli. Per alcune organizzazioni, possono essere le stesse persone.

| Amministratore delle informazioni | Knowledge Manager | Collaboratore dell'argomento |
|:-------|:-------|:-------|:-------|
| Ruolo AAD | Ruolo AAD | PMI |
| Ha accesso all'interfaccia di amministrazione | Ha accesso all'interfaccia di amministrazione | Nessun accesso all'interfaccia di amministrazione |
| Configura le esperienze degli argomenti | Possiede la gestione e la qualità degli argomenti | Contribuisce agli argomenti in base alle proprie competenze. |
| Assicura che gli standard di sicurezza e conformità siano applicati e comprendano il contratto di licenza.| Esegue le attività di gestione degli argomenti, ad esempio, creare, modificare, eliminare e rifiutare. Supporta gli argomenti che collaborano con le rispettive attività. | Cura le informazioni e il contenuto nelle pagine degli argomenti, tra cui le persone e le risorse sono state bloccate a quell'argomento. |

I punti salienti e le schede verranno visualizzati dagli utenti nel contesto del lavoro, ad esempio quando sfogliano le pagine moderne in SharePoint. È possibile controllare l'esperienza dell'utente finale per gli argomenti.

- Chi può visualizzare gli argomenti? La visibilità dell'argomento è configurata nell'interfaccia di amministrazione di Microsoft 365. Scegliere i gruppi che consentono di visualizzare gli argomenti:
  - Tutti gli utenti dell'organizzazione. "Tutti" non include gli ospiti, sono tutti gli utenti interni nella directory
  - Solo persone o gruppi di sicurezza selezionati (questa opzione è valida anche quando si eseguono ancora le esperienze sugli argomenti, in modo da poter eseguire il test con un sottoinsieme di utenti). Se si desidera che gli utenti visualizzino gli argomenti, è necessario utilizzare l'opzione "persone o gruppi di sicurezza selezionati" e concedere loro una licenza.
  - Nessuno.

    Tutti gli utenti, anche gli utenti guest, dovranno applicare una licenza per visualizzare l'argomento Experience. E ricorda che le autorizzazioni controllano sempre ciò che può essere visto.

- Quali sono gli argomenti visibili? È possibile scegliere di:
  - Mostra tutti gli argomenti candidati.
  - Mostra solo gli argomenti confermati.

Ora che sono presenti i responsabili, gli esperti e gli utenti, è possibile parlare degli argomenti stessi.

- È consigliabile eseguire il seeding degli argomenti nell'elenco dei temi. La qualità e la quantità degli argomenti si basano sul contenuto: verrà creato solo come argomento se è incluso nel contenuto che si trova nell'ambito. Se sono disponibili informazioni e prove sufficienti per l'argomento, verrà creato dall'IA. Gli argomenti di seeding sono il luogo in cui possono essere utili gli esperti del Knowledge Manager e del soggetto. La combinazione della conoscenza umana con l'IA è il percorso migliore per gli argomenti di qualità. Pertanto, se sono presenti argomenti che possono essere creati manualmente, è possibile creare questi elementi nell'argomento centro. In questo modo si otterrà un segnale forte della pertinenza dell'argomento e verranno identificate le risorse e gli utenti da associare a questo argomento.
- Utilizzare le tassonomie esistenti per facilitare la pianificazione dell'argomento, sia da SharePoint o altrove. Le tassonomie esistenti includono spesso termini organizzativi, prodotti, aree tematiche e così via. Le origini per gli argomenti possono provenire anche da elenchi di progetti, segnalibri di ricerca esistenti e così via.
