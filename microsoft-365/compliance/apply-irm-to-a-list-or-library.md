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

È possibile utilizzare Information Rights Management (IRM) per controllare e proteggere i file scaricati da elenchi o raccolte. Questa funzionalità è supportata solo nel cloud globale Microsoft. IRM non è supportato per SharePoint e raccolte nelle distribuzioni cloud nazionali.
  
## <a name="administrator-preparations-before-applying-irm"></a>Preparazione dell'amministratore prima di applicare IRM

- Il servizio Azure Rights Management (Azure RMS) di Azure Information Protection e l'equivalente locale, Active Directory Rights Management Services (AD RMS), supportano Information Rights Management per i siti. Non sono necessarie installazioni separate o aggiuntive.

- Prima di applicare IRM a un elenco o a una raccolta, è necessario abilitare IRM per il sito. Per abilitare IRM, sono necessarie le autorizzazioni di amministratore.

- Per applicare IRM a un elenco o a una raccolta, è necessario disporre delle autorizzazioni di amministratore per tale elenco o raccolta.

- Se si usa SharePoint Online, è possibile che si verifichino timeout durante il download di file protetti da IRM di grandi dimensioni. Per evitare timeout, utilizzare i programmi Office per applicare la protezione IRM e archiviare file di dimensioni maggiori in una raccolta SharePoint che non utilizza IRM.

> [!NOTE]
> Se si utilizza SharePoint Server 2013, un amministratore del server deve installare le protezione in tutti i server Web front-end per ogni tipo di file che gli utenti dell'organizzazione desiderano proteggere tramite IRM.
  
## <a name="apply-irm-to-a-list-or-library"></a>Applicare IRM a un elenco o a una raccolta
<a name="__toc256598179"> </a>

