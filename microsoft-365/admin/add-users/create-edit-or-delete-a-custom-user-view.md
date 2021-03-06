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
description: Informazioni su come usare i filtri per creare, modificare o eliminare una visualizzazione utente personalizzata in Microsoft 365.
ms.openlocfilehash: b4177a561d13d76f6d5a0a1077fe8037d469ee48
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683224"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Creazione, modifica o eliminazione di una visualizzazione utente personalizzata

Se si è un amministratore globale o di gestione utenti di un abbonamento Microsoft 365 per le aziende, è possibile creare visualizzazioni utente personalizzate per visualizzare un sottoinsieme specifico di utenti. Queste visualizzazioni sono in aggiunta al set standard di visualizzazioni. È possibile creare, modificare o eliminare le visualizzazioni utente personalizzate e quelle create dall'utente sono disponibili per tutti gli amministratori.
  
## <a name="custom-user-views-in-the-admin-center"></a>Visualizzazioni utente personalizzate nell'interfaccia di amministrazione

Quando si crea, si modifica o si elimina una visualizzazione  utente personalizzata, le modifiche verranno visualizzate nell'elenco Filtro visualizzato da tutti gli amministratori della società quando passano alla **pagina** Utenti. È possibile creare al massimo 50 visualizzazioni personalizzate. 

> [!TIP]
>  Per impostazione predefinita, le visualizzazioni utente standard vengono mostrate nell'elenco a discesa **Filtri**. I filtri standard includono Tutti gli utenti, Utenti con licenza, Utenti guest, Accesso consentito, Accesso bloccato, Utenti senza licenza, Utenti con  **errori,** Amministratori **fatturazione,** Amministratori **globali,** Amministratori   **helpdesk,** Amministratori del servizio e Amministratori gestione **utenti.**     Non è possibile modificare o eliminare le visualizzazioni standard. 

Alcune informazioni sulle visualizzazioni standard da tenere presente: 

- Alcune visualizzazioni standard mostrano un elenco non ordinato se questo contiene più di 2000 utenti. Per individuare utenti specifici nell'elenco, usare la casella di ricerca. 
- Se non hai acquistato Microsoft 365 da **Microsoft,** gli amministratori della fatturazione non vengono visualizzati nell'elenco delle visualizzazioni standard. Per ulteriori informazioni, vedere [Assegnazione di ruoli di amministratore](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Scegliere i filtri per la visualizzazione utente personalizzata

È possibile creare e modificare le visualizzazioni personalizzate nel **riquadro Filtro** personalizzato. Se si selezionano più opzioni di filtro, nei risultati vengono inclusi gli utenti che corrispondono a tutti i criteri selezionati. L'esempio seguente descrive come creare una visualizzazione personalizzata denominata "Utenti canadesi" che mostra tutti gli utenti di un dominio specifico che si trovano in Canada. 

  
 **A - Dominio** Se si dispone di più domini per l'organizzazione, è possibile scegliere tra un elenco a discesa di domini disponibili. 
  
 **B - Stato di accesso** Scegliere gli utenti consentiti o bloccati. 
  
 **C - Posizione** Scegliere una posizione da un elenco a discesa di paesi. 
  
 **D - Licenza del prodotto assegnata** Scegliere da un elenco a discesa di licenze disponibili nell'organizzazione. Usare questo filtro per mostrare gli utenti a cui è assegnata la licenza selezionata. Gli utenti possono avere anche altre licenze. 
  
È anche possibile filtrare in base ad altri dettagli del profilo utente usati all'interno dell'organizzazione, ad esempio il reparto, la città, lo stato o la provincia, il paese o l'area geografica oppure la posizione lavorativa.
  
 **Altre condizioni:**
  
- **Utenti sincronizzati:** selezionare questa casella per visualizzare tutti gli utenti sincronizzati con il servizio Active Directory locale, indipendentemente dallo stato di attivazione. 
    
- **Utenti con errori:** selezionare questa casella per visualizzare gli utenti con errori di provisioning. 
    
- **Utenti senza licenza:** selezionare questa casella per trovare tutti gli utenti a cui non è stata assegnata una licenza. I risultati di questa visualizzazione possono anche includere utenti che hanno una cassetta postale di Exchange ma non una licenza. Per individuare tali utenti, usare il filtro **Utenti senza licenza con cassette postali o archivi di Exchange**. I risultati di questa visualizzazione possono includere anche utenti che hanno un archivio di Exchange, ma non una licenza.
    
- **Utenti senza licenza con Exchange cassette postali o archivi** Selezionare questa casella per visualizzare gli account utente creati in Exchange Online e con una cassetta postale Exchange, ma a cui non è stata assegnata una Microsoft 365 licenza. I risultati di questo filtro includono gli utenti a cui è stato assegnato o che dispongono di un Exchange archivio. 

> [!NOTE]
> Il filtro Utenti senza licenza con Exchange cassette postali funziona quando:The **Unlicensed users with Exchange mailboxes** filter works when:
1. La cassetta postale è stata recentemente convertita **da condivisa** **a utente** e non dispone di licenza.
2. La cassetta postale è stata migrata di recente a Microsoft 365 ma non è stata assegnata una licenza.
3. La cassetta postale è stata creata con PowerShell e non è stata assegnata una licenza.
4. Viene eseguito il provisioning di una nuova cassetta postale creata in locale con New-RemoteMailbox cmdlet per l'utente.
    
> [!TIP]
> Se si crea una visualizzazione personalizzata che restituisce più di 2000 utenti, l'elenco utenti risultante non sarà ordinato. In questo caso, utilizzare la casella di ricerca per trovare gli utenti o modificare la visualizzazione personalizzata per perfezionare la ricerca. 
  
## <a name="create-a-custom-user-view"></a>Creare una visualizzazione utente personalizzata

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
  
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.  

::: moniker-end
    
2. Nella pagina **Utenti attivi** selezionare **Filtri e** selezionare **Nuovo filtro.**
  
3. Nella pagina **Filtro personalizzato** immettere il nome del filtro, scegliere le condizioni per il filtro personalizzato e quindi selezionare **Aggiungi**. La visualizzazione personalizzata è ora inclusa nell'elenco a discesa dei filtri.

## <a name="edit-or-delete-a-custom-user-view"></a>Modificare o eliminare una visualizzazione utente personalizzata

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare a **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

::: moniker-end 
    
2. Nella pagina **Utenti attivi** selezionare **Filtro,** selezionare il filtro che si desidera modificare e quindi selezionare **Modifica filtro.** 
    
    > [!TIP]
    > È possibile modificare solo le visualizzazioni personalizzate. 
  
3. Nella pagina **Filtro personalizzato** modificare le informazioni in base alle esigenze e quindi selezionare **Salva**. In caso contrario, per eliminare il filtro, nella parte inferiore della pagina selezionare **Elimina.** 

## <a name="related-content"></a>Contenuto correlato

[Panoramica dell'Microsoft 365 di amministrazione](../../business-video/admin-center-overview.md) (video)\
[Informazioni sui ruoli di](../add-users/about-admin-roles.md) amministratore (video)\
[Personalizzare il Microsoft 365 tema per l'organizzazione](../setup/customize-your-organization-theme.md) (articolo)


     