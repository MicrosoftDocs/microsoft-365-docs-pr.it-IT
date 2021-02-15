---
title: Prepara l'ambiente per gli argomenti di Microsoft Viva
description: Prepara l'ambiente in modo da poter fornire il maggior numero possibile di contenuti agli utenti con Microsoft Viva Topics.
ms.author: samanro
author: samanro
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 5a13af3e78848471b436d44ab051eca945176c74
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107697"
---
# <a name="get-your-environment-ready-for-microsoft-viva-topics"></a>Prepara l'ambiente per gli argomenti di Microsoft Viva

Per utilizzare al meglio Viva Topics, è necessario includere il maggior numero possibile di contenuti per l'individuazione degli argomenti, in modo da poter disporre di una ricca serie di argomenti per gli utenti. Ma quale contenuto deve essere usato per l'individuazione degli argomenti? Come è possibile ottimizzare il contenuto indicizzato, mantenendo il controllo? Maggiore è l'ambito del contenuto, migliori sono le informazioni che l'intelligenza artificiale può scoprire. In questo articolo viene illustrata la procedura di pianificazione per assicurarsi di includere il contenuto appropriato e di disporre delle persone e delle risorse appropriate per un'esperienza ottimale per gli utenti.

Per pianificare Viva Topics, è necessario:

