---
title: Consentire agli utenti di reimpostare le loro password in Office 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Informazioni su come è possibile reimpostare le password utilizzando lo strumento di reimpostazione della password self-service.
ms.openlocfilehash: 87accc393d08b922ebc3f75ef1aa5ddb2d0b2955
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241603"
---
# <a name="let-users-reset-their-own-passwords"></a>Consentire agli utenti di reimpostare le loro password

Cosa fare per non ricevere più richieste di modifica delle password degli utenti? Come amministratore di Microsoft 365, è possibile consentire agli utenti di utilizzare lo [strumento di reimpostazione della password in modalità self-service](https://go.microsoft.com/fwlink/p/?LinkId=522677) in modo che non sia necessario reimpostare le password. Un gran risparmio di tempo! 
  
Ecco alcune informazioni utili:
  
- Con tutti i piani a pagamento di Office 365 Business, Education o Nonprofit, agli utenti viene fornita **gratuitamente** l'opzione di reimpostazione della password in modalità self-service. Questa opzione non funziona con la versione di valutazione di Office 365. 
    
- Si basa su Azure. Questa funzionalità verrà scaricata automaticamente e **gratuitamente** in Azure quando si esegue questa procedura. L'attivazione della reimpostazione della password in modalità self-service non costa nulla se non si usano altre funzionalità di Azure. 
    
- **Se si utilizza Active Directory locale**, non si applicano i due punti sopra riportati. Piuttosto, è possibile configurare questa impostazione, ma **richiede un abbonamento a pagamento ad Azure ad Premium**. 

Guardare un breve video su come consentire agli utenti di reimpostare le proprie password. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="let-people-reset-their-own-passwords"></a>Consentire alle persone di reimpostare le proprie password 

Con questi passaggi si attiva la reimpostazione della password in modalità self-service per tutti gli utenti dell'azienda.
  
::: moniker range="o365-worldwide"
1.  Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">protezione & privacy</a> .

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>passare alla pagina **Impostazioni** \> **privacy sicurezza &amp; ** .

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>passare alla pagina **Impostazioni** \> **privacy sicurezza &amp; ** .

::: moniker-end

   
2. In **Consenti alle persone di reimpostare**le proprie password, selezionare il collegamento per l'interfaccia di **amministrazione di Azure ad**. Azure verrà scaricato gratuitamente.
  
3. Selezionare **gli utenti** nella barra di spostamento sinistra, quindi selezionare **Reimposta password**.
  
4. Nella pagina delle proprietà, selezionare **tutto** per attivarlo per tutti gli utenti dell'azienda, quindi selezionare **Salva**.
  
5. Quando gli utenti accedono a Office 365, verrà richiesto di immettere altre informazioni di contatto che gli consentiranno di reimpostare più facilmente la password in futuro.

## <a name="related-articles"></a>Articoli correlati

[Impostare i criteri di scadenza delle password per l'organizzazione](../manage/set-password-expiration-policy.md)
  
[Impostare la password di un singolo utente in modo che non scada mai](set-password-to-never-expire.md)

[Video per la formazione di Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
