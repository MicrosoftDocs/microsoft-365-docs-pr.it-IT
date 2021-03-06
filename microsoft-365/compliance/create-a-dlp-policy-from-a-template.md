---
title: Create a DLP policy from a template
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-mar2020
description: In questo articolo viene illustrato come creare criteri DLP utilizzando uno dei modelli inclusi in Office 365.
ms.openlocfilehash: 0088381698b47b2451f52fde32716a2436e8c073
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113968"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Creare criteri di prevenzione della perdita dei dati da un modello

Il modo più facile e più diffuso per iniziare a utilizzare i criteri DLP consiste nel servirsi dei modelli inclusi in Office 365. È possibile utilizzare uno di questi modelli così come sono oppure personalizzare le regole per soddisfare i requisiti di conformità specifici dell'organizzazione.
  
Microsoft 365 include oltre 40 modelli pronti all'uso che consentono di soddisfare un'ampia gamma di esigenze normative e di criteri aziendali comuni. Ad esempio, esistono modelli di criteri DLP per:
  
- Gramm-Leach-Bliley Act (GLBA)
    
- Payment Card Industry Data Security Standard (PCI-DSS)
    
- United States Personally Identifiable Information (U.S. PII)
    
- United States Health Insurance Act (HIPAA)
    
È possibile ottimizzare un modello modificando alcune delle regole esistenti oppure aggiungendone di nuove. Ad esempio, è possibile aggiungere nuovi tipi di informazioni riservate a una regola, modificare i conteggi in una regola per renderne più difficile o più facile l'attivazione, consentire agli utenti di eseguire l'override delle azioni in una regola fornendo una motivazione aziendale oppure modificare i destinatari delle notifiche e dei rapporti sulle operazioni non consentite. Un modello di criteri DLP è un punto di partenza adatto a molti scenari di conformità comuni.
  
È inoltre possibile scegliere il modello personalizzato (che non dispone di regole predefinite) e configurare il criterio DLP da zero, per rispondere ai requisiti di conformità specifici dell'organizzazione.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Esempio: identificare le informazioni riservate in tutti i siti OneDrive for Business e limitare l'accesso per le persone esterne all'organizzazione

OneDrive for Business consente agli utenti dell'organizzazione di collaborare e condividere documenti in modo semplice. Tuttavia, un problema comune per i responsabili della conformità è che le informazioni riservate archiviate negli account OneDrive for Business possono essere inavvertitamente condivise con persone esterne all'organizzazione. Un criterio DLP potrebbe ridurre questo rischio.
  
In questo esempio verrà creato un criterio DLP che identifica i dati delle informazioni personali degli Stati Uniti, che includono i numeri di identificazione dei singoli contribuenti (ITIN), i numeri di previdenza sociale e i numeri di passaporto degli Stati Uniti. Inizierai a usare un modello e quindi modificherai il modello per soddisfare i requisiti di conformità dell'organizzazione, in particolare:
  
- Aggiungere un paio di tipi di informazioni riservate, ovvero numeri di conto corrente bancario e numeri di patente di guida statunitensi, in modo che il criterio DLP protegga ancora di più i dati sensibili.
    
- Rendere il criterio più sensibile, in modo che una singola occorrenza di informazioni riservate sia sufficiente per limitare l'accesso per gli utenti esterni.
    
- Si consentirà agli utenti di eseguire l'override delle azioni fornendo una motivazione aziendale o segnalando un falso positivo. In questo modo, il criterio DLP non impedirà agli utenti dell'organizzazione di lavorare, purché abbia un valido motivo aziendale per condividere le informazioni riservate.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Creare criteri di prevenzione della perdita dei dati da un modello

