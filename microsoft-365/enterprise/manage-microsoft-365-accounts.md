---
title: Gestire Microsoft 365 account utente
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
description: Informazioni su come gestire gli Microsoft 365 utente.
ms.openlocfilehash: c0387bf50228e0eeb763b4807b15c8d57e02eeac
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909563"
---
# <a name="manage-microsoft-365-user-accounts"></a>Gestire Microsoft 365 account utente

È possibile gestire Microsoft 365 account utente in diversi modi, a seconda della configurazione. È possibile gestire gli account utente nell'interfaccia di amministrazione di [Microsoft 365,](../admin/add-users/index.yml) [PowerShell,](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)in Servizi di dominio Active Directory o nel portale di amministrazione di Azure Active Directory (Azure AD). 

Non appena si acquista un Microsoft 365, l'interfaccia Microsoft 365 e PowerShell possono essere usati per gestire gli account. Quando si gestiscono le identità cloud, ogni persona dell'organizzazione ha un nome account utente e una password separati. Se si desidera eseguire l'integrazione con l'infrastruttura locale e sincronizzare gli account utente con Microsoft 365, è possibile usare Azure AD Connessione per fornire la sincronizzazione delle identità e delle password per la funzionalità Single Sign-on (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Pianificare dove e come gestire gli account utente

La posizione e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per l'Microsoft 365. I due modelli globali sono solo cloud e ibridi.
  
### <a name="cloud-only"></a>Solo cloud

Gli utenti vengono creati e gestiti nell'Microsoft 365 di amministrazione. Puoi anche usare PowerShell o l'interfaccia di amministrazione di Azure AD. 
    
### <a name="hybrid"></a>Configurazione ibrida

Gli account utente vengono sincronizzati con Microsoft 365 da Servizi di dominio Active Directory, quindi è necessario utilizzare gli strumenti di Servizi di dominio Active Directory locali per gestire gli account utente. 
    
## <a name="managing-accounts"></a>Gestione degli account

Quando si decide in che modo l'organizzazione creerà e gestirà gli account, considerare i requisiti seguenti:
  
- Il software di sincronizzazione della directory deve essere installato nei server all'interno dell'ambiente locale per connettere le identità tra Microsoft 365 e Servizi di dominio Active Directory.
    
- Qualsiasi opzione di sincronizzazione della directory, incluse le opzioni SSO, richiede che gli attributi di Servizi di dominio Active Directory soddisfino gli standard. Le specifiche degli attributi utilizzati nella directory e le eventuali operazioni di pulizia necessarie sono descritte in [Prepare for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md). 
    
- Pianificare la modalità di creazione di Microsoft 365 account.
    
Nella tabella seguente sono elencati i diversi strumenti di gestione degli account.
    
|Strumento|Note|
|:-----|:-----|
|Interfaccia di amministrazione di Microsoft 365  <br/> |[Aggiungere utenti singolarmente o in blocco](../admin/add-users/add-users.md) <br/>  Fornisce un'interfaccia Web semplice per aggiungere e modificare gli account utente.  <br/>  Non può essere utilizzato per modificare gli utenti se è abilitata la sincronizzazione della directory (è possibile impostare la posizione e l'assegnazione delle licenze).  <br/>  Non può essere usato con le opzioni SSO.  <br/> |
|Windows PowerShell  <br/> |[Gestire Microsoft 365 con Windows PowerShell](./manage-microsoft-365-with-microsoft-365-powershell.md) <br/>  Consente di aggiungere utenti in blocco utilizzando uno script Windows PowerShell blocco.  <br/>  Può essere utilizzato per assegnare la posizione e le licenze agli account, indipendentemente dalla modalità di creazione degli account.  <br/> |
|Importazione in blocco  <br/> |[Aggiungere più utenti contemporaneamente](add-several-users-at-the-same-time.md) <br/>  Consente di importare un file CSV per aggiungere un gruppo di utenti a Microsoft 365.  <br/>  Non può essere usato con le opzioni SSO.  <br/> |
|Azure AD  <br/> |Ottieni un'edizione gratuita di Azure AD con l'Microsoft 365 abbonamento. Puoi eseguire funzioni come la reimpostazione della password in modalità self-service per gli utenti cloud e la personalizzazione delle pagine di accesso e pannello di accesso tramite l'edizione gratuita. Per ottenere funzionalità avanzate, è possibile eseguire l'aggiornamento all'edizione di base, Azure AD Premium P1 o Azure AD Premium P2. Per [l'elenco](/azure/active-directory/fundamentals/active-directory-whatis) delle funzionalità supportate, vedere Edizioni di Azure AD.  <br/> |
|Sincronizzazione della directory  <br/> |[Integrazione delle identità locali con Azure AD](/azure/active-directory/hybrid/whatis-hybrid-identity) <br/>  Per la sincronizzazione della directory con o senza sincronizzazione delle password, usare [Azure AD Connessione con impostazioni rapide.](/azure/active-directory/hybrid/how-to-connect-install-express)  <br/>  Per più foreste e opzioni SSO, usare [Installazione personalizzata di Azure AD Connessione](/azure/active-directory/hybrid/how-to-connect-install-custom).  <br/>  Fornisce l'infrastruttura necessaria per abilitare SSO.  <br/>  Obbligatorio per molti scenari ibridi, ad esempio la migrazione a fasi e l'Exchange  <br/>  Sincronizza i gruppi di sicurezza e abilitati alla posta elettronica da Servizi di dominio Active Directory.  <br/> |
|||
   
- Indipendentemente da come si intende aggiungere gli account utente a Microsoft 365, è necessario gestire diverse funzionalità dell'account, ad esempio l'assegnazione di licenze, la specifica della posizione e così via. Queste funzionalità possono essere gestite a lungo termine dall'Microsoft 365 di amministrazione oppure è anche possibile creare account [utente con PowerShell.](./create-user-accounts-with-microsoft-365-powershell.md)
    
    Se si sceglie di aggiungere e gestire tutti gli utenti tramite l'interfaccia di amministrazione, sarà necessario specificare la posizione e assegnare le licenze contemporaneamente alla creazione dell'account Microsoft 365 utente. Di conseguenza, non è necessaria molta pianificazione.
    
    > [!IMPORTANT]
    > La creazione di account in Microsoft 365 senza assegnare una licenza (ad esempio SharePoint Online) significa che il proprietario dell'account può visualizzare il centro Microsoft 365 ma non può accedere a nessuno dei servizi all'interno dell'abbonamento aziendale. Dopo aver assegnato una posizione e la licenza, l'account viene replicato nel servizio o nei servizi assegnati. L'utente può accedere al proprio account e usare i servizi assegnati. 
  
## <a name="see-also"></a>Vedere anche

[Interfaccia di amministrazione di Microsoft 365](../admin/add-users/index.yml)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)