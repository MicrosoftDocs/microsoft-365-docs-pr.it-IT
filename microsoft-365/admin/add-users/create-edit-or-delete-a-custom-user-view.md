---
title: Creazione, modifica o eliminazione di una visualizzazione utente personalizzata
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Informazioni su come utilizzare i filtri per creare, modificare o eliminare una visualizzazione utente personalizzata in Microsoft 365.
ms.openlocfilehash: faea21f0e5142d197cc2b90d6ade99490f9f88e3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387214"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a>Creare, modificare o eliminare una visualizzazione utente personalizzata in Office 365

Se l'utente è un amministratore Gestione utenti o un amministratore globale di Office 365, è possibile creare visualizzazioni utente personalizzate per visualizzare un sottoinsieme specifico di utenti. Queste visualizzazioni si aggiungono all'insieme standard di visualizzazioni incluso in Office 365. È possibile creare, modificare o eliminare le visualizzazioni utente personalizzate e quelle create dall'utente sono disponibili per tutti gli amministratori.

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a>Visualizzazioni utente personalizzate nell'interfaccia di amministrazione

::: moniker range="o365-worldwide"

Quando si crea, modifica o Elimina una visualizzazione utente personalizzata, le modifiche verranno visualizzate nell'elenco dei **filtri** che tutti gli amministratori della società vedranno quando andranno alla pagina **utenti** . È possibile creare al massimo 50 visualizzazioni personalizzate. 

::: moniker-end

::: moniker range="o365-germany"

Quando si crea, modifica o Elimina una visualizzazione utente personalizzata, le modifiche vengono visualizzate nell'elenco **visualizzazioni** che tutti gli amministratori della società visualizzano quando passano alla pagina **utenti** . È possibile creare al massimo 50 visualizzazioni personalizzate. 

::: moniker-end

::: moniker range="o365-21vianet"

Quando si crea, modifica o Elimina una visualizzazione utente personalizzata, le modifiche vengono visualizzate nell'elenco **visualizzazioni** che tutti gli amministratori della società visualizzano quando passano alla pagina **utenti** . È possibile creare al massimo 50 visualizzazioni personalizzate. 

::: moniker-end

> [!TIP]
>  Per impostazione predefinita, le visualizzazioni utente standard vengono mostrate nell'elenco a discesa **Filtri**. I filtri standard includono **tutti gli**utenti, gli utenti con **licenza**, **gli utenti Guest**, l' **accesso consentito**, l' **accesso bloccato**, **gli utenti senza licenza**, **gli utenti con errori**, gli amministratori di **fatturazione**, gli **amministratori globali**, gli amministratori del **supporto tecnico**, gli amministratori dei **Servizi**e gli **amministratori di gestione degli**utenti. Non è possibile modificare o eliminare le visualizzazioni standard. 

Alcune informazioni sulle visualizzazioni standard da tenere presente: 

- Alcune visualizzazioni standard mostrano un elenco non ordinato se questo contiene più di 2000 utenti. Per individuare utenti specifici nell'elenco, usare la casella di ricerca. 
- Se non è stato acquistato Microsoft 365 da Microsoft, gli **amministratori di fatturazione** non vengono visualizzati nell'elenco delle visualizzazioni standard. Per ulteriori informazioni, vedere [Assegnazione di ruoli di amministratore](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Scegliere i filtri per la visualizzazione utente personalizzata

È possibile creare e modificare le visualizzazioni personalizzate nel riquadro **filtro personalizzato** . Se si selezionano più opzioni di filtro, nei risultati vengono inclusi gli utenti che corrispondono a tutti i criteri selezionati. L'esempio seguente descrive come creare una visualizzazione personalizzata denominata "Utenti canadesi" che mostra tutti gli utenti di un dominio specifico che si trovano in Canada. 

  
 **A-Domain** Se si dispone di più domini per l'organizzazione, è possibile scegliere da un elenco a discesa dei domini disponibili. 
  
 **Stato di accesso B** Scegliere gli utenti che sono consentiti o bloccati. 
  
 **C-posizione** Scegliere un percorso da un elenco a discesa dei paesi. 
  
 **Licenza del prodotto D-assegnato** Scegliere da un elenco a discesa di licenze disponibili nell'organizzazione. Usare questo filtro per mostrare gli utenti a cui è assegnata la licenza selezionata. Gli utenti possono avere anche altre licenze. 
  
