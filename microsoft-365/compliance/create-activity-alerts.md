---
title: Creare avvisi attività
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- BCS160
- MET150
ms.assetid: 72bbad69-035b-4d33-b8f4-549a2743e97d
ROBOTS: NOINDEX, NOFOLLOW
description: Aggiungere e gestire gli avvisi di attività nel centro sicurezza & conformità in modo che Microsoft 365 invierà notifiche di posta elettronica quando gli utenti eseguono attività specifiche.
ms.openlocfilehash: e6800bf5b8bbc013586a4be248a4e9e71fc70507
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943165"
---
# <a name="create-activity-alerts"></a>Creare avvisi attività

È possibile creare un avviso di attività che invierà una notifica tramite posta elettronica quando gli utenti eseguono attività specifiche in Office 365. Gli avvisi attività sono simili alla ricerca di eventi nel registro di controllo, tranne per il fatto che verrà inviato un messaggio di posta elettronica quando si verifica un evento per un'attività a cui è stato creato un avviso. 
  
 **Perché utilizzare gli avvisi attività anziché cercare il log di controllo?** È possibile che alcuni tipi di attività o attività vengano eseguiti da utenti specifici che si desidera conoscere. Invece di dover ricordare di eseguire la ricerca nel registro di controllo per tali attività, è possibile utilizzare gli avvisi attività affinché Microsoft 365 invii un messaggio di posta elettronica quando gli utenti eseguono tali attività. Ad esempio, è possibile creare un avviso di attività per notificare quando un utente elimina i file in SharePoint oppure è possibile creare un avviso per segnalare quando un utente Elimina definitivamente i messaggi dalla propria cassetta postale. La notifica di posta elettronica inviata contiene informazioni su quali attività sono state eseguite e sull'utente che lo ha eseguito.

> [!NOTE]
> Gli avvisi di attività sono deprecati. Si consiglia di iniziare a utilizzare i criteri di avviso nel centro sicurezza e conformità invece di creare nuovi avvisi attività. I criteri di avviso offrono funzionalità aggiuntive, come la possibilità di creare un criterio di avviso che attiva un avviso quando un utente esegue un'attività specificata e visualizza avvisi nella pagina **Visualizza avvisi** nel centro sicurezza e conformità. Per ulteriori informazioni, vedere [criteri di avviso](alert-policies.md).
  
## <a name="before-you-begin"></a>Informazioni preliminari

- Per gestire gli avvisi di attività, è necessario che il ruolo Configurazione organizzazione sia assegnato al centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli amministratore conformità e gestione organizzazione. Per ulteriori informazioni sull'aggiunta di membri ai gruppi di ruoli, vedere [Give users access to the Security & Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
    
- L'utente (o un altro amministratore) deve prima attivare la registrazione di controllo per l'organizzazione prima di iniziare a utilizzare gli avvisi attività. A tale scopo, è sufficiente fare clic su **Avvia registrazione attività utente e amministratore** nella pagina **avvisi attività** . Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione. È inoltre possibile abilitare il controllo nella pagina di **ricerca del registro di controllo** nel centro sicurezza & Compliance (andare alla ricerca nel **Registro di controllo**di **ricerca** \> ). È necessario eseguire questa operazione una sola volta per l'organizzazione.
  
