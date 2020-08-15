---
title: Strumenti per gestire gli account utente di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Informazioni sugli strumenti da utilizzare e su come gestire gli account Microsoft 365.
ms.openlocfilehash: 205c61c0cff896f93069d225c84dc3086ca30eb5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691445"
---
# <a name="tools-to-manage-microsoft-365-user-accounts"></a>Strumenti per gestire gli account utente di Microsoft 365

È possibile gestire gli utenti di Microsoft 365 in vari modi, a seconda della configurazione. È possibile gestire gli utenti nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com), Windows PowerShell, in servizi di dominio Active Directory (ad DS) o nel portale di amministrazione di Azure Active Directory (Azure ad). 

Non appena si acquista Microsoft 365, è possibile utilizzare l'interfaccia di amministrazione e Windows PowerShell per gestire gli account. Quando si gestiscono le identità cloud, ogni persona dell'organizzazione ha un ID utente e una password distinti per Microsoft 365. Se si desidera eseguire l'integrazione con l'infrastruttura locale e fare in modo che gli account utente siano sincronizzati con Microsoft 365, è possibile utilizzare Azure AD Connect per fornire la sincronizzazione delle identità e delle password per la funzionalità Single Sign-on.
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Pianificare la posizione e la modalità di gestione degli account utente

Il percorso e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per Microsoft 365. I due modelli complessivi sono autenticazione del cloud e autenticazione federata.
  
### <a name="cloud-authentication"></a>Autenticazione del cloud

- Autenticazione cloud: creare e gestire gli utenti nell'interfaccia di amministrazione di Microsoft 365. È inoltre possibile utilizzare Windows PowerShell o Azure AD. 
    
- Sincronizzazione della password hash (pH) con Single Sign-on senza soluzione di continuità: il modo più semplice per abilitare l'autenticazione per gli oggetti di servizi di dominio Active Directory in Azure AD. Con pH, è possibile sincronizzare gli oggetti dell'account utente di servizi di dominio Active Directory con Microsoft 365 e gestire gli utenti in locale. 
    
- Autenticazione pass-through (PTA) con accesso Single Sign-on-fornisce una semplice convalida delle password per i servizi di autenticazione di Azure AD utilizzando un agente software in esecuzione su uno o più server locali per convalidare gli utenti direttamente con il servizio di dominio Active Directory. 
    
### <a name="federated-authentication"></a>Autenticazione federata

- Opzioni di autenticazione federata-principalmente per organizzazioni aziendali di grandi dimensioni con requisiti di autenticazione più complessi, gli oggetti di servizi di dominio Active Directory vengono sincronizzati con Microsoft 365 e gli account utente vengono gestiti in locale. 
    
- [Autenticazione di terze parti e provider di identità](about-microsoft-365-identity.md) -gli oggetti di servizi di dominio Active Directory possono essere sincronizzati con Microsoft 365 e l'accesso alle risorse cloud è gestito principalmente da un provider di identità di terze parti. 
    
## <a name="managing-accounts"></a>Gestione degli account

Quando si decide in che modo l'organizzazione creerà e gestirà gli account, prendere in considerazione i requisiti seguenti:
  
- Il software di sincronizzazione della directory deve essere installato nei server all'interno dell'ambiente locale per connettere le identità tra Microsoft 365 e il servizio AD DS.
    
- Qualsiasi opzione di sincronizzazione della directory, incluse le opzioni SSO, richiede che gli attributi di AD DS soddisfino gli standard. Le specifiche di quali attributi vengono utilizzate nella directory e quali operazioni di pulizia (se presenti) sono necessarie sono descritte in [Prepare to provisioning users through Directory Synchronization to Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Pianificare il modo in cui si intende creare gli account Microsoft 365.
    
    Nella tabella seguente sono elencati i diversi strumenti di gestione degli account.
    
|**Opzione**|**Note**|
|:-----|:-----|
|Interfaccia di amministrazione  <br/> |[Aggiungere utenti singolarmente o in blocco](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Fornisce una semplice interfaccia Web per aggiungere e modificare gli account utente.  <br/>  Non può essere utilizzato per modificare gli utenti se la sincronizzazione della directory è abilitata (è possibile impostare il percorso e l'assegnazione delle licenze).  <br/>  Non può essere utilizzato con le opzioni SSO.  <br/> |
|Windows PowerShell  <br/> |[Gestire Microsoft 365 con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Consente di aggiungere utenti in blocco tramite uno script di Windows PowerShell.  <br/>  Può essere utilizzato per assegnare posizioni e licenze agli account, indipendentemente dal modo in cui vengono creati gli account.  <br/> |
|Importazione in blocco  <br/> |[Aggiungere più utenti contemporaneamente](add-several-users-at-the-same-time.md) <br/>  Consente di importare un file CSV per aggiungere un gruppo di utenti a Microsoft 365.  <br/>  Non può essere utilizzato con le opzioni SSO.  <br/> |
|Azure AD  <br/> |È possibile ottenere un'edizione gratuita di Azure AD con l'abbonamento a Microsoft 365. È possibile eseguire funzioni quali la reimpostazione della password in modalità self-service per gli utenti cloud e la personalizzazione delle pagine di accesso e del riquadro di Access tramite la versione gratuita. Per ottenere funzionalità migliorate, è possibile eseguire l'aggiornamento a Basic Edition, Azure AD Premium P1 o Azure AD Premium P2. Vedere le [edizioni di Azure ad](https://go.microsoft.com/fwlink/p/?LinkId=698465) per l'elenco delle funzionalità supportate.  <br/> |
|Sincronizzazione della directory  <br/> |[Integrazione delle identità locali con Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Per la sincronizzazione della directory con o senza la sincronizzazione delle password, utilizzare [Azure ad Connect with Express Settings](https://go.microsoft.com/fwlink/p/?LinkID=698537).  <br/>  Per più foreste e opzioni SSO, utilizzare l' [installazione personalizzata di Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).  <br/>  Fornisce l'infrastruttura necessaria per abilitare SSO.  <br/>  Necessario per molti scenari ibridi:  <br/>  Migrazione a fasi  <br/>  Exchange ibrido  <br/>  Sincronizza i gruppi di sicurezza e abilitati alla posta elettronica da servizi di dominio Active Directory.  <br/> |
   
- Indipendentemente dal modo in cui si intende aggiungere gli account utente a Microsoft 365, è necessario gestire diverse funzionalità dell'account, ad esempio l'assegnazione di licenze, la specifica del percorso e così via. Queste funzionalità possono essere gestite a lungo termine dall'interfaccia di amministrazione oppure è anche possibile [creare account utente con PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=717083).
    
    Se si sceglie di aggiungere e gestire tutti gli utenti tramite l'interfaccia di amministrazione, è possibile specificare il percorso e assegnare le licenze contemporaneamente alla creazione dell'account Microsoft 365. Di conseguenza, non è necessaria una pianificazione eccessiva.
    
    > [!IMPORTANT]
    > La creazione di account in Microsoft 365 senza assegnare una licenza (ad esempio a SharePoint Online) significa che il proprietario dell'account può visualizzare il centro Microsoft 365 ma non può accedere ad alcuno dei servizi all'interno della sottoscrizione dell'azienda. Dopo aver assegnato un percorso e la licenza, l'account viene replicato nel servizio o nei servizi assegnati. L'utente può accedere al proprio account e utilizzare i servizi assegnati. 
  
## <a name="next-steps"></a>Passaggi successivi

[Integrazione di Microsoft 365 con ambienti locali](microsoft-365-integration.md)
  
## <a name="see-also"></a>Vedere anche

[Gestire utenti e gruppi in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)
  
