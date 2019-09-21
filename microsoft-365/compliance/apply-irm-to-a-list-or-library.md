---
title: Applicazione di Information Rights Management (IRM) a un elenco o a una raccolta
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
description: È possibile utilizzare Information Rights Management (IRM) per controllare e proteggere i file scaricati da elenchi o raccolte.
ms.openlocfilehash: 3c350a3648b77992dd8e86ee47498efc327b2af8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083337"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Applicazione di Information Rights Management (IRM) a un elenco o a una raccolta

È possibile utilizzare Information Rights Management (IRM) per controllare e proteggere i file scaricati da elenchi o raccolte.
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Il servizio Azure Rights Management (Azure RMS) di Azure Information Protection e l'equivalente locale, Active Directory Rights Management Services (AD RMS), supportano Information Rights Management per i siti. Non sono necessarie installazioni separate o aggiuntive.
    
- Prima di applicare IRM a un elenco o a una raccolta, è necessario che sia abilitato per la prima volta da un amministratore del sito.
    
- Per applicare IRM a un elenco o a una raccolta, è necessario disporre delle autorizzazioni di amministratore per l'elenco o la raccolta.
    
- Se si utilizza SharePoint Online, è possibile che gli utenti verifichino timeout durante il download di file protetti con IRM di grandi dimensioni. In questo caso, applicare la protezione IRM tramite le applicazioni di Office e archiviare file di grandi dimensioni in una raccolta di SharePoint che non utilizza IRM.
    
> [!NOTE]
> Se si utilizza SharePoint Server 2013, è necessario che un amministratore del server installi protettori su tutti i server Web front-end per ogni tipo di file che gli utenti dell'organizzazione desiderano proteggere tramite IRM. 
  
## <a name="apply-irm-to-a-list-or-library"></a>Applicazione di IRM a un elenco o a una raccolta
<a name="__toc256598179"> </a>

