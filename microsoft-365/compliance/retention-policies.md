---
title: Informazioni sui criteri di conservazione per conservare o eliminare automaticamente il contenuto
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
description: Usare i criteri di conservazione per decidere in modo proattivo se conservare il contenuto, eliminarlo o entrambe le cose, ovvero conservarlo ed eliminarlo successivamente, se applicare un singolo criterio all'intera organizzazione o a posizioni o utenti specifici e se applicare un criterio a tutti i contenuti o al contenuto che soddisfa specifiche condizioni.
ms.openlocfilehash: cf38eecaeaf23371c370ad07e723177e3770c7ba
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432337"
---
# <a name="learn-about-retention-policies"></a>Informazioni sui criteri di conservazione

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Per la maggior parte delle organizzazioni, il volume e la complessità dei dati aumentano giorno dopo giorno, a causa di posta elettronica, documenti, messaggi istantanei e altro ancora. La gestione o il controllo efficace di queste informazioni è importante perché è necessario:
  
- **Conformarsi in modo proattivo alle normative del settore e ai criteri interni** che richiedono di conservare il contenuto per un periodo di tempo minimo, ad esempio la norma Sarbanes-Oxley Act richiede che alcuni tipi di contenuto vengano conservati per sette anni. 
    
- **Ridurre i rischi in caso di controversie legali o di violazioni della sicurezza** eliminando definitivamente i contenuti obsoleti che non è più necessario mantenere. 
    
- **Aiutare l'organizzazione a condividere le informazioni in modo efficace e a essere più flessibile** assicurando che gli utenti usino solo contenuti aggiornati e pertinenti. 
    
Un criterio di conservazione consente di raggiungere tutti questi obiettivi. La gestione dei contenuti in genere richiede due azioni:
  
- **Conservare** il contenuto in modo che non possa essere eliminato definitivamente prima del termine del periodo di conservazione. 
    
- **Eliminare** il contenuto in modo permanente alla fine del periodo di conservazione. 
    
Con i criteri di conservazione è possibile:
  
- Decidere proattivamente se conservare il contenuto, eliminarlo o entrambe le cose, ovvero conservarlo ed eliminarlo successivamente.
    
- Applicare un singolo criterio all'intera organizzazione o a posizioni o utenti specifici.
    
- Applicare i criteri a tutto il contenuto o al contenuto che soddisfa specifiche condizioni, ad esempio che contiene parole chiave o [tipi di informazioni sensibili](what-the-sensitive-information-types-look-for.md).
    
Quando si impostano criteri di conservazione per il contenuto, gli utenti possono continuare a modificare e usare il contenuto come sempre. Il contenuto viene mantenuto sul posto, nella posizione originale. Se però qualcuno modifica o elimina contenuto soggetto ai criteri di conservazione, una copia dell'originale viene salvata in una posizione sicura e conservata finché restano in vigore i criteri. Per altre informazioni, vedere la sezione [Funzionamento dei criteri di conservazione con il contenuto presente](#how-a-retention-policy-works-with-content-in-place).
  
