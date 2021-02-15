---
title: Applicare Information Rights Management (IRM) a un elenco o a una raccolta
f1.keywords:
- NOCSH
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
- SPO_Content
description: È possibile utilizzare Information Rights Management (IRM) per controllare e proteggere i file scaricati da elenchi o raccolte.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233352"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Applicare Information Rights Management (IRM) a un elenco o a una raccolta

È possibile utilizzare Information Rights Management (IRM) per controllare e proteggere i file scaricati da elenchi o raccolte. Questa funzionalità è supportata solo nel cloud globale Microsoft. IRM non è supportato per gli elenchi e le raccolte di SharePoint nelle distribuzioni cloud nazionali.
  
## <a name="administrator-preparations-before-applying-irm"></a>Operazioni di preparazione dell'amministratore prima dell'applicazione di IRM

- Il servizio Azure Rights Management (Azure RMS) di Azure Information Protection e l'equivalente locale, Active Directory Rights Management Services (AD RMS), supportano Information Rights Management per i siti. Non sono necessarie installazioni separate o aggiuntive.

- Prima di applicare IRM a un elenco o a una raccolta, è necessario abilitare IRM per il sito. You'll need administrator permissions to enable IRM.

- Per applicare IRM a un elenco o a una raccolta, è necessario disporre delle autorizzazioni di amministratore per tale elenco o raccolta.

- Se si usa SharePoint Online, è possibile che si verifichino timeout durante il download di file protetti con IRM di dimensioni maggiori. Per evitare timeout, utilizzare le applicazioni di Office per applicare la protezione IRM e archiviare file di dimensioni maggiori in una raccolta di SharePoint che non utilizza IRM.

> [!NOTE]
> Se si utilizza SharePoint Server 2013, un amministratore del server deve installare le impostazioni di protezione in tutti i server Web front-end per ogni tipo di file che gli utenti dell'organizzazione desiderano proteggere tramite IRM.
  
## <a name="apply-irm-to-a-list-or-library"></a>Applicare IRM a un elenco o a una raccolta
<a name="__toc256598179"> </a>