1. Passare a [https://protection.office.com](https://protection.office.com).
    
2. Accedere usando l'account di lavoro o della scuola. Si è ora nel Centro &amp; sicurezza e conformità.
    
3. Nel riquadro di spostamento a sinistra del Centro sicurezza e conformità Criteri di prevenzione della &amp; \> \> **perdita** \>  \> **dei dati + Crea un criterio**.
    
    ![Pulsante Crea un criterio](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Scegliere il modello di criteri DLP che protegge i tipi di informazioni riservate necessarie per \> **next**.
    
    In questo esempio, si seleziona **Privacy** Dati personali \> **(PII)** perché include già la maggior parte dei tipi di informazioni riservate che si desidera proteggere, che verranno aggiunti in un secondo momento. 
    
    Quando si seleziona un modello, è possibile leggere la descrizione a destra per informazioni sui tipi di informazioni riservate che il modello protegge.
    
    ![Pagina per la scelta di un modello di criterio DLP](../media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Assegnare al criterio il nome \> **Next**.
    
6. Per scegliere i percorsi che si desidera proteggere dal criterio DLP, eseguire una delle operazioni seguenti:
    
  - Scegliere **Tutte le posizioni in Office 365** \> **Avanti**.
    
  - Scegliere **Consenti di scegliere posizioni specifiche** \> **Avanti.** Per questo esempio, scegliere questa opzione.
    
    Per includere o escludere un'intera posizione, ad esempio tutti Exchange di  posta elettronica o tutti gli account OneDrive, attivare o disattivare lo stato di tale posizione. 
    
    Per includere solo siti SharePoint o account OneDrive for Business specifici,  impostare lo stato su Attiva e quindi fare clic sui collegamenti **in** Includi per scegliere siti o account specifici. Quando si applica un criterio a un sito, le regole configurate in tale criterio vengono applicate automaticamente a tutti i siti secondari del sito. 
    
    ![Opzioni per le posizioni in cui è possibile applicare i criteri di prevenzione della perdita dei dati](../media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    In questo esempio, per proteggere le informazioni riservate archiviate  in tutti gli account OneDrive for Business, disattivare lo stato sia per i siti di posta elettronica **di Exchange** che per i siti **di SharePoint** e lasciare attiva la proprietà **Status** per gli account **OneDrive**.
    
7. Scegliere **Usa impostazioni avanzate** \> **Avanti.**
    
8. Un modello di criteri DLP contiene regole predefinite con condizioni e azioni che rilevano e agiscono su tipi specifici di informazioni riservate. È possibile modificare, eliminare o disattivare una delle regole esistenti o aggiungerne di nuove. Al termine, fare clic su **Avanti.**
    
    ![Regole espanse nel modello di criteri informazioni personali usa](../media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    In questo esempio, il modello DATI PERSONALI degli Stati Uniti include due regole predefinite:
    
  - **Volume ridotto di contenuto rilevato informazioni** personali negli Stati Uniti Questa regola cerca i file contenenti da 1 a 10 occorrenze di ognuno dei tre tipi di informazioni riservate (NUMERI ITIN, SSN e numeri di passaporto degli Stati Uniti), in cui i file vengono condivisi con persone esterne all'organizzazione. Se trovata, la regola invia una notifica tramite posta elettronica all'amministratore principale della raccolta siti, al proprietario del documento e alla persona che ha modificato il documento per l'ultima volta. 
    
  - **Volume elevato di contenuto rilevato informazioni** personali negli Stati Uniti Questa regola cerca i file contenenti 10 o più occorrenze di ognuno degli stessi tre tipi di informazioni riservate, in cui i file vengono condivisi con persone esterne all'organizzazione. Se viene trovata, questa azione invia anche una notifica tramite posta elettronica, oltre a limitare l'accesso al file. Per il contenuto di un account OneDrive for Business, ciò significa che le autorizzazioni per il documento sono limitate per tutti gli utenti tranne l'amministratore principale della raccolta siti, il proprietario del documento e la persona che ha modificato il documento per l'ultima volta. 
    
    Per soddisfare i requisiti specifici dell'organizzazione, è possibile semplificare l'attivazione delle regole, in modo che una singola occorrenza di informazioni riservate sia sufficiente per bloccare l'accesso per gli utenti esterni. Dopo aver individuato queste regole, si è consapevoli che non sono necessarie regole di conteggio basso e elevato, ma solo una singola regola che blocca l'accesso se vengono trovate informazioni riservate.
    
    Espandere quindi la regola denominata **Low volume of content detected U.S. PII** Delete \> **rule**.
    
    ![Pulsante Elimina regola](../media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. Ora, in questo esempio, è necessario aggiungere due tipi di informazioni riservate (numeri di conto corrente bancario statunitense e numeri di patente di guida statunitensi), consentire agli utenti di ignorare una regola e modificare il conteggio in qualsiasi occorrenza. È possibile eseguire tutte queste operazioni modificando una regola, quindi selezionare Volume elevato di contenuto rilevato **U.S. PiI** \> **Edit rule**.
    
    ![Pulsante Modifica regola](../media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Per aggiungere un tipo di informazioni riservate, nella sezione **Condizioni** \> **Aggiungere o modificare i tipi**. Quindi, in **Aggiungi o modifica tipi** scegli \> **Aggiungi** \> seleziona **U.S. Bank Account Number** e **U.S. Driver's License Number** \> **Add** \> **Done**.
    
    ![Opzione per aggiungere o modificare i tipi](../media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Riquadro Aggiungi o modifica tipi](../media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Per modificare il conteggio (il numero di istanze di informazioni riservate necessarie per attivare la regola), in **Conteggio istanze** scegliere il valore minimo \> per ogni tipo immettere  \> 1. Il conteggio minimo non può essere vuoto. Il conteggio massimo può essere vuoto. un valore **massimo** vuoto viene convertito in **qualsiasi valore**.
    
    Al termine, il conteggio minimo per tutti i tipi di informazioni riservate deve essere **1** e il conteggio massimo deve essere **qualsiasi**. In altre parole, qualsiasi occorrenza di questo tipo di informazioni riservate soddisferà questa condizione.
    
    ![Conteggi delle istanze per i tipi di informazioni riservate](../media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Per la personalizzazione finale, non si desidera che i criteri DLP blocchino le attività degli utenti quando hanno una giustificazione aziendale valida o riscontrano un falso positivo, pertanto si desidera che la notifica dell'utente includa opzioni per ignorare l'azione di blocco.
    
    Nella sezione **Notifiche utente** puoi vedere che le notifiche tramite posta elettronica e i suggerimenti per i criteri sono attivati per impostazione predefinita per questa regola nel modello. 
    
    Nella sezione **Sostituzioni** utente è possibile vedere che le sostituzioni per una giustificazione aziendale sono attivate, ma le sostituzioni per segnalare falsi positivi non lo sono. Scegliere **Ignora automaticamente la regola se viene segnalata come falso positivo.**
    
    ![Sezione Notifiche utente e sezione Sostituzioni utente](../media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Nella parte superiore dell'editor delle regole, modificare  il nome di questa regola dall'impostazione predefinita Volume elevato di contenuti rilevati negli Stati Uniti in Qualsiasi contenuto rilevato con informazioni personali statunitensi perché ora è attivato da qualsiasi occorrenza dei relativi tipi di informazioni riservate.  
    
14. Nella parte inferiore dell'editor delle regole \> **Salva**.
    
15. Esaminare le condizioni e le azioni per questa regola \> **Avanti.**
    
    A destra, notare **l'opzione Stato** per la regola. Se si disattiva un intero criterio, vengono disattivate anche tutte le regole contenute nel criterio. Tuttavia, qui è possibile disattivare una regola specifica senza disattivare l'intero criterio. Questo può essere utile nei casi in cui è necessario esaminare una regola che genera un gran numero di falsi positivi. 
    
16. Nella pagina successiva leggere e comprendere quanto segue e quindi scegliere se attivare la regola o testarla prima \> **Avanti.**
    
     Prima di aver creato i criteri DLP, è necessario distribuirli gradualmente per valutarne l'impatto e l'efficacia, prima di applicarli completamente. Ad esempio, non si desidera che un nuovo criterio DLP blocchi involontariamente l'accesso a migliaia di documenti necessari agli utenti per eseguire il proprio lavoro. 
    
    Se si creano criteri DLP con un forte impatto potenziale, si consiglia di attenersi alla sequenza riportata di seguito:
    
17. Iniziare in modalità test senza suggerimenti per i criteri, quindi utilizzare i report DLP per valutare l'impatto. È possibile utilizzare i report DLP per visualizzare il numero, il percorso, il tipo e la gravità di corrispondenza del criterio. A seconda dei risultati, è possibile ottimizzare le regole in modo adeguato. In modalità test, i criteri DLP non avranno effetto sulla produttività degli utenti dell'organizzazione. 
    
18. Passare alla modalità test con notifiche e suggerimenti per i criteri in modo da istruire gli utenti in merito ai criteri di conformità e prepararli all'applicazione delle regole. In questa fase, è inoltre possibile chiedere agli utenti di segnalare i falsi positivi per definire ulteriormente le regole.
    
19. Attivare i criteri in modo che le regole vengano applicate e che il contenuto sia protetto. Continuare a eseguire il monitoraggio dei report di prevenzione della perdita dei dati e dei rapporti operazioni non consentite oppure delle notifiche per essere certi di ottenere i risultati desiderati. 
    
    ![Opzioni per l'utilizzo della modalità di test e attivazione dei criteri](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Rivedere le impostazioni per questo criterio \> scegliere **Crea**.
    
Dopo aver creato e attivare un criterio DLP, questo viene distribuito in tutte le origini di contenuto incluse, ad esempio i siti di SharePoint Online o gli account OneDrive for Business, in cui il criterio inizia automaticamente ad applicazione delle relative regole su tale contenuto.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Visualizzare lo stato di un criterio DLP

In qualsiasi momento, è possibile visualizzare lo  stato dei criteri DLP nella pagina Criteri nella sezione **Prevenzione** della perdita dei dati del Centro &amp; sicurezza e conformità. In questa pagina sono disponibili informazioni importanti, ad esempio se un criterio è stato correttamente attivato o disattivato oppure se il criterio è in modalità test. 
  
Di seguito sono riportati i diversi stati e il loro significato.
  
|**Stato**|**Spiegazione**|
|:-----|:-----|
|**Attivazione in corso...** <br/> |Il criterio viene distribuito alle origini del contenuto che include. Il criterio non è ancora applicato su tutte le origini.  <br/> |
|**Test, con notifiche** <br/> |Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio vengono inviate ai destinatari specificati.  <br/> |
|**Test, senza notifiche** <br/> |Il criterio è in modalità test. Le azioni in una regola non sono applicate, ma vengono raccolte le corrispondenze del criterio ed è possibile visualizzarle tramite i report DLP. Le notifiche relative alle corrispondenze del criterio non vengono inviate ai destinatari specificati.  <br/> |
|**Attivato** <br/> |Il criterio è attivo e applicato. Il criterio è stato distribuito correttamente a tutte le origini del contenuto.  <br/> |
|**Disattivazione in corso...** <br/> |Il criterio viene rimosso dalle origini del contenuto che include. Il criterio potrebbe essere ancora attivo e applicato in alcune origini. La disattivazione di un criterio potrebbe richiedere fino a 45 minuti.  <br/> |
|**Disattivato** <br/> |Il criterio non è attivo e non applicato. Le impostazioni del criterio (origini, parole chiave, durata e così via) vengono salvate.  <br/> |
|**Eliminazione in corso...** <br/> |Il criterio è in corso di eliminazione. Il criterio non è attivo e non applicato. In genere, un criterio richiede un'ora per eseguire il delet <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Disattivare un criterio DLP

È possibile modificare o disattivare un criterio DLP in qualsiasi momento. La disattivazione di un criterio disabilita tutte le regole nel criterio.
  
Per modificare o disattivare un criterio DLP, nella pagina **Criterio** \> selezionare il criterio Modifica \> **criterio**.
  
![Pulsante Modifica criterio](../media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Inoltre, è possibile disattivare ogni regola singolarmente modificando il criterio e quindi disattivando lo **stato** di tale regola, come descritto in precedenza. 
  
## <a name="more-information"></a>Ulteriori informazioni

- [Informazioni sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md)
- [Inviare notifiche e visualizzare i suggerimenti per i criteri di prevenzione della perdita dei dati](use-notifications-and-policy-tips.md)
- [Creare criteri di prevenzione della perdita dei dati per proteggere i documenti con FCI o altre proprietà](protect-documents-that-have-fci-or-other-properties.md)
- [Elementi inclusi nei modelli dei criteri di prevenzione della perdita dei dati](what-the-dlp-policy-templates-include.md)
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
