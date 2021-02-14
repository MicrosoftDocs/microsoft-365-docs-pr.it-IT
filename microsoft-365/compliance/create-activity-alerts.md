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
description: Aggiungere e gestire avvisi attività nel Centro sicurezza & conformità in modo che Microsoft 365 invii notifiche tramite posta elettronica quando gli utenti eseguono attività specifiche
ms.openlocfilehash: ac78c57d368e27c43cc5f25733d49fad5fe4374a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818025"
---
# <a name="create-activity-alerts"></a>Creare avvisi attività

È possibile creare un avviso attività che invierà una notifica tramite posta elettronica quando gli utenti eseguono attività specifiche in Office 365. Gli avvisi attività sono simili alla ricerca di eventi nel log di controllo, con la differenza che verrà inviato un messaggio di posta elettronica quando si verifica un evento per un'attività per cui è stato creato un avviso. 
  
 **Perché usare gli avvisi attività invece di eseguire ricerche nel log di controllo?** È possibile che alcuni tipi di attività o attività eseguite da utenti specifici siano effettivamente da conoscere. Anziché ricordare di cercare tali attività nel log di controllo, è possibile usare gli avvisi attività per fare in modo che Microsoft 365 invii un messaggio di posta elettronica quando gli utenti eseguono tali attività. Ad esempio, è possibile creare un avviso attività per notificare quando un utente elimina i file in SharePoint oppure è possibile creare un avviso per informare l'utente quando un utente elimina definitivamente i messaggi dalla propria cassetta postale. La notifica tramite posta elettronica inviata include informazioni sull'attività eseguita e sull'utente che l'ha eseguita.

> [!NOTE]
> Gli avvisi attività sono deprecati. È consigliabile iniziare a usare i criteri di avviso nel Centro sicurezza e conformità invece di creare nuovi avvisi attività. I criteri di avviso forniscono funzionalità aggiuntive, ad esempio la possibilità di creare un criterio di  avviso che attiva un avviso quando un utente esegue un'attività specificata e di visualizzare avvisi nella pagina Visualizza avvisi nel Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Criteri di avviso.](alert-policies.md)
  
## <a name="confirm-roles-and-configure-audit-logging"></a>Verificare i ruoli e configurare la registrazione di controllo

- Per gestire gli avvisi di attività, è necessario disporre del ruolo Configurazione organizzazione nel Centro sicurezza & conformità. Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli Amministratore conformità e Gestione organizzazione. Per ulteriori informazioni sull'aggiunta di membri ai gruppi di ruoli, vedere Concedere agli utenti l'accesso al [Centro sicurezza & conformità.](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)
    
- Prima di iniziare a usare gli avvisi attività, è necessario che tu o un altro amministratore attivi la registrazione di controllo per l'organizzazione. A tale scopo, è sufficiente fare clic su **Avvia registrazione attività** utente e amministratore nella pagina **Avvisi** attività. Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione. È anche possibile attivare il controllo nella pagina di ricerca del **log** di controllo nel Centro sicurezza & conformità (andare **a Ricerca** log \> **di controllo**). È necessario eseguire questa operazione solo una volta per l'organizzazione.
  
