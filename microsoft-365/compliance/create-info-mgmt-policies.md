---
title: Creare e applicare criteri di gestione delle informazioni
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come configurare un criterio di gestione delle informative per controllare la durata delle informazioni e tenere conto di chi utilizza le informazioni.
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817995"
---
# <a name="create-and-apply-information-management-policies"></a>Creare e applicare criteri di gestione delle informazioni

I criteri di gestione delle informazioni consentono all'organizzazione di controllare il periodo di conservazione del contenuto, di verificare le persone che hanno a che fare con il contenuto e di aggiungere codici a barre o etichette ai documenti. Un criterio può contribuire a garantire la conformità ai regolamenti legali e governativi o ai processi aziendali interni. In qualità di amministratore, è possibile configurare un criterio per controllare la modalità di gestione dei documenti e la durata della conservazione dei documenti.
  
È possibile creare un criterio di gestione delle informazioni può essere in tre posizioni diverse nella gerarchia dei siti, dalla più ampia alla più stretta:
  
- Creare un criterio da utilizzare su più tipi di contenuto all'interno di una raccolta siti.
    
- Creare un criterio per un tipo di contenuto del sito.
    
- Creare un criterio per un elenco o una raccolta.
    
Per ulteriori informazioni, vedere [Introduzione ai criteri di gestione delle informazioni](intro-to-info-mgmt-policies.md).
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Creare un criterio per più tipi di contenuto all'interno di una raccolta siti
<a name="__toc261001590"> </a>

Per garantire che un criterio di informazioni venga applicato a tutti i documenti di un determinato tipo all'interno di una raccolta siti, prendere in considerazione la possibilità di creare il criterio a livello di raccolta siti e successivamente applicarlo ai tipi di contenuto. Questi vengono definiti criteri di raccolta siti. 
  
