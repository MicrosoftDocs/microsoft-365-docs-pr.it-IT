---
title: Create a DLP policy from a template
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 'Il modo più facile e più diffuso per iniziare a utilizzare i criteri DLP consiste nel servirsi dei modelli inclusi in Office 365. '
ms.openlocfilehash: 2f7618f80f02865816a1f937b36c9f09b794b77d
ms.sourcegitcommit: 8ad30e6c5cd77a72e5c1ce463c9f693132cc0b15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "38686342"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Creazione di un criterio DLP da un modello

Il modo più facile e più diffuso per iniziare a utilizzare i criteri DLP consiste nel servirsi dei modelli inclusi in Office 365. È possibile utilizzare uno di questi modelli come è o personalizzare le regole per soddisfare i requisiti di conformità specifici dell'organizzazione.
  
In Office 365 sono disponibili più di 40 modelli pronti all'uso che consentono di soddisfare una vasta gamma di comuni necessità normative e aziendali. Ad esempio, esistono modelli di criteri DLP per:
  
- Gramm-Leach-Bliley Act (GLBA)
    
- Payment Card Industry Data Security Standard (PCI-DSS)
    
- United States Personally Identifiable Information (U.S. PII)
    
- United States Health Insurance Act (HIPAA)
    
È possibile ottimizzare un modello modificando alcune delle regole esistenti oppure aggiungendone di nuove. Ad esempio, è possibile aggiungere nuovi tipi di informazioni riservate a una regola, modificare i conteggi in una regola per renderne più difficile o più facile l'attivazione, consentire agli utenti di eseguire l'override delle azioni in una regola fornendo una motivazione aziendale oppure modificare i destinatari delle notifiche e dei rapporti sulle operazioni non consentite. Un modello di criteri DLP è un punto di partenza adatto a molti scenari di conformità comuni.
  
È inoltre possibile scegliere il modello personalizzato (che non dispone di regole predefinite) e configurare il criterio DLP da zero, per rispondere ai requisiti di conformità specifici dell'organizzazione.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Esempio: identificare informazioni riservate in tutti i siti di OneDrive for business e limitare l'accesso per gli utenti esterni all'organizzazione

Gli account di OneDrive for business facilitano la collaborazione e la condivisione dei documenti da parte di utenti dell'organizzazione. Tuttavia, una preoccupazione comune per i responsabili della conformità è che le informazioni riservate archiviate negli account di OneDrive for business possono essere condivise inavvertitamente con persone esterne all'organizzazione. Un criterio DLP potrebbe ridurre questo rischio.
  
In questo esempio, verrà creato un criterio DLP che identifica i dati delle informazioni personali degli Stati Uniti, che include i numeri di identificazione dei contribuenti individuali, i numeri di previdenza sociale e i numeri di passaporto degli Stati Uniti. Per iniziare, è possibile utilizzare un modello e quindi modificare il modello per soddisfare i requisiti di conformità dell'organizzazione, in particolare:
  
- Aggiungere un paio di tipi di informazioni riservate, ovvero numeri di conto corrente bancario e numeri di licenza degli Stati Uniti, in modo che il criterio DLP protegga ancora di più i dati sensibili.
    
- Rendere il criterio più sensibile, in modo che una singola occorrenza di informazioni riservate sia sufficiente per limitare l'accesso per gli utenti esterni.
    
- Si consentirà agli utenti di eseguire l'override delle azioni fornendo una motivazione aziendale o segnalando un falso positivo. In questo modo, i criteri DLP non impediscono agli utenti dell'organizzazione di svolgere il proprio lavoro, purché dispongano di un motivo aziendale valido per la condivisione delle informazioni riservate.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Creazione di un criterio DLP da un modello

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione. Si è ora nel centro sicurezza &amp; e conformità di Office 365.
    