- È possibile creare avvisi per le stesse attività che è possibile cercare nel log di controllo. Vedi la [sezione Altre informazioni](#more-information) per un elenco degli scenari comuni (e dell'attività specifica da monitorare) per cui puoi creare avvisi. 
    
- È possibile utilizzare **la** pagina Avvisi attività nel Centro sicurezza & conformità per creare avvisi solo per le attività eseguite dagli utenti elencati nella rubrica dell'organizzazione. Non è possibile utilizzare questa pagina per creare avvisi per attività eseguite da utenti esterni non elencati nella rubrica. 
    
## <a name="create-an-activity-alert"></a>Creare un avviso attività

1. Passare a [https://protection.office.com/managealerts](https://protection.office.com/managealerts).
    
2. Accedere usando l'account di lavoro o della scuola.
    
3. Nella pagina **Avvisi attività fare** clic su Aggiungi icona ![ ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Nuovo.**

   Viene visualizzata la pagina del riquadro a comparsa per creare un avviso attività.

    
    ![Creare un avviso attività](../media/53888bd5-9fa2-4398-8ccc-1a9dc72517ac.png)
  
4. Completare i campi seguenti per creare un avviso attività:
    
    a. **Nome:** digitare un nome per l'avviso. I nomi degli avvisi devono essere univoci all'interno dell'organizzazione.
    
    b. **Descrizione** (facoltativo): descrivere l'avviso, ad esempio le attività e gli utenti monitorati e gli utenti a cui vengono inviate notifiche tramite posta elettronica. Le descrizioni forniscono un modo semplice e rapido per descrivere lo scopo dell'avviso ad altri amministratori.
    
    c. **Tipo di** avviso: verifica che **l'opzione** Personalizzata sia selezionata. 

    d. **Invia questo avviso quando** - Fai clic su **Invia questo avviso quando** e quindi configura questi due campi:
    
    - **Attività:** fare clic sull'elenco a discesa per visualizzare le attività per cui è possibile creare un avviso. Si tratta dello stesso elenco di attività visualizzato quando si esegue una ricerca nel log di controllo. È possibile selezionare una o più attività specifiche oppure fare clic sul nome del gruppo di attività per selezionare tutte le attività nel gruppo. Per una descrizione di queste attività, vedere la sezione "Attività verificate" in [Ricerca nel log di controllo.](search-the-audit-log-in-security-and-compliance.md#audited-activities) Quando un utente esegue una qualsiasi delle attività aggiunte all'avviso, viene inviata una notifica tramite posta elettronica. 
    
     - **Utenti:** fare clic su questa casella e quindi selezionare uno o più utenti. Se gli utenti in questa casella eseguono  le attività aggiunte alla casella Attività, verrà inviato un avviso. Lasciare vuota **la casella** Utenti per inviare un avviso quando un utente dell'organizzazione esegue le attività specificate dall'avviso. 

    e. Invia questo avviso  **a:** fare clic su  Invia questo avviso, quindi fare clic nella casella Destinatari e digitare un nome per aggiungere un  utente che riceverà una notifica tramite posta elettronica quando un utente (specificato nella casella Utenti) esegue un'attività (specificata nella casella Attività).  Si noti che l'utente viene aggiunto all'elenco dei destinatari per impostazione predefinita. È possibile rimuovere il proprio nome dall'elenco.
    
5. Fare **clic su** Salva per creare l'avviso. 
    
    Il nuovo avviso viene visualizzato nell'elenco nella **pagina Avvisi** attività. 
    
    ![Nella pagina Avvisi attività viene visualizzato un elenco di avvisi](../media/02b774f2-1719-41de-bbc9-5e5b7576f335.png)
  
    Lo stato dell'avviso è impostato su **Attivato.** Si noti che vengono elencati anche i destinatari che riceveranno una notifica tramite posta elettronica quando viene inviato un avviso. 
  
## <a name="turn-off-an-activity-alert"></a>Disattivare un avviso attività

È possibile disattivare un avviso attività in modo che non sia inviata una notifica tramite posta elettronica. Dopo aver disattivato l'avviso attività, questo viene comunque visualizzato nell'elenco degli avvisi attività per l'organizzazione ed è comunque possibile visualizzarne le proprietà.
  
1. Passare a [https://protection.office.com/managealerts](https://protection.office.com/managealerts) .
    
2. Accedere usando l'account aziendale o dell'istituto di istruzione.
    
3. Nell'elenco degli avvisi attività per l'organizzazione fare clic sull'avviso che si desidera disattivare.
    
4. Nella pagina **Modifica avviso** fare clic **sull'interruttore** Attiva per impostare lo stato su **Disattivato** e quindi su **Salva.**
    
    Lo stato dell'avviso nelle pagine **Avvisi** attività è impostato su **Disattivato.** 
    
Per riattivare un avviso attività, ripeti questi passaggi e fai clic sull'interruttore **Disattiva** per impostare lo stato su **Attivato.**
  
## <a name="more-information"></a>Altre informazioni

- Ecco un esempio di notifica tramite posta elettronica inviata agli utenti specificati nel campo Invia  questo  avviso a (ed elencati in Destinatari nella pagina Avvisi attività) nel Centro sicurezza & conformità. 
    
    ![Esempio di notifica tramite posta elettronica inviata per un avviso attività](../media/a5f91611-fae6-4fe9-82f5-58521a2e2541.png)
  
- Ecco alcune attività comuni relative a documenti e messaggi di posta elettronica per cui è possibile creare avvisi attività. Le tabelle descrivono l'attività, il nome dell'attività per cui creare un avviso e il  nome del gruppo di attività in cui l'attività è elencata nell'elenco a discesa Attività. Per visualizzare un elenco completo delle attività per cui è possibile creare avvisi attività, vedere la sezione "Attività verificate" nel log [di controllo.](search-the-audit-log-in-security-and-compliance.md#audited-activities)
    
    > [!TIP]
    > È possibile creare un avviso attività per una sola attività eseguita da qualsiasi utente. In caso di creazione di un avviso attività che tiene traccia di più attività eseguite da uno o più utenti. 
  
    Nella tabella seguente sono elencate alcune attività comuni relative ai documenti in SharePoint o OneDrive for Business.
    
    |**Quando un utente esegue questa operazione...**|**Creare un avviso per questa attività**|**Gruppo attività**|
    |:-----|:-----|:-----|
    |Visualizza un documento in un sito.  <br/> |File aperto  <br/> |Attività su file e cartelle  <br/> |
    |Modifica o modifica un documento.  <br/> |File modificato  <br/> |Attività su file e cartelle  <br/> |
    |Condivide un documento con un utente esterno all'organizzazione.  <br/> |Condividere file, cartella o sito  <br/> E  <br/> Invito alla condivisione creato  <br/> Per altre informazioni, vedere [Usare il controllo della condivisione nel log di controllo](use-sharing-auditing.md).  <br/> |Attività di richiesta di accesso e condivisione  <br/> |
    |Carica o scarica un documento.  <br/> |File caricato  <br/> E/o  <br/> File scaricato  <br/> |Attività su file e cartelle  <br/> |
    |Modifica le autorizzazioni di accesso a un sito.  <br/> |Autorizzazioni sito modificate  <br/> |Attività di amministrazione siti  <br/> |

    Nella tabella seguente sono elencate alcune attività comuni relative alla posta elettronica in Exchange Online.

    |**Quando un utente esegue questa operazione...**|**Creare un avviso per questa attività**|**Gruppo attività**|
    |:-----|:-----|:-----|
    |Elimina definitivamente (elimina) un messaggio di posta elettronica dalla propria cassetta postale.  <br/> |Messaggi eliminati dalla cassetta postale  <br/> | Attività su cassette postali di Exchange  <br/> |
    |Invia un messaggio di posta elettronica da una cassetta postale condivisa.  <br/> |Messaggio inviato con autorizzazioni Invia come  <br/> E  <br/> Messaggio inviato con autorizzazioni Invia per conto di  <br/> | Attività su cassette postali di Exchange  <br/> |
   
- È inoltre possibile utilizzare i cmdlet **New-ActivityAlert** e **Set-ActivityAlert** in PowerShell per Centro sicurezza & conformità per creare e modificare avvisi attività. Tenere presente quanto segue se si utilizzano questi cmdlet per creare o modificare avvisi attività: 
    
  - Se si utilizza un cmdlet per aggiungere un'attività all'avviso non elencato nell'elenco a discesa Attività, nella pagina delle proprietà viene visualizzato un messaggio per l'avviso "Questo avviso contiene operazioni personalizzate non elencate nella selezione".  
    
  - Un buon motivo per utilizzare i cmdlet per creare o modificare un avviso attività è l'invio di notifiche tramite posta elettronica a un utente esterno all'organizzazione. Questo utente esterno verrà elencato nell'elenco dei destinatari per l'avviso. Tuttavia, se si rimuove questo utente esterno dall'avviso, tale utente non può essere aggiunto di nuovo all'avviso utilizzando la **pagina Modifica** avviso. Sarà necessario aggiungere nuovamente l'utente esterno utilizzando il cmdlet **Set-ActivityAlert** oppure utilizzare il cmdlet **New-ActivityAlert** per aggiungere lo stesso (o diverso) utente esterno a un nuovo avviso. 