![Information Rights Management Impostazioni](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Passare all'elenco o alla raccolta per cui si desidera configurare IRM.

2. Sulla barra multifunzione selezionare la **scheda Raccolta** e quindi selezionare Raccolta **Impostazioni**. Se si sta lavorando in un elenco, selezionare la **scheda Elenco** e quindi selezionare Elenco **Impostazioni**).
    
    ![SharePoint Pulsanti Impostazioni raccolta sulla barra multifunzione](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. In **Autorizzazioni e gestione** selezionare Information Rights **Management.** Se il collegamento Information Rights Management non viene visualizzato, È possibile che IRM non sia abilitato per il sito. Contattare l'amministratore del server per verificare se è possibile abilitare IRM per il sito. Il **collegamento Information Rights Management** non viene visualizzato per le raccolte immagini.

4. Nella pagina **Information Rights Management Impostazioni** selezionare  la casella di controllo Limita l'autorizzazione ai documenti in questa raccolta al download per applicare autorizzazioni limitate ai documenti scaricati dagli utenti da questo elenco o raccolta.

5. Nella casella **Crea un titolo del criterio di** autorizzazione immettere un nome descrittivo per il criterio. Utilizzare un nome che consente di identificare questo criterio da altri criteri. Ad esempio, utilizzare **Company Confidential** per applicare autorizzazioni limitate a un elenco o a una raccolta contenente documenti aziendali riservati.

6. Nella casella **Aggiungi una descrizione dei** criteri di autorizzazione digitare una descrizione che verrà visualizzata agli utenti che utilizzano l'elenco o la raccolta che spiega come devono gestire i documenti in questo elenco o raccolta. Ad esempio, è possibile digitare **Discutere** il contenuto del documento solo con altri dipendenti se si desidera limitare l'accesso alle informazioni contenute in questi documenti ai dipendenti interni. 

7. Per applicare ulteriori restrizioni ai documenti di questo elenco o raccolta, selezionare **Mostra** opzioni ed eseguire una delle operazioni seguenti:

|**Per eseguire l'operazione:**|**Procedere come segue:**|
|:-----|:-----|
|Consenti agli utenti di stampare documenti da questo elenco o raccolta|Selezionare la **casella di controllo Consenti ai visualizzatori** di stampare.|
|Consentire agli utenti con almeno l'autorizzazione Visualizza elementi di eseguire codice incorporato o macro in un documento.|Selezionare la **casella di controllo Consenti ai visualizzatori di eseguire script e utilità per** la lettura dello schermo per funzionare nei documenti scaricati. Se si seleziona questa opzione, gli utenti potrebbero eseguire codice per estrarre il contenuto di un documento.           |
|Selezionare questa opzione se si desidera limitare l'accesso al contenuto a un periodo di tempo specificato. Se si seleziona questa opzione, le licenze di rilascio degli utenti per accedere al contenuto scadranno dopo il numero di giorni specificato e gli utenti doranno tornare al server per verificare le proprie credenziali e scaricare una nuova copia.|Selezionare la casella di controllo Dopo il download, i diritti di accesso al documento scadranno dopo questo numero di giorni **(1-365)** e quindi specificare il numero di giorni per cui si desidera che il documento sia visualizzabile.|
| Impedire agli utenti di caricare documenti che non supportano IRM in questo elenco o raccolta. Se si seleziona questa opzione, gli utenti non saranno in grado di caricare i tipi di file seguenti: tipi di file per i quali non sono installate le corrispondenti protettori IRM in tutti i server Web front-end. I tipi di file SharePoint Server 2010 non possono decrittografare. Tipi di file protetti tramite IRM in un altro programma.|Selezionare la casella di controllo Non consentire agli utenti di caricare documenti **che non supportano IRM.**|
|Rimuovere le autorizzazioni limitate dall'elenco o dalla raccolta in una data specifica.|Selezionare la **casella di controllo Interrompi limitazione** accesso alla raccolta in corrispondenza e quindi selezionare la data desiderata.|
|Controlla l'intervallo di memorizzazione delle credenziali nella cache per il programma concesso in licenza per aprire il documento.|Selezionare la casella di controllo Gli utenti devono verificare le proprie credenziali utilizzando questo intervallo **(giorni),** quindi immettere l'intervallo per la memorizzazione delle credenziali nella cache in numero di giorni.|
|Consentire la protezione dei gruppi in modo che gli utenti possano condividerli con i membri dello stesso gruppo.|Selezionare **Consenti protezione gruppo** e immettere il nome del gruppo per la condivisione.|

8. Dopo aver selezionato le opzioni desiderate, selezionare **OK.**
  
## <a name="what-is-information-rights-management"></a>Che cos'è Information Rights Management?
<a name="__toc256598175"> </a>

Information Rights Management (IRM) consente di limitare le azioni che gli utenti possono eseguire sui file scaricati da elenchi o raccolte. IRM consente di crittografare i file scaricati e limitare il gruppo di utenti e programmi autorizzati a decrittografare tali file. IRM può inoltre limitare i diritti degli utenti a cui è consentito leggere i file, in modo che non possano eseguire azioni quali la stampa di copie dei file o la copia di testo da essi.
  
È possibile utilizzare IRM in elenchi o raccolte per limitare la diffusione di contenuto sensibile. Ad esempio, se si sta creando una raccolta documenti per condividere informazioni sui prodotti futuri con rappresentanti di marketing selezionati, è possibile utilizzare IRM per impedire a questi utenti di condividere questo contenuto con altri dipendenti della società.
  
In un sito si applica IRM a un intero elenco o raccolta anziché a singoli file. In questo modo è più semplice garantire un livello di protezione coerente per un intero set di documenti o file. IRM può pertanto aiutare l'organizzazione a applicare criteri aziendali che regolano l'uso e la diffusione di informazioni riservate o proprietarie.
  
> [!NOTE]
> Le informazioni contenute in questa pagina relative a Information Rights Management sostituisce qualsiasi termine che fa riferimento a "Information Rights Management" in qualsiasi contratto di licenza di Microsoft SharePoint Server 2013 e SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Come IRM può aiutare a proteggere il contenuto
<a name="__toc256598176"> </a>

IRM consente di proteggere il contenuto con restrizioni nei modi seguenti:
  
- Consente di impedire a un visualizzatore autorizzato di copiare, modificare, stampare, inviare fax o copiare e incollare il contenuto per uso non autorizzato
    
- Aiuta a impedire a un visualizzatore autorizzato di copiare il contenuto utilizzando la funzionalità Schermo di stampa in Microsoft Windows
    
- Consente di impedire a un visualizzatore non autorizzato di visualizzare il contenuto se viene inviato tramite posta elettronica dopo il download dal server
    
- Limita l'accesso al contenuto a un periodo di tempo specificato, dopo il quale gli utenti devono confermare le credenziali e scaricare di nuovo il contenuto
    
- Consente di applicare criteri aziendali che regolano l'utilizzo e la diffusione del contenuto all'interno dell'organizzazione
    
### <a name="how-irm-cannot-help-protect-content"></a>Come IRM non è in grado di proteggere il contenuto
<a name="__toc256598177"> </a>

IRM non è in grado di proteggere il contenuto con restrizioni dagli elementi seguenti:
  
- Cancellazione, furto, acquisizione o trasmissione da parte di programmi dannosi come trojan horse, keystroke logger e determinati tipi di spyware
    
- Perdita o danneggiamento a causa delle azioni di virus informatici
    
- Copia manuale o ridenotipo del contenuto dallo schermo
    
- Fotografia digitale o cinematografica del contenuto visualizzato su uno schermo
    
- Copia tramite l'uso di programmi di acquisizione dello schermo di terze parti
    
- Copia dei metadati del contenuto (valori di colonna) tramite l'uso di programmi di acquisizione schermo di terze parti o azioni di copia e incolla
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Funzionamento di IRM per elenchi e raccolte
<a name="__toc256598178"> </a>

La protezione IRM viene applicata ai file a livello di elenco o di raccolta. Quando IRM è abilitato per una raccolta, rights management si applica a tutti i file in tale raccolta. Quando IRM è abilitato per un elenco, rights management si applica solo ai file allegati alle voci di elenco, non alle voci di elenco effettive.
  
Quando gli utenti scaricano file in un elenco o una raccolta abilitata per IRM, i file vengono crittografati in modo che solo gli utenti autorizzati possano visualizzarli. Ogni file rights-managed contiene anche una licenza di rilascio che impone restrizioni alle persone che visualizzano il file. Le restrizioni tipiche includono la creazione di un file di sola lettura, la disabilitazione della copia del testo, l'impedimento del salvataggio di una copia locale e la stampa del file da parte degli utenti. I programmi client in grado di leggere i tipi di file supportati da IRM utilizzano la licenza di rilascio all'interno del file rights-managed per applicare queste restrizioni. Questo è il modo in cui un file rights-managed mantiene la protezione anche dopo essere stato scaricato dal server.
  
I tipi di restrizioni applicati a un file quando viene scaricato da un elenco o da una raccolta si basano sulle autorizzazioni del singolo utente nel sito che contiene il file. Nella tabella seguente viene illustrato come le autorizzazioni per i siti corrispondono alle autorizzazioni IRM.
  
|**Autorizzazioni**|**Autorizzazioni IRM**|
|:-----|:-----|
|Gestire le autorizzazioni, gestire il sito Web|**Controllo completo** (come definito dal programma client): questa autorizzazione in genere consente a un utente di leggere, modificare, copiare, salvare e modificare le autorizzazioni del contenuto protetto.|
|Modifica elementi, gestione elenchi, aggiunta e personalizzazione di pagine|**Modifica**, **Copia** e Salva **:** un utente  può stampare un file solo se la casella di controllo Consenti agli utenti di stampare documenti è selezionata nella pagina Information Rights Management Impostazioni per l'elenco o la raccolta.|
|Visualizzazione elementi|**Lettura**: un utente può leggere il documento, ma non può copiarne o modificarne il contenuto. Un utente può stampare  solo se la casella di controllo Consenti agli utenti di stampare documenti è selezionata nella pagina Information Rights Management Impostazioni per l'elenco o la raccolta.|
|Altro|Nessun'altra autorizzazione corrisponde direttamente alle autorizzazioni IRM.|
   
Quando si abilita IRM per un elenco o una raccolta in SharePoint Server 2013, è possibile proteggere solo i tipi di file nell'elenco o nella raccolta per cui è installata una protezione in tutti i server Web front-end. Una protezione è un programma che controlla la crittografia e la decrittografia dei file gestiti da Rights Managed di un formato di file specifico. SharePoint include protettori per i tipi di file seguenti:
  
- Microsoft Office Moduli di InfoPath
    
- I formati di file 97-2003 per i programmi Microsoft Office seguenti: Word, Excel e PowerPoint
    
- I Office Open XML per i Microsoft Office seguenti: Word, Excel e PowerPoint
    
- Formato XPS (XML Paper Specification)
    
Se l'organizzazione prevede di utilizzare IRM per proteggere altri tipi di file oltre a quelli elencati in precedenza, l'amministratore del server deve installare le protezione per questi formati di file aggiuntivi.
  