3. Nel &amp; centro \> sicurezza e conformità left navigation \> **policy** \> di prevenzione \> della **perdita dei dati** **+ creare un criterio**.
    
    ![Pulsante Crea un criterio](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Scegliere il modello di criteri DLP che protegge i tipi di informazioni riservate necessarie \> **successivamente**.
    
    In questo esempio, si selezionerà la **privacy** \> **degli Stati Uniti informazioni di identificazione personale (PII)** , perché include già la maggior parte dei tipi di informazioni riservate che si desidera proteggere, aggiungere una coppia in un secondo momento. 
    
    Quando si seleziona un modello, è possibile leggere la descrizione sul lato destro per sapere quali tipi di informazioni riservate protegge il modello.
    
    ![Pagina per la scelta di un modello di criteri DLP](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Denominare \> il criterio **successivo**.
    
6. Per scegliere i percorsi che si desidera proteggere dal criterio DLP, effettuare una delle seguenti operazioni:
    
  - Scegliere **tutte le posizioni in Office 365** \> **Avanti**.
    
  - Scegliere **Consenti di scegliere le posizioni** \> specifiche **successive**. Per questo esempio, scegliere questo.
    
    Per includere o escludere un'intera posizione, ad esempio tutti i messaggi di posta elettronica di Exchange o tutti gli account di OneDrive, attivare o disattivare lo **stato** di tale percorso. 
    
    Per includere solo i siti di SharePoint specifici o gli account di OneDrive for business, impostare lo **stato** su attivato e quindi fare clic sui collegamenti in **Includi** per scegliere i siti o gli account specifici. Quando si applica un criterio a un sito, le regole configurate in tale criterio vengono applicate automaticamente a tutti i siti secondari del sito. 
    
    ![Opzioni per la posizione in cui è possibile applicare un criterio DLP](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    In questo esempio, per proteggere le informazioni riservate archiviate in tutti gli account di OneDrive for business, disattivare lo **stato** sia per la **posta elettronica di Exchange** che per i **siti di SharePoint**e lasciare lo **stato** su per gli **account di OneDrive**.
    
7. Scegliere **Usa impostazioni** \> avanzate **successive**.
    
8. Un modello di criteri DLP contiene regole predefinite con condizioni e azioni che rilevano e agiscono su tipi specifici di informazioni riservate. È possibile modificare, eliminare o disabilitare una o più delle regole esistenti oppure aggiungerne di nuove. Al termine, fare clic su **Avanti**.
    
    ![Regole espanse nel modello di criteri di PII Stati Uniti](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    In questo esempio, il modello di dati delle informazioni personali degli Stati Uniti include due regole predefinite:
    
  - **Volume basso del contenuto rilevato informazioni personali degli Stati Uniti** Questa regola consente di cercare i file che contengono tra 1 e 10 occorrenze di ognuno dei tre tipi di informazioni riservate (it, SSN e numeri di passaporto degli Stati Uniti), in cui i file vengono condivisi con utenti esterni all'organizzazione. Se si trova, la regola invierà una notifica tramite posta elettronica all'amministratore principale della raccolta siti, al proprietario del documento e alla persona che ha modificato il documento. 
    
  - **Volume elevato del contenuto rilevato informazioni personali degli Stati Uniti** Questa regola cerca i file che contengono 10 o più occorrenze di ognuno degli stessi tre tipi di informazioni riservate, in cui i file vengono condivisi con utenti esterni all'organizzazione. Se si trova, questa azione invierà anche una notifica di posta elettronica, oltre a limitare l'accesso al file. Per il contenuto in un account di OneDrive for business, le autorizzazioni per il documento sono limitate per tutti, tranne l'amministratore principale della raccolta siti, il proprietario del documento e l'ultima persona che ha modificato il documento. 
    
    Per soddisfare i requisiti specifici dell'organizzazione, è consigliabile rendere più semplice l'attivazione delle regole, in modo che una singola occorrenza di informazioni riservate sia sufficiente per bloccare l'accesso per gli utenti esterni. Dopo aver analizzato queste regole, è necessario capire che non sono necessarie regole di conteggio basso e alto, ma è necessaria una sola regola che blocchi l'accesso se viene trovata una qualsiasi occorrenza di informazioni riservate.
    
    In questo modo si espande la regola denominata **low volume of content detected US pii** \> **delete rule**.
    
    ![Pulsante Elimina regola](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. Ora, in questo esempio, è necessario aggiungere due tipi di informazioni riservate (numeri di conto corrente bancario statunitense e numeri di licenza degli Stati Uniti), consentire agli utenti di ignorare una regola e modificare il conteggio in qualsiasi occorrenza. È possibile eseguire tutte queste modifiche modificando una regola, quindi selezionare un \> **volume elevato di contenuto rilevato dalla regola di modifica delle informazioni personali degli Stati Uniti** . ****
    
    ![Pulsante Modifica regola](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Per aggiungere un tipo di informazioni riservate, **** nella sezione \> condizioni **aggiungere o modificare i tipi**. Quindi, in **Aggiungi o modifica tipi** \> scegliere **Aggiungi** \> selezionare **il numero di conto corrente bancario statunitense** e **il numero** \> della patente di guida statunitense **Aggiungi** \> **completato**.
    
    ![Opzione per aggiungere o modificare i tipi](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Riquadro dei tipi di aggiunta o modifica](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Per modificare il conteggio, ovvero il numero di istanze di informazioni riservate necessarie per attivare la regola, in **conteggio** \> istanze scegliere il valore **minimo** per ogni \> tipo immettere 1. Il numero minimo non può essere vuoto. Il numero massimo può essere vuoto. valore **massimo** vuoto convertito in **any**.
    
    Al termine, il conteggio minimo per tutti i tipi di informazioni riservate deve essere **1** e il numero massimo dovrebbe essere **qualsiasi**. In altre parole, qualsiasi occorrenza di questo tipo di informazioni riservate soddisferà questa condizione.
    
    ![Conteggi di istanze per i tipi di informazioni riservate](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Per la personalizzazione finale, non si desidera che i criteri DLP impediscono agli utenti di eseguire il proprio lavoro quando hanno una giustificazione aziendale valida o si verificano un falso positivo, quindi si desidera che la notifica dell'utente includa opzioni per ignorare l'azione di blocco.
    
    Nella sezione **notifiche utente** , è possibile vedere che le notifiche di posta elettronica e i suggerimenti per i criteri sono attivati per impostazione predefinita per questa regola nel modello. 
    
    Nella sezione **override dell'utente** , è possibile vedere che le sostituzioni per una giustificazione aziendale sono attivate, ma le sostituzioni per segnalare falsi positivi non lo sono. Scegliere **Sostituisci automaticamente la regola se lo segnalano come falso positivo**.
    
    ![Sezione delle notifiche degli utenti e delle sostituzioni degli utenti](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Nella parte superiore dell'editor delle regole cambiare il nome di questa regola dall' **alto volume predefinito di contenuto delle informazioni personali rilevate dagli Stati Uniti** a **qualsiasi contenuto rilevato con i dati personali degli Stati Uniti** , in quanto è ora attivato da qualsiasi occorrenza dei relativi tipi di informazione sensibili. 
    
14. Nella parte inferiore dell'editor \> delle regole **salvare**.
    
15. Esaminare le condizioni e le azioni per la \> regola **successive**.
    
    A destra, notare l'opzione di **stato** per la regola. Se si disattiva un intero criterio, tutte le regole incluse nel criterio sono disattivate. Tuttavia, è possibile disattivare una regola specifica senza disattivare l'intero criterio. Questo può essere utile nei casi in cui è necessario esaminare una regola che genera un gran numero di falsi positivi. 
    
16. Nella pagina successiva leggere e comprendere quanto segue, quindi scegliere se accendere la regola o \> testarla **prima.**
    
     Prima di aver creato i criteri DLP, è necessario distribuirli gradualmente per valutarne l'impatto e l'efficacia, prima di applicarli completamente. Ad esempio, non si desidera che un nuovo criterio DLP involontariamente blocca l'accesso a migliaia di documenti necessari per ottenere il proprio lavoro. 
    
    Se si stanno creando criteri DLP con un impatto potenziale elevato, è consigliabile seguire questa sequenza:
    
17. Iniziare in modalità test senza suggerimenti per i criteri, quindi utilizzare i report DLP per valutare l'impatto. È possibile utilizzare i report DLP per visualizzare il numero, il percorso, il tipo e la gravità di corrispondenza del criterio. A seconda dei risultati, è possibile ottimizzare le regole in modo adeguato. In modalità test, i criteri DLP non avranno effetto sulla produttività degli utenti dell'organizzazione. 
    
18. Passare alla modalità test con notifiche e suggerimenti per i criteri in modo da istruire gli utenti in merito ai criteri di conformità e prepararli all'applicazione delle regole. In questa fase, è inoltre possibile chiedere agli utenti di segnalare i falsi positivi per definire ulteriormente le regole.
    
19. Attiva i criteri in modo che le regole vengano applicate e il contenuto sia protetto. Continuare a eseguire il monitoraggio dei report DLP e di eventuali eventi imprevisti oppure delle notifiche per essere certi di ottenere i risultati desiderati. 
    
    ![Opzioni per l'utilizzo della modalità di test e dell'attivazione dei criteri](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Esaminare le impostazioni per questo criterio \> scegliere **Crea**.
    
Dopo aver creato e attivato un criterio DLP, viene distribuito in tutte le origini di contenuto che include, ad esempio i siti di SharePoint Online o gli account di OneDrive for business, in cui il criterio inizia automaticamente a applicare le regole su tale contenuto.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Visualizzare lo stato di un criterio DLP

In qualsiasi momento, è possibile visualizzare lo stato dei criteri DLP nella pagina **criteri** nella sezione **prevenzione perdita di dati** del Centro sicurezza &amp; e conformità. In questa pagina sono disponibili informazioni importanti, ad esempio se un criterio è stato correttamente attivato o disattivato oppure se il criterio è in modalità test. 
  
Di seguito sono riportati i diversi stati e il loro significato.
  
|**Stato**|**Spiegazione**|
|:-----|:-----|
|**Attivazione in corso...** <br/> |Il criterio viene distribuito alle origini del contenuto che include. Il criterio non è ancora applicato su tutte le origini.  <br/> |
|**Test, con notifiche** <br/> |Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio vengono inviate ai destinatari specificati.  <br/> |
|**Test, senza notifiche** <br/> |Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio non vengono inviate ai destinatari specificati.  <br/> |
|**Attivato** <br/> |Il criterio è attivo e applicato. Il criterio è stato distribuito correttamente a tutte le origini del contenuto.  <br/> |
|**Disattivazione in corso...** <br/> |Il criterio viene rimosso dalle origini del contenuto che include. Il criterio potrebbe essere ancora attivo e applicato in alcune origini. La disattivazione di un criterio potrebbe richiedere fino a 45 minuti.  <br/> |
|**Disattivato** <br/> |Il criterio non è attivo e non applicato. Le impostazioni del criterio (origini, parole chiave, durata e così via) vengono salvate.  <br/> |
|**Eliminazione di...** <br/> |Il criterio è in corso di eliminazione. Il criterio non è attivo e non applicato. Per i criteri delet richiede di solito un'ora <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Disattivare un criterio DLP

È possibile modificare o disattivare un criterio DLP in qualsiasi momento. La disattivazione di un criterio Disattiva tutte le regole del criterio.
  
Per modificare o disabilitare un criterio DLP, nella pagina \> **criterio** selezionare il criterio di modifica dei criteri. **** \>
  
![Pulsante Modifica criterio](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Inoltre, è possibile disattivare singolarmente ogni regola modificando il criterio e quindi disattivando lo **stato** di tale regola, come descritto in alto. 
  
## <a name="more-information"></a>Ulteriori informazioni

- [Panoramica relativa ai criteri di prevenzione della perdita di dati](data-loss-prevention-policies.md)
    
- [Inviare notifiche e visualizzare i suggerimenti per i criteri DLP](use-notifications-and-policy-tips.md)
    
- [Creare un criterio di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà](protect-documents-that-have-fci-or-other-properties.md)
    
- [Elementi inclusi nei modelli di criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
    
- [Inventario di tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md)
    

