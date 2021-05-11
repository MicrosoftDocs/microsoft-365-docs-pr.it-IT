---
title: Introduzione ai casi di eDiscovery di base in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Descrive come iniziare a usare Core eDiscovery in Microsoft 365. Dopo aver assegnato le autorizzazioni di eDiscovery e aver creato un caso, è possibile aggiungere membri, creare blocchi di eDiscovery e quindi cercare ed esportare contenuto rilevante per l'indagine.
ms.openlocfilehash: 00506c2f072fff6aa30c7d96bffdc18eb5eda20b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311017"
---
# <a name="get-started-with-core-ediscovery-in-microsoft-365"></a>Introduzione a Core eDiscovery in Microsoft 365

Core eDiscovery in Microsoft 365 fornisce uno strumento di eDiscovery di base che le organizzazioni possono utilizzare per cercare ed esportare contenuto in Microsoft 365 e Office 365. È inoltre possibile utilizzare Core eDiscovery per inserire un blocco di eDiscovery sui percorsi del contenuto, ad esempio cassette postali di Exchange, siti SharePoint, account OneDrive e Microsoft Teams. Non è necessario distribuire Core eDiscovery, ma esistono alcune attività preliminari che un amministratore IT e un responsabile di eDiscovery devono completare prima che l'organizzazione possa iniziare a usare Core eDiscovery per cercare, esportare e conservare il contenuto.

In questo articolo vengono illustrati i passaggi necessari per configurare Core eDiscovery. Ciò include la garanzia delle licenze appropriate necessarie per accedere a Core eDiscovery e mantenere eDiscovery nei percorsi dei contenuti, nonché assegnare autorizzazioni al team IT, legale e di indagine in modo che possano accedere e gestire i casi. In questo articolo viene inoltre fornita una panoramica generale dell'utilizzo dei casi per cercare ed esportare contenuto.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Passaggio 1: Verificare e assegnare licenze appropriate

Le licenze per Core eDiscovery richiedono l'abbonamento all'organizzazione appropriato e le licenze per utente.

- **Sottoscrizione organizzazione:** Per accedere a Core eDiscovery nel Centro conformità Microsoft 365 o nel Centro sicurezza & di Office 365 e utilizzare le funzionalità di conservazione ed esportazione, l'organizzazione deve disporre di una sottoscrizione Microsoft 365 E3 o Office 365 E3 o successiva.

- **Licenze per utente:** Per inserire un blocco di eDiscovery su cassette postali e siti, a un utente deve essere assegnata una delle licenze seguenti, a seconda della sottoscrizione dell'organizzazione:

  - Una Microsoft 365 E3 o Office 365 E3 o superiore

   OPPURE

  - Office 365 Licenza E1 con una licenza Exchange Online Piano 2 o Archiviazione Exchange Online di componente aggiuntivo

  E

  - Office 365 Licenza E1 con una licenza SharePoint online piano 2 o OneDrive for Business licenza del componente aggiuntivo Piano 2
  
  Per informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](../admin/manage/assign-licenses-to-users.md)

Per informazioni sulle licenze:

- Scarica e vedi la soluzione "Individuazione & rispondi" nel confronto delle licenze [Microsoft 365 conformità](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).

