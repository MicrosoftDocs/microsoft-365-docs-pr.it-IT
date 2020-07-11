---
title: Domande frequenti sulla distribuzione centralizzata
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Esaminare le risposte alle domande frequenti sulla distribuzione centralizzata dall'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: b1b5ccbb5373bf5d536208efdfe487bc0c872f25
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102885"
---
# <a name="centralized-deployment-faq"></a>Domande frequenti sulla distribuzione centralizzata

La distribuzione centralizzata è il modo consigliato per un amministratore di Office 365 di distribuire i componenti aggiuntivi di Office (Word, Excel, PowerPoint e Outlook) a utenti e gruppi all'interno di un'organizzazione, purché l'organizzazione soddisfi tutti i requisiti per l'utilizzo della distribuzione centralizzata come illustrato in questo articolo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Come verificare se l'organizzazione è configurata per la distribuzione centralizzata.  

La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino Microsoft 365 Apps for Enterprise (e che siano firmati in Office con le credenziali di accesso dell'organizzazione) e dispongano di cassette postali di Exchange Online. La directory di sottoscrizione deve trovarsi o federata in Azure Active Directory.  
 
La distribuzione centralizzata è supportata solo per le cassette postali online. La distribuzione non è supportata per le cassette postali di Exchange locali.

È possibile utilizzare la [Verifica compatibilità della distribuzione centralizzata](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)   per determinare se la sottoscrizione è idonea. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Come si indirizzano le assegnazioni degli utenti ai componenti aggiuntivi con la distribuzione centralizzata?  

La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e tutti i clienti del tenant. La distribuzione centralizzata può essere utilizzata per gli utenti di gruppi o gruppi di primo livello senza gruppi padre, ma non per gli utenti di gruppi o gruppi nidificati con gruppi padre. La distribuzione centralizzata fa anche parte della maggior parte dei gruppi di Azure Active Directory, inclusi i gruppi di Office 365, le liste di distribuzione e i gruppi di sicurezza.  

È preferibile utilizzare le assegnazioni dei gruppi anziché l'assegnazione di singoli utenti per semplificare la gestione.
 
Per ulteriori informazioni, vedere [assegnazioni di utenti e gruppi](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Quanto tempo occorre per visualizzare i componenti aggiuntivi per tutti gli utenti?  

È possibile richiedere fino a 24 ore affinché un componente aggiuntivo venga visualizzato per tutti gli utenti. Può richiedere la stessa quantità di tempo per gli aggiornamenti del componente aggiuntivo, le modifiche apportate alle rimozioni di attivazione o disattivazione o di aggiunta. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Come amministratore, come è possibile gestire l'accesso degli utenti ai componenti aggiuntivi per l'organizzazione?

Per semplificare la distribuzione dei componenti aggiuntivi agli utenti, ai gruppi o all'intera organizzazione, è consigliabile che gli amministratori utilizzino la distribuzione centralizzata.

Per ulteriori informazioni sulla gestione dell'accesso degli utenti, vedere:
 - [Impedisci download del componente aggiuntivo disattivando l'archivio di Office in tutti i client (eccetto Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Specifica degli amministratori e degli utenti in grado di installare e gestire componenti aggiuntivi per Outlook](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>La distribuzione centralizzata fornisce agli amministratori la possibilità di scegliere il metodo di distribuzione per i componenti aggiuntivi di Outlook?  

Sì. La distribuzione centralizzata fornisce agli amministratori la possibilità di scegliere uno dei tre metodi di distribuzione per i componenti aggiuntivi di Outlook durante la distribuzione dei componenti aggiuntivi:

**Risolto (impostazione predefinita)**   Il componente aggiuntivo viene distribuito automaticamente agli utenti assegnati e non è possibile rimuoverlo.  
 
**Disponibile** Gli utenti possono installare il componente aggiuntivo in Outlook scegliendo **Home > ottenere altri componenti aggiuntivi > gestiti dall'amministratore**.
 
**Facoltativo** Il componente aggiuntivo viene distribuito automaticamente agli utenti assegnati, ma è possibile sceglierlo per rimuoverlo.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Gli amministratori possono aggiornare i componenti aggiuntivi line-of-business (LOB)?  

Sì. Gli amministratori possono caricare un nuovo file manifesto per supportare le modifiche ai metadati per i componenti aggiuntivi LOB distribuiti dall'amministratore. Il componente aggiuntivo viene aggiornato la volta successiva che vengono avviate le applicazioni di Office. L'applicazione Web può essere modificata in qualsiasi momento.  
 
Per ulteriori informazioni, vedere [componente aggiuntivo line-of-business](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security).  

## <a name="can-admins-turn-off-add-ins"></a>Gli amministratori possono disattivare i componenti aggiuntivi?  

Sì. Gli amministratori possono abilitare o disabilitare i componenti aggiuntivi che distribuiscono per tutti gli utenti dall'interfaccia di amministrazione di Microsoft.

Per ulteriori informazioni, vedere [stati dei componenti](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)aggiuntivi.  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Gli amministratori possono eliminare o rimuovere i componenti aggiuntivi?

Sì. Gli amministratori possono eliminare i componenti aggiuntivi che sono stati distribuiti per tutti gli utenti dall'interfaccia di amministrazione di Microsoft.

Per ulteriori informazioni, vedere [eliminare un componente aggiuntivo](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Gli amministratori possono distribuire i componenti aggiuntivi a pagamento da Office Store utilizzando la distribuzione centralizzata? 

No. Non è possibile distribuire i componenti aggiuntivi a pagamento da Office Store utilizzando la distribuzione centralizzata in questo momento.  
 
È consigliabile contattare lo sviluppatore ISV per il componente aggiuntivo a pagamento per richiedere un file manifesto o un URL. L'amministratore del tenant può quindi distribuire il componente aggiuntivo come componente aggiuntivo LOB utilizzando la distribuzione centralizzata.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Quale ruolo di amministratore è necessario per gestire i componenti aggiuntivi per l'organizzazione?  

Per gestire i componenti aggiuntivi è necessario disporre del ruolo di amministratore globale. Se si è la persona che ha acquistato l'abbonamento a Microsoft 365 per le aziende, si è l'amministratore globale. 
 
L'abbonamento viene fornito con un set di ruoli di amministratore che è possibile assegnare ad altri utenti dell'organizzazione. Ogni ruolo di amministratore esegue il mapping alle funzioni aziendali comuni e fornisce alle persone delle autorizzazioni dell'organizzazione l'esecuzione di attività specifiche nell'interfaccia di amministrazione di Microsoft 365.  
 
Per ulteriori informazioni, vedere [assegnare ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).  
