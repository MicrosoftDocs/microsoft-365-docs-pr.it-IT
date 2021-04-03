---
title: Domande frequenti sulla distribuzione centralizzata
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Leggere le risposte alle domande frequenti sulla distribuzione centralizzata dall'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579303"
---
# <a name="centralized-deployment-faq"></a>Domande frequenti sulla distribuzione centralizzata

La distribuzione centralizzata è il modo consigliato per un amministratore di Office 365 per distribuire componenti aggiuntivi di Office (Word, Excel, PowerPoint e Outlook) a utenti e gruppi all'interno di un'organizzazione, purché l'organizzazione soddisfi tutti i requisiti per l'utilizzo della distribuzione centralizzata, come descritto in questo articolo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Come è possibile sapere se l'organizzazione è impostata per la distribuzione centralizzata?  

La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino Microsoft 365 Apps for enterprise (e siano connessi a Office con le credenziali di accesso dell'organizzazione) e che le cassette postali di Exchange Online siano disponibili. La directory di sottoscrizione deve essere in Azure Active Directory o federata.  
 
La distribuzione centralizzata è supportata solo per le cassette postali online. Non supporta la distribuzione alle cassette postali di Exchange locali.

È possibile utilizzare Verifica compatibilità distribuzione [centralizzata](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   per determinare se l'abbonamento è idoneo. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Come vengono mirate le assegnazioni degli utenti dei componenti aggiuntivi con la distribuzione centralizzata?  

La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e a tutti gli utenti del tenant. La distribuzione centralizzata può essere utilizzata per gli utenti di gruppi di primo livello o gruppi senza gruppi padre, ma non per gli utenti di gruppi annidati o gruppi con gruppi padre. La distribuzione centralizzata fa anche parte della maggior parte dei gruppi di Azure Active Directory, inclusi i gruppi di Office 365, le liste di distribuzione e i gruppi di sicurezza.  

È meglio usare le assegnazioni dei gruppi anziché l'assegnazione di singoli utenti per semplificare la gestione.
 
Per ulteriori informazioni, vedere [Assegnazioni di utenti e gruppi.](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments)  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Quanto tempo è necessario per la visualizzazione dei componenti aggiuntivi per tutti gli utenti?  

La visualizzazione di un componente aggiuntivo per tutti gli utenti può richiedere fino a 24 ore. Può richiedere la stessa quantità di tempo per gli aggiornamenti dei componenti aggiuntivi, le modifiche dall'attivazione o dalla disattivazione o le rimozioni dei componenti aggiuntivi. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Come amministratore, come si gestisce l'accesso utente ai componenti aggiuntivi per l'organizzazione?

Per una distribuzione agevole dei componenti aggiuntivi a utenti, gruppi o all'intera organizzazione, è consigliabile che gli amministratori utilizzino la distribuzione centralizzata.

Per ulteriori informazioni sulla gestione dell'accesso utente, vedere:
 - [Impedire i download di componenti aggiuntivi disattivando Office Store in tutti i client (ad eccezione di Outlook)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Specifica degli amministratori e degli utenti in grado di installare e gestire componenti aggiuntivi per Outlook](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>La distribuzione centralizzata offrirà agli amministratori la flessibilità di scegliere il metodo di distribuzione per i componenti aggiuntivi di Outlook?  

Sì. La distribuzione centralizzata offre agli amministratori la flessibilità di scegliere uno dei tre metodi di distribuzione per i componenti aggiuntivi di Outlook durante la distribuzione dei componenti aggiuntivi:

**Risolto (predefinito)**   Il componente aggiuntivo viene distribuito automaticamente agli utenti assegnati e non può essere rimosso.  
 
**Disponibile** Gli utenti possono installare il componente aggiuntivo in Outlook scegliendo Home > Altri componenti aggiuntivi **> gestito dall'amministratore.**
 
**Facoltativo** Il componente aggiuntivo viene distribuito automaticamente agli utenti assegnati, ma può scegliere di rimuoverlo.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Gli amministratori possono aggiornare i componenti aggiuntivi Line-of-Business (LOB) ?  

Sì. Gli amministratori possono caricare un nuovo file manifesto per supportare le modifiche dei metadati per i componenti aggiuntivi LOB distribuiti dall'amministratore. Il componente aggiuntivo viene aggiornato al successivo avvio delle applicazioni di Office. L'applicazione Web può essere modificata in qualsiasi momento.  
 
Per ulteriori informazioni, vedere componente aggiuntivo [line-of-business](./manage-addins-in-the-admin-center.md).  

## <a name="can-admins-turn-off-add-ins"></a>Gli amministratori possono disattivare i componenti aggiuntivi?  

Sì. Gli amministratori possono attivare o disattivare i componenti aggiuntivi distribuiti per tutti gli utenti dall'interfaccia di amministrazione di Microsoft.

Per ulteriori informazioni, vedere [Stati dei componenti aggiuntivi](./manage-addins-in-the-admin-center.md#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Gli amministratori possono eliminare o rimuovere componenti aggiuntivi?

Sì. Gli amministratori possono eliminare i componenti aggiuntivi distribuiti per tutti gli utenti dall'interfaccia di amministrazione di Microsoft.

Per ulteriori informazioni, vedere [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Gli amministratori possono distribuire componenti aggiuntivi a pagamento da Office Store tramite la distribuzione centralizzata? 

No. Non è possibile distribuire componenti aggiuntivi a pagamento da Office Store utilizzando la distribuzione centralizzata in questo momento.  
 
Ti consigliamo di contattarlo per lo sviluppatore ISV per il componente aggiuntivo a pagamento per richiedere un file manifesto o un URL. L'amministratore tenant può quindi distribuire il componente aggiuntivo come componente aggiuntivo LOB tramite distribuzione centralizzata.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Quale ruolo di amministratore è necessario per gestire i componenti aggiuntivi per l'organizzazione?  

L'amministratore globale è il ruolo consigliato con accesso completo al ciclo di vita di gestione dei componenti aggiuntivi. Altri ruoli di amministratore hanno un accesso limitato al ciclo di vita della distribuzione dei componenti aggiuntivi. Se sei la persona che ha acquistato l'abbonamento a Microsoft 365 per le aziende, sei l'amministratore globale. 
 
La sottoscrizione include un set di ruoli di amministratore che è possibile assegnare ad altri utenti dell'organizzazione. Ogni ruolo di amministratore è mappato a funzioni aziendali comuni e fornisce agli utenti dell'organizzazione le autorizzazioni per eseguire attività specifiche nell'interfaccia di amministrazione di Microsoft 365.  
 
Per ulteriori informazioni, vedere [Assegnare ruoli di amministratore.](../add-users/assign-admin-roles.md?view=o365-worldwide) 