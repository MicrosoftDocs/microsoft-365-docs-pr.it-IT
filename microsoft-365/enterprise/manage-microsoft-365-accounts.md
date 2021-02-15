---
title: Gestire gli account utente di Microsoft 365
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
description: Informazioni su come gestire gli account utente di Microsoft 365.
ms.openlocfilehash: a7b6d89a0f66605dde168b85d74fcd8e513afc15
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327760"
---
# <a name="manage-microsoft-365-user-accounts"></a>Gestire gli account utente di Microsoft 365

È possibile gestire gli account utente di Microsoft 365 in diversi modi, a seconda della configurazione. È possibile gestire gli account utente nell'interfaccia di amministrazione di [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/add-users/) [in PowerShell,](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)in Servizi di dominio Active Directory o nel portale di amministrazione di Azure Active Directory (Azure AD). 

Non appena si acquista Microsoft 365, è possibile usare l'interfaccia di amministrazione di Microsoft 365 e PowerShell per gestire gli account. Quando si gestiscono le identità cloud, ogni persona dell'organizzazione dispone di un nome account utente e di una password separati. Se si desidera eseguire l'integrazione con l'infrastruttura locale e sincronizzare gli account utente con Microsoft 365, è possibile utilizzare Azure AD Connect per fornire la sincronizzazione delle identità e delle password per la funzionalità Single #A0 (SSO).
  
## <a name="plan-for-where-and-how-you-will-manage-your-user-accounts"></a>Pianificare dove e come gestire gli account utente

La posizione e la modalità di gestione degli account utente dipendono dal modello di identità che si vuole usare per Microsoft 365. I due modelli generali sono solo cloud e ibridi.
  
### <a name="cloud-only"></a>Solo cloud

Gli utenti vengono creati e gestiti nell'interfaccia di amministrazione di Microsoft 365. Puoi anche usare PowerShell o l'interfaccia di amministrazione di Azure AD. 
    
### <a name="hybrid"></a>Ibrido

Gli account utente vengono sincronizzati con Microsoft 365 da Servizi di dominio Active Directory, quindi è necessario usare gli strumenti di Servizi di dominio Active Directory locali per gestire gli account utente. 
    
## <a name="managing-accounts"></a>Gestione degli account

Quando si decide in che modo l'organizzazione creerà e gestirà gli account, considerare i requisiti seguenti:
  
- Il software di sincronizzazione della directory deve essere installato nei server all'interno dell'ambiente locale per connettere le identità tra Microsoft 365 e Servizi di dominio Active Directory.
    
- Qualsiasi opzione di sincronizzazione della directory, incluse le opzioni SSO, richiede che gli attributi di Servizi di dominio Active Directory soddisfino gli standard. Le specifiche degli attributi utilizzati nella directory e le eventuali operazioni di pulizia necessarie sono descritte in Preparazione della sincronizzazione della directory con [Microsoft 365.](prepare-for-directory-synchronization.md) 
    
- Pianificare la modalità di creazione degli account di Microsoft 365.
    
Nella tabella seguente sono elencati i diversi strumenti di gestione degli account.
    
|Strumento|Note|
|:-----|:-----|
|Interfaccia di amministrazione di Microsoft 365  <br/> |[Aggiungere utenti singolarmente o in blocco](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) <br/>  Fornisce una semplice interfaccia Web per aggiungere e modificare account utente.  <br/>  Non può essere usato per modificare gli utenti se è abilitata la sincronizzazione della directory (è possibile impostare la posizione e l'assegnazione delle licenze).  <br/>  Non può essere utilizzato con le opzioni SSO.  <br/> |
|Windows PowerShell  <br/> |[Gestire Microsoft 365 con Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=698471) <br/>  Consente di aggiungere utenti in blocco utilizzando uno script Windows PowerShell gruppo.  <br/>  Può essere usato per assegnare la posizione e le licenze agli account, indipendentemente dalla modalità di creazione degli account.  <br/> |
|Importazione in blocco  <br/> |[Aggiungere più utenti contemporaneamente](add-several-users-at-the-same-time.md) <br/>  Consente di importare un file CSV per aggiungere un gruppo di utenti a Microsoft 365.  <br/>  Non può essere utilizzato con le opzioni SSO.  <br/> |
|Azure AD  <br/> |Si ottiene un'edizione gratuita di Azure AD con l'abbonamento a Microsoft 365. È possibile eseguire funzioni come la reimpostazione della password in modalità self-service per gli utenti cloud e la personalizzazione delle pagine di accesso e del pannello di accesso tramite l'edizione gratuita. Per ottenere funzionalità avanzate, puoi eseguire l'aggiornamento all'edizione di base, Azure AD Premium P1 o Azure AD Premium P2. Vedi [le edizioni di Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=698465) per l'elenco delle funzionalità supportate.  <br/> |
|Sincronizzazione della directory  <br/> |[Integrazione delle identità locali con Azure AD](https://go.microsoft.com/fwlink/p/?LinkID=624168) <br/>  Per la sincronizzazione della directory con o senza sincronizzazione delle password, usare [Azure AD Connect con le impostazioni rapide.](https://go.microsoft.com/fwlink/p/?LinkID=698537)  <br/>  Per più foreste e opzioni SSO, usare [l'installazione personalizzata di Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkId=698430)  <br/>  Fornisce l'infrastruttura necessaria per abilitare SSO.  <br/>  Obbligatorio per molti scenari ibridi, ad esempio la migrazione a fasi e Exchange ibrido  <br/>  Sincronizza i gruppi di sicurezza e abilitati alla posta elettronica da Servizi di dominio Active Directory.  <br/> |
|||
   
- Indipendentemente da come si intende aggiungere gli account utente a Microsoft 365, è necessario gestire diverse funzionalità dell'account, ad esempio l'assegnazione di licenze, la specifica della posizione e così via. Queste funzionalità possono essere gestite a lungo termine dall'interfaccia di amministrazione di Microsoft 365 oppure è anche possibile [creare account utente con PowerShell.](https://go.microsoft.com/fwlink/p/?LinkId=717083)
    
    Se si sceglie di aggiungere e gestire tutti gli utenti tramite l'interfaccia di amministrazione, sarà necessario specificare il percorso e assegnare le licenze contemporaneamente alla creazione dell'account di Microsoft 365. Di conseguenza, non sono necessarie molte attività di pianificazione.
    
    > [!IMPORTANT]
    > La creazione di account in Microsoft 365 senza assegnare una licenza (ad esempio a SharePoint Online) significa che il proprietario dell'account può visualizzare il Centro Microsoft 365 ma non può accedere a nessuno dei servizi all'interno dell'abbonamento aziendale. Dopo aver assegnato una posizione e la licenza, l'account viene replicato nel servizio o nei servizi assegnati. L'utente può accedere al proprio account e usare i servizi assegnati. 
  
## <a name="see-also"></a>Vedere anche

[Interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users)

[PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)  
