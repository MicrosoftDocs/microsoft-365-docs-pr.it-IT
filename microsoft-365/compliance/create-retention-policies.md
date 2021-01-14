---
title: Creare e configurare criteri di conservazione per conservare o eliminare automaticamente il contenuto
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
description: Usare i criteri di conservazione per tenere sotto controllo molto efficacemente i contenuti che gli utenti generano con posta elettronica, documenti e conversazioni. Mantenere il contenuto desiderato e liberarsi di quello che non serve.
ms.openlocfilehash: d79a505731eea8b48e19507ff6ae9558cb9a78b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840869"
---
# <a name="create-and-configure-retention-policies"></a>Creare e configurare criteri di conservazione

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Usare un criterio di conservazione per decidere proattivamente se conservare il contenuto, eliminarlo o entrambe le cose, ovvero conservarlo ed eliminarlo successivamente.

I criteri di conservazione permettono di farlo in modo molto efficiente, assegnando le stesse impostazioni di conservazione per il contenuto in base alla posizione, a livello di sito o di cassetta postale. Se non si sa se occorre usare un criterio di conservazione o un'etichetta di conservazione, vedere [Criteri di conservazione ed etichette di conservazione](retention.md#retention-policies-and-retention-labels).

Per saperne di più sul funzionamento della conservazione e sui criteri di conservazione, vedere [Informazioni sui criteri e le etichette di conservazione](retention.md).

## <a name="before-you-begin"></a>Prima di iniziare

L'amministratore globale dell'organizzazione dispone delle autorizzazioni complete per creare e modificare le etichette conservazione. Se non si esegue l'accesso come amministratore globale, vedere le [autorizzazioni necessarie per creare e gestire criteri di conservazione ed etichette di conservazione](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="create-and-configure-a-retention-policy"></a>Creare e configurare un criterio di conservazione

Anche se un criterio di conservazione può supportare più posizioni, non è possibile creare un singolo criterio di conservazione che includa tutte le posizioni supportate:

- Posta elettronica di Exchange
- Sito di SharePoint
- Account di OneDrive
- Gruppi di Microsoft 365
- Skype for Business
- Cartelle pubbliche di Exchange
- Messaggi del canale di Teams
- Chat di Teams
- Messaggi della community di Yammer
- Messaggi privati di Yammer

Se si selezionano le posizioni di Teams o Yammer quando si crea un criterio di conservazione, le altre posizioni vengono automaticamente escluse. Di conseguenza, le istruzioni da seguire variano in base alla necessità o meno di includere le posizioni di Teams o Yammer:

- [Istruzioni per un criterio di conservazione per posizioni di Teams](#retention-policy-for-teams-locations)
- [Istruzioni per un criterio di conservazione per posizioni di Yammer](#retention-policy-for-yammer-locations)
- [Istruzioni per un criterio di conservazione per posizioni diverse da Teams e Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)

Se sono presenti più criteri di conservazione e quando si usano anche etichette di conservazione, vedere [Precedenza nei principi di conservazione](retention.md#the-principles-of-retention-or-what-takes-precedence) per comprendere cosa accade quando più impostazioni di conservazione si applicano allo stesso contenuto.

### <a name="retention-policy-for-teams-locations"></a>Criterio di conservazione per posizioni di Teams

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) selezionare **Criteri** > **Conservazione**.

2. Selezionare **Nuovo criterio di conservazione** per avviare la procedura guidata Crea etichetta di conservazione, e assegnare un nome al nuovo criterio di conservazione.

3. Nella pagina **Scegli posizioni a cui applicare il criterio**, selezionare una o entrambe le posizioni di Teams: **Messaggi del canale di Teams** e **Chat di Teams**.

   Per **Messaggi del canale di Teams** sono inclusi i messaggi provenienti da canali standard ma non dai [canali privati](https://docs.microsoft.com/microsoftteams/private-channels). I canali privati non sono al momento supportati dai criteri di conservazione.

   Per impostazione predefinita, [tutti i team e gli utenti sono selezionati](#a-policy-that-applies-to-entire-locations), ma si può raffinare la ricerca selezionando le opzioni [**Scegli** ed **Escludi**](#a-policy-with-specific-inclusions-or-exclusions).

4. Nella pagina **Decidere se si vuole conservare il contenuto, eliminarlo e entrambi** della procedura guidata specificare le opzioni di configurazione per la conservazione e l'eliminazione del contenuto.

   È possibile creare un criterio che si limita a conservare il contenuto senza eliminarlo, lo conserva e quindi lo elimina dopo un periodo di tempo specificato oppure semplicemente elimina il contenuto dopo un periodo di tempo specificato. Per altre informazioni, vedere [Impostazioni per la conservazione e l'eliminazione del contenuto](#settings-for-retaining-and-deleting-content) in questa pagina.

5. Completare la procedura guidata per salvare le impostazioni.

Per altre informazioni sui criteri di conservazione per Teams, vedere [Criteri di conservazione in Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies) nella documentazione di Teams.

#### <a name="additional-retention-policy-needed-to-support-teams"></a>Un altro criterio di conservazione necessario per supportare Teams

Teams non offre solo chat e messaggi del canale. Se sono presenti team creati da un gruppo di Microsoft 365 (in precedenza gruppo di Office 365), è consigliabile configurare anche un criterio di conservazione che includa tale gruppo di Microsoft 365 usando il percorso **Gruppi di Microsoft 365**. Questo criterio di conservazione si applica al contenuto della cassetta postale, dei siti e dei file del gruppo.

Se si hanno siti del team non connessi a un gruppo di Microsoft 365, è necessario un criterio di conservazione che includa i percorsi dei **siti di SharePoint** o degli **account di OneDrive** per conservare ed eliminare file in Teams:

- i file condivisi in chat vengono archiviati nell'account di OneDrive dell'utente che ha condiviso il file.

- I file caricati nei canali vengono archiviati nel sito di SharePoint del team.

> [!TIP]
> È possibile applicare un criterio di conservazione ai file di un solo team che non è connesso a un gruppo di Microsoft 365 selezionando il sito di SharePoint per il team e gli account di OneDrive per gli utenti del team.

È possibile che i criteri di conservazione applicati ai gruppi di Microsoft 365, ai siti di SharePoint o agli account OneDrive eliminino un file a cui viene fatto riferimento nel messaggio di una chat o di un canale di Teams prima che tali messaggi vengano eliminati. In questo scenario, il file viene comunque visualizzato nel messaggio di Teams, ma se gli utenti selezionano il file visualizzeranno l'errore "File non trovato". Questo comportamento non è specifico dei criteri di conservazione e può verificarsi anche se un utente elimina manualmente un file da SharePoint o da OneDrive.

### <a name="retention-policy-for-yammer-locations"></a>Criterio di conservazione per posizioni di Yammer

> [!NOTE]
> I criteri di conservazione per Yammer vengono distribuiti in anteprima. Se i nuovi percorsi di Yammer non sono ancora visualizzati, riprovare tra qualche settimana.
>
> Per usare questa funzionalità, la rete Yammer deve essere in [Modalità nativa](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode), non nella Modalità ibrida.

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) selezionare **Criteri** > **Conservazione**.

2. Selezionare **Nuovo criterio di conservazione** per creare un nuovo criterio.

3. Nella pagina **Decidere se si vuole conservare il contenuto, eliminarlo e entrambi** della procedura guidata specificare le opzioni di configurazione per la conservazione e l'eliminazione del contenuto. 
    
    È possibile creare un criterio che si limita a conservare il contenuto senza eliminarlo, lo conserva e quindi lo elimina dopo un periodo di tempo specificato oppure semplicemente elimina il contenuto dopo un periodo di tempo specificato. Per altre informazioni, vedere [Impostazioni per la conservazione e l'eliminazione del contenuto](#settings-for-retaining-and-deleting-content) in questa pagina.
    
    Non selezionare **Usa le impostazioni di conservazione avanzate**, perché questa opzione non è supportata per le posizioni di Yammer. 

4. Nella pagina **Scegli posizioni** selezionare **Consenti la scelta di posizioni specifiche**. Quindi, attivare una o entrambe le posizioni di Yammer: **Messaggi della community di Yammer** e **Messaggi privati di Yammer**.
    
    Per impostazione predefinita, vengono selezionate tutte le community e tutti gli utenti, ma si può modificare la selezione specificando community e utenti da includere o escludere.
    
    Per i messaggi privati di Yammer: 
    - Se si lascia il valore predefinito, **Tutti**, i guest di Azure B2B non sono inclusi. 
    - Se si seleziona **Scegli utente**, si può applicare un criterio di conservazione agli utenti esterni, se il loro account è noto.

5. Completare la procedura guidata per salvare le impostazioni.

Per altre informazioni sul funzionamento dei criteri di Yammer, vedere [Informazioni sulla conservazione dei dati di Yammer](retention-policies-yammer.md).

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Altri criteri di conservazione necessari per supportare Yammer

Yammer non è solo messaggi della community e messaggi privati. Per conservare e cancellare i messaggi di posta elettronica della rete Yammer, configurare un altro criterio di conservazione che includa tutti i gruppi di Microsoft 365 usati per Yammer usando la posizione **Gruppi di Microsoft 365**. 

Per conservare ed eliminare file che sono memorizzati in Yammer, è necessario un criteri di conservazione che includa le posizioni dei **siti di SharePoint** o degli **account di OneDrive**:

- I file condivisi in messaggi privati vengono archiviati nell'account di OneDrive dell'utente che ha condiviso il file. 

- I file caricati nelle community vengono archiviati nel sito di SharePoint della community di Yammer.

È possibile che un criterio di conservazione applicato ai siti di SharePoint o agli account di OneDrive possa eliminare un file a cui viene fatto riferimento in un messaggio di Yammer prima che tale messaggio sia eliminato. In questo scenario, il file viene comunque visualizzato nel messaggio di Yammer, ma se gli utenti selezionano il file visualizzeranno l'errore "File non trovato". Questo comportamento non è specifico dei criteri di conservazione, e può verificarsi anche se un utente elimina manualmente un file da SharePoint o da OneDrive.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Criterio di conservazione per posizioni diverse da Teams e Yammer

Usare le istruzioni seguenti per i criteri di conservazione che si applicano a uno qualsiasi di questi servizi:

- Exchange: posta elettronica e cartelle pubbliche
- SharePoint: siti
- OneDrive: account
- Gruppi di Microsoft 365
- Skype for Business

1. Nel [Centro conformità Microsoft 365](https://compliance.microsoft.com/) selezionare **Criteri** > **Conservazione**.

2. Selezionare **Nuovo criterio di conservazione** per avviare la procedura guidata Crea etichetta di conservazione, e assegnare un nome al nuovo criterio di conservazione.

3. Nella pagina **Scegli posizioni**, attivare o disattivare le posizioni desiderate, tranne quelle di Teams. Per ogni posizione, è possibile lasciare la configurazione predefinita [applica il criterio all'intera posizione](#a-policy-that-applies-to-entire-locations), o [specifica cosa includere ed escludere](#a-policy-with-specific-inclusions-or-exclusions).

    Informazioni specifiche per le posizioni:
    - [Posta elettronica di Exchange e cartelle pubbliche di Exchange](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [Siti di SharePoint e account di OneDrive](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Gruppi di Microsoft 365](#configuration-information-for-microsoft-365-groups)
    - [Skype for Business](#configuration-information-for-skype-for-business)

4. Nella pagina **Decidere se si vuole conservare il contenuto, eliminarlo e entrambi** della procedura guidata specificare le opzioni di configurazione per la conservazione e l'eliminazione del contenuto.

    È possibile creare un criterio che si limita a conservare il contenuto senza eliminarlo, lo conserva e quindi lo elimina dopo un periodo di tempo specificato oppure semplicemente elimina il contenuto dopo un periodo di tempo specificato. Per altre informazioni, vedere [Impostazioni per la conservazione e l'eliminazione del contenuto](#settings-for-retaining-and-deleting-content) in questa pagina.

5. Completare la procedura guidata per salvare le impostazioni.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Informazioni di configurazione per la posta elettronica di Exchange e le cartelle pubbliche di Exchange

La posizione **Posta elettronica di Exchange** supporta la conservazione per i messaggi di posta elettronica, il calendario e altri elementi delle cassette postali degli utenti applicando le impostazioni di conservazione a livello di cassetta postale.

Per informazioni dettagliate sugli elementi inclusi ed esclusi quando si configurano le impostazioni di conservazione per Exchange, vedere [Cosa è incluso per la conservazione e l'eliminazione](retention-policies-exchange.md#whats-included-for-retention-and-deletion)

Si noti che anche se un gruppo di Microsoft 365 ha una cassetta postale di Exchange, un criterio di conservazione che include l'intero percorso **Posta elettronica di Exchange** non includerà il contenuto nelle cassette postali del gruppo di Microsoft 365. Per conservare il contenuto delle cassette postali, selezionare la posizione **Gruppi di Microsoft 365**.

La posizione **Cartelle pubbliche di Exchange** applica le impostazioni di conservazione a tutte le cartelle pubbliche e non può essere applicata a livello di cartella o cassetta postale.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Informazioni di configurazione per siti di SharePoint e account di OneDrive

Selezionando la posizione **Siti di SharePoint**, il criterio di conservazione può conservare ed eliminare documenti all'interno di siti di comunicazione di SharePoint, siti del team non collegati a gruppi di Microsoft 365 e siti classici. I siti del team collegati a gruppi di Microsoft 365 non sono supportati con questa opzione. In alternativa, usare la posizione **Gruppi di Microsoft 365** che si applica al contenuto dei file, del sito e della cassetta postale del gruppo.

Anche se il criterio di conservazione è applicato a livello di sito, le impostazioni di conservazione sono applicate solo ai documenti. Per informazioni dettagliate cosa è incluso ed escluso quando si configurano le impostazioni di conservazione per SharePoint and OneDrive, vedere [Cosa è incluso per la conservazione e l'eliminazione](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion). 

Quando si specificano le posizioni dei siti di SharePoint o gli account di OneDrive, non è necessario disporre delle autorizzazioni per accedere ai siti e non viene eseguita alcuna convalida quando si specifica l'URL nella pagina **Modificare le posizioni**. Tuttavia, viene verificata l’esistenza dei siti di SharePoint specificati al termine della procedura guidata. Se la verifica dell'URL immesso fallisce, verrà visualizzato un messaggio di errore e la procedura guidata non creerà il criterio di conservazione fino al successo della verifica. Se si visualizza il messaggio di errore, tornare alla procedura guidata per cambiare l'URL o rimuovere il sito dal criterio di conservazione.

Per specificare singoli account di OneDrive da includere o escludere, l'URL ha il formato seguente: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

Ad esempio, per un utente nel tenant Contoso con il nome utente "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

Per verificare la sintassi del tenant e identificare gli URL per gli utenti, vedere [Ottenere un elenco di tutti gli URL di OneDrive dell'utente nell'organizzazione](https://docs.microsoft.com/onedrive/list-onedrive-urls).

### <a name="configuration-information-for-microsoft-365-groups"></a>Informazioni di configurazione per i gruppi di Microsoft 365

Per conservare o eliminare il contenuto di un gruppo di Microsoft 365 (in precedenza gruppo di Office365), è necessario usare la posizione **Gruppi di Microsoft 365**. Anche se un gruppo di Microsoft 365 ha una cassetta postale di Exchange, un criterio di conservazione che include l'intero percorso **Posta elettronica di Exchange** non includerà il contenuto nelle cassette postali del gruppo di Microsoft 365. Inoltre, anche se il percorso **Posta elettronica di Exchange** consente inizialmente di selezionare una cassetta postale del gruppo da includere o escludere, provando a salvare il criterio di conservazione si riceverà un messaggio di errore che segnala che "RemoteGroupMailbox" non è una selezione valida per il percorso di Exchange.

I criteri di conservazione applicati a un gruppo di Microsoft 365 includono la cassetta postale del gruppo e il sito del team di SharePoint. I file archiviati nel sito del team di SharePoint sono inclusi in questa posizione, i messaggi delle chat o dei canali di Teams hanno invece le proprie posizioni per i criteri di conservazione.

### <a name="configuration-information-for-skype-for-business"></a>Informazioni di configurazione per Skype for Business

A differenza della posta elettronica di Exchange, non è possibile attivare lo stato della posizione Skype per includere automaticamente tutti gli utenti ma quando si attiva la posizione, sarà necessario scegliere manualmente gli utenti di cui si desidera conservare le conversazioni:

![Scegliere il percorso Skype per i criteri di conservazione](../media/skype-location-retention-policies.png)

Quando si seleziona **Scegli utente**, si possono includere rapidamente tutti gli utenti selezionando la casella **Seleziona tutto**. È necessario considerare, però, che ciascun utente viene conteggiato come specifica inclusione nei criteri. Quindi, se si includono 1.000 utenti selezionando la casella **Seleziona tutto**, ciò corrisponde all'inclusione manuale di 1.000 utenti, ossia il numero massimo di utenti supportato da Skype for Business.  

Si noti che **Cronologia conversazioni**, una cartella di Outlook, è una caratteristica che non ha nulla a che fare con l'archiviazione di Skype. **Cronologia conversazioni** può essere disattivata dall'utente finale, mentre l'archiviazione per Skype avviene memorizzando una copia delle conversazioni di Skype in una cartella nascosta che è inaccessibile all'utente ma disponibile per eDiscovery.

## <a name="settings-for-retaining-and-deleting-content"></a>Impostazioni per la conservazione e l'eliminazione del contenuto

Scegliendo le impostazioni per la conservazione e l'eliminazione del contenuto, il criterio di conservazione avrà una delle configurazioni seguenti per un periodo di tempo specificato:

- Conserva solo

    Per questa configurazione, scegliere **Conserva elementi per un periodo specifico** e **Al termine del periodo di conservazione: non fare nulla**. Oppure selezionare **Conserva gli elementi per sempre**.

- Conserva ed elimina

    Per questa configurazione, scegliere **Scegli elementi per un periodo specifico** e **Al termine del periodo di conservazione: elimina automaticamente gli elementi**.

- Elimina solo

    Per questa configurazione, scegliere **Elimina gli elementi solo quando raggiungono una certa età**.

### <a name="retaining-content-for-a-specific-period-of-time"></a>Conservazione del contenuto per un periodo di tempo specifico

Quando si configura un criterio di conservazione, si sceglie di conservare gli elementi per un numero specifico di giorni, mesi o anni. In alternativa, conservare gli elementi per sempre.

Quando si configura un criterio di conservazione, si può scegliere di conservare il contenuto per un periodo di tempo indefinito o per un numero specifico di giorni, mesi o anni. Il calcolo relativo al periodo di conservazione del contenuto è basato sulla data di modifica del contenuto e non sulla data di applicazione dei criteri di conservazione.

Per l'inizio del periodo di conservazione, è anche possibile scegliere quando il contenuto è stato creato o quando il contenuto è stato modificato l'ultima volta. Quest’ultima opzione è supportata solo per i file e per i gruppi SharePoint, OneDrive e Microsoft 365.

Esempi:

- SharePoint: se si vuole conservare gli elementi di una raccolta siti per sette anni dopo l'ultima modifica del contenuto e un documento presente nella raccolta siti non è stato modificato per sei anni, il documento verrà conservato solo per un altro anno se non viene modificato. Se il documento viene nuovamente modificato, la durata viene ricalcolata in base alla nuova data di modifica e il documento verrà conservato per altri sette anni.

- Exchange: se si vuole conservare gli elementi di una cassetta postale per sette anni e un messaggio è stato inviato sei anni fa, il messaggio verrà conservato solo per un altro anno. Per gli elementi di Exchange, l'età dipende dalla data di ricezione per la posta in arrivo o dalla data di invio per la posta in uscita. La conservazione degli elementi in base all'ultima modifica si applica solo ai contenuti dei siti di OneDrive e SharePoint.

Al termine del periodo di conservazione, si sceglie se si vuole eliminare definitivamente il contenuto:

![Pagina delle impostazioni di conservazione](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>Eliminazione di contenuto antecedente a una data specifica

I criteri di conservazione possono conservare e quindi eliminare gli elementi successivamente, o eliminare gli elementi obsoleti senza conservarli.

In entrambi i casi, se i criteri di conservazione eliminano gli elementi, è importante tenere presente che il periodo di tempo specificato per i criteri di conservazione viene calcolato dal momento in cui l'elemento è stato creato o modificato, non dal momento dell'assegnazione dei criteri.

Perciò, prima di assegnare un criterio di conservazione per la prima volta, e specialmente quando il criterio elimina degli elementi, bisogna per prima cosa considerare l'età del contenuto e il modo in cui il criterio potrebbe condizionarlo.  Potrebbe inoltre essere necessario comunicare il nuovo criterio agli utenti prima di assegnarlo, per dargli il tempo di valutare il possibile impatto.

### <a name="a-policy-that-applies-to-entire-locations"></a>Criteri validi per intere posizioni

Se si scelgono le posizioni, a eccezione di Skype for Business, l'impostazione predefinita è **Tutte** quando lo stato della posizione è **Attivato**.

Quando un criterio di conservazione si applica a qualsiasi combinazione di posizioni complete, non sono previsti limiti per il numero di destinatari, siti, account, gruppi, ecc. che possono essere inclusi nel criterio.

Ad esempio, se un criterio include tutta la posta elettronica di Exchange e tutti i siti di SharePoint, verranno inclusi tutti i siti e i destinatari, indipendentemente dal numero. Per Exchange, le nuove cassette postali create dopo l'applicazione del criterio ereditano automaticamente il criterio.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Criteri con specifiche inclusioni o esclusioni

Solo se si utilizza la configurazione facoltativa per definire l'ambito delle impostazioni di conservazione a utenti specifici, gruppi di Microsoft 365 specifici o siti specifici, esistono alcuni limiti dei criteri di cui tenere conto: 

- Valori massimi per criteri di conservazione:
  - 1.000 cassette postali (degli utenti o di gruppo)
  - 1.000 gruppi di Microsoft 365
  - 1.000 utenti per le chat private di Teams
  - 100 siti (OneDrive o SharePoint)

Queste limitazioni sono basate sui criteri, quindi sarà necessario usare specifiche inclusioni o esclusioni che comportano di usare questi numeri, è possibile creare altri criteri di conservazione con le stesse impostazioni di conservazione. Vedere la sezione successiva per alcuni[Scenari e soluzioni di esempio](#examples-of-using-inclusions-and-exclusions) che usano più criteri di conservazione. L'uso di criteri di conservazione multipla multipli determina costi amministrativi superiori, perciò verificare sempre se le inclusioni e le esclusioni siano davvero necessarie. Tenere presente che la configurazione predefinita che si applica all'intero percorso non ha alcuna limitazione, e che questa configurazione potrebbe essere una soluzione migliore rispetto alla creazione e alla gestione di più criteri.

> [!TIP]
> Sì è necessario creare e gestire più criteri di conservazione per questo scenario, si consiglia di usare di usare [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) per una configurazione più efficiente.

Inoltre il un numero massimo di criteri supportati per un tenant è di 10.000. Per Exchange Online il numero massimo di criteri supportati è di 1.800. Il numero massimo include i criteri di conservazione, i criteri per le etichette di conservazione e i criteri di conservazione applicati automaticamente.

Per usare la configurazione facoltativa per definire l'ambito delle impostazioni di conservazione, assicurarsi che lo **Stato** di tale posizione sia **Attivato**, quindi usare i collegamenti per includere o escludere determinati utenti, gruppi di Microsoft 365 o siti.

> [!WARNING]
> Se si configurano inclusioni e poi si rimuove l'ultima di esse, verrà ripristinata la configurazione **Tutti** per la posizione.  Verificare che la configurazione sia quella desiderata prima di salvare il criterio.
>
> Ad esempio, se si specifica un sito di SharePoint da includere nei criteri di conservazione configurato per l'eliminazione dei dati e poi si rimuove quell’unico sito, per impostazione predefinita i criteri di conservazione che eliminano definitivamente i dati verranno applicati a tutti i siti di SharePoint. Lo stesso vale per inclusioni come destinatari di Exchange, account OneDrive, utenti della chat di Teams e così via.
>
> In questo scenario, disabilitare la posizione se non si vuole che l’impostazione **Tutti** per tale posizione sia soggetta ai criteri di conservazione. In alternativa, specificare esclusioni da esonerare dall’applicazione del criterio.

#### <a name="examples-of-using-inclusions-and-exclusions"></a>Esempi di uso di esclusioni ed inclusioni

Gli esempi seguenti descrivono alcune soluzioni di progettazione per i casi in cui non è possibile specificare il percorso di un criterio di conservazione, e devono tenere in considerazione le limitazioni descritte nella sezione precedente.

Esempio di Exchange:

- **Requisito**: in una organizzazione che ha più di 40.000 cassette postali degli utenti, la posta elettronica deve essere conservata per sette anni per gran parte degli utenti, ma un sottoinsieme di utenti identificati (425) deve conservare la posta elettronica solo per 5 anni. 

- **Soluzione**: creare un criterio di conservazione per la posta elettronica di Exchange con un periodo di conservazione di sette anni, ed escludere il sottoinsieme di utenti. Creare poi un secondo criterio di conservazione per la posta elettronica di Exchange, con un periodo di conservazione di cinque anni, e includere il sottoinsieme di utenti. 
    
    In entrambi casi, il numero incluso ed escluso è inferiore a un numero massimo di cassette postali specificate per un singolo criterio, e il sottoinsieme di utenti deve essere escluso esplicitamente dalla primo criterio perché ha [periodo di conservazione più lungo](retention.md#the-principles-of-retention-or-what-takes-precedence) del secondo criterio. Se il sottoinsieme di utenti richiede un periodo di conservazione più lungo, non è necessario escluderli dal primo criterio.
     
    Con questa soluzione, se un nuovo dipendente entra nell'organizzazione, la sua cassetta postale viene automaticamente inclusa nel primo criterio per sette anni, e non ci sono conseguenze per il numero massimo supportato. Tuttavia, i nuovi utenti che richiedono il periodo di conservazione da 5 anni sono aggiunti ai numeri da includere ed escludere, e questo limite viene raggiunto a 1.000.

Esempio di SharePoint:

- **Requisito**: l'organizzazione ha diverse migliaia di siti di SharePoint, ma soltanto 2000 siti richiedono un periodo di conservazione da 10 anni, e 8000 siti richiedono un periodo di conservazione da quattro anni.

- **Soluzione**: creare 20 criteri di conservazione per SharePoint con un periodo di conservazione da 10 anni che includa 100 siti specifici, e creare 80 criteri di conservazione per SharePoint con un periodo di conservazione da quattro anni che includa 100 siti specifici.
    
    Poiché non è necessario conservare tutti i siti di SharePoint, bisogna creare criteri di conservazione che specificano i siti. Dato che i criteri di conservazione non supportano più di 100 siti specifici, è necessario creare criteri specifici per i due periodi di conservazione. Questo criterio di conservazione hanno il numero massimo di siti inclusi, perciò un nuovo criterio di conservazione deve essere creato per il prossimo nuovo sito che richiede la conservazione, indipendentemente dal periodo di conservazione.

## <a name="updating-retention-policies"></a>Aggiornamento dei criteri di conservazione

Alcune impostazioni non possono essere modificate dopo aver creato e salvato i criteri di conservazione, tra cui:
- Il nome del criterio di conservazione e le impostazioni di conservazione, ad eccezione del periodo di conservazione e l’inizio di tale periodo.

Se si modifica un criterio di conservazione ed esistono già elementi soggetti alle impostazioni originali del criterio, le impostazioni aggiornate verranno applicate automaticamente a tali elementi oltre che ai nuovi elementi identificati.

In genere l'aggiornamento è piuttosto rapido, ma può richiedere alcuni giorni. Una volta completata la replica del criterio nelle diverse posizioni di Microsoft 365, il suo stato nel Centro conformità Microsoft 365 passerà da **Attivato (in sospeso)** ad **Attivato (operazione riuscita)**.

## <a name="locking-the-policy-to-prevent-changes"></a>Blocco dei criteri per evitare le modifiche

Se occorre fare in modo che nessuno possa disattivare o eliminarle i criteri o renderli meno restrittivi, vedere [Usare la protezione dell'archiviazione per limitare le modifiche ai criteri di conservazione e ai criteri per le etichette di conservazione](retention-preservation-lock.md).