- È possibile creare avvisi per le stesse attività di cui è possibile eseguire la ricerca nel registro di controllo. Vedere la sezione [ulteriori informazioni](#more-information) per un elenco di scenari comuni (e l'attività specifica da monitorare) per la quale è possibile creare avvisi. 
    
- È possibile utilizzare la pagina **avvisi attività** nel centro sicurezza & conformità per creare avvisi solo per le attività eseguite dagli utenti elencati nella rubrica dell'organizzazione. Non è possibile utilizzare questa pagina per creare avvisi per attività eseguite da utenti esterni che non sono elencati nella rubrica. 
    
## <a name="create-an-activity-alert"></a>Creare un avviso di attività

1. Passare a [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Accedere usando l'account di lavoro o della scuola.
    
3. Nella pagina **avvisi attività** fare clic ![su Aggiungi icona](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **nuovo**.

   Viene visualizzata la pagina del riquadro a comparsa per creare un avviso di attività.

    
    ![Creare un avviso di attività](../media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Completare i seguenti campi per creare un avviso di attività:
    
    a. **Nome** -digitare un nome per l'avviso. I nomi degli avvisi devono essere univoci all'interno dell'organizzazione.
    
    b. **Description** (facoltativo): consente di descrivere l'avviso, ad esempio le attività e gli utenti monitorati, e gli utenti a cui vengono inviate le notifiche tramite posta elettronica. Le descrizioni forniscono un modo semplice e rapido per descrivere lo scopo dell'avviso ad altri amministratori.
    
    c. **Tipo di avviso** : verificare che l'opzione **personalizzata** sia selezionata. 

    d. **Invia questo avviso quando** si fa clic su **Invia questo avviso quando** e quindi si configurano i due campi seguenti:
    
    - **Attività** -fare clic sull'elenco a discesa per visualizzare le attività per le quali è possibile creare un avviso. Questo è lo stesso elenco di attività visualizzato quando si esegue una ricerca nel registro di controllo. È possibile selezionare una o più attività specifiche oppure fare clic sul nome del gruppo di attività per selezionare tutte le attività del gruppo. Per una descrizione di queste attività, vedere la sezione "attività controllate" in [Search the audit log](search-the-audit-log-in-security-and-compliance.md#audited-activities). Quando un utente esegue una delle attività aggiunte all'avviso, viene inviata una notifica di posta elettronica. 
    
     - **Utenti** : fare clic su questa casella e quindi selezionare uno o più utenti. Se gli utenti di questa casella eseguono le attività che sono state aggiunte alla casella **attività** , verrà inviato un avviso. Lasciare vuota la casella **utenti** per inviare un avviso quando un utente dell'organizzazione esegue le attività specificate dall'avviso. 

    e. **Invia questo avviso a** -fare clic su **Invia questo avviso**, quindi fare clic nella casella **destinatari** e digitare un nome per aggiungere un utente che riceverà una notifica tramite posta elettronica quando un cliente (specificato nella casella **utenti** ) esegue un'attività (specificata nella casella **attività** ). Si noti che per impostazione predefinita viene aggiunto all'elenco dei destinatari. È possibile rimuovere il nome dall'elenco.
    
5. Fare clic su **Salva** per creare l'avviso. 
    
    Il nuovo avviso viene visualizzato nell'elenco nella pagina **avvisi attività** . 
    
    ![Un elenco di avvisi viene visualizzato nella pagina avvisi attività](../media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    Lo stato dell'avviso è impostato **su**attivato. Si noti che i destinatari che riceveranno una notifica tramite posta elettronica quando viene inviato un avviso sono anche elencati. 
  
## <a name="turn-off-an-activity-alert"></a>Disattivare un avviso di attività

È possibile disattivare un avviso di attività in modo che non venga inviata una notifica di posta elettronica. Dopo aver disattivato l'avviso attività, viene comunque visualizzato nell'elenco degli avvisi attività per l'organizzazione ed è comunque possibile visualizzarne le proprietà.
  
1. Vai a Vai a [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Accedere usando l'account aziendale o dell'istituto di istruzione.
    
3. Nell'elenco degli avvisi attività per l'organizzazione, fare clic sull'avviso che si desidera disattivare.
    
4. Nella pagina **Modifica avviso** fare **clic sull'opzione attiva/disattiva** per modificare lo stato su **disattivato**, quindi fare clic su **Salva**.
    
    Lo stato dell'avviso nelle pagine **avvisi attività** è impostato su **disattivato**. 
    
Per riattivare un avviso di attività, ripetere questi passaggi e fare clic sull'opzione **Attiva/Disattiva per modificare lo** stato **su**attivato.
  
## <a name="more-information"></a>Ulteriori informazioni

- Di seguito è riportato un esempio di notifica di posta elettronica inviato agli utenti specificati nel campo inviato questo avviso a (ed elencati in **destinatari** nella pagina **avvisi attività** ) nel centro sicurezza & Compliance. 
    
    ![Esempio di un messaggio di posta elettronica notifica inviato per un avviso di attività](../media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Di seguito sono riportate alcune attività comuni relative a documenti e messaggi di posta elettronica a cui è possibile creare avvisi di attività. Nelle tabelle vengono descritte l'attività, il nome dell'attività per cui creare un avviso e il nome del gruppo di attività in cui è elencata l'attività nell'elenco a discesa **attività** . Per visualizzare un elenco completo delle attività per cui è possibile creare avvisi attività, vedere la sezione "attività controllate" in [Search the audit log](search-the-audit-log-in-security-and-compliance.md#audited-activities).
    
    > [!TIP]
    > Potrebbe essere necessario creare un avviso di attività per una sola attività eseguita da qualsiasi utente. In alternativa, è possibile creare un avviso di attività che rintracci più attività eseguite da uno o più utenti. 
  
    Nella tabella seguente sono elencate alcune attività comuni relative ai documenti in SharePoint o OneDrive for business.
    
    |**Quando un utente esegue questa operazione...**|**Creare un avviso per questa attività**|**Gruppo attività**|
    |:-----|:-----|:-----|
    |Visualizza un documento in un sito.  <br/> |File aperto  <br/> |Attività di file e cartelle  <br/> |
    |Modifica o modifiche di un documento.  <br/> |File modificato  <br/> |Attività di file e cartelle  <br/> |
    |Condivide un documento con un utente esterno all'organizzazione.  <br/> |Condivisione di file, cartelle o siti  <br/> E  <br/> Invito alla condivisione creato  <br/> Per altre informazioni, vedere [Usare il controllo della condivisione nel log di controllo](use-sharing-auditing.md).  <br/> |Attività di richiesta di accesso e condivisione  <br/> |
    |Carica o Scarica un documento.  <br/> |File caricato  <br/> E/o  <br/> File scaricato  <br/> |Attività di file e cartelle  <br/> |
    |Modifica le autorizzazioni di accesso a un sito.  <br/> |Autorizzazioni sito modificate  <br/> |Attività di amministrazione siti  <br/> |

    Nella tabella seguente sono elencate alcune attività comuni relative alla posta elettronica in Exchange Online.

    |**Quando un utente esegue questa operazione...**|**Creare un avviso per questa attività**|**Gruppo attività**|
    |:-----|:-----|:-----|
    |Elimina definitivamente (Purges) un messaggio di posta elettronica dalla propria cassetta postale.  <br/> |Messaggi eliminati dalla cassetta postale  <br/> | Attività su cassette postali di Exchange  <br/> |
    |Invia un messaggio di posta elettronica da una cassetta postale condivisa.  <br/> |Messaggio inviato con autorizzazioni Invia come  <br/> E  <br/> Messaggio inviato con autorizzazioni Invia per conto di  <br/> | Attività su cassette postali di Exchange  <br/> |
   
- È inoltre possibile utilizzare i cmdlet **New-ActivityAlert** e **set-ActivityAlert** in PowerShell per la sicurezza & Compliance Center per creare e modificare gli avvisi di attività. Se si utilizzano questi cmdlet per creare o modificare gli avvisi di attività, tenere presente quanto segue: 
    
  - Se si utilizza un cmdlet per aggiungere un'attività all'avviso che non è elencato nell'elenco a discesa **attività** , viene visualizzato un messaggio nella pagina delle proprietà per l'avviso che indica che "questo avviso ha operazioni personalizzate non elencate nella selezione". 
    
  - Un buon motivo per utilizzare i cmdlet per creare o modificare un avviso di attività consiste nell'inviare notifiche tramite posta elettronica a un utente esterno all'organizzazione. Questo utente esterno verrà elencato nell'elenco dei destinatari per l'avviso. Tuttavia, se si rimuove l'utente esterno dall'avviso, l'utente non può essere aggiunto nuovamente all'avviso utilizzando la pagina **Modifica avviso** . Sarà necessario aggiungere di nuovo l'utente esterno utilizzando il cmdlet **set-ActivityAlert** oppure utilizzare il cmdlet **New-ActivityAlert** per aggiungere lo stesso utente esterno (o diverso) a un altro avviso. 
