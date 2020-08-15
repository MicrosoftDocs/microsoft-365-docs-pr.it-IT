---
title: Recuperare gli elementi eliminati nella cassetta postale di un utente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: eb15194b-63ec-41b0-8d90-1823d3f558e4
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: In questo articolo sono contenute informazioni per gli amministratori che consentono di recuperare gli elementi eliminati, se non sono stati rimossi definitivamente dalla cassetta postale dell'utente.
ms.openlocfilehash: a4755e592182d93c37a241958ba37c95d1565cdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691037"
---
# <a name="recover-deleted-items-in-a-user-mailbox"></a>Recuperare gli elementi eliminati nella cassetta postale di un utente

**Questo articolo è rivolto agli amministratori. Si sta tentando di recuperare gli elementi eliminati nella propria cassetta postale? ** Eseguire una delle seguenti operazioni:
- [Recuperare gli elementi eliminati in Outlook per Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
- [Recuperare elementi o messaggi di posta elettronica eliminati in Outlook Web App](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
- [Ripristinare i messaggi di posta elettronica eliminati in Outlook sul Web](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
- [Outlook.com](https://go.microsoft.com/fwlink/p/?LinkID=623435)
   
Può accadere che un utente elimini in modo permanente alcuni elementi della propria cassetta postale di Outlook e che voglia recuperarli senza riuscirci. È possibile recuperare gli elementi eliminati se non sono stati rimossi definitivamente dalla cassetta postale dell'utente. Per eseguire questa operazione, usare lo strumento eDiscovery sul posto di Exchange Online per cercare i messaggi e altri elementi eliminati, ad esempio i contatti, gli appuntamenti del calendario e le attività, dalla cassetta postale di un utente. Se si trovano gli elementi eliminati, è possibile esportarli in un file PST, o file di dati di Outlook, che l'utente può poi usare per ripristinare gli elementi nella cassetta postale.
  
Ecco i passaggi per ripristinare gli elementi eliminati nella cassetta postale di un utente. Quanto tempo è necessario? La prima volta può richiedere da 20 a 30 minuti per il completamento di tutti i passaggi, a seconda del numero di elementi che si vuole recuperare.
  
> [!NOTE]
> È necessario essere un **amministratore di Exchange** o un **amministratore globale** in Microsoft 365 o essere un membro del gruppo di ruoli Gestione organizzazione in Exchange Online per eseguire la procedura descritta in questo articolo. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d). 
  
## <a name="step-1-assign-yourself-ediscovery-permissions"></a>Passaggio 1: Assegnare a se stessi le autorizzazioni di eDiscovery
<a name="step1"> </a>

Il primo passaggio consiste nell'assegnare a se stessi le autorizzazioni necessarie di Exchange Online per poter usare lo strumento eDiscovery sul posto per eseguire ricerche nella cassetta postale di un utente. Questa procedura deve essere eseguita una sola volta. Se sarà necessario eseguire una ricerca in un'altra cassetta postale in futuro, è possibile ignorare questo passaggio.
  
1. [Dove accedere a Microsoft 365 for business](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) con il proprio account aziendale o dell'Istituto di istruzione. 
    
2. Selezionare l'icona di avvio ![ delle app icona di avvio delle app in Microsoft 365 ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) nell'angolo in alto a sinistra e fare clic su **amministratore**.
    
3. Nel riquadro di spostamento a sinistra nell'interfaccia di amministrazione di Microsoft 365, espandere **Interfaccia di amministrazione** e poi fare clic su **Exchange**.
    
    ![Elenco Interfacce di amministrazione](../media/7d308eb7-ba63-4156-a845-3770facc5de4.PNG)
  
4. Nell’Interfaccia di amministrazione fare clic su **Autorizzazioni** e poi su **Ruoli amministratore**.
    
5. In questo elenco, selezionare **Gestione individuazione**, poi fare clic su **Modifica**![Icona Modifica](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).
    
    ![Aggiungersi al gruppo di ruoli Gestione individuazione nell'interfaccia di amministrazione di Exchange](../media/e5c98e93-d6a0-40c5-a143-bac956eedaa7.png)
  
6. In **Gruppi di ruoli**, sotto **Membri**, fare clic su **Aggiungi**![Icona aggiungi](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).
    
7. In **Scegli i membri**, selezionare il proprio nome nell'elenco, fare clic su **Aggiungi** e poi su **OK**.
    
    > [!NOTE]
    > È anche possibile aggiungere un gruppo di cui si è un membro, ad esempio il gruppo di gestione dell'organizzazione o degli amministratori del tenant. Se si aggiunge un gruppo, agli altri membri del gruppo vengono assegnate le autorizzazioni necessarie per eseguire lo strumento eDiscovery sul posto. 
  
8. In **Gruppo di ruoli**, fare clic su **Salva**.
    
9. Disconnettersi da Microsoft 365.
    
    È necessario disconnettersi prima di iniziare il passaggio successivo, in modo da rendere effettive le nuove autorizzazioni.
    
> [!CAUTION]
> I membri del gruppo di ruoli Gestione individuazione possono accedere al contenuto dei messaggi riservati. Sono incluse le ricerche in tutte le cassette postali dell'organizzazione, la visualizzazione in anteprima dei risultati della ricerca, e di altri elementi della cassetta postale, la copia dei risultati in una cassetta postale di individuazione e l’esportazione dei risultati della ricerca in un file PST. 
  
[Inizio pagina](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-2-search-the-users-mailbox-for-deleted-items"></a>Passaggio 2: Cercare gli elementi eliminati nella cassetta postale dell'utente
<a name="step2"> </a>

Quando si esegue una ricerca eDiscovery sul posto, la cartella Elementi ripristinabili nella cassetta postale in cui si sta eseguendo la ricerca viene automaticamente inclusa nella ricerca. La cartella Elementi ripristinabili è il luogo dove vengono archiviati gli elementi eliminati fino a quando non vengono rimossi per sempre dalla cassetta postale. Pertanto, se un elemento non è stato rimosso, è possibile trovarlo con lo strumento eDiscovery sul posto.
  
1. [Dove accedere a Microsoft 365 for business](https://support.microsoft.com/office/where-to-sign-into-microsoft-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) con il proprio account aziendale o dell'Istituto di istruzione. 
    
2. Selezionare l'icona di avvio ![ delle app icona di avvio delle app in Microsoft 365 ](../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) nell'angolo in alto a sinistra e fare clic su **amministratore**.
    
3. Nel riquadro di spostamento a sinistra nell'interfaccia di amministrazione di Office 365, espandere **Amministratore** e poi fare clic su **Exchange**.
    
4. Nell'interfaccia di amministrazione di Exchange fare clic su **Gestione conformità**, poi su **eDiscovery &amp;blocco sul posto**e infine fare clic sull’icona **Nuovo**![Icona Aggiungi](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).
    
    ![Nella pagina gestione conformità dell'Interfaccia di amministrazione di Exchange fare clic su eDiscovery e blocco sul posto](../media/9d9ff0f5-b9be-45b8-8b5e-6037a856b0a8.png)
  
5. Nella pagina **Nome e descrizione** digitare un nome per la ricerca, ad esempio il nome dell'utente per cui si sta ripristinando la posta elettronica, una descrizione facoltativa e poi fare clic su **Avanti**.
    
6. Nella pagina **Cassette postali** fare clic su **Specifica le cassette postali in cui cercare** e quindi fare clic su **Aggiungi**![Icona Aggiungi](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif).
    
    ![Fare clic su Specifica le cassette postali in cui cercare per limitare la ricerca a una cassetta postale specifica](../media/83879a40-5e5c-49a8-be3b-c0023d197588.png)
  
7. Trovare e selezionare il nome dell'utente per cui si ripristinano i messaggi di posta elettronica eliminati, fare clic su **Aggiungi** e dopo su **OK**.
    
8. Fare clic su **Avanti**.
    
    Viene visualizzata la pagina **Query di ricerca**. In questa posizione si definiscono i criteri di ricerca che consentono di trovare gli elementi mancanti nella cassetta postale dell'utente. 
    
9. Nella pagina **Query di ricerca** compilare i seguenti campi: 
    
  - **Includi tutto il contenuto** Selezionare questa opzione per includere tutto il contenuto della cassetta postale dell'utente nei risultati della ricerca. Se viene selezionata questa opzione, non è possibile specificare ulteriori criteri di ricerca. 
    
  - **Filtra sulla base dei criteri** Selezionare questa opzione per specificare i criteri di ricerca, incluse le parole chiave, le date di inizio e di fine, gli indirizzi del mittente e del destinatario e i tipi di messaggio. 
    
    ![Creare una ricerca basata su criteri come parole chiave, intervalli di date, destinatari e tipi di messaggio](../media/ee47b833-9122-46a0-85e6-fcbe25be0dd5.png)
  
|**Campo**|**Utilizzare questa opzione per...**|
|:-----|:-----|
|![Numero uno in un cerchio rosa](../media/a4da261d-2516-48c5-b58a-9c452b9086b8.png)           <br/> |Specificare le parole chiave, un intervallo di date, i destinatari e i tipi di messaggi.  <br/> |
|![Numero due in un cerchio rosa.](../media/de3c1ab4-4f01-4026-b1ba-3265bdb32a89.png)           <br/> |Cercare i messaggi con parole chiave o frasi e usare gli operatori logici, ad esempio **AND** oppure **OR**.  <br/> |
|![Numero tre in un cerchio rosa.](../media/60fa378c-6ac1-4cbd-a782-2fa7ca619dc6.png)           <br/> |Cercare i messaggi inviati o ricevuti in un intervallo di date.  <br/> |
|![Number quattro in a pink circle.](../media/1a0ff2ce-0942-405a-94e3-9bfeb1e5059e.png)           <br/> |Cercare i messaggi ricevuti o inviati a utenti specifici.  <br/> |
|![Numero cinque in un cerchio rosa.](../media/878cc815-0165-49ba-a1ee-9236e5980403.png)           <br/> |Cercare tutti i tipi di messaggi oppure selezionarne di specifici.  <br/> |
   
   > [!TIP]
   >  Ecco alcuni suggerimenti su come creare una query di ricerca per trovare gli elementi mancanti. Provare a ottenere dall'utente tutte le informazioni necessarie per creare una query di ricerca idonea per trovare gli elementi cercati. Se non si è sicuri di come trovare un messaggio mancante, è consigliabile usare l'opzione **Includi tutto il contenuto**. I risultati della ricerca includeranno tutti gli elementi nella cartella Elementi ripristinabili dell'utente, tra cui la cartella nascosta (denominata Ripuliture) che contiene gli elementi che sono stati eliminati dall'utente. A questo punto è possibile passare al passaggio 3, copiare i risultati in una cassetta postale di individuazione e osservare il messaggio nella cartella nascosta. Se si conosce approssimativamente quando il messaggio mancante è stato inviato o ricevuto dall'utente originariamente, usare le opzioni **Specifica la data di inizio** e **Specifica la data di fine** per specificare un intervallo di date. Verranno restituiti tutti i messaggi inviati o ricevuti dall'utente in tale intervallo di date. Specificare un intervallo di date è un modo molto efficace per limitare i risultati della ricerca. Se si conosce chi ha inviato i messaggi mancanti, usare la casella **Da** per specificare il mittente. Se si vuole limitare i risultati della ricerca a tipi diversi di elementi della cassetta postale, fare clic su **Seleziona tipi di messaggi**, quindi su **Scegli i tipi di messaggi in cui cercare** e infine scegliere un tipo di messaggio specifico da cercare. È ad esempio possibile cercare solo gli elementi del calendario o i contatti. Ecco una schermata che illustra i diversi tipi di messaggio che è possibile cercare. Per impostazione predefinita vengono cercati tutti i tipi di messaggio. 
  
   Fare clic su **Avanti** dopo aver completato la pagina **Query di ricerca**. 
    
10. Nella pagina **Impostazioni di blocco sul posto** fare clic su **Fine** per avviare la ricerca. Per recuperare i messaggi eliminati, non occorre impostare un blocco per la cassetta postale dell'utente. 
    
    Dopo aver iniziato la ricerca, Exchange visualizzerà una stima delle dimensioni totali e del numero di elementi restituiti dalla ricerca in base ai criteri specificati.
    
11. Selezionare la ricerca appena creata e fare clic su **Aggiorna**![aggiorna](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) per aggiornare le informazioni visualizzate nel riquadro dei dettagli. Lo stato di **Stima completata** indica che la ricerca è terminata. Exchange visualizza anche una stima del numero totale di elementi, e delle relative dimensioni, trovati mediante la ricerca in base ai criteri di ricerca specificati nel passaggio 9. 
    
12. Nel riquadro dei dettagli, fare clic su **Anteprima risultati della ricerca** per visualizzare gli elementi che sono stati individuati. Questo potrebbe aiutare a identificare gli elementi che si stanno cercando. Se si trovano gli elementi che si vogliono recuperare, andare al passaggio 4 per esportare i risultati della ricerca in un file PST. 
    
    ![Fare clic su Anteprima risultati della ricerca per visualizzare l'elemento che si sta provando a recuperare](../media/a2cea921-dafa-45d6-97d4-ae45a226b8d3.png)
  
13. Se non si trova ciò che sta cercando, è possibile modificare i criteri di ricerca facendo clic sull’icona **Modifica**![Icona Modifica](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) e poi su **Query di ricerca**. Modificare i criteri di ricerca e quindi eseguire di nuovo la ricerca.
    
[Inizio pagina](recover-deleted-items-in-a-mailbox.md)
  
## <a name="optional-step-3-copy-the-search-results-to-a-discovery-mailbox"></a>(Facoltativo) Passaggio 3: Copiare i risultati della ricerca in una cassetta postale di individuazione
<a name="step3"> </a>

Se non si riesce a trovare un elemento nell’anteprima dei risultati della ricerca o se si vuole vedere quali elementi sono presenti nella cartella Elementi ripristinabili, è possibile copiare i risultati della ricerca in una cassetta postale speciale denominata cassetta postale di individuazione e quindi aprirla in Outlook sul Web per visualizzare gli elementi effettivi. La copia dei risultati della ricerca rappresenta il modo migliore di visualizzare gli elementi nella cartella Elementi ripristinabili dell'utente. È molto probabile che l'elemento che si vuole recuperare si trovi nella sottocartella Ripuliture. 
  
1. Nell'interfaccia di amministrazione di Exchange passare a **Gestione conformità**\>**eDiscovery &amp; blocco sul posto**.
    
2. Nell'elenco delle ricerche selezionare la ricerca creata nel passaggio 2.
    
3. Fare clic su** Ricerca**![ricerca](../media/c94e8591-7044-4650-a0d1-c57c0633ab4f.png), poi su **Copia risultati della ricerca** dall'elenco a discesa. 
    
    ![Fare clic su Cerca e poi su Copia risultati della ricerca](../media/7888df82-94b4-4e44-8a53-f66854dc7c86.png)
  
4. Nella pagina **Copia risultati della ricerca** fare clic su **Sfoglia**.
    
    ![Lasciare deselezionate le caselle di controllo quando si recuperano gli elementi eliminati](../media/37f27999-a5b2-4fed-87e2-bad6dc23cdae.png)
  
5. In **Nome visualizzato** fare clic su **Cassetta postale di individuazione** e quindi su **OK**.
    
    ![Copiare i risultati della ricerca nella cassetta postale di individuazione predefinita](../media/36e8ef47-0035-4982-9ed6-426719c5f9ec.png)
  
    > [!NOTE]
    > La cassetta postale di ricerca di individuazione è una cassetta postale di individuazione predefinita creata automaticamente nell'organizzazione Microsoft 365. 
  
6. Tornare alla pagina **Copia risultati della ricerca**, fare clic su **Copia** per avviare la copia dei risultati della ricerca nella assetta postale di individuazione. 
    
    ![Fare clic su Copia per copiare i risultati della ricerca nella cassetta postale di individuazione](../media/71307a9d-f7a1-4e01-ae37-1d49040cc3fd.png)
  
7. Fare clic su **Aggiorna**![aggiorna](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) per aggiornare le informazioni sullo stato della copia visualizzate nel riquadro dei dettagli. 
    
8. Al termine della copia, fare clic su **Apri** per aprire la cassetta postale di individuazione e visualizzare i risultati della ricerca. 
    
    ![Fare clic su Apri per passare alla cassetta postale di individuazione e visualizzare i risultati della ricerca](../media/6cc81e0f-ceed-4464-9040-79b6f920de35.png)
  
    I risultati della ricerca copiati nella cassetta postale di individuazione vengono inseriti in una cartella con lo stesso nome della ricerca eDiscovery sul posto. È possibile fare clic su una cartella per visualizzare gli elementi presenti.
    
    ![Risultati della ricerca nella cassetta postale di individuazione; gli elementi della cartella Ripuliture possono essere recuperati solo da un amministratore](../media/2ef8e5fb-3e63-4f62-938e-307efe9f6998.gif)
  
    Quando si esegue una ricerca, la ricerca viene effettuata anche nella cartella Elementi ripristinabili dell'utente. Pertanto, se gli elementi nella cartella Elementi ripristinabili soddisfano i criteri di ricerca, vengono inclusi nei risultati della ricerca. Gli elementi nella cartella Eliminazioni sono gli elementi eliminati in modo permanente dall'utente: gli elementi eliminati dalla cartella Posta eliminata oppure gli elementi selezionati con successiva esecuzione di **MAIUC+CANC**. Un utente può usare lo strumento Recupera Posta eliminata in Outlook o Outlook sul Web per recuperare gli elementi nella cartella Eliminazioni. Gli elementi nella cartella Ripuliture sono elementi che l'utente ha eliminato tramite lo strumento Recupera elementi eliminati o eliminati automaticamente dai criteri applicati alla cassetta postale. In entrambi i casi, solo un amministratore può recuperare gli elementi nella cartella Ripuliture. 
    
    > [!TIP]
    > Se un utente non riesce a trovare un elemento eliminato tramite lo strumento Elementi ripristinabili, ma tale elemento è comunque ripristinabile, in quanto non è stato rimosso definitivamente dalla cassetta postale, è molto probabile che si trovi nella cartella Purges. Pertanto, assicurarsi di controllare la cartella Ripuliture per cercare gli elementi eliminati che si vuole recuperare per un utente. 
  
[Inizio pagina](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-4-export-the-search-results-to-a-pst-file"></a>Passaggio 4: Esportare i risultati della ricerca in un file PST
<a name="step4"> </a>

Dopo aver individuato l'elemento che si vuole recuperare per un utente, occorre esportare i risultati della ricerca eseguita al passaggio 2 in un file PST. L'utente userà questo file PST nel passaggio successivo per ripristinare l'elemento eliminato nella propria cassetta postale.
  
1. Nell'interfaccia di amministrazione di Exchange passare a **Gestione conformità**\>**eDiscovery &amp; blocco sul posto**.
    
2. Nell'elenco delle ricerche selezionare la ricerca creata nel passaggio 2.
    
3. Fare clic su **Esporta in un file PST**.
    
    ![Fare clic su Esporta in un file PST](../media/4e59ae17-4541-43f4-a6d1-1f8b9ba9404b.png)
  
4. Se viene richiesto di installare lo strumento di esportazione di eDiscovery, fare clic su **Esegui**.
    
5. Nello strumento di esportazione PST eDiscovery fare clic su **Sfoglia** per specificare il percorso in cui si vuole scaricare il file PST. 
    
    ![Strumento di esportazione PST eDiscovery](../media/17274d27-992e-4034-8133-8f793f554e6c.png)
  
    È possibile ignorare le opzioni per abilitare la deduplicazione e includere elementi non ricercabili.
    
6. Fare clic su **Start** per scaricare il file PST nel computer. 
    
    Lo **strumento di esportazione di eDiscovery** mostra le informazioni relative all stato del processo di esportazione. Quando l'esportazione è completa, è possibile accedere al file nella posizione in cui è stato scaricato. 
    
[Inizio pagina](recover-deleted-items-in-a-mailbox.md)
  
## <a name="step-5-restore-the-recovered-items-to-the-users-mailbox"></a>Passaggio 5: Ripristinare gli elementi recuperati nella cassetta postale dell'utente
<a name="step5"> </a>

Il passaggio finale consiste nell'usare il file PST esportato nel passaggio 4 per ripristinare gli elementi recuperati nella cassetta postale dell'utente. Dopo l'invio del file PST, l'utente esegue la parte restante di questo passaggio per aprire il file PST e quindi spostare gli elementi recuperati in un'altra cartella nella propria cassetta postale. Per istruzioni dettagliate, è anche possibile inviare all'utente un collegamento a questo argomento: [Aprire e chiudere file di dati di Outlook (PST)](https://support.office.com/article/381b776d-7511-45a0-953a-0935c79d24f2). In alternativa, è possibile inviare all'utente un collegamento alla sezione [Ripristinare gli elementi eliminati in una cassetta postale tramite un file PST](recover-deleted-items-in-a-mailbox.md#restoredeleteditems) e chiedergli di eseguire questa procedura. 
  
 **Inviare il file PST all'utente**
  
Il passaggio finale che è necessario eseguire è inviare all'utente il file PST esportato al passaggio 4. Questa operazione si può eseguire in vari modi:
  
- Allegare il file PST a un messaggio di posta elettronica. Se Outlook è configurato per bloccare i file PST, sarà necessario comprimere il file e quindi allegarlo al messaggio. Ecco come:
    
1. In Windows Explorer o File Explorer passare al file PST.
    
2. Fare clic con il pulsante destro del mouse sul file, quindi selezionare **Invia a** \> **Cartella compressa**. Windows crea un nuovo file ZIP a cui assegna lo stesso nome del file PST.
    
3. Allegare il file PST compresso a un messaggio di posta elettronica e inviarlo all'utente, che potrà poi decomprimere il file semplicemente facendo clic su di esso.
    
- Copiare il file PST in una cartella condivisa a cui l'utente potrà accedere per recuperarlo.
    
La procedura descritta nella sezione seguente viene eseguita dall'utente per ripristinare gli elementi eliminati nella propria cassetta postale.
  
 <a name="restoredeleteditems"></a>
**Ripristinare gli elementi eliminati in una cassetta postale tramite un file PST**
  
Per ripristinare un elemento eliminato tramite un file PST, è necessario usare l'app desktop di Outlook. Non è possibile usare Outlook Web App o Outlook sul Web per aprire un file PST.
  
1. In Outlook 2013 o Outlook 2016 fare clic sulla scheda **File**. 
    
2. Fare clic su **Apri &amp; esporta** e quindi su **Apri file di dati di Outlook**.
    
3. Passare al percorso in cui è stato salvato il file PST inviato dall'amministratore.
    
4. Selezionare il file PST e poi fare clic su **Apri**.
    
    Il file PST viene visualizzato nella barra di spostamento sinistra di Outlook.
    
    ![Il file PST viene visualizzato nella barra di spostamento sinistra di Outlook](../media/c9389392-d08a-4aa7-848c-4986d448b0f2.png)
  
5. Fare clic sulle frecce per espandere il file PST e le cartelle secondarie per individuare l'elemento da recuperare.
    
    ![Cercare l'elemento da recuperare nella cartella Ripuliture](../media/d4e372d9-ac23-4e95-8639-d8da690fefa7.png)
  
    > [!TIP]
    > Cercare l'elemento da recuperare nella cartella Ripuliture. Si tratta di una cartella nascosta in cui vengono spostati gli elementi eliminati. È probabile che l'elemento recuperato dall'amministratore sia in questa cartella. 
  
6. Fare clic con il pulsante destro del mouse sull'elemento da recuperare e poi fare clic su **Sposta** \> **Altra cartella**.
    
    ![Fare clic su Sposta e quindi selezionare Altra cartella](../media/090063df-2aa0-444a-8e47-abd6fe6cf7a8.png)
  
7. Per spostare l'elemento nella cartella Posta in arrivo, fare clic su **Posta in arrivo** e poi su **OK**.
    
    **Suggerimento:** Per recuperare altri tipi di elementi, eseguire una delle operazioni seguenti: 
    
  - Per recuperare un elemento del calendario, fare clic su di esso con il pulsante destro del mouse e scegliere **Sposta** \> **Altra cartella** \> **Calendario**.
    
  - Per recuperare un contatto, fare clic su di esso con il pulsante destro del mouse e scegliere **Sposta** \> **Altra cartella** \> ** Contatti**.
    
  - Per recuperare un'attività, fare clic su di essa con il pulsante destro del mouse e scegliere **Sposta** \> **Altra cartella** \> **Attività**.
    
![Selezionare una cartella in cui spostare altri tipi di elementi](../media/f8290131-43f2-46f1-bc07-228c2d83b96c.png)
  
   > [!NOTE]
   > Gli elementi del calendario, i contatti e le attività si trovano direttamente nella cartella Ripuliture e non in una sottocartella del calendario, dei contatti o delle attività. È possibile tuttavia ordinare per **tipo** per raggruppare i tipi di elementi simili. 
    
8. Dopo aver completato il recupero degli elementi eliminati, fare clic con il pulsante destro del mouse sul file PST nella barra di spostamento sinistra e selezionare **Chiudi "nome del file PST"**.
    
[Inizio pagina](recover-deleted-items-in-a-mailbox.md)
  
## <a name="more-information"></a>Altre informazioni
<a name="moreinfo"> </a>

- Un utente può recuperare un elemento eliminato definitivamente, se il periodo di conservazione degli elementi eliminati non è scaduto. È possibile che l'amministratore abbia specificato per quanto tempo sono disponibili gli elementi nella cartella Elementi ripristinabili. Ad esempio, possono essere stati configurati dei criteri in base ai quali tutti gli elementi contenuti nella cartella Posta eliminata vengono eliminati dopo 30 giorni e altri criteri che consentono di recuperare gli elementi nella cartella Elementi ripristinabili per altri 14 giorni. Tuttavia, dopo 14 giorni, è ancora possibile recuperare un elemento della cassetta postale di un utente tramite le procedure descritte in questo argomento.
    
- Gli utenti possono ripristinare un elemento se non è stato rimosso e se non è scaduto il periodo di conservazione per quell'elemento. Per aiutare gli utenti a recuperare gli elementi eliminati nella propria cassetta postale, suggerire loro di consultare gli argomenti seguenti:
    
  - [Ripristinare gli elementi eliminati in Outlook per Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)
    
  - [Ripristinare gli elementi eliminati in Outlook 2010](https://support.office.com/article/cd9dfe12-8e8c-4a21-bbbf-4bd103a3f1fe)
    
  - [Recuperare elementi o messaggi di posta elettronica eliminati in Outlook Web App](https://support.office.com/article/c3d8fc15-eeef-4f1c-81df-e27964b7edd4)
    
  - [Ripristinare i messaggi di posta elettronica eliminati in Outlook sul Web](https://support.office.com/article/a8ca78ac-4721-4066-95dd-571842e9fb11)
    
  - [Recuperare un contatto eliminato in Outlook](https://support.office.com/article/51c83288-6888-4dcd-8c99-4932daabf643)
    
  - [Ripristinare i messaggi di posta elettronica eliminati in Outlook.com](https://go.microsoft.com/fwlink/p/?LinkID=623435)
    
[Inizio pagina](recover-deleted-items-in-a-mailbox.md)
  