![Eseguire la migrazione, connettersi, modernizzare, proteggere e identificare i passaggi per l'onboarding alla gestione delle conoscenze](../media/knowledge-management/km-adoption-onboarding-checklist.png)

1. [Eseguire la migrazione del contenuto a SharePoint](#1-migrate-content-to-microsoft-365)
    - L'indicizzazione degli argomenti include solo il contenuto dei siti di SharePoint.
      - Se possibile, eseguire la migrazione di contenuti importanti in SharePoint Online da origini esterne.
      - Assegnare priorità alle origini di contenuto con un elevato potenziale per la conoscenza tacita.
      - Evidenziare i vantaggi della gestione delle informazioni per incoraggiare gli utenti a spostare il contenuto da OneDrive ai siti di SharePoint.

2. [Connettere le informazioni a Microsoft Graph](#2-connect-information-to-microsoft-graph)
    - In futuro, il contenuto esterno potrà essere inserito nel knowledge graph e diventare disponibile.
    - Per i contenuti che non possono essere spostati, è consigliabile utilizzare i connettori graph per migliorare la ricerca e prepararsi per l'inclusione futura.

3. [Modernizzare le pagine di SharePoint](#3-modernize-sharepoint-pages)
    - Le schede degli argomenti possono essere etere solo nelle pagine moderne.
    - Identificare le pagine classiche di alto profilo candidate alla modernizzazione.

4. [Proteggere il contenuto in modo appropriato](#4-secure-content-appropriately)
    - Le risorse degli argomenti sono limitate per motivi di sicurezza in base alle autorizzazioni di un utente.
    - Identificare eventuali contenuti che potrebbero disporre di autorizzazioni estese o restrittive in modo errato:
      - Incoraggiare i proprietari dei siti a usare i report di condivisione per esaminare le autorizzazioni
      - Fare in modo che gli amministratori controllino il contenuto ampiamente condiviso tramite la ricerca
      - Incoraggiare i proprietari di contenuti a condividere contenuti non sensibili e che potrebbero avere vantaggi più ampi per l'organizzazione.
    - Esaminare la configurazione di Microsoft Graph per gli utenti e il contenuto:
      - L'indicizzazione degli argomenti rispetta la configurazione escludendo il contenuto dalla ricerca o da Delve (ad esempio, NOINDEX). Verificare se queste configurazioni sono ancora pertinenti.

5. [Identificare i knowledge manager e gli argomenti](#5-identify-knowledge-managers-and-topics)
    - Usa tassonomie esistenti per creare manualmente argomenti o assistenza per confermare gli argomenti suggeriti dall'intelligenza artificiale.
    - Identificare gli esperti in materia (SME) per argomenti anticipati o seeded.
    - Identificare i siti che coprono una grande quantità di dati importanti che possono essere utilizzati per il mining di argomenti pilota.
    - Coinvolgere i knowledge manager e le community pratiche.

## <a name="1-migrate-content-to-microsoft-365"></a>1. Eseguire la migrazione del contenuto a Microsoft 365

Sono disponibili diversi strumenti e servizi utili per la migrazione: è possibile ottenere una panoramica e informazioni su come eseguire la migrazione in Eseguire la migrazione dei contenuti a [Microsoft 365.](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) Gli strumenti di migrazione includono:

- [Gestione migrazione](https://docs.microsoft.com/sharepointmigration/mm-get-started)
- [Strumento di migrazione di SharePoint](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)
- [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)
- [Strumenti e servizi per la migrazione dei partner](https://www.microsoft.com/solution-providers)

Utilizzare al meglio la migrazione:

- Eseguire la migrazione a un sito moderno, che include Microsoft Teams. Anche se l'indicizzazione può avvenire in qualsiasi sito di SharePoint (classico o moderno), la visualizzazione di argomenti agli utenti tramite evidenziazioni e schede avviene solo nelle pagine moderne.
- Mantenere i nomi utente: la maggior parte degli strumenti di migrazione consente di mappare le identità degli utenti durante la migrazione, in modo che le proprietà come Creato da o Modificato da siano mantenute dopo la migrazione. Questo è importante per gli argomenti perché la creazione dei file viene utilizzata per identificare gli esperti che vengono aggiunti a una pagina o a una scheda dell'argomento. 
- Rendere descrittivi i nomi degli account di servizio: in alcuni casi non è possibile mantenere i nomi utente. Ad esempio, se si esegue la migrazione di contenuto creato da un utente che non è più un dipendente dell'organizzazione. In questo caso, la maggior parte degli strumenti di migrazione sposta un file come se fosse stato creato da un account amministratore o da un account di servizio. Se ciò accade di frequente, l'account di servizio potrebbe essere elencato in base agli argomenti come esperto. È qui che la denominazione dell'account diventa molto importante. Se si rende descrittivo, la presenza di questi account non umani sarà comprensibile agli utenti che utilizzano gli argomenti.

## <a name="2-connect-information-to-microsoft-graph"></a>2. Connettere le informazioni a Microsoft Graph

Se non è possibile eseguire la migrazione di alcuni contenuti, connetterlo con Microsoft Graph:

- Prendere in considerazione [l'implementazione di Graph Content Connectors.](https://docs.microsoft.com/microsoftsearch/connectors-overview) Utilizzando i connettori, il contenuto esterno può essere indicizzato in Microsoft Graph, dove gli utenti possono individuarlo tramite Microsoft Search.
- Gli sviluppi futuri porteranno i dati esterni in Viva Topics.

## <a name="3-modernize-sharepoint-pages"></a>3. Modernizzare le pagine di SharePoint

Poiché le schede degli argomenti e le evidenziazioni possono essere visualizzate solo nelle pagine moderne, aggiorna le pagine che vuoi includere in Viva Topics dal classico al moderno. Vedere [Modernizzare i siti di SharePoint classici.](https://docs.microsoft.com/sharepoint/dev/transform/modernize-classic-sites) È possibile utilizzare lo [scanner di modernizzazione di SharePoint per](https://docs.microsoft.com/sharepoint/dev/transform/modernize-scanner) preparare i siti classici per la modernizzazione.

Se si dispone di molti siti classici, assegnare priorità alle pagine di alto profilo per la conversione in moderna.

## <a name="4-secure-content-appropriately"></a>4. Proteggere il contenuto in modo appropriato

Quando gli utenti interagiscono con una scheda argomento o una pagina di argomento, possono visualizzare risorse diverse. Ciò è dovuto al fatto che hanno accesso a file diversi associati all'argomento. Se le autorizzazioni sottostanti sono troppo rigide, gli aspetti più serendipiti dell'individuazione delle informazioni tramite gli argomenti potrebbero essere ridotte. D'altra parte, se sono troppo ampi, un argomento potrebbe presentare contenuto a un utente che non vuoi che veda.
Una buona gestione delle autorizzazioni è fondamentale in questo caso. Inoltre, una buona gestione delle autorizzazioni si basa su una partnership continua tra amministratori e proprietari di contenuti. Anche se può trattarsi di un'attività continua, esistono alcuni passaggi pratici che è possibile eseguire durante la preparazione degli argomenti:

- Incoraggiare i proprietari dei siti a rivedere la condivisione e le autorizzazioni.

  I proprietari dei siti di SharePoint possono esaminare un report di condivisione per il proprio sito che mostra tutti i dettagli di tutte le autorizzazioni e i collegamenti di condivisione configurati nel sito, vedere [Rapporti di condivisione.](https://docs.microsoft.com/sharepoint/sharing-reports) Vengono elencati gli utenti interni ed esterni (guest).

  I proprietari dei siti possono inoltre vedere chi dispone delle autorizzazioni per il sito andando nelle **pagine Autorizzazioni sito** e Impostazioni avanzate **autorizzazioni.**

  1. Nel sito scegliere **Impostazioni**  >  **autorizzazioni sito.** Verificare chi è elencato in Proprietari del sito, Membri del sito e Visitatori del sito. Verificare la presenza di eventuali utenti guest.
  2. Nella pagina **Autorizzazioni** scegliere **Impostazioni avanzate autorizzazioni.** È possibile verificare la presenza di autorizzazioni univoche e vedere chi ha accesso limitato a qualsiasi elemento del sito.

- Controllare i gruppi di Microsoft 365 e Teams per verificare che siano impostati in modo appropriato come gruppi o team pubblici o privati. I nuovi team e i gruppi di Microsoft 365 sono impostati come privati per impostazione predefinita, ma al primo rilascio sono pubblici per impostazione predefinita. Se si sono già adottati in precedenza queste tecnologie, è consigliabile esaminarlo. Inoltre, la funzione di un team si evolve spesso nel corso del ciclo di vita e potrebbe essere necessario aggiornare l'impostazione in modo da riflettere l'uso corrente del team.
- Esaminare l'uso di "tutti", "tutti tranne gli utenti esterni" o gruppi di sicurezza generali. Il contenuto potrebbe essere condiviso in modo errato con questi valori. Per esaminare l'uso di questi gruppi, è possibile:
  - Creare un account senza appartenenza a gruppi
  - Usare la ricerca con questo account per individuare contenuti condivisi su larga parte.
  - Se il contenuto inappropriato è visibile a questo account tramite la ricerca, è possibile collaborare con i proprietari del sito per correggere la configurazione delle autorizzazioni.

Oltre alle autorizzazioni, è anche possibile controllare l'ambito di ciò che è individuabile tramite gli argomenti. Si ha sempre il controllo di ciò che è indicizzato.

Gli amministratori possono configurare l'indicizzazione nell'interfaccia di amministrazione di Microsoft 365. Quando si configura [Knowledge Management,](set-up-topic-experiences.md)è possibile:

- Consentire l'individuazione in tutti i siti di SharePoint o specificare i siti da includere o escludere come origini degli argomenti.
- Se si dispone di termini riservati, è anche possibile escludere gli argomenti in base al nome. Ad esempio, se hai il nome di un progetto sensibile, in cui non vuoi visualizzare un'evidenziazione o una scheda, indipendentemente dalle autorizzazioni dell'utente, puoi escludere il nome del progetto.

A livello di contenuto, è anche possibile controllare gli elementi individuabili. Tutte le configurazioni eseguite per escludere il contenuto dalla ricerca verranno usate anche dall'individuazione del contenuto. Se ad esempio si è esclusa la visualizzazione di una raccolta documenti specifica nei risultati di ricerca, questa raccolta documenti non verrà utilizzata per l'individuazione degli argomenti.

## <a name="5-identify-knowledge-managers-and-topics"></a>5. Identificare i knowledge manager e gli argomenti

La gestione degli argomenti implica tre ruoli chiave, tra cui due nuovi ruoli di Azure Active Directory (AAD): Amministratore delle conoscenze e Knowledge Manager:

- L'amministratore della knowledge base (KA) è un ruolo tecnico, in genere nell'IT. Questo ruolo consente la configurazione degli argomenti Viva nell'interfaccia di amministrazione di M365, nonché la configurazione dell'individuazione e della visibilità degli argomenti.
- Il Knowledge Manager (KM) collabora con gli argomenti e supervisiona la qualità e la completezza.
- I collaboratori agli argomenti (TC) non si basano su un ruolo di AAD, ma sulle autorizzazioni nell'interfaccia di amministrazione. Sono esperti in materia in grado di curare il contenuto degli argomenti, aggiungendo risorse e persone.

A seconda dell'organizzazione, potrebbero essere presenti poche o molte persone che agiscono in questi ruoli. Per alcune organizzazioni, queste potrebbero essere le stesse persone.

| Amministratore della knowledge base | Knowledge Manager | Collaboratore argomento |
|:-------|:-------|:-------|:-------|
| Ruolo AAD | Ruolo AAD | SME |
| Ha accesso all'interfaccia di amministrazione | Ha accesso all'interfaccia di amministrazione | Nessun accesso all'interfaccia di amministrazione |
| Configurare Viva Topics | È proprietaria della gestione e della qualità degli argomenti | Contribuisce agli argomenti in base alle proprie competenze. |
| Garantisce che vengano applicati gli standard di sicurezza e conformità e comprendi il contratto di licenza.| Esegue attività di gestione degli argomenti, ad esempio la creazione, la modifica, l'eliminazione e il rifiuto di argomenti. Supporta i collaboratori degli argomenti con le loro attività. | Cura le informazioni e il contenuto nelle pagine degli argomenti, incluse le persone e le risorse aggiunte a tale argomento. |

Le evidenziazioni e le schede verranno visualizzate agli utenti nel contesto del proprio lavoro, ad esempio durante l'esplorazione delle pagine moderne in SharePoint. È possibile controllare l'esperienza dell'utente finale per gli argomenti.

- Chi può visualizzare gli argomenti? La visibilità degli argomenti è configurata nell'interfaccia di amministrazione di Microsoft 365. Scegliere i gruppi da consentire di visualizzare gli argomenti:
  - Tutti gli utenti dell'organizzazione. "Tutti" non include gli utenti guest, ma tutti gli utenti interni nella directory
  - Solo le persone o i gruppi di sicurezza selezionati (questa opzione è valida durante l'implementazione di Viva Topics, in modo da poter testare con un sottoinsieme di utenti). Se si desidera che gli utenti guest visualizzano gli argomenti, è necessario utilizzare l'opzione "Utenti o gruppi di sicurezza selezionati" e concedere loro una licenza.
  - Nessuno.

    Tutti gli utenti, anche gli utenti guest, dovranno avere una licenza applicata per visualizzare l'esperienza dell'argomento. Tenere presente che le autorizzazioni controllano sempre ciò che può essere visualizzato.

- Quali argomenti sono visibili? È possibile scegliere di:
  - Mostra tutti gli argomenti candidati.
  - Mostra solo gli argomenti confermati.

Ora che abbiamo i responsabili, gli esperti e gli utenti, possiamo parlare degli argomenti.

- È buona norma eseguire il seeder degli argomenti nell'elenco degli argomenti. La qualità e la quantità di argomenti si basano sul contenuto, che verrà creato come argomento solo se è incluso nel contenuto nell'ambito. Se sono disponibili informazioni e prove sufficienti per l'argomento, verrà creato dall'intelligenza artificiale. Negli argomenti relativi al seeding possono essere utili il Knowledge Manager e gli esperti in materia. La combinazione delle conoscenze umane con l'intelligenza artificiale è il percorso migliore per gli argomenti relativi alla qualità. Pertanto, se ci sono argomenti che prevedi di poter creare manualmente nel Centro argomenti. In questo modo l'intelligenza artificiale riceverà un segnale forte della pertinenza di tale argomento e identificherà le risorse e le persone da associare a tale argomento.
- Usare tassonomie esistenti per facilitare la pianificazione dell'argomento, da SharePoint o altrove. Le tassonomie esistenti spesso includono termini dell'organizzazione, prodotti, aree soggette e così via. Le origini degli argomenti possono inoltre derivare da elenchi di progetti, segnalibri di ricerca esistenti e così via.
