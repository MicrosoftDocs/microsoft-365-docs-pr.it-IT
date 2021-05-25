---
title: Configurare Posta in arrivo evidenziata per tutti gli utenti nell'organizzazione
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: Se si è responsabili della configurazione delle impostazioni di posta elettronica per tutti gli utenti aziendali, questo articolo spiega come configurare la Posta in arrivo evidenziata per gli utenti.
ms.openlocfilehash: ddd0886988072139a199bfc3f6e8adbbf25ad58b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623702"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Configurare Posta in arrivo evidenziata per tutti gli utenti nell'organizzazione

Se si è responsabili della configurazione della posta elettronica per TUTTI gli utenti di un'azienda, questo articolo contiene tutte le informazioni necessarie. Spiega come personalizzare o disattivare l'opzione per l'azienda e risponde alle [domande frequenti](#faq-for-focused-inbox).

Se si vuole disattivare la Posta in arrivo evidenziata solo per il proprio account, vedere [Disattivare Posta in arrivo evidenziata](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  

Per essere certi che gli utenti ricevano specifici messaggi di posta elettronica aziendali, ad esempio dal reparto Risorse umane o Paghe e stipendi, è possibile configurare Posta in arrivo evidenziata in modo che questi messaggi siano inclusi nella visualizzazione Evidenziata. È anche possibile scegliere se consentire agli utenti dell'organizzazione di visualizzare Posta in arrivo evidenziata nella propria cassetta postale.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Attivare o disattivare Posta in arrivo evidenziata nell'organizzazione

Per attivare o disattivare Posta in arrivo evidenziata per tutti gli utenti dell'organizzazione, si usa PowerShell. Si vuole eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365? È possibile comunicarlo al team di progettazione Microsoft. **[Votare qui.](https://go.microsoft.com/fwlink/?linkid=862489)**
  
**Per disattivare la Posta in arrivo evidenziata:**
  
L'esempio di PowerShell seguente **disattiva** la Posta in arrivo evidenziata nell'organizzazione. La funzionalità rimane comunque disponibile per gli utenti, che, se vogliono, possono riabilitarla in ciascuno dei propri client. 
  
1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Per poter eseguire queste procedure occorre aver ricevuto le autorizzazioni appropriate. Per informazioni sulle autorizzazioni necessarie, vedere la voce "Regole di trasporto" in [Criteri di messaggistica e autorizzazioni di conformità](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. Eseguire il cmdlet **Get-OrganizationConfig**. 

    ```powershell
    Get-OrganizationConfig
    ```

4. Cercare **FocusedInboxOn** per visualizzare l'impostazione corrente: 

    ![Risposta di PowerShell sullo stato della Posta in arrivo evidenziata.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Eseguire il cmdlet seguente per disattivare la Posta in arrivo evidenziata.

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. Eseguire di nuovo il cmdlet **Get-OrganizationConfig**. Si vedrà che FocusedInboxOn è impostato su $false, che indica che è disattivato. 

**Per attivare la Posta in arrivo evidenziata:**
  
- Nel passaggio 5 precedente eseguire il cmdlet seguente per attivare la Posta in arrivo evidenziata.

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Cosa vedono gli utenti dopo l'attivazione della Posta in arrivo evidenziata? 

Per accedere alla visualizzazione Evidenziata, gli utenti devono chiudere e riavviare Outlook. Dopo il riavvio di Outlook, nell'interfaccia utente di Outlook vedranno una descrizione comando che consentirà loro di usare la nuova Posta in arrivo evidenziata.
  
![Come appare la funzionalità Posta in arrivo evidenziata quando un utente apre Outlook sul Web per la prima volta.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
Se si passa da Messaggi secondari a Posta in arrivo evidenziata, è possibile scegliere se abilitare ("Prova") o ignorare la funzionalità. Se l'utente ha più client (supportati), può abilitare o disabilitare la Posta in arrivo evidenziata sui singoli client. Il suggerimento è simile a quanto segue:
  
![Come appare la funzionalità Posta in arrivo evidenziata quando viene distribuita agli utenti e Outlook viene riaperto.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
Quando un utente decide di iniziare a usare la Posta in arrivo evidenziata, la funzionalità Messaggi secondari viene disabilitata automaticamente. La cartella Messaggi secondari viene convertita in una cartella standard, che può essere rinominata o eliminata.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Attivare o disattivare la Posta in arrivo evidenziata per utenti specifici

Questo esempio **disattiva** Posta in arrivo evidenziata per Lorenzo Russo nell'organizzazione Contoso. La caratteristica rimarrà comunque disponibile per l’utente che, se vuole, può abilitare di nuovo Posta in arrivo evidenziata in ognuno dei propri client. 
  
1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Prima di eseguire queste procedure, è necessario che siano assegnate le autorizzazioni. Per informazioni sulle autorizzazioni necessarie, vedere la voce "Regole di trasporto" nell'argomento Criteri di messaggistica e autorizzazioni di conformità.

3. Eseguire il cmdlet **Get-FocusedInbox**, ad esempio: 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. Cercare FocusedInboxOn per visualizzare l'impostazione corrente:

    ![Risposta di PowerShell sullo stato della Posta in arrivo evidenziata.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Eseguire il cmdlet seguente per disattivare la Posta in arrivo evidenziata:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    OPPURE, eseguire il cmdlet seguente per attivarla:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Usare l'interfaccia utente per creare una regola di trasporto che indirizzi i messaggi di posta elettronica alla visualizzazione Evidenziata per tutti gli utenti

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.

2. Passare a **Flusso di posta** \> **Regole**. Selezionare l'![icona Aggiungi dell'interfaccia di amministrazione di Exchange](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) e quindi selezionare **Crea nuova regola...**. 

3. Dopo aver creato la nuova regola, selezionare **Salva** per avviarla.

    L'immagine seguente mostra un esempio in cui tutti i messaggi inviati da "Reparto Retribuzioni" devono essere recapitati in Posta in arrivo evidenziata.

    ![focusedinbox payroll](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > Il testo del valore dell’intestazione del messaggio in questo esempio è **X-MS-Exchange-Organization-BypassFocusedInbox**.
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Usare PowerShell per creare una regola di trasporto che indirizzi i messaggi di posta elettronica alla visualizzazione Evidenziata per tutti gli utenti

1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Per poter eseguire queste procedure occorre aver ricevuto le autorizzazioni appropriate. Per informazioni sulle autorizzazioni necessarie, vedere la voce "Regole di trasporto" in [Criteri di messaggistica e autorizzazioni di conformità](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. Eseguire questo comando per consentire il recapito di tutti i messaggi inviati, ad esempio, da "Reparto Retribuzioni" alla Posta in arrivo evidenziata.

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> In questo esempio sia "X-MS-Exchange-Organization-BypassFocusedInbox" che "true" fanno distinzione tra maiuscole e minuscole.
> Inoltre, Posta in arrivo evidenziata rispetterà l'intestazione X per evitare i messaggi secondari, pertanto se si usa questa impostazione in Messaggi secondari, verrà usata anche in Posta in arrivo evidenziata. Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](/powershell/module/exchange/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

È possibile controllare le intestazioni dei messaggi di posta elettronica per vedere se i messaggi vengono spostati nella Posta in arrivo in seguito all'applicazione del bypass della regola di trasporto di Posta in arrivo evidenziata. Selezionare un messaggio di posta elettronica da una cassetta postale dell'organizzazione a cui è applicata la regola di trasporto Posta in arrivo evidenziata. Nelle intestazioni del messaggio cercare **X-MS-Exchange-Organization-BypassFocusedInbox: true**. Se è visualizzato, il bypass è stato applicato. Per informazioni su come trovare le informazioni sull'intestazione, consultare l'articolo [Visualizzare le informazioni di intestazione Internet per un messaggio di posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=822530).

### <a name="what-will-the-user-see"></a>Cosa visualizza l'utente?

Se è presente una regola di trasporto, verrà visualizzata una notifica per l'override. Outlook sul Web disabiliterà il messaggio "Sposta sempre in Altra" e mostrerà una descrizione comando. I client Outlook sul desktop consentiranno la selezione di "Sposta sempre in Altra" e apriranno una finestra di dialogo.

## <a name="turn-onoff-clutter"></a>Attivare/disattivare Messaggi secondari

Alcuni utenti hanno segnalato che la funzionalità Messaggi secondari ha smesso improvvisamente di funzionare. In questo caso, è possibile abilitarla nuovamente per utenti specifici. Vedere [Configurare Messaggi secondari per l'organizzazione](../email/configure-clutter.md).

## <a name="faq-for-focused-inbox"></a>Domande frequenti su Posta in arrivo evidenziata

Ecco le risposte ad alcune domande frequenti su Posta in arrivo evidenziata.

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Si può controllare la distribuzione di Posta in arrivo evidenziata nell'organizzazione?

Sì. È possibile attivare o disattivare Posta in arrivo evidenziata per l'intera organizzazione oppure per utenti specifici. Vedere sopra.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>La funzionalità Posta in arrivo evidenziata è disponibile SOLO per i clienti di Office 2016?

Sì, solo gli utenti di Office 2016 sono interessati. Questa funzionalità non sarà inserita in Outlook 2013 o versioni precedenti.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Quanto tempo richiede l'applicazione delle modifiche di Posta in arrivo evidenziata in Outlook?

Dopo avere attivato o disattivato Posta in arrivo evidenziata, le impostazioni diverranno effettive quando gli utenti chiudono e riavviano Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Che cosa succede a Messaggi secondari dopo l'attivazione di Posta in arrivo evidenziata?

Dopo il passaggio, la posta elettronica meno interattiva non verrà più recapitata nella cartella Messaggi secondari, ma verrà invece suddivisa tra le schede Evidenziata e Altra nella Posta in arrivo. Lo stesso algoritmo di spostamento degli elementi nella cartella Messaggi secondari è ora alla base di Posta in arrivo evidenziata, vale a dire che tutti i messaggi che sono stati impostati per essere spostati in Messaggi secondari verranno ora spostati nella scheda Altra. Tutti i messaggi già presenti nella cartella Messaggi secondari vi rimarranno fino a quando non si decide di eliminarli o spostarli.
  
Vedere questo post di [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP Microsoft: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (Sostituzione di Messaggi secondari con Posta in arrivo evidenziata in Office 365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>È possibile mantenere gli utenti in Messaggi secondari? Che cosa consiglia Microsoft in relazione all'uso di Messaggi secondari e Posta in arrivo evidenziata?

Sì, è possibile mantenere gli utenti in Messaggi secondari e disabilitare Posta in arrivo evidenziata, anche se alla fine la funzionalità Messaggi secondari verrà completamente sostituita da Posta in arrivo evidenziata. Di conseguenza Microsoft consiglia di passare subito a Posta in arrivo evidenziata. Per altre informazioni su come usare Messaggi secondari con Exchange Online, vedere il post di blog di [aggiornamento su Posta in arrivo evidenziata e sul destino di Messaggi secondari](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>È necessario disabilitare Messaggi secondari per gli utenti finali se si intende attivare Posta in arrivo evidenziata per tutti gli utenti?

No. È possibile disabilitare esplicitamente Messaggi secondari per una cassetta postale eseguendo il cmdlet Set-Clutter. Se però si esegue questa operazione, il proprietario della cassetta postale noterà che i messaggi reindirizzati in precedenza a Messaggi secondari rimarranno in Posta in arrivo e dovrà elaborare manualmente tali messaggi finché il proprio client non viene aggiornato a una versione che supporta Posta in arrivo evidenziata. È quindi consigliabile non disabilitare Messaggi secondari finché non sono disponibili i client aggiornati.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Perché sono presenti due diversi cmdlet per la gestione di Posta in arrivo evidenziata?

A Posta in arrivo evidenziata sono associati due stati.
  
- **Livello organizzazione**: Stato di Posta in arrivo evidenziata con timestamp dell'ultimo aggiornamento associato.

- **Livello cassetta postale**: Stato di Posta in arrivo evidenziata con timestamp dell'ultimo aggiornamento associato 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>In che modo Outlook sceglie la visualizzazione di Posta in arrivo evidenziata con questi due stati?

Outlook decide di mostrare la Posta in arrivo evidenziata con il timestamp più recente. Per impostazione predefinita, entrambi i timestamp sono "null" e, in questo caso, la funzionalità è abilitata.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Perché il cmdlet Get-FocusedInbox restituisce "true" quando la Posta in arrivo evidenziata dell'organizzazione viene disattivata?

Sono disponibili due cmdlet per il controllo di Posta in arrivo evidenziata. Quando si esegue il cmdlet Get-FocusedInbox per una cassetta postale, restituisce lo stato della funzionalità a livello della cassetta postale. L'esperienza in Outlook viene scelta in base allo stato del cmdlet modificato per ultimo.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>È possibile eseguire uno script per vedere chi ha attivato la Posta in arrivo evidenziata?

No e si tratta di un comportamento da progettazione. L'abilitazione della Posta in arrivo evidenziata è un'impostazione sul lato client, quindi il cmdlet può solo indicare se la cassetta postale dell'utente è idonea per l'esperienza client. Questa funzionalità potrebbe essere abilitata in alcuni client e disabilitata in altri allo stesso momento, ad esempio abilitata nell'app Outlook e in Outlook Mobile, ma disabilitata in Outlook sul web.

## <a name="related-content"></a>Contenuto correlato

[Configurare Messaggi secondari per l'organizzazione](../email/configure-clutter.md) (articolo)\
[Configurare le impostazioni della cassetta postale condivisa](../email/configure-a-shared-mailbox.md) (articolo)\
[Creare firme e dichiarazioni di non responsabilità](create-signatures-and-disclaimers.md) (video)
