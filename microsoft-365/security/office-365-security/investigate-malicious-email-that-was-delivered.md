---
title: Individuare e studiare messaggi di posta elettronica dannosi che sono stati recapitati in Office 365
keywords: TIMailData-inline, incidenti di sicurezza, incidenti, ATP PowerShell, malware per la posta elettronica, utenti compromessi, phishing di posta elettronica, malware per la posta elettronica, lettura intestazioni e-mail, leggere intestazioni, aprire intestazioni di posta elettronica
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Informazioni su come utilizzare le funzionalità di analisi e risposta alle minacce per individuare e studiare messaggi di posta elettronica dannosi.
ms.openlocfilehash: 57d419c291fdfed3a5d7237ae2021e9ef06723f5
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031901"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a>Individuare e studiare messaggi di posta elettronica dannosi che sono stati recapitati in Office 365

[Office 365 Advanced Threat Protection](office-365-atp.md) consente di analizzare le attività che inseriscono i rischi per l'organizzazione e di intervenire per proteggere l'organizzazione. Ad esempio, se si fa parte del team di sicurezza dell'organizzazione, è possibile trovare e analizzare i messaggi di posta elettronica sospetti che sono stati recapitati. A tale scopo, è possibile utilizzare [Esplora minacce (o rilevamenti in tempo reale)](threat-explorer.md).
  
## <a name="before-you-begin"></a>Prima di iniziare...

Verificare che vengano soddisfatti i seguenti requisiti:
  
- L'organizzazione dispone di [Office 365 Advanced Threat Protection](office-365-atp.md) e le [licenze vengono assegnate agli utenti](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- La [registrazione di controllo di Office 365](../../compliance/turn-audit-log-search-on-or-off.md) è attivata per l'organizzazione. 
    
- L'organizzazione dispone di criteri definiti per la protezione da posta indesiderata, anti-malware, anti-phishing e così via. Vedere [protezione dalle minacce in Office 365](protect-against-threats.md).
    
- Si è un amministratore globale di Office 365 oppure è stato assegnato l'amministratore della sicurezza o il ruolo di ricerca ed eliminazione nel centro sicurezza &amp; e conformità. Vedere [Permissions in the Office &amp; 365 Security Compliance Center](permissions-in-the-security-and-compliance-center.md). Per alcune azioni, è necessario disporre anche di un nuovo ruolo di anteprima assegnato. 

#### <a name="preview-role-permissions"></a>Autorizzazioni per il ruolo di anteprima

Per eseguire determinate azioni, ad esempio la visualizzazione delle intestazioni dei messaggi o il download del contenuto del messaggio di posta elettronica, è necessario un nuovo ruolo denominato *Anteprima* aggiunto a un altro gruppo di ruoli Office 365 appropriato. La tabella seguente consente di chiarire i ruoli e le autorizzazioni necessari.

|Attività  |Gruppo di ruolo |Ruolo di anteprima necessario?  |
|---------|---------|---------|
|Utilizzo di Esplora minacce (e rilevamenti in tempo reale) per l'analisi delle minacce     |Amministratore globale di Office 365 <br> Amministratore della sicurezza <br> Lettore di sicurezza     | No   |
|Utilizzare Esplora minacce (e rilevamenti in tempo reale) per visualizzare le intestazioni dei messaggi di posta elettronica così come l'anteprima e il download dei messaggi di posta elettronica in quarantena    |Amministratore globale di Office 365 <br> Amministratore della sicurezza <br>Lettore di sicurezza   |       No  |
|Utilizzare Esplora minacce per visualizzare le intestazioni e scaricare i messaggi di posta elettronica recapitati alle cassette postali     |Amministratore globale di Office 365 <br>Amministratore della sicurezza <br> Lettore di sicurezza <br> Anteprima   |   Sì      |