![Impostazioni di Information Rights Management](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Passare all'elenco o alla raccolta per cui si desidera configurare IRM.

2. Sulla barra multifunzione selezionare la **scheda Raccolta** e quindi Selezionare **Impostazioni raccolta.** Se si sta lavorando in un elenco, selezionare la **scheda Elenco** e quindi selezionare **Impostazioni elenco.**
    
    ![Pulsanti Impostazioni raccolta SharePoint sulla barra multifunzione](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. In **Autorizzazioni e gestione** selezionare Information Rights **Management.** Se il collegamento Information Rights Management non viene visualizzato, È possibile che IRM non sia abilitato per il sito. Contattare l'amministratore del server per verificare se è possibile abilitare IRM per il sito. Il **collegamento Information Rights Management** non viene visualizzato per le raccolte immagini.

4. Nella pagina **Impostazioni Information Rights**  Management selezionare la casella di controllo Limita autorizzazioni per i documenti della raccolta al download per applicare autorizzazioni limitate ai documenti scaricati dagli utenti dall'elenco o dalla raccolta.

5. Nella casella **Crea un titolo per i criteri di** autorizzazione immettere un nome descrittivo per il criterio. Utilizzare un nome che consente di identificare questo criterio da altri criteri. Ad esempio, utilizzare **Company Confidential** per applicare autorizzazioni limitate a un elenco o a una raccolta contenente documenti aziendali riservati.

6. Nella casella **Aggiungi una descrizione dei** criteri di autorizzazione digitare una descrizione che verrà visualizzata agli utenti che utilizzano questo elenco o raccolta in cui viene spiegato come devono gestire i documenti nell'elenco o nella raccolta. È ad esempio possibile **digitare** Discuti il contenuto di questo documento solo con altri dipendenti se si desidera limitare l'accesso alle informazioni contenute in questi documenti ai dipendenti interni. 

7. Per applicare ulteriori restrizioni ai documenti di questo elenco o raccolta, selezionare **Mostra** opzioni ed eseguire una delle operazioni seguenti:

|**Per eseguire l'operazione:**|**Procedere come segue:**|
|:-----|:-----|
|Consenti agli utenti di stampare documenti da questo elenco o raccolta|Selezionare la **casella di controllo Consenti ai visualizzatori di** stampare.|
|Consentire agli utenti con almeno l'autorizzazione Visualizzazione elementi di eseguire macro o codice incorporato in un documento.|Selezionare la **casella di controllo Consenti ai visualizzatori di eseguire script e utilità per** la lettura dello schermo per funzionare sui documenti scaricati. Se si seleziona questa opzione, gli utenti potrebbero eseguire codice per estrarre il contenuto di un documento.           |
|Selezionare questa opzione se si desidera limitare l'accesso al contenuto a un periodo di tempo specificato. Se si seleziona questa opzione, le licenze di emissione degli utenti per accedere al contenuto scadranno dopo il numero di giorni specificato e agli utenti verrà richiesto di tornare al server per verificare le credenziali e scaricare una nuova copia.|Selezionare la casella di controllo Dopo il download, i diritti di accesso al documento scadranno dopo questi giorni **(1-365)** e quindi specificare il numero di giorni per cui si desidera che il documento sia visualizzabile.|
| Impedire agli utenti di caricare documenti che non supportano IRM in questo elenco o raccolta. Se si seleziona questa opzione, gli utenti non saranno in grado di caricare i tipi di file seguenti: tipi di file in cui non sono installate le corrispondenti programmi di protezione IRM in tutti i server Web front-end. Tipi di file che SharePoint Server 2010 non è in grado di decrittografare. Tipi di file protetti da IRM in un altro programma.|Selezionare la **casella di controllo Non consentire agli utenti di caricare documenti che non supportano IRM.**|
|Rimuovere le autorizzazioni limitate dall'elenco o dalla raccolta in una data specifica.|Selezionare la **casella di controllo Interrompi limitazione** accesso alla raccolta e quindi selezionare la data desiderata.|
|Controllare l'intervallo di memorizzazione nella cache delle credenziali per il programma concesso in licenza per l'apertura del documento.|Selezionare la casella di controllo Gli utenti devono verificare le credenziali utilizzando questo intervallo **(giorni),** quindi immettere l'intervallo per la memorizzazione delle credenziali nella cache in numero di giorni.|
|Consentire la protezione dei gruppi in modo che gli utenti possano condividere con i membri dello stesso gruppo.|Selezionare **Consenti protezione gruppo** e immettere il nome del gruppo per la condivisione.|

8. Dopo aver selezionato le opzioni desiderate, selezionare **OK.**
  
## <a name="what-is-information-rights-management"></a>Che cos'è Information Rights Management?
<a name="__toc256598175"> </a>

Information Rights Management (IRM) consente di limitare le azioni che gli utenti possono eseguire sui file scaricati da elenchi o raccolte. IRM consente di crittografare i file scaricati e limitare il gruppo di utenti e programmi autorizzati a decrittografare tali file. IRM può inoltre limitare i diritti degli utenti autorizzati a leggere i file, in modo che non possano eseguire azioni quali la stampa di copie dei file o la copia di testo da essi.
  
È possibile utilizzare IRM per elenchi o raccolte per limitare la diffusione di contenuto sensibile. Ad esempio, se si sta creando una raccolta documenti per condividere informazioni sui prodotti futuri con alcuni rappresentanti di marketing selezionati, è possibile utilizzare IRM per impedire a questi utenti di condividere questo contenuto con altri dipendenti dell'azienda.
  
In un sito, IRM viene applicato a un intero elenco o a un'intera raccolta anziché a singoli file. In questo modo è più semplice garantire un livello di protezione coerente per un intero set di documenti o file. IRM può pertanto aiutare l'organizzazione ad applicare criteri aziendali che regolano l'uso e la diffusione di informazioni riservate o proprietarie.
  
> [!NOTE]
> Le informazioni contenute in questa pagina relative a Information Rights Management hanno la priorità su tutti i termini che fanno riferimento a "Information Rights Management" nei contratti di licenza di Microsoft SharePoint Server 2013 e SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Come IRM consente di proteggere il contenuto
<a name="__toc256598176"> </a>

IRM consente di proteggere il contenuto con restrizioni nei modi seguenti:
  
- Consente di impedire a un visualizzatore autorizzato di copiare, modificare, stampare, inviare fax o copiare e incollare il contenuto per uso non autorizzato
    
- Consente di impedire a un visualizzatore autorizzato di copiare il contenuto utilizzando la funzionalità Stampa schermo in Microsoft Windows
    
- Consente di impedire a un visualizzatore non autorizzato di visualizzare il contenuto se viene inviato tramite posta elettronica dopo il download dal server
    
- Limita l'accesso al contenuto a un periodo di tempo specificato, dopo il quale gli utenti devono confermare le credenziali e scaricare di nuovo il contenuto
    
- Consente di applicare criteri aziendali che regolano l'uso e la diffusione di contenuti all'interno dell'organizzazione
    
### <a name="how-irm-cannot-help-protect-content"></a>Come IRM non è in grado di proteggere il contenuto
<a name="__toc256598177"> </a>

IRM non è in grado di proteggere il contenuto con restrizioni dagli elementi seguenti:
  
- Cancellazione, furto, acquisizione o trasmissione da parte di programmi dannosi come trojan horse, keystroke logger e alcuni tipi di spyware
    
- Perdita o danneggiamento a causa delle azioni dei virus del computer
    
- Copia manuale o ridenotipo del contenuto dallo schermo
    
- Fotografia digitale o su film del contenuto visualizzato su uno schermo
    
- Copia tramite l'uso di programmi di acquisizione schermo di terze parti
    
- Copia dei metadati del contenuto (valori delle colonne) tramite l'uso di programmi di acquisizione schermo di terze parti o azione di copia e incolla
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Funzionamento di IRM per elenchi e raccolte
<a name="__toc256598178"> </a>

La protezione IRM viene applicata ai file a livello di elenco o di raccolta. Quando IRM è abilitato per una raccolta, la gestione dei diritti si applica a tutti i file in tale raccolta. Quando IRM è abilitato per un elenco, la gestione dei diritti si applica solo ai file allegati alle voci di elenco e non alle voci di elenco effettive.
  
Quando gli utenti scaricano file in un elenco o in una raccolta abilitata per IRM, i file vengono crittografati in modo che solo gli utenti autorizzati possano visualizzarli. Ogni file rights-managed contiene anche una licenza di pubblicazione che impone restrizioni alle persone che visualizzano il file. Le restrizioni tipiche includono la possibilità di rendere un file di sola lettura, disabilitare la copia del testo, impedire agli utenti di salvare una copia locale e impedire agli utenti di stampare il file. I programmi client in grado di leggere i tipi di file supportati da IRM utilizzano la licenza di pubblicazione all'interno del file protetto da Rights Management per applicare queste restrizioni. In questo modo un file rights-managed mantiene la protezione anche dopo essere stato scaricato dal server.
  
I tipi di restrizioni applicati a un file quando viene scaricato da un elenco o da una raccolta si basano sulle autorizzazioni del singolo utente nel sito che contiene il file. Nella tabella seguente viene illustrato in che modo le autorizzazioni per i siti corrispondono alle autorizzazioni IRM.
  
|**Autorizzazioni**|**Autorizzazioni IRM**|
|:-----|:-----|
|Gestione autorizzazioni, Gestione sito Web|**Controllo completo** (come definito dal programma client): questa autorizzazione consente in genere a un utente di leggere, modificare, copiare, salvare e modificare le autorizzazioni del contenuto protetto.|
|Modifica elementi, Gestione elenchi, Aggiunta e personalizzazione pagine|**Modifica,** **Copia** e **Salva:** un utente può  stampare un file solo se la casella di controllo Consenti agli utenti di stampare documenti è selezionata nella pagina Impostazioni Information Rights Management per l'elenco o la raccolta.|
|Visualizzazione elementi|**Lettura:** un utente può leggere il documento, ma non può copiarne o modificarne il contenuto. Un utente può stampare  solo se la casella di controllo Consenti agli utenti di stampare documenti è selezionata nella pagina Impostazioni Information Rights Management per l'elenco o la raccolta.|
|Altro|Nessuna altra autorizzazione corrisponde direttamente alle autorizzazioni IRM.|
   
Quando si abilita IRM per un elenco o una raccolta in SharePoint Server 2013, è possibile proteggere solo i tipi di file in tale elenco o raccolta per cui è installata una protezione in tutti i server Web front-end. Una protezione è un programma che controlla la crittografia e la decrittografia dei file rights-managed di un formato di file specifico. SharePoint include strumenti di protezione per i tipi di file seguenti:
  
- Microsoft Office infopath
    
- Formati di file della versione 97-2003 per i Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formati Office Open XML per i programmi Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formato XPS (XML Paper Specification)
    
Se l'organizzazione prevede di utilizzare IRM per proteggere altri tipi di file oltre a quelli elencati in precedenza, l'amministratore del server deve installare le impostazioni di protezione per questi formati di file aggiuntivi.
  