- Vedere la [descrizione del & Centro sicurezza e conformità.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="step-2-assign-ediscovery-permissions"></a>Passaggio 2: Assegnare le autorizzazioni di eDiscovery

Per accedere a Core eDiscovery o essere aggiunto come membro di un caso di eDiscovery di base, a un utente devono essere assegnate le autorizzazioni appropriate. In particolare, un utente deve essere aggiunto come membro del gruppo di ruoli Manager eDiscovery nel Centro sicurezza Office 365 & conformità. I membri di questo gruppo di ruoli possono creare e gestire i casi di eDiscovery di base. Possono aggiungere e rimuovere membri, inserire un blocco eDiscovery sugli utenti, creare e modificare ricerche ed esportare contenuto da un caso di eDiscovery di base.

Completare la procedura seguente per aggiungere utenti al gruppo di ruoli Manager eDiscovery:

1. Accedere a e accedere usando le credenziali per un account amministratore [https://protection.office.com/permissions](https://protection.office.com/permissions) nell'organizzazione Microsoft 365 o Office 365 aziendale.

2. Nella pagina **Autorizzazioni** selezionare il gruppo di ruoli **Manager eDiscovery.**

3. Nella pagina a comparsa Gestione eDiscovery fare clic su **Modifica** accanto alla sezione **Gestione eDiscovery.**

4. Nella pagina **Choose eDiscovery Manager** della procedura guidata edit role group fare clic **su Choose Discovery Manager.**

5. Fare **clic su** Aggiungi, quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Fare **clic su** Aggiungi per aggiungere gli utenti selezionati e quindi fare clic su **Fine.**

7. Fare **clic** su Salva per aggiungere gli utenti al gruppo di ruoli, quindi fare clic su **Chiudi** per completare il passaggio.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Ulteriori informazioni sul gruppo di ruoli Manager eDiscovery

Esistono due sottogruppi nel gruppo di ruoli Manager eDiscovery. La differenza tra questi sottogruppi dipende dall'ambito.

- **eDiscovery Manager:** può visualizzare e gestire i casi di eDiscovery di base creati o di cui sono membri. Se un altro responsabile di eDiscovery crea un caso ma non aggiunge un secondo responsabile di eDiscovery come membro di tale caso, il secondo gestore di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina eDiscovery di base nel Centro conformità. In generale, la maggior parte degli utenti dell'organizzazione può essere aggiunta al sottogruppo Manager di eDiscovery.

- **Amministratore di eDiscovery:** può eseguire tutte le attività di gestione dei casi che possono essere eseguite da un responsabile di eDiscovery. Inoltre, un amministratore di eDiscovery è in grado di:

  - Visualizzare tutti i casi elencati nella pagina Core eDiscovery.
  
  - Gestire qualsiasi caso nell'organizzazione dopo essersi aggiunti come membri del caso.

  - Accedere ed esportare i dati del caso per qualsiasi caso nell'organizzazione.

  A causa dell'ampio ambito di accesso, un'organizzazione deve avere solo pochi amministratori membri del sottogruppo Amministratori di eDiscovery.

Per ulteriori informazioni sulle autorizzazioni di eDiscovery e una descrizione di ogni ruolo assegnato al gruppo di ruoli Manager eDiscovery, vedere [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Passaggio 3: Creare un caso di eDiscovery di base

Il passaggio successivo consiste nel creare un caso e iniziare a usare Core eDiscovery. Completare la procedura seguente per creare un caso e aggiungere membri. L'utente che crea il caso viene aggiunto automaticamente come membro.

1. Accedere a e accedere utilizzando le credenziali per un account utente a cui sono state assegnate [https://compliance.microsoft.com](https://compliance.microsoft.com) le autorizzazioni eDiscovery appropriate. I membri del gruppo di ruoli Gestione organizzazione possono anche creare casi di eDiscovery di base.

2. Nel riquadro di spostamento sinistro del Centro Microsoft 365 conformità fare clic su **Mostra** tutto e quindi su **eDiscovery > Core**.

3. Nella pagina **Core eDiscovery** fare clic **su Crea un caso.**

4. Nella pagina Riquadro a **comparsa Nuovo** caso assegnare al caso un nome (obbligatorio) e quindi digitare una descrizione facoltativa. Il nome del caso deve essere univoco nell'organizzazione.

5. Fare **clic su** Salva per creare il caso.

   Il nuovo caso viene creato e visualizzato nella pagina Core eDiscovery. Potrebbe essere necessario fare clic **su Aggiorna** per visualizzare il nuovo caso.

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Passaggio 4 (facoltativo): Aggiungere membri a un caso di eDiscovery di base

Se si crea un caso nel passaggio 3 e si è l'unica persona che utilizzerà il caso, non è necessario eseguire questo passaggio. È possibile iniziare a utilizzare il caso per creare blocchi di eDiscovery, cercare contenuto ed esportare i risultati della ricerca. Eseguire questo passaggio se si desidera concedere ad altri utenti (o gruppi di ruoli) l'accesso al caso.

1. Nella pagina **Core eDiscovery** nel Centro Microsoft 365 conformità fare clic sul nome del caso a cui si desidera aggiungere membri.

2. Nella home page del caso, selezionare la **Impostazioni** e quindi selezionare Autorizzazioni **& accesso**.

3. Nella pagina **a comparsa & accesso,** **in** Membri, fare clic su **Aggiungi** per aggiungere membri al caso.

    È inoltre possibile scegliere di aggiungere gruppi di ruoli come membri di un caso. In **Gruppi di ruoli** fare clic su **Aggiungi.** È possibile assegnare a un caso solo i gruppi di ruoli di cui si è membri. Questo perché i gruppi di ruoli controllano chi può assegnare membri a un caso di eDiscovery.

4. Nell'elenco delle persone o dei gruppi di ruoli che possono essere aggiunti come membri del caso, fare clic a sinistra del nome delle persone (o dei gruppi di ruoli) che si desidera aggiungere. Se si dispone di un elenco di utenti o gruppi  di ruoli che possono essere aggiunti come membri, utilizzare la casella di ricerca per cercare una persona o un gruppo di ruoli specifico nell'elenco.
  
5. Dopo aver selezionato le persone o i gruppi di ruoli da aggiungere come membri del caso, fare clic su **Salva** per salvare i nuovi membri o gruppi di ruoli.

## <a name="explore-the-core-ediscovery-workflow"></a>Esplorare il flusso di lavoro di eDiscovery di base

Per iniziare a usare eDiscovery di base, ecco un semplice flusso di lavoro per la creazione di blocchi di eDiscovery per le persone di interesse, la ricerca di contenuti rilevanti per l'indagine e quindi l'esportazione di questi dati per un'ulteriore revisione. In ognuno di questi passaggi, verranno evidenziate anche alcune funzionalità estese di eDiscovery di base che è possibile esplorare.

![Flusso di lavoro eDiscovery di base](../media/CoreEdiscoveryWorkflow.png)

1. **[Creare un blocco di eDiscovery](create-ediscovery-holds.md)**. Il primo passaggio dopo la creazione di un caso consiste nell'inserire un'esenzione (nota anche come blocco *di eDiscovery)* sulle posizioni dei contenuti delle persone di interesse nell'indagine. I percorsi del contenuto includono Exchange cassette postali, SharePoint, account OneDrive, cassette postali e siti associati a Microsoft Teams e Office 365 gruppi. Anche se questo passaggio è facoltativo, la creazione di un blocco di eDiscovery mantiene il contenuto che potrebbe essere rilevante per il caso durante l'indagine. Quando si crea un blocco di eDiscovery, è possibile conservare tutto il contenuto in percorsi di contenuto specifici oppure creare un blocco basato su query per conservare solo il contenuto corrispondente a una query di blocco. Oltre a conservare il contenuto, un altro buon motivo per creare blocchi di eDiscovery consiste nel cercare rapidamente le posizioni di contenuto in attesa (invece di dover selezionare ogni posizione in cui eseguire la ricerca) quando si creano ed eseguono ricerche nel passaggio successivo. Dopo aver completato l'indagine, è possibile rilasciare qualsiasi blocco creato.

2. **[Cercare contenuto](search-for-content-in-core-ediscovery.md)**. Dopo aver creato i blocchi di eDiscovery, utilizzare lo strumento di ricerca incorporato per cercare i percorsi di contenuto in attesa. È inoltre possibile cercare in altri percorsi di contenuto i dati che potrebbero essere rilevanti per il caso. È possibile creare ed eseguire ricerche diverse associate al caso. Le parole chiave, le proprietà e le condizioni vengono utilizzate per creare [query](keyword-queries-and-search-conditions.md) di ricerca che restituiscono risultati di ricerca con i dati più rilevanti per il caso. È inoltre possibile:

   - Visualizzare le statistiche di ricerca che consentono di perfezionare una query di ricerca per restringere i risultati.

   - Visualizzare in anteprima i risultati della ricerca per verificare rapidamente se vengono trovati i dati pertinenti.

   - Rivedere una query ed eseguire di nuovo la ricerca.

3. **[Esportare e scaricare i risultati della ricerca](export-content-in-core-ediscovery.md)**. Dopo aver cercato e trovato i dati rilevanti per l'indagine, è possibile esportarlo fuori Office 365 per la revisione da parte di persone esterne al team di indagine. L'esportazione dei dati è un processo in due passaggi. Il primo passaggio consiste nell'esportare i risultati di una ricerca in caso di Office 365. Questa operazione viene eseguita copiando i risultati di una ricerca in un percorso Archiviazione di Azure fornito da Microsoft. Il passaggio successivo consiste nell'utilizzare lo strumento di esportazione di eDiscovery per scaricare il contenuto in un computer locale. Oltre ai file di dati esportati, il contenuto del pacchetto di esportazione contiene anche un report di esportazione, un rapporto riepilogativo e un rapporto errori.