> [!NOTE]
> L' *Anteprima* è un ruolo e non un gruppo di ruoli. il ruolo di anteprima deve essere aggiunto a un gruppo di ruoli esistente per Office 365. Al ruolo di amministratore globale di Office 365 viene assegnato l'interfaccia di amministrazione[https://admin.microsoft.com](https://admin.microsoft.com)di Microsoft 365 () e i ruoli amministratore sicurezza e lettore di sicurezza sono assegnati nel centro[https://protection.office.com](https://protection.office.com)protezione & conformità di Office 365. Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Individuare ed eliminare messaggi di posta elettronica sospetti recapitati

Threat Explorer è un potente report che può servire a molteplici scopi, ad esempio la ricerca e l'eliminazione dei messaggi, l'identificazione dell'indirizzo IP di un mittente di posta elettronica dannoso o l'avvio di un incidente per ulteriori indagini. La procedura seguente si concentra sull'utilizzo di Esplora risorse per individuare ed eliminare messaggi di posta elettronica dannosi dalle cassette postali dei destinatari.

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Nel riquadro di spostamento a sinistra, scegliere **gestione** \> **** minacce.

    ![Explorer con campi azione di recapito e posizione di recapito.](../media/ThreatExFields.PNG)

    È possibile notare la nuova colonna **azioni speciali** . Questa funzionalità ha lo scopo di informare gli amministratori sull'esito dell'elaborazione di un messaggio di posta elettronica. È possibile accedere alla colonna **azioni speciali** nello stesso luogo in cui si trova l' **operazione di recapito** e il **percorso di recapito**. Le azioni speciali potrebbero essere aggiornate alla fine della sequenza temporale della posta elettronica di Threat Explorer, che è una nuova funzionalità che consente di migliorare l'esperienza di ricerca per gli amministratori.

3. Per visualizzare una cronologia della posta elettronica, fare clic sull'oggetto di un messaggio di posta elettronica, quindi fare clic su **sequenza temporale della posta elettronica**. (Viene visualizzato tra le altre intestazioni del pannello come **Riepilogo** o **Dettagli**).

    Dopo aver aperto la sequenza temporale della posta elettronica, dovrebbe essere visualizzata una tabella che indica gli eventi successivi al recapito per la posta. In caso di nessun altro evento per il messaggio di posta elettronica, dovrebbe essere visualizzato un singolo appuntamento per il recapito originale che dichiara un risultato come **bloccato** con un verdetto come **phishing**. La scheda ha anche la possibilità di esportare l'intera sequenza temporale della posta elettronica e questo Esporta tutti i dettagli nella scheda e dettagli sul messaggio di posta elettronica (elementi come Subject, sender, Recipient, Network, and Message ID).

    La sequenza temporale della posta elettronica riduce la randomizzazione perché è necessario meno tempo per controllare posizioni diverse per cercare di comprendere gli eventi accaduti dopo l'arrivo del messaggio di posta elettronica. Quando più eventi si verificano in un messaggio di posta elettronica o vicino allo stesso tempo, tali eventi vengono visualizzati in una visualizzazione sequenza temporale. 
    
    Alcuni eventi che si verificano dopo il recapito alla posta vengono acquisiti nella colonna **azioni speciali** . La combinazione delle informazioni dalla sequenza temporale della posta elettronica con le azioni speciali eseguite sulla posta elettronica dopo il recapito fornisce agli amministratori informazioni su come funzionano i propri criteri, in cui l'indirizzo di posta elettronica è stato definitivamente instradato e, in alcuni casi, la valutazione finale. 

4. Scegliere **tutti i messaggi di posta elettronica**dal menu **Visualizza** .

    ![Utilizzare il menu Visualizza per scegliere tra la posta elettronica e i rapporti di contenuto](../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Si notino le etichette che vengono visualizzate nel report, ad esempio **recapitate**, **sconosciute**o **recapitate in posta indesiderata**.

    ![Esplora minacce che mostra i dati per tutti i messaggi di posta](../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    A seconda delle operazioni eseguite nei messaggi di posta elettronica per l'organizzazione, è possibile che vengano visualizzate altre etichette, ad esempio **bloccate** o **sostituite**.
    
6. Nel rapporto scegliere **recapitato** per visualizzare solo i messaggi di posta elettronica che sono finiti nelle cassette postali degli utenti.

    ![Se si fa clic su "recapitato alla posta indesiderata", vengono rimossi](../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. Al di sotto del grafico, esaminare l'elenco di **posta elettronica** al di sotto del grafico.

    ![Sotto il grafico, visualizzare un elenco di messaggi di posta elettronica che sono stati rilevati](../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. Nell'elenco, scegliere un elemento per visualizzare ulteriori dettagli sul messaggio di posta elettronica. Ad esempio, è possibile fare clic sulla riga dell'oggetto per visualizzare le informazioni sul mittente, i destinatari, gli allegati e altri messaggi di posta elettronica simili.

    ![È possibile visualizzare ulteriori informazioni su un elemento](../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. Dopo aver visualizzato le informazioni sui messaggi di posta elettronica, selezionare uno o più elementi nell'elenco per attivare **+ azioni**.
    
10. Utilizzare l'elenco **+ Actions** per applicare un'azione, ad esempio **Move to deleted** Items. Consente di eliminare i messaggi selezionati dalle cassette postali dei destinatari.

    ![Quando si selezionano uno o più messaggi di posta elettronica, è possibile scegliere tra diverse azioni disponibili](../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a>Gestione dei messaggi di posta elettronica sospetti

Gli utenti malintenzionati potrebbero inviare messaggi all'interno dell'organizzazione nel tentativo di phishing le proprie credenziali e accedere ai segreti aziendali. Per evitare questo, è possibile utilizzare i servizi di protezione dalle minacce in Office 365, tra cui [Exchange Online Protection](exchange-online-protection-overview.md) e [Advanced Threat Protection](office-365-atp.md). Tuttavia, accade occasionalmente che un utente malintenzionato invii messaggi di posta elettronica contenenti un collegamento (URL) che punta solo in seguito a contenuti dannosi, ad esempio malware. In alternativa, potrebbe risultare troppo tardi che un utente dell'organizzazione è stato compromesso e, anche se sono stati compromessi, un utente malintenzionato ha utilizzato il proprio account per inviare messaggi di posta elettronica ad altre persone dell'organizzazione. Nell'ambito dell'utilizzo di uno di questi scenari, è possibile rimuovere i messaggi di posta elettronica sospetti dalle cassette postali degli utenti. A tale scopo, è possibile utilizzare [Esplora minacce](threat-explorer.md).

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a>Ricerca di messaggi di posta elettronica reinstradati dopo aver eseguito le operazioni

Threat Explorer fornisce al team delle operazioni di sicurezza i dettagli necessari per esaminare la posta elettronica sospetta. Il team delle operazioni di sicurezza può:

- [Visualizzare le intestazioni di posta elettronica e scaricare il corpo del messaggio di posta elettronica](#view-the-email-headers-and-download-the-email-body) 

- [Controllare l'azione e il percorso di recapito](#check-the-delivery-action-and-location)

- [Visualizzare la sequenza temporale del messaggio di posta elettronica](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a>Visualizzare le intestazioni di posta elettronica e scaricare il corpo del messaggio di posta elettronica

La possibilità di visualizzare in anteprima le intestazioni di posta elettronica e scaricare il corpo di un corpo di posta elettronica è una funzionalità potente in Esplora minacce. Le [autorizzazioni](permissions-in-the-security-and-compliance-center.md) appropriate devono essere assegnate. Vedere [Preview Role Permissions](#preview-role-permissions).

Per accedere all'intestazione del messaggio e alle opzioni di download della posta elettronica, eseguire la procedura seguente: 

1. Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione per Office 365. Questo porta al centro sicurezza &amp; e conformità. 
    
2. Nel riquadro di spostamento a sinistra, scegliere **gestione** \> **** minacce.

3. Fare clic su un oggetto nella tabella Esplora minacce. 

    Verrà aperto il riquadro a comparsa, in cui sono posizionati entrambi i collegamenti di anteprima e di download della posta elettronica.

    ![Riquadro a comparsa di Esplora minacce con collegamenti per il download e l'anteprima nella pagina.](../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> Questa funzionalità non viene visualizzata per i messaggi di posta elettronica che non sono mai stati trovati nella cassetta postale di un utente, che può verificarsi se un messaggio di posta elettronica è stato eliminato o se il recapito non è riuscito Nei casi in cui i messaggi di posta elettronica sono stati eliminati dalle cassette postali degli utenti, gli amministratori visualizzano un messaggio di errore "posta non trovata".

### <a name="check-the-delivery-action-and-location"></a>Controllare l'azione e il percorso di recapito

In [Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md), ora sono presenti le colonne dell' **azione** di recapito e del **percorso** di recapito anziché la precedente colonna **stato di recapito** . Questo comporta un'immagine più completa della posizione in cui i messaggi di posta elettronica atterrano. Parte dell'obiettivo di questa modifica è semplificare la ricerca per le operazioni di sicurezza, ma il risultato finale è la conoscenza del percorso dei messaggi di posta elettronica problematici.

Lo stato di recapito è ora suddiviso in due colonne:

- **Azione di recapito** -qual è lo stato di questo messaggio di posta elettronica?

- **Percorso di recapito** -dove è stato instradato il messaggio di posta elettronica come risultato?

Azione di recapito è l'azione intrapresa su un messaggio di posta elettronica a causa di criteri o rilevamenti esistenti. Ecco le possibili azioni che un messaggio di posta elettronica può eseguire:

- **Recapitato** : la posta elettronica è stata recapitata alla posta in arrivo o alla cartella di un utente e l'utente può accedervi direttamente.

- **Junked** – la posta elettronica è stata inviata alla cartella posta indesiderata o alla cartella eliminata dell'utente e l'utente ha accesso ai messaggi di posta elettronica nella cartella posta indesiderata o eliminata.

- **Bloccato** : tutti i messaggi di posta elettronica in quarantena, che hanno avuto esito negativo o sono stati eliminati. (Questo è completamente inaccessibile dall'utente).

- **Sostituito** – qualsiasi messaggio di posta elettronica in cui gli allegati dannosi sono stati sostituiti dai file. txt che affermano che l'allegato è dannoso
 
Il percorso di recapito consente di visualizzare i risultati dei criteri e i rilevamenti eseguiti dopo il recapito. È collegato a un'azione di recapito. Questo campo è stato aggiunto per fornire informazioni dettagliate sull'azione intrapresa quando viene trovata una posta elettronica problematica. Di seguito sono riportati i possibili valori del percorso di recapito:

- **Posta in arrivo o cartella** – il messaggio di posta elettronica si trova nella cartella posta in arrivo o in una directory (secondo le regole di posta elettronica).

- **On-Prem o External** -la cassetta postale non esiste sul cloud ma è in locale.

- **Cartella posta indesiderata** : la posta elettronica si trova nella cartella posta indesiderata di un utente.

- **Cartella Posta eliminata** – l'e-mail si trova nella cartella degli elementi eliminati di un utente.

- **Quarantine** : la posta elettronica in quarantena e non nella cassetta postale di un utente.

- **Failed** : la posta elettronica non è riuscita a raggiungere la cassetta postale.

- **Eliminato** : il messaggio di posta elettronica viene perso da qualche parte nel flusso di posta.

### <a name="view-the-timeline-of-your-email"></a>Visualizzare la sequenza temporale del messaggio di posta elettronica
  
La **sequenza temporale della posta elettronica** è un campo in Esplora minacce che facilita la ricerca per il team delle operazioni di sicurezza. Quando più eventi si verificano alla stessa ora o in prossimità di un messaggio di posta elettronica, tali eventi vengono visualizzati in una visualizzazione sequenza temporale. Alcuni eventi che si verificano dopo il recapito al messaggio di posta elettronica vengono acquisiti nella colonna **azioni speciali** . La combinazione di informazioni dalla sequenza temporale di un messaggio di posta elettronica con le azioni speciali eseguite dopo il recapito consente agli amministratori di esaminare i criteri e la gestione delle minacce (ad esempio la posizione in cui è stata instradata la posta elettronica e, in alcuni casi, la valutazione finale).
  
## <a name="related-topics"></a>Argomenti correlati

[Office 365 Advanced Threat Protection](office-365-ti.md)
  
[Protezione dalle minacce in Office 365](protect-against-threats.md)
  
[Visualizzare i report per Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  

