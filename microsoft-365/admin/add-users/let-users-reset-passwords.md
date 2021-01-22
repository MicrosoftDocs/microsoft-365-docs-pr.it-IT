---
title: Consentire agli utenti di reimpostare le loro password
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
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Scopri come reimpostare le password usando lo strumento di reimpostazione delle password in modalità self-service.
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925555"
---
# <a name="let-users-reset-their-own-passwords"></a>Consentire agli utenti di reimpostare le loro password

L'amministratore di Microsoft 365 può consentire agli utenti di usare lo strumento di reimpostazione della password in modalità [self-service,](https://go.microsoft.com/fwlink/p/?LinkId=522677) in modo da non doverle reimpostare. Un gran risparmio di tempo!
  
## <a name="before-you-begin"></a>Prima di iniziare
  
- Si ottiene gratuitamente la reimpostazione  della password self-service per gli utenti cloud con qualsiasi piano a pagamento di Microsoft 365 business, education o no profit. Non funziona con la versione di valutazione di Microsoft 365.

- Si basa su Azure. Questa funzionalità verrà scaricata automaticamente e **gratuitamente** in Azure quando si esegue questa procedura. L'attivazione della reimpostazione della password in modalità self-service non costa nulla se non si usano altre funzionalità di Azure.

- **Se si usa Active Directory** locale, i due punti precedenti non sono applicabili. È invece possibile configurare questa funzionalità, ma **richiede una sottoscrizione a pagamento ad Azure AD Premium.**

Questo articolo è per le persone che impostano criteri di scadenza delle password in un'azienda, un istituto di istruzione o un'organizzazione no profit. Per completare questa procedura, è necessario accedere con l'account amministratore di Microsoft 365. [Che cos'è un account amministratore?](../admin-overview/admin-overview.md)

Per eseguire questa [procedura, è](about-admin-roles.md) necessario essere un amministratore globale o un amministratore delle password.

## <a name="watch-let-users-reset-their-own-passwords"></a>Guardare: Consentire agli utenti di reimpostare le proprie password

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="steps-let-people-reset-their-own-passwords"></a>Passaggi: consentire agli utenti di reimpostare le proprie password

Con questi passaggi si attiva la reimpostazione della password in modalità self-service per tutti gli utenti dell'azienda.
  
::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Impostazioni** > **organizzazione.**

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Impostazioni** \> **sicurezza &amp; privacy.**

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Impostazioni** \>  \> **&amp; protezione privacy.**

::: moniker-end

2. Nella parte superiore della pagina **Impostazioni organizzazione** selezionare la scheda Sicurezza **& Privacy.**
  
3. Selezionare **Reimpostazione password self-service.**

4. In **Reimpostazione password self-service** selezionare Vai al portale di Azure per attivare **la reimpostazione della password in self-service.**

5. Nel riquadro di spostamento sinistro selezionare **Utenti** e quindi nella pagina **Utenti | Pagina Tutti gli** utenti, selezionare **Reimpostazione password.**
  
6. Nella pagina **Proprietà** selezionare **Tutto per** abilitarlo per tutti gli utenti dell'azienda e quindi selezionare **Salva.**
  
7. Quando gli utenti emettono l'accesso, gli verrà richiesto di immettere ulteriori informazioni di contatto che li aiuteranno a reimpostare la password in futuro.

## <a name="related-content"></a>Contenuti correlati

[Impostare i criteri di scadenza delle password per l'organizzazione](../manage/set-password-expiration-policy.md)

[Impostare la password di un singolo utente in modo che non scada mai](set-password-to-never-expire.md)

[Video per la formazione di Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