Infine, alcune organizzazioni hanno la necessità di conformarsi a normative come la regola 17a-4 della SEC (Securities and Exchange Commission). In base a questa regola, i criteri di conservazione attivati non possono essere disattivati o resi meno restrittivi. Per soddisfare questo requisito, è possibile usare la funzionalità **Protezione dell'archiviazione**. Una volta bloccato un criterio di conservazione, nessuno può disattivarlo o renderlo meno restrittivo, nemmeno un amministratore. Per altre informazioni, vedere la sezione [Usare la protezione dell'archiviazione per la conformità ai requisiti normativi](#use-preservation-lock-to-comply-with-regulatory-requirements) in questa pagina.

## <a name="how-a-retention-policy-works-with-content-in-place"></a>Funzionamento dei criteri di conservazione con il contenuto presente

Quando si include una posizione, ad esempio un sito o una cassetta postale, nei criteri di conservazione, il contenuto rimane nella posizione originale. Gli utenti possono continuare a lavorare normalmente con i propri documenti o messaggi di posta elettronica. Tuttavia, se modificano o eliminano il contenuto incluso nei criteri di conservazione, viene conservata una copia del contenuto al momento dell'applicazione dei criteri.
  
- Per i siti di SharePoint e OneDrive: la copia viene conservata nella **raccolta di archiviazione**. Tenere presente che la raccolta di archiviazione utilizza la quota di spazio di archiviazione del sito.

- Per la posta elettronica e le cartelle pubbliche, la copia viene conservata nella cartella **Elementi ripristinabili**. 

- Per il contenuto di Teams, la copia viene conservata nella cartella **Elementi ripristinabili** di Exchange.

- Per i gruppi di Microsoft 365 ([in precedenza gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), 
    - la cassetta postale del gruppo viene conservata nella cartella **Elementi ripristinabili** di Exchange.
    - Il contenuto del sito viene conservato nella **raccolta di archiviazione**.

> [!NOTE]
> La raccolta di archiviazione consuma spazio di archiviazione non è esente dalla quota di archiviazione di un sito. Potrebbe essere necessario aumentare lo spazio di archiviazione quando si usano criteri di conservazione per i gruppi di SharePoint e Microsoft 365.
> 
Queste posizioni sicure e il contenuto conservato non sono visibili alla maggior parte degli utenti. Con i criteri di conservazione, non è neanche necessario che gli utenti sappiano che il contenuto è soggetto a criteri.

Per informazioni più dettagliate sul funzionamento dei criteri di conservazione con carichi di lavoro diversi, vedere gli articoli seguenti:

- [Informazioni sui criteri di conservazione per SharePoint e OneDrive](retention-policies-sharepoint.md)
- [Informazioni sui criteri di conservazione per Microsoft Teams](retention-policies-teams.md)
- [Informazioni sui criteri di conservazione per Exchange](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Principi di conservazione: cosa ha la precedenza?

È possibile, o addirittura probabile, che al contenuto siano applicati più criteri di conservazione con azioni (conservare, eliminare oppure conservare e quindi eliminare) e periodi di conservazione diversi. Cosa ha la precedenza? Al livello più alto, un contenuto che viene conservato in base a un particolare criterio di conservazione non può essere eliminato definitivamente da un altro criterio di conservazione.
  
![Diagramma dei principi di conservazione](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Per comprendere in che modo i diversi criteri di conservazione vengono applicati al contenuto, tenere presente questi principi di conservazione:
  
1. **La conservazione prevale sull'eliminazione.** Si supponga di avere un criterio di conservazione configurato per eliminare la posta elettronica di Exchange dopo tre anni e un altro criterio di conservazione configurato per conservare la posta elettronica di Exchange per cinque anni e quindi eliminarla. Il contenuto che supera i tre anni verrà eliminato e nascosto agli utenti, ma comunque conservato nella cartella Elementi ripristinabili fino a raggiungere i cinque anni, quando verrà eliminato definitivamente. 
    
2. **Prevale il periodo di conservazione più lungo.** Se un contenuto è soggetto a più criteri di conservazione, verrà mantenuto fino al termine del periodo di conservazione più lungo. 
    
3. **L'inclusione esplicita prevale sull'inclusione implicita.** Questo significa che: 
    
    1. Se un utente assegna manualmente un'etichetta di conservazione con impostazioni di conservazione a un elemento, ad esempio un messaggio di posta elettronica di Exchange o un documento di OneDrive, l'etichetta di conservazione ha la precedenza sui criteri di conservazione assegnati a livello di sito o di cassetta postale e su un'etichetta di conservazione predefinita assegnata tramite la raccolta documenti. Ad esempio, se l'etichetta di conservazione esplicita è configurata per conservare il contenuto per dieci anni, ma i criteri di conservazione assegnati dal sito indicano di conservare il contenuto solo per cinque anni, l'etichetta di conservazione ha la precedenza. Le etichette di conservazione applicate automaticamente sono considerate implicite e non esplicite, perché vengono applicate automaticamente da Microsoft 365.
    
    2. Se un criterio di conservazione include una posizione specifica, ad esempio la cassetta postale o l'account di OneDrive di un particolare utente, il criterio di conservazione ha la precedenza su un altro criterio di conservazione applicato alle cassette postali o agli account di OneDrive di tutti gli utenti, ma che non include specificamente la cassetta postale di quell'utente.
    
4. **Prevale il periodo di eliminazione più breve.** Analogamente, se un contenuto è soggetto a più criteri di conservazione che eliminano il contenuto senza un periodo di conservazione, verrà eliminato alla fine del periodo di conservazione più breve. 
    
I principi di conservazione funzionano come un flusso di risoluzione di conflitti dall'alto verso il basso: se le regole applicate da tutti i criteri o le etichette di conservazione sono le stesse in un determinato livello, il flusso si sposta verso il basso al livello successivo per determinare la priorità di applicazione di ogni regola.
  
Infine, un criterio di conservazione o un'etichetta di conservazione non può eliminare definitivamente qualsiasi contenuto che si trovi in stato di blocco per eDiscovery. Quando il blocco viene rilasciato, il contenuto torna idoneo per il processo di pulizia descritto in precedenza.

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>Usare la protezione dell'archiviazione per la conformità ai requisiti normativi

Per alcune organizzazioni può essere necessario rispettare i regolamenti definiti da enti normativi come la Securities and Exchange Commission (SEC) Rule 17a-4, in base alla quale, una volta attivato, un criterio di conservazione non può essere disattivato o reso meno restrittivo. 

La protezione dell'archiviazione garantisce che l'organizzazione possa rispettare tali requisiti normativi perché blocca i criteri di conservazione in modo che nessuno, incluso l'amministratore, possa disattivarli o renderli meno restrittivi.
  
Quando un criterio di conservazione è bloccato:

- Nessuno può disattivarlo
- È possibile aggiungere percorsi, ma non rimuoverli 
- Il contenuto soggetto al criterio non può essere modificato o eliminato durante il periodo di conservazione
- È possibile estendere un periodo di conservazione, ma non ridurlo

In sintesi, un criterio bloccato può essere aumentato o esteso, ma non ridotto, disabilitato o disattivato.
  
> [!IMPORTANT]
> Prima di bloccare un criterio di conservazione, è essenziale comprendere l'impatto dell'operazione e verificare se sia necessario all'organizzazione per soddisfare i requisiti di conformità.

## <a name="releasing-a-retention-policy"></a>Rilascio dei criteri di conservazione

Posto che un criterio di conservazione non sia bloccato con Protezione dell'archiviazione, è possibile disattivarlo o eliminarlo in qualsiasi momento. 

Eseguendo questa operazione, il contenuto di SharePoint o OneDrive conservato nella Raccolta di archiviazione non viene eliminato immediatamente e definitivamente. Per evitare perdite accidentali di dati, è previsto un periodo di tolleranza di 30 giorni, durante il quale la scadenza del contenuto per tale criterio non viene applicata alla raccolta di archiviazione, in modo da poter ripristinare qualsiasi contenuto in caso di necessità. Inoltre, non è possibile eliminare manualmente questo contenuto durante il periodo di tolleranza.

È possibile attivare di nuovo i criteri di conservazione durante il periodo di tolleranza; in tal caso, nessun contenuto verrà eliminato per tale criterio.

Il periodo di tolleranza di 30 giorni in SharePoint e in OneDrive corrisponde al periodo di attesa di 30 giorni in Exchange. Per altre informazioni, vedere [Gestione della permanenza nelle cassette postali ](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

## <a name="use-a-retention-policy-instead-of-older-features"></a>Usare i criteri di conservazione anziché funzionalità precedenti

Un singolo criterio di conservazione può essere facilmente applicato a un'intera organizzazione e alle posizioni in Microsoft 365, inclusi Exchange Online, SharePoint Online, OneDrive e i gruppi di Microsoft 365. Se è necessario conservare o eliminare contenuti in una qualsiasi posizione in Microsoft 365, è consigliabile usare un criterio di conservazione e, facoltativamente, integrarlo con [etichette di conservazione](labels.md).
  
Se in precedenza sono state usate altre configurazioni per conservare o eliminare il contenuto in Microsoft 365, queste continueranno a funzionare insieme ai criteri di conservazione e alle etichette di conservazione. Tuttavia, si consiglia per il futuro di usare i criteri di conservazione e le etichette di conservazione. Forniscono infatti un unico meccanismo per gestire in modo centralizzato sia la conservazione che l'eliminazione del contenuto in Microsoft 365.

Ecco le funzionalità precedenti che possono essere state usate:
  
**Funzionalità precedenti di Exchange Online:**

- [Gestione di casi di eDiscovery nel Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (blocco di eDiscovery) 
    
- [Blocco sul posto e blocco per controversia legale](https://go.microsoft.com/fwlink/?linkid=846124) (blocco di eDiscovery) 

- [Come identificare il tipo di blocco applicato a una cassetta postale di Exchange Online](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Tag di conservazione e criteri di conservazione](https://go.microsoft.com/fwlink/?linkid=846125), noti anche come [gestione record di messaggistica (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (solo eliminazione)
    
**Funzionalità precedenti di SharePoint e OneDrive:**

- [Gestione di casi di eDiscovery nel Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery) (blocco di eDiscovery) 
    
- [Aggiunta di un contenuto a un caso e archiviare origini blocco nel centro eDiscovery](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (blocco di eDiscovery) 
    
- [Criteri di eliminazione dei documenti](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (solo eliminazione)
    
- [Configurare la gestione dei record sul posto](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (solo conservazione) 
    
- [Usare criteri per la chiusura e l'eliminazione di siti](https://support.microsoft.com/it-IT/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (solo eliminazione) 
    
- [Criteri di gestione delle informazioni ](intro-to-info-mgmt-policies.md) (solo eliminazione)
     
Se in passato sono stati usati blocchi di eDiscovery per la governance delle informazioni, per garantire una conformità proattiva ora si devono usare invece i criteri di conservazione. Usare eDiscovery solo per i blocchi.
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>Criteri di conservazione e criteri tipo di contenuto di SharePoint o criteri di gestione delle informazioni

Se si sono configurati i siti di SharePoint per criteri tipo di contenuto o criteri di gestione delle informazioni mirati alla conservazione del contenuto di un elenco o una raccolta, tali criteri vengono ignorati quando sono applicati i criteri di conservazione. 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a>I criteri di conservazione precedenti vengono convertiti nei nuovi criteri di conservazione

Se si usavano i precedenti criteri di conservazione per conservare i dati in cassette postali, siti di SharePoint o OneDrive oppure cartelle pubbliche, questi criteri ora vengono convertiti automaticamente nei nuovi criteri di conservazione che usano solo l'azione di conservazione. I criteri non eliminano il contenuto. Per ottenere lo stesso risultato dei precedenti criteri di conservazione configurati, non sono necessarie modifiche.

Tutti i criteri già configurati sono disponibili nella pagina **Criteri** nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) o nella pagina **Conservazione** in **Governance delle informazioni** del [Centro sicurezza&amp; e conformità](https://protection.office.com/). È possibile cambiare i criteri di conservazione per modificare il periodo di conservazione, ma non è possibile apportare altre modifiche, ad esempio l'aggiunta o la rimozione delle posizioni. 


## <a name="related-information"></a>Informazioni correlate

- [Informazioni sulle etichette di conservazione](labels.md)
- [Limiti di SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limiti e specifiche per Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Rispettare la SEC Rule 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>Passaggi successivi

Se si è pronti per creare criteri di conservazione, vedere [Creare e configurare criteri di conservazione](create-retention-policies.md).