1. Nella Home page della raccolta siti fare \> **Settings** ![ clic sul pulsante impostazioni di SharePoint 2016 sulla barra del titolo.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Impostazioni sito**.
    
    In un sito collegato a un gruppo di SharePoint fare clic su **Impostazioni**, quindi su **contenuto del sito**e quindi su **Impostazioni sito**. 
    
2. Nella pagina Impostazioni sito, in modelli di criteri tipo di contenuto **Amministrazione raccolta siti** \> **Content Type Policy Templates**. 
  
![Collegamento Modelli di criteri tipo di contenuto nella pagina Impostazioni sito](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Nella pagina criteri \> **creare**. 
    
4. Immettere un nome e una descrizione per il criterio, quindi scrivere una breve istruzione di criteri che spieghi agli utenti il criterio.
    
5. Vedere la sezione successiva sulla creazione di criteri per un tipo di contenuto del sito per informazioni su come configurare le funzionalità che si desidera associare al criterio. 
    
6. Scegliere **OK**.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Creare un criterio per un tipo di contenuto del sito
<a name="__create_a_policy"> </a>

L'aggiunta di un criterio di gestione delle informazioni a un tipo di contenuto consente di associare facilmente le caratteristiche dei criteri a più elenchi o raccolte. È possibile scegliere di aggiungere un criterio di gestione delle informazioni esistente a un tipo di contenuto o di creare un criterio univoco specifico per un singolo tipo di contenuto.
  
 È inoltre possibile aggiungere un criterio di gestione delle informazioni a un tipo di contenuto specifico per gli elenchi. Questo ha l'effetto di applicare il criterio solo agli elementi dell'elenco che utilizzano il tipo di contenuto. 
  
1. Nella Home page della raccolta siti fare \> **Settings** ![ clic sul pulsante impostazioni di SharePoint 2016 sulla barra del titolo.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Impostazioni sito**.
    
    In un sito collegato a un gruppo di SharePoint fare clic su **Impostazioni**, quindi su **contenuto del sito**e quindi su **Impostazioni sito**. 
    
2. Nella pagina Impostazioni sito, in tipi di contenuto del sito per le **raccolte web designer** \> **Site content types**.
  
![Collegamento Tipi di contenuto del sito nella pagina Impostazioni sito](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. Nella pagina Impostazioni tipo di contenuto del sito selezionare il tipo di contenuto a cui si desidera aggiungere un criterio.
    
4. Nella pagina tipo di contenuto del sito, **Settings** in impostazioni impostazioni \> **dei criteri di gestione delle informazioni**.
    
5. Nella pagina Modifica criterio immettere un nome e una descrizione per il criterio, quindi scrivere una breve descrizione che spieghi agli utenti il criterio.
    
6. Nelle sezioni successive selezionare le caratteristiche dei criteri individuali che si desidera aggiungere ai criteri di gestione delle informazioni. 
  
![Tipi di criteri del contenuto](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Per specificare un periodo di conservazione per i documenti e gli elementi soggetti a questo criterio, scegliere **Enable retention**, quindi specificare il periodo di conservazione e le azioni che si desidera eseguire quando gli elementi scadono.
    
    Per specificare un periodo di conservazione
    
||||||**1.**|* * Scegliere * * aggiungere una fase di conservazione per i record... * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Selezionare un'opzione periodo di conservazione per specificare quando i documenti o gli elementi sono impostati in modo che scadano. Eseguire una delle operazioni seguenti:  <br/>  Per impostare la data di scadenza in base a una proprietà date, in **evento** \> **questa fase si basa su una proprietà date sull'elemento**e quindi selezionare l'azione documento o elemento (ad esempio, creato o modificato) e l'incremento del tempo dopo questa azione, ad esempio il numero di giorni, mesi o anni, quando si desidera che l'elemento scada.  <br/>  Per utilizzare una formula di conservazione personalizzata per determinare la scadenza, scegliere **imposta da una formula di conservazione personalizzata installata nel server**.  <br/> > [!NOTE]> questa opzione è disponibile solo se è stata configurata una formula personalizzata dall'amministratore.           |
||||||3.  <br/> |L'opzione **avvia un flusso di lavoro** è disponibile solo se si definisce un criterio per un elenco, una raccolta o un tipo di contenuto a cui è già associato un flusso di lavoro. Verrà quindi data la possibilità di scegliere tra i flussi di lavoro.  <br/> |
||||||4.  <br/> |Nella sezione **ricorrenza** selezionare **Ripeti azione di questo passaggio...** e immettere la frequenza con cui si desidera che l'azione venga rieseguita.  <br/> > [!NOTE]> questa opzione è disponibile solo se l'azione selezionata può essere ripetuta. Ad esempio, non è possibile impostare la ricorrenza per l'azione **Elimina definitivamente**.           |
||||||5.  <br/> |Scegliere **OK**.  <br/> |
   
1. Per abilitare il controllo per i documenti e gli elementi che sono soggetti a questo criterio, scegliere **Enable auditing**, quindi specificare gli eventi che si desidera controllare.
    
    Per abilitare il controllo
    
||||||1. * * * *|Nella pagina Modifica criterio, * * **in** **controllo** **\>** **Abilita controllo** * *, quindi selezionare le caselle di controllo accanto agli eventi per cui si desidera mantenere una traccia di controllo. * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Per richiedere agli utenti di inserire i codici a barre nei documenti,** **scegliere** **Richiedi agli utenti di inserire un codice a barre prima del salvataggio o della stampa** **.** <br/> |
||||||**3.** <br/> |Fare **clic** su **OK** * * per applicare la funzionalità di controllo al criterio. ** <br/> |
|||||||La funzionalità dei criteri di controllo consente alle organizzazioni di creare e analizzare percorsi di controllo per i documenti e di elencare gli elementi, ad esempio elenchi di attività, elenchi di problemi, gruppi di discussione e calendari. Questa caratteristica dei criteri garantisce un registro di controllo in cui vengono registrati gli eventi, ad esempio il momento di visualizzazione, modifica o eliminazione del contenuto.  <br/> |
|||||||Quando il controllo è abilitato nell'ambito di un criterio di gestione delle informazioni, gli amministratori possono visualizzare i dati di controllo nei report sull'utilizzo dei criteri basati su Microsoft Excel e riassumendo l'utilizzo corrente. Gli amministratori possono utilizzare questi report per determinare come vengono utilizzate le informazioni all'interno dell'organizzazione. Tali rapporti possono inoltre consentire alle organizzazioni di verificare e documentare la conformità normativa o di indagare su potenziali problemi.  <br/> |
|||||||Nel registro di controllo vengono registrate le informazioni seguenti: nome dell'evento, data e ora dell'evento e nome di sistema dell'utente che ha eseguito l'azione.  <br/> |
   
1. Quando i codici a barre sono abilitati nell'ambito di un criterio, vengono aggiunti alle proprietà del documento e vengono visualizzati nell'area di intestazione del documento a cui è applicato il codice a barre. Come le etichette, è possibile rimuovere manualmente anche i codici a barre da un documento. È possibile specificare se gli utenti devono essere invitati a includere il codice a barre durante la stampa o il salvataggio di un elemento o se il codice a barre deve essere inserito manualmente utilizzando la scheda **Inserisci** in 2010 programmi di Office Release. 
    
    Per abilitare i codici a barre
    
||||||1. * * * *|**Nella pagina Modifica criterio, in **codici** a barre \> **abilitare i codici a barre**.**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Per richiedere agli utenti di inserire i codici a barre nei documenti, scegliere **Richiedi agli utenti di inserire un codice a barre prima del salvataggio o della stampa**.  <br/> |
||||||**3.** <br/> |Scegliere **OK** per applicare la caratteristica Barcode al criterio.  <br/> |
|||||||
 Il criterio Barcode genera codici a barre standard di codice 39. Ogni immagine del codice a barre contiene testo sotto il simbolo del codice a barre che rappresenta il valore del codice a barre In questo modo è possibile utilizzare i dati del codice a barre anche quando l'hardware di analisi non è disponibile. Gli utenti possono digitare manualmente il numero di codice a barre nella casella di ricerca per individuare l'elemento in un sito.  <br/> |
   
1. Per richiedere che i documenti soggetti a questo criterio dispongano di etichette, scegliere **Abilita etichette**e quindi specificare le impostazioni desiderate per le etichette.
    
    Per abilitare le etichette
    
||||||**1.**|* * Per richiedere agli utenti di aggiungere un'etichetta a un documento, scegliere **Richiedi agli utenti di inserire un'etichetta prima del salvataggio o della stampa**.  <br/> > [!NOTE]> se si desidera che le etichette siano facoltative, non selezionare questa casella di controllo.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Per bloccare un'etichetta in modo che non possa essere modificata dopo l'inserimento, scegliere **Impedisci modifiche alle etichette dopo che sono state aggiunte**.  <br/>  Questa impostazione consente di evitare che il testo dell'etichetta venga aggiornato dopo l'inserimento dell'etichetta in un elemento all'interno di un'applicazione client, ad esempio Word, Excel o PowerPoint. Se si desidera che l'etichetta venga aggiornata in caso di aggiornamento delle proprietà del documento o dell'elemento, non selezionare questa casella di controllo.  <br/> |
||||||3.  <br/> |Nella casella formato etichetta immettere il testo per l'etichetta che si desidera visualizzare. Le etichette possono contenere fino a 10 riferimenti di colonna, ognuno dei quali può avere una lunghezza massima di 255 caratteri. Per creare il formato per l'etichetta, eseguire le operazioni seguenti:  <br/> Digitare i nomi delle colonne che si desidera includere nell'etichetta nell'ordine in cui si desidera che vengano visualizzate. Racchiudere i nomi delle colonne racchiuse tra parentesi graffe ( {} ), come illustrato nell'esempio nella pagina Modifica criterio.  <br/> Digitare parole per identificare le colonne all'esterno delle parentesi quadre, come illustrato nell'esempio nella pagina Modifica criterio.  <br/> |
||||||4.  <br/> |Per aggiungere un'interruzione di riga, immettere **\n** in cui si desidera che l'interruzione di riga venga visualizzata.  <br/> |
||||||5.  <br/> |Selezionare la dimensione e lo stile del carattere desiderati e specificare se si desidera che l'etichetta sia posizionata a sinistra, al centro o a destra all'interno del documento.  <br/>  Selezionare un tipo di carattere e uno stile disponibili nei computer degli utenti. Dalla dimensione del tipo di carattere dipende la quantità di testo visualizzabile sull'etichetta.  <br/> |
||||||6.  <br/> |Immettere l'altezza e la larghezza dell'etichetta. L'altezza e la larghezza dell'etichetta possono essere comprese tra 0,5 cm e 50 cm. Il testo dell'etichetta viene sempre centrato verticalmente all'interno dell'immagine dell'etichetta.  <br/> |
||||||7.  <br/> |Scegliere **Refresh** per visualizzare un'anteprima del contenuto dell'etichetta.  <br/> |
   
1. Scegliere **OK**.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Creare un criterio per un elenco, una raccolta o cartella (criteri di conservazione basati sulla posizione)
<a name="__create_a_policy"> </a>

È possibile definire un criterio di conservazione che si applica solo a un elenco, una raccolta o una cartella specifica. Tuttavia, se si crea un criterio di conservazione in questo modo, non è possibile riutilizzare questo criterio in altri elenchi, raccolte, cartelle o siti e non è possibile applicare un criterio di raccolta siti a un criterio basato sulla posizione.
  
Se si desidera applicare un singolo criterio di conservazione a tutti i tipi di contenuto in un'unica posizione, è molto probabile che si desideri utilizzare la conservazione basata sulla posizione. Nella maggior parte degli altri casi, è necessario verificare che sia specificato un criterio di conservazione per tutti i tipi di contenuto.
  
 Ogni sottocartella eredita il criterio di conservazione dell'elemento padre, a meno che non si scelga di interrompere l'ereditarietà e definire un nuovo criterio di conservazione a livello di figlio. 
  
Se si desidera definire un criterio di gestione delle informazioni diverso da quello di conservazione per un elenco o una raccolta, è necessario definire un criterio di gestione delle informazioni per ogni singolo tipo di contenuto elenco associato a tale elenco o raccolta.
  
 Se in qualsiasi momento si decide di passare dal tipo di contenuto ai criteri basati sulla posizione per un elenco o una raccolta, solo il criterio di conservazione verrà utilizzato come criterio basato sulla posizione. Tutti gli altri criteri di gestione (controlli, codici a barre e codici a barre) verranno ereditati dai tipi di contenuto associati. 
  
 I criteri basati sulla posizione possono essere disattivati per una raccolta siti disattivando la funzionalità di conservazione della raccolta e della cartella. In questo modo gli amministratori della raccolta siti possono garantire che i criteri dei tipi di contenuto non vengano ignorati dai criteri basati sulla posizione di un amministratore di elenco. 
  
È necessaria almeno l'autorizzazione Gestione elenchi per modificare le impostazioni dei criteri di gestione delle informazioni per un elenco o una raccolta.
  
1. Passare all'elenco o alla raccolta per cui si desidera specificare un criterio di gestione delle informazioni. 
    
2. Sulla barra multifunzione, scegliere le impostazioni della raccolta o dell'elenco della scheda **raccolta** o **elenco** \> **Library Settings** . **List Settings**
    
    In SharePoint Online, fare clic su **Impostazioni** , quindi fare clic su impostazioni **elenco** o **Impostazioni raccolta**. 
    
3. In **autorizzazioni e gestione** \> **delle impostazioni dei criteri di gestione delle informazioni**.
  
![Collegamento ai criteri gestione informazioni nella pagina di impostazioni per una raccolta documenti](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Nella pagina impostazioni dei criteri di gestione delle informazioni verificare che l'origine di conservazione per l'elenco o la raccolta sia impostata su raccolta e cartelle. 
  
Se il **tipo di contenuto** viene visualizzato come origine, fare clic su **Cambia origine**e quindi su **raccolta e cartelle**. Si avverte che i criteri di conservazione dei tipi di contenuto verranno ignorati. Scegliere **OK**. 
    
5. Nella pagina Modifica criterio, in **pianificazione conservazione basata su raccolta**, immettere una breve descrizione per il criterio che si sta creando. 
    
6. Scegliere **Aggiungi una fase di conservazione...**
    
     Tenere presente che in Records è possibile scegliere di definire diversi criteri di conservazione per i record selezionando l'opzione definire diverse fasi di conservazione per i record. 
    
7. Nella finestra di dialogo Proprietà Stage selezionare un'opzione periodo di conservazione per specificare quando i documenti o gli elementi sono impostati in modo che scadano. Eseguire una delle operazioni seguenti:
    
  - Per impostare la data di scadenza in base a una proprietà date, in **evento** \> **questa fase si basa su una proprietà date sull'elemento**e quindi selezionare l'azione documento o elemento (ad esempio, creato o modificato) e l'incremento del tempo dopo questa azione, ad esempio il numero di giorni, mesi o anni, quando si desidera che l'elemento scada. 
    
  - Per utilizzare una formula di conservazione personalizzata per determinare la scadenza, scegliere **imposta da una formula di conservazione personalizzata installata nel server**. 
    
    > [!NOTE]
    >  Questa opzione è disponibile solo se è stata configurata una formula personalizzata dall'amministratore. 
  
  - In **azione**specificare cosa si desidera verificare quando il documento o l'elemento scade. Per attivare un'azione specifica per il documento o l'elemento, ad esempio l'eliminazione, selezionare un'azione dall'elenco. 
    
8. L'opzione **avvia un flusso di lavoro** è disponibile solo se si definisce un criterio per un elenco, una raccolta o un tipo di contenuto a cui è già associato un flusso di lavoro. Verrà quindi data la possibilità di scegliere tra i flussi di lavoro. 
    
9. In **ricorrenza**scegliere **Ripeti azione di questa fase...** e immettere la frequenza con cui si desidera che l'azione venga rieseguita. 
    
    > [!NOTE]
    >  Questa opzione è disponibile solo se l'azione selezionata può essere ripetuta. Ad esempio, non è possibile impostare la ricorrenza per l'azione **Elimina definitivamente**. 
  
10. Scegliere **OK**.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Applicazione di un criterio di raccolta siti a un tipo di contenuto
<a name="__apply_a_site"> </a>

Se i criteri di gestione delle informazioni sono già stati creati per il sito come criteri di raccolta siti, è possibile applicare uno dei criteri a un tipo di contenuto. In questo modo, è possibile applicare lo stesso criterio a più tipi di contenuto in una raccolta siti che non condividono lo stesso tipo di contenuto padre.
  
 Se si desidera applicare i criteri a più tipi di contenuto in una raccolta siti e si dispone di un servizio metadati gestiti configurato, è possibile utilizzare la pubblicazione dei tipi di contenuto per pubblicare le polizie di gestione delle informazioni in più raccolte siti. Per ulteriori informazioni, vedere la sezione [applicare un criterio tra le raccolte siti](#apply-a-policy-across-site-collections) . 
  
1. Passare all'elenco o alla raccolta che contiene il tipo di contenuto a cui si desidera applicare un criterio.
    
2. Sulla barra multifunzione, scegliere le impostazioni della raccolta o dell'elenco della scheda **raccolta** o **elenco** \> **Library Settings** . **List Settings**
    
    In SharePoint Online, fare clic su **Impostazioni** , quindi fare clic su impostazioni **elenco** o **Impostazioni raccolta**. 
    
3. In **autorizzazioni e gestione** \> **delle impostazioni dei criteri di gestione delle informazioni**.
  
![Collegamento ai criteri gestione informazioni nella pagina di impostazioni per una raccolta documenti](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Verificare che l'origine dei criteri sia impostata su **tipi di contenuto**e in **criteri tipo di contenuto** Selezionare il tipo di contenuto a cui si desidera applicare il criterio. 
    
5. In **specifica il** criterio \> **utilizzare un criterio di raccolta siti**e quindi selezionare il criterio che si desidera applicare dall'elenco. 
    
    > [!NOTE]
    >  Se l'opzione **Usa criterio raccolta siti** non è disponibile, non sono stati definiti criteri di raccolta siti per la raccolta siti. 
  
6. Scegliere **OK**.
    
     Se l'elenco o la raccolta che si sta utilizzando supporta la gestione di più tipi di contenuto, in **tipi di contenuto** è possibile scegliere il tipo di contenuto per il quale si desidera specificare un criterio di gestione delle informazioni. In questo modo è possibile passare direttamente al passaggio 5 sopra riportato. 
    
## <a name="apply-a-policy-across-site-collections"></a>Applicare un criterio tra le raccolte siti
<a name="__toc260646789"> </a>

Condividere tipi di contenuto tra raccolte siti tramite un'applicazione di servizio metadati gestiti per configurare la pubblicazione dei tipi di contenuto. La pubblicazione dei tipi di contenuto consente di gestire i contenuti e i metadati in modo coerente tra i siti perché i tipi di contenuto possono essere creati e aggiornati in modalità centrale e gli aggiornamenti possono essere pubblicati su più raccolte siti o applicazioni Web di sottoscrizione.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Creare un modello da un criterio esistente da utilizzare nelle raccolte siti
<a name="__toc262125409"> </a>

È possibile definire un criterio di gestione delle informazioni e quindi crearne un modello da utilizzare in base alle esigenze di più raccolte siti. Questo metodo può essere utilizzato se si desidera disporre di un backup dei criteri delle informazioni oppure può essere utilizzato anche come metodo alternativo per l'utilizzo della pubblicazione dei tipi di contenuto per l'applicazione di un criterio tra le raccolte siti. È possibile creare un modello o un backup dei criteri esportando il criterio da una raccolta siti e quindi importarlo in una posizione salvata o in un'altra raccolta siti.
  
> [!IMPORTANT]
>  Se si utilizza la caratteristica di esportazione/importazione per creare un set di modelli di criteri, tenere presente che esiste un identificatore univoco nel file Policy. XML. Per questo motivo, non è possibile importare il criterio in un sito più di una volta senza modificare questo identificatore univoco. 
  
### <a name="export-a-policy"></a>Esportare un criterio
<a name="__toc260646790"> </a>

1. Nella Home page della raccolta siti scegliere **Impostazioni** ![ piccole impostazioni ingranaggio che ha il posto delle impostazioni del ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) sito. \> **Site Settings**
    
    In un sito collegato a un gruppo di SharePoint fare clic su **Impostazioni**, quindi su **contenuto del sito**e quindi su **Impostazioni sito**. 
    
2. Nella pagina Impostazioni sito, in modelli di criteri tipo di contenuto **Amministrazione raccolta siti** \> **Content Type Policy Templates**. 
  
![Collegamento Modelli di criteri tipo di contenuto nella pagina Impostazioni sito](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Selezionare il criterio che si desidera esportare \> scorrere fino all' \> **esportazione**in basso.
    
4. Al prompt dei comandi per salvare o aprire il file, scegliere **Salva**, quindi selezionare un percorso in cui salvare il file. Assicurarsi di selezionare un percorso disponibile per le raccolte siti che stanno importando il criterio.
    
5. Quando viene visualizzata la finestra di dialogo download completo, fare clic su **Chiudi**.
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importare un criterio in una raccolta siti diversa
<a name="__toc260646791"> </a>

L'importazione di un criterio di gestione delle informazioni consente di applicarla a più tipi di contenuto a livello di sito o di elenco all'interno di una determinata raccolta siti. I vantaggi derivanti dall'esecuzione di questa operazione sono duplici: non è necessario ridefinire e applicare il criterio su ogni tipo di contenuto ed è possibile gestire più facilmente le modifiche ai criteri apportando modifiche ai criteri in una sola posizione.
  
1. Nella Home page della raccolta siti in cui si desidera applicare il criterio, scegliere **Impostazioni** ![ piccole impostazioni ingranaggio che ha avuto luogo delle impostazioni del sito. ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Impostazioni**del sito.
    
    In un sito collegato a un gruppo di SharePoint fare clic su **Impostazioni**, quindi su **contenuto del sito**e quindi su **Impostazioni sito**. 
    
2. Nella pagina Impostazioni sito, in modelli di criteri tipo di contenuto **Amministrazione raccolta siti** \> **Content Type Policy Templates**.
    
3. Nella pagina criteri \> **importare** \> **Sfoglia** per trovare il file XML per il criterio. 
    
4. Selezionare il file XML in cui il criterio è stato salvato \> **Open**. 
    
5. Nell'importazione della pagina importa un criterio di raccolta siti \> **Import** per aggiungere il criterio alla raccolta siti. 
    
È ora possibile applicare i criteri importati a uno o più tipi di contenuto a livello di sito o di elenco. 
  
I criteri di gestione delle informazioni consentono all'organizzazione di controllare il periodo di conservazione del contenuto, di verificare le persone che hanno a che fare con il contenuto e di aggiungere codici a barre o etichette ai documenti. Un criterio può contribuire a garantire la conformità ai regolamenti legali e governativi o ai processi aziendali interni. In qualità di amministratore, è possibile configurare un criterio per controllare la modalità di gestione dei documenti e la durata della conservazione dei documenti.

È possibile creare un criterio di gestione delle informazioni può essere in tre posizioni diverse nella gerarchia dei siti, dalla più ampia alla più stretta:
- Creare un criterio da utilizzare su più tipi di contenuto all'interno di una raccolta siti.
- Creare un criterio per un tipo di contenuto del sito.
- Creare un criterio per un elenco o una raccolta.

Per ulteriori informazioni, vedere [Introduzione ai criteri di gestione delle informazioni](intro-to-info-mgmt-policies.md).
  