![Impostazioni di Information Rights Management](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Passare all'elenco o alla raccolta per cui si desidera configurare IRM.
    
2. Sulla barra multifunzione fare clic sulla scheda **raccolta** e quindi su **Impostazioni raccolta**. Se si utilizza un elenco, fare clic sulla scheda **elenco** e quindi su **Impostazioni elenco**.
    
    ![Pulsanti delle impostazioni della raccolta di SharePoint sulla barra multifunzione](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. In **autorizzazioni e gestione**fare clic su **Information Rights Management**. Se il collegamento Information Rights Management non è visualizzato, IRM potrebbe non essere abilitato per il sito. Contattare l'amministratore del server per verificare se è possibile abilitare IRM per il sito. Il collegamento Information Rights Management non è visualizzato per le raccolte immagini.
    
4. Nella pagina **impostazioni di Information Rights Management** selezionare la casella di controllo **limitare l'autorizzazione per i documenti in questa raccolta** per applicare le autorizzazioni limitate ai documenti scaricati dall'elenco o dalla raccolta. 
    
5. Nella casella **Crea un titolo** per i criteri di autorizzazione digitare un nome descrittivo per il criterio che è possibile utilizzare in un secondo momento per differenziare questo criterio da altri criteri. Ad esempio, è possibile digitare **Confidential Company** se si sta applicando un'autorizzazione limitata a un elenco o a una raccolta che conterrà documenti aziendali riservati. 
    
6. Nella casella di testo **Aggiungi una** descrizione per i criteri di autorizzazione digitare una descrizione che verrà visualizzata agli utenti che utilizzano l'elenco o la raccolta che spiega come gestire i documenti in questo elenco o nella raccolta. Ad esempio, è possibile digitare **Discuti il contenuto del documento solo con altri dipendenti** se si desidera limitare l'accesso alle informazioni contenute in questi documenti ai dipendenti interni. 
    
7. Per applicare ulteriori restrizioni ai documenti presenti in questo elenco o raccolta, fare clic su **Mostra opzioni**e quindi eseguire una delle operazioni seguenti:
    
|**Per eseguire questa operazione:**|**Procedere come segue:**|
|:-----|:-----|
|Consenti agli utenti di stampare documenti da questo elenco o dalla raccolta  <br/> |Selezionare la casella **di controllo Consenti stampa visualizzatori** .  <br/> |
|Consentire alle persone con almeno l'autorizzazione Visualizza elementi di eseguire codice incorporato o macro in un documento.  <br/> |Selezionare la casella di controllo **Consenti agli utenti di eseguire lo script e il lettore schermo per funzionare nei documenti scaricati** .  <br/> Se si seleziona questa opzione, gli utenti potrebbero eseguire codice per estrarre il contenuto di un documento.           |
|Richiedere che gli utenti verifichino le proprie credenziali a intervalli specifici.  <br/> Selezionare questa opzione se si desidera limitare l'accesso al contenuto a un determinato periodo di tempo. Se si seleziona questa opzione, le licenze di pubblicazione degli utenti per accedere al contenuto scadranno dopo il numero di giorni specificato e gli utenti saranno tenuti a tornare al server per verificare le credenziali e scaricare una nuova copia.  <br/> |Selezionare la casella di controllo **intervalli (giorni) per gli utenti devono verificare le proprie credenziali** e quindi specificare il numero di giorni per cui si desidera visualizzare il documento.  <br/> |
| Impedire agli utenti di caricare documenti che non supportano IRM nell'elenco o nella raccolta.  <br/>  Se si seleziona questa opzione, gli utenti non saranno in grado di caricare uno dei tipi di file seguenti:  <br/>  I tipi di file che non dispongono di protettori IRM corrispondenti sono installati in tutti i server Web front-end.  <br/>  Tipi di file che SharePoint Server 2010 non è in grado di decrittografare.  <br/>  Tipi di file che sono protetti da IRM in un altro programma  <br/> |Selezionare la casella di controllo non **consentire agli utenti di caricare i documenti che non supportano IRM** .  <br/> |
|Rimuovere le autorizzazioni limitate dall'elenco o dalla raccolta in base a una data specifica.  <br/> |Selezionare la casella di controllo **Interrompi la limitazione dell'accesso alla raccolta** e quindi selezionare la data desiderata.  <br/> |
|Controllare l'intervallo di memorizzazione nella cache delle credenziali per il programma concesso in licenza per l'apertura del documento.  <br/> |Nell' **intervallo imposta protezione e credenziali di gruppo**immettere theinterval per le credenziali di memorizzazione nella cache in numero di giorni.  <br/> |
|Consenti protezione di gruppo in modo che gli utenti possano condividerli con i membri dello stesso gruppo.  <br/> |Selezionare **Consenti protezione gruppo**e immettere il nome del gruppo per la condivisione.  <br/> |
   
8. Dopo aver selezionato le opzioni desiderate, fare clic su **OK**.
  
## <a name="what-is-information-rights-management"></a>Che cos'è Information Rights Management?
<a name="__toc256598175"> </a>

Information Rights Management (IRM) consente di limitare le operazioni che gli utenti possono eseguire sui file scaricati da elenchi o raccolte. IRM consente di crittografare i file scaricati e limitare il gruppo di utenti e programmi autorizzati a decrittografare tali file. IRM può anche limitare i diritti degli utenti autorizzati a leggere i file in modo che non possano intraprendere azioni come la stampa di copie dei file o la copia di testo da essi.
  
È possibile utilizzare IRM in elenchi o raccolte per limitare la diffusione di contenuto riservato. Se ad esempio si sta creando una raccolta documenti per condividere informazioni sui prodotti imminenti con rappresentanti di marketing selezionati, è possibile utilizzare IRM per impedire a tali utenti di condividere questo contenuto con altri dipendenti dell'azienda.
  
In un sito, è possibile applicare IRM a un intero elenco o raccolta anziché a singoli file. In questo modo è più facile garantire un livello di protezione omogeneo per un intero insieme di documenti o file. IRM può quindi aiutare l'organizzazione a applicare i criteri aziendali che regolano l'utilizzo e la divulgazione di informazioni riservate o proprietarie.
  
> [!NOTE]
> Le informazioni contenute in questa pagina per informazioni su Information Rights Management sostituiscono qualsiasi termine che fa riferimento a' Information Rights Management ' nei contratti di licenza di Microsoft SharePoint Server 2013 e SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Informazioni su come IRM può contribuire alla protezione del contenuto
<a name="__toc256598176"> </a>

IRM consente di proteggere il contenuto limitato nei modi seguenti:
  
- Consente di impedire a un visualizzatore autorizzato la copia, la modifica, la stampa, l'invio di fax o la copia e incolla del contenuto per l'utilizzo non autorizzato
    
- Consente di impedire a un visualizzatore autorizzato di copiare il contenuto utilizzando la funzionalità Stampa schermo in Microsoft Windows
    
- Consente di impedire a un visualizzatore non autorizzato di visualizzare il contenuto se viene inviato in un messaggio di posta elettronica dopo che è stato scaricato dal server
    
- Limita l'accesso al contenuto a un determinato periodo di tempo, dopo il quale gli utenti devono confermare le proprie credenziali e scaricare di nuovo il contenuto.
    
- Consente di applicare i criteri aziendali che regolano l'utilizzo e la divulgazione dei contenuti all'interno dell'organizzazione
    
### <a name="how-irm-cannot-help-protect-content"></a>Informazioni su come IRM non è in grado di proteggere il contenuto
<a name="__toc256598177"> </a>

IRM non è in grado di proteggere il contenuto limitato dai seguenti elementi:
  
- Cancellazione, furto, acquisizione o trasmissione da parte di programmi dannosi, ad esempio cavalli di cavallo, logger di tasti e alcuni tipi di spyware
    
- Perdita o danneggiamento a causa delle azioni dei virus informatici
    
- Copia manuale o ridigitazione del contenuto dalla visualizzazione su schermo
    
- Fotografia digitale o cinematografica del contenuto visualizzato in uno schermo
    
- Copia tramite l'utilizzo di programmi di acquisizione schermo di terze parti
    
- Copia dei metadati del contenuto (valori di colonna) tramite l'utilizzo di programmi di acquisizione schermo di terze parti o di un'azione copia e incolla
    
[Applicare Information Rights Management a un elenco o a una raccolta](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Funzionamento di IRM per elenchi e raccolte
<a name="__toc256598178"> </a>

La protezione IRM viene applicata ai file a livello di elenco o di raccolta. Quando IRM è abilitato per una raccolta, Rights Management si applica a tutti i file della raccolta. Quando IRM è abilitato per un elenco, Rights Management si applica solo ai file associati a voci di elenco e non alle voci di elenco effettive.
  
Quando gli utenti scaricano i file in un elenco o in una raccolta abilitata per IRM, i file vengono crittografati in modo che solo le persone autorizzate possano visualizzarle. Ogni file con diritti gestiti contiene anche una licenza di pubblicazione che impone restrizioni agli utenti che visualizzano il file. Le restrizioni tipiche includono l'esecuzione di un file di sola lettura, la disattivazione della copia del testo, impedire agli utenti di salvare una copia locale e impedire agli utenti di stampare il file. I programmi client in grado di leggere i tipi di file supportati da IRM utilizzano la licenza di pubblicazione all'interno del file Rights-Managed per applicare queste restrizioni. Questo è il modo in cui un file con diritti gestiti conserva la propria protezione anche dopo che è stato scaricato dal server.
  
I tipi di restrizioni applicati a un file quando vengono scaricati da un elenco o da una raccolta si basano sulle autorizzazioni dei singoli utenti nel sito che contiene il file. Nella tabella seguente viene illustrato il modo in cui le autorizzazioni per i siti corrispondono alle autorizzazioni IRM.
  
|**Autorizzazioni**|**Autorizzazioni IRM**|
|:-----|:-----|
|Gestione delle autorizzazioni, gestione sito Web  <br/> |**Controllo completo** (come definito dal programma client): questa autorizzazione consente in genere a un utente di leggere, modificare, copiare, salvare e modificare le autorizzazioni per il contenuto protetto.  <br/> |
|Modifica elementi, gestione elenchi, aggiunta e personalizzazione pagine  <br/> |**Modifica**, **copia**e **Salva**: un utente può stampare un file solo se la casella **di controllo Consenti agli utenti di stampare i documenti** è selezionata nella pagina impostazioni di Information Rights Management per l'elenco o la raccolta.  <br/> |
|Visualizzazione elementi  <br/> |**Lettura**: un utente può leggere il documento, ma non è in grado di copiarlo o modificarne il contenuto. Un utente può stampare solo se la casella **di controllo Consenti agli utenti di stampare i documenti** è selezionata nella pagina delle impostazioni di Information Rights Management per l'elenco o la raccolta.  <br/> |
|Altro  <br/> |Nessun'altra autorizzazione corrisponde direttamente alle autorizzazioni IRM.  <br/> |
   
Quando si abilita IRM per un elenco o una raccolta in SharePoint Server 2013, è possibile proteggere solo i tipi di file nell'elenco o nella raccolta di cui è installato un Protector su tutti i server Web front-end. Un Protector è un programma che controlla la crittografia e la decrittografia dei file con diritti gestiti di un formato di file specifico. SharePoint include protettori per i seguenti tipi di file:
  
- Moduli di Microsoft Office InfoPath
    
- Formati di file di 97-2003 per le seguenti applicazioni di Microsoft Office: Word, Excel e PowerPoint
    
- Formati di Office Open XML per le seguenti applicazioni di Microsoft Office: Word, Excel e PowerPoint
    
- Formato XML Paper Specification (XPS)
    
Se l'organizzazione prevede di utilizzare IRM per proteggere altri tipi di file oltre a quelli sopra elencati, è necessario che l'amministratore del server installi i protettori per questi formati di file aggiuntivi.
  

