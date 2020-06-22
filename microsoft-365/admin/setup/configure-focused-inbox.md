---
title: Configurare Posta in arrivo evidenziata per tutti gli utenti nell'organizzazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: "Informazioni su come configurare Posta in arrivo evidenziata per tutti gli utenti o per utenti specifici dell'organizzazione. "
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779930"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Configurare Posta in arrivo evidenziata per tutti gli utenti nell'organizzazione

  Se si è responsabili della configurazione della posta elettronica per TUTTI gli utenti di un'azienda, questo articolo contiene tutte le informazioni necessarie. Spiega come personalizzare o disattivare l'opzione per l'azienda e risponde alle [domande frequenti](#faq-for-focused-inbox).  <br/> Se si vuole disattivare la Posta in arrivo evidenziata solo per il proprio account, vedere [Disattivare Posta in arrivo evidenziata](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Attivare o disattivare Posta in arrivo evidenziata nell'organizzazione

Per attivare o disattivare Posta in arrivo evidenziata per tutti gli utenti dell'organizzazione, si usa PowerShell. Si vuole eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365? È possibile comunicarlo al team di progettazione Microsoft. **[Votare qui.](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **Per disattivare la Posta in arrivo evidenziata:**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. Eseguire il cmdlet **Get-OrganizationConfig**. 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. Cercare **FocusedInboxOn** per visualizzare l'impostazione corrente: 
    
    ![Risposta di PowerShell sullo stato della Posta in arrivo evidenziata.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Eseguire il cmdlet seguente per disattivare la Posta in arrivo evidenziata.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. Eseguire di nuovo il cmdlet **Get-OrganizationConfig**. Si vedrà che FocusedInboxOn è impostato su $false, che indica che è disattivato. 
    
 **Per attivare la Posta in arrivo evidenziata:**
  
- Nel passaggio 5 precedente eseguire il cmdlet seguente per attivare la Posta in arrivo evidenziata.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Cosa vedono gli utenti dopo l'attivazione della Posta in arrivo evidenziata? 

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![Come appare la funzionalità Posta in arrivo evidenziata quando un utente apre Outlook sul Web per la prima volta.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![Come appare la funzionalità Posta in arrivo evidenziata quando viene distribuita agli utenti e Outlook viene riaperto.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Attivare o disattivare la Posta in arrivo evidenziata per utenti specifici

This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients. 
  
1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. Eseguire il cmdlet **Get-FocusedInbox**, ad esempio: 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. Cercare FocusedInboxOn per visualizzare l'impostazione corrente:
    
    ![Risposta di PowerShell sullo stato della Posta in arrivo evidenziata.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Eseguire il cmdlet seguente per disattivare la Posta in arrivo evidenziata:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. OPPURE, eseguire il cmdlet seguente per attivarla:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Usare l'interfaccia utente per creare una regola di trasporto che indirizzi i messaggi di posta elettronica alla visualizzazione Evidenziata per tutti gli utenti

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.
    
2. Passare a **Flusso di posta** \> **Regole**. Selezionare l'![icona Aggiungi dell'interfaccia di amministrazione di Exchange](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) e quindi selezionare **Crea nuova regola...**. 
    
3. Dopo aver creato la nuova regola, selezionare **Salva** per avviarla. 
    
    L'immagine seguente mostra un esempio in cui tutti i messaggi inviati da "Reparto Retribuzioni" devono essere recapitati in Posta in arrivo evidenziata.
    
    ![focusedinbox payroll](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Usare PowerShell per creare una regola di trasporto che indirizzi i messaggi di posta elettronica alla visualizzazione Evidenziata per tutti gli utenti

1. [Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. Eseguire questo comando per consentire il recapito di tutti i messaggi inviati, ad esempio, da "Reparto Retribuzioni" alla Posta in arrivo evidenziata.
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> In questo esempio sia "X-MS-Exchange-Organization-BypassFocusedInbox" che "true" fanno distinzione tra maiuscole e minuscole.
> Inoltre, Posta in arrivo evidenziata rispetterà l'intestazione X per evitare i messaggi secondari, pertanto se si usa questa impostazione in Messaggi secondari, verrà usata anche in Posta in arrivo evidenziata. Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

È possibile controllare le intestazioni dei messaggi di posta elettronica per vedere se i messaggi vengono spostati nella Posta in arrivo in seguito all'applicazione del bypass della regola di trasporto di Posta in arrivo evidenziata. Selezionare un messaggio di posta elettronica da una cassetta postale dell'organizzazione a cui è applicata la regola di trasporto Posta in arrivo evidenziata. Nelle intestazioni del messaggio cercare **X-MS-Exchange-Organization-BypassFocusedInbox: true**. Se è visualizzato, il bypass è stato applicato. Per informazioni su come trovare le informazioni sull'intestazione, consultare l'articolo [Visualizzare le informazioni di intestazione Internet per un messaggio di posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=822530). 
 
## <a name="turn-onoff-clutter"></a>Attivare/disattivare Messaggi secondari
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>Domande frequenti su Posta in arrivo evidenziata

Ecco le risposte ad alcune domande frequenti su Posta in arrivo evidenziata. 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Si può controllare la distribuzione di Posta in arrivo evidenziata nell'organizzazione?

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>La funzionalità Posta in arrivo evidenziata è disponibile SOLO per i clienti di Office 2016?

Sì, solo gli utenti di Office 2016 sono interessati. Questa funzionalità non sarà inserita in Outlook 2013 o versioni precedenti.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Quanto tempo richiede l'applicazione delle modifiche di Posta in arrivo evidenziata in Outlook?

Dopo avere attivato o disattivato Posta in arrivo evidenziata, le impostazioni diverranno effettive quando gli utenti chiudono e riavviano Outlook.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Che cosa succede a Messaggi secondari dopo l'attivazione di Posta in arrivo evidenziata?

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
Vedere questo post di [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP Microsoft: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (Sostituzione di Messaggi secondari con Posta in arrivo evidenziata in Office 365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>È possibile mantenere gli utenti in Messaggi secondari? Che cosa consiglia Microsoft in relazione all'uso di Messaggi secondari e Posta in arrivo evidenziata?

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>È necessario disabilitare Messaggi secondari per gli utenti finali se si intende attivare Posta in arrivo evidenziata per tutti gli utenti?

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Perché sono presenti due diversi cmdlet per la gestione di Posta in arrivo evidenziata?

A Posta in arrivo evidenziata sono associati due stati.
  
- **Livello organizzazione**: Stato di Posta in arrivo evidenziata con timestamp dell'ultimo aggiornamento associato. 
    
- **Livello cassetta postale**: Stato di Posta in arrivo evidenziata con timestamp dell'ultimo aggiornamento associato 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>In che modo Outlook sceglie la visualizzazione di Posta in arrivo evidenziata con questi due stati?

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Perché il cmdlet Get-FocusedInbox restituisce "true" quando la Posta in arrivo evidenziata dell'organizzazione viene disattivata?

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>È possibile eseguire uno script per vedere chi ha attivato la Posta in arrivo evidenziata?

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