È anche possibile filtrare in base ad altri dettagli del profilo utente usati all'interno dell'organizzazione, ad esempio il reparto, la città, lo stato o la provincia, il paese o l'area geografica oppure la posizione lavorativa.
  
 **Altre condizioni:**
  
- **Utenti sincronizzati:** selezionare questa casella per visualizzare tutti gli utenti sincronizzati con il servizio Active Directory locale, indipendentemente dallo stato di attivazione. 
    
- **Utenti con errori:** selezionare questa casella per visualizzare gli utenti con errori di provisioning. 
    
- **Utenti senza licenza:** selezionare questa casella per trovare tutti gli utenti a cui non è stata assegnata una licenza. I risultati di questa visualizzazione possono anche includere utenti che hanno una cassetta postale di Exchange ma non una licenza. Per individuare tali utenti, usare il filtro **Utenti senza licenza con cassette postali o archivi di Exchange**. I risultati di questa visualizzazione possono includere anche utenti che hanno un archivio di Exchange, ma non una licenza.
    
- **Utenti senza licenza con archivi o cassette postali di Exchange** Selezionare questa casella per visualizzare gli account utente creati in Exchange Online e avere una cassetta postale di Exchange, ma non è stata assegnata una licenza Microsoft 365. I risultati di questo filtro includono gli utenti a cui è stato assegnato o che dispongono di un Exchange archivio. 

> [!NOTE]
> Il filtro **utenti senza licenza con cassette postali di Exchange** funziona quando:
1. La cassetta postale è stata recentemente convertita da **Shared** a **User** e non ha alcuna licenza.
2. La cassetta postale è stata di recente migrata a Microsoft 365 ma non è stata assegnata una licenza.
3. La cassetta postale è stata creata utilizzando PowerShell e non è stata assegnata una licenza.
4. Viene effettuato il provisioning di una nuova cassetta postale creata in locale con un cmdlet New-RemoteMailbox per l'utente.
    
> [!TIP]
> Se si crea una visualizzazione personalizzata che restituisce più di 2000 utenti, l'elenco utenti risultante non sarà ordinato. In questo caso, utilizzare la casella di ricerca per trovare gli utenti o modificare la visualizzazione personalizzata per affinare la ricerca. 
  
## <a name="create-a-custom-user-view"></a>Creare una visualizzazione utente personalizzata

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
    
2. Nella pagina **utenti attivi** selezionare **filtri** e selezionare **nuovo filtro**.
  
3. Nella pagina **filtro personalizzato** , immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi fare clic su **Aggiungi**. La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.
    
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Nella pagina **utenti attivi** selezionare **visualizzazioni** e quindi **Aggiungi visualizzazione personalizzata**.
  
3. Nella pagina **visualizzazione personalizzata** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi fare clic su **Aggiungi**. La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.

::: moniker-end


::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Nella pagina **utenti attivi** selezionare **visualizzazioni** e quindi **Aggiungi visualizzazione personalizzata**.
  
3. Nella pagina **visualizzazione personalizzata** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi fare clic su **Aggiungi**. La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Modificare o eliminare una visualizzazione utente personalizzata

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
    
2. Nella pagina **utenti attivi** selezionare **filtro**, selezionare il filtro che si desidera modificare e quindi scegliere **Modifica filtro**. 
    
    > [!TIP]
    > È possibile modificare solo le visualizzazioni personalizzate. 
  
3. Nella pagina **filtro personalizzato** modificare le informazioni in base alle esigenze e quindi fare clic su **Salva**. In alternativa, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Nella pagina **utenti attivi** selezionare **visualizzazioni**, selezionare il filtro che si desidera modificare, quindi selezionare **modifica questa visualizzazione**. 
    
    > [!TIP]
    > È possibile modificare solo le visualizzazioni personalizzate. 
  
3. Nella pagina **visualizzazione personalizzata** modificare le informazioni in base alle esigenze e quindi fare clic su **Salva**. In alternativa, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina visualizzazione personalizzata**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Nella pagina **utenti attivi** selezionare **visualizzazioni**, selezionare il filtro che si desidera modificare, quindi selezionare **modifica questa visualizzazione**. 
    
    > [!TIP]
    > È possibile modificare solo le visualizzazioni personalizzate. 
  
3. Nella pagina **visualizzazione personalizzata** modificare le informazioni in base alle esigenze e quindi fare clic su **Salva**. In alternativa, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina visualizzazione personalizzata**. 

::: moniker-end


     