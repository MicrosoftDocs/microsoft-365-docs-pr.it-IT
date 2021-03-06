---
title: 'Passaggio 1: impedire a un dipendente di accedere a Microsoft 365'
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Impedire a un ex dipendente di accedere e bloccare l'accesso Microsoft 365 servizi.
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177118"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Passaggio 1 - Impedire a un ex dipendente di accedere e bloccare l'accesso Microsoft 365 servizi

Se è necessario impedire immediatamente l'accesso di un utente, è consigliabile reimpostare la password. In questo passaggio forzare la disconnessione dell'utente da Microsoft 365.

> [!NOTE]
> È necessario essere un amministratore globale per avviare la disconnessione per altri amministratori. Per gli utenti non amministratori, è possibile utilizzare un amministratore utente o un utente amministratore dell'helpdesk per eseguire questa azione. [Altre informazioni sui ruoli di amministratore](about-admin-roles.md)

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare la casella accanto al nome dell'utente e quindi selezionare **Reimposta password.**
3. Immettere una nuova password e quindi selezionare **Reimposta**. Non inviarlo a loro.
4. Selezionare il nome dell'utente per passare al riquadro delle proprietà e nella scheda **Account** selezionare Disconnetta **tutte le sessioni.**

Entro un'ora o dopo aver lasciato la pagina Microsoft 365 corrente in cui si trova, viene richiesto di accedere di nuovo. Un token di accesso è valido per un'ora, quindi la sequenza temporale dipende dal tempo che rimane su quel token e dal fatto che si snavigare fuori dalla pagina Web corrente.
  
> [!IMPORTANT]
> Se l'utente è in Outlook sul web, basta fare clic nella propria cassetta postale, potrebbe non essere espulso immediatamente. Non appena selezionano un riquadro diverso, ad esempio OneDrive o aggiornano il browser, viene avviata la disconnessione.
  
Per usare PowerShell per disconnettere immediatamente un utente, vedere il cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)
  
Per altre informazioni sul tempo necessario per rimuovere un dipendente dalla posta elettronica, vedere [Cosa occorre sapere sulla chiusura delle sessione di posta elettronica di un dipendente](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Bloccare l'accesso di un ex dipendente Microsoft 365 servizi

> [!IMPORTANT]
 > L'applicazione del blocco di un account può richiedere fino a 24 ore. Se devi impedire immediatamente l'accesso di un utente, segui i passaggi precedenti e reimposta la password.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare il nome del dipendente che si desidera bloccare e, sotto il nome dell'utente, selezionare il simbolo **per Blocca questo utente.**
3. Seleziona **Blocca l'accesso dell'utente** e quindi seleziona **Salva.**

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloccare l'accesso alla posta elettronica (Exchange Online) di un ex dipendente

Se hai posta elettronica come parte dell'abbonamento Microsoft 365, accedi all'interfaccia di amministrazione di Exchange e segui questa procedura per impedire all'ex dipendente di accedere alla posta elettronica.
  
1. Accedere all'<a href="https://admin.exchange.microsoft.com/" target="_blank">interfaccia di amministrazione di Exchange</a>.
2. Nell'Interfaccia di amministrazione di Exchange passare a **Destinatari** \> **Cassette postali**.
3. Fai doppio clic sull'utente e vai a **Gestisci le impostazioni delle app di posta elettronica** in App di posta **elettronica**. Disattiva **il** dispositivo di scorrimento per tutte le opzioni; **Mobile (Exchange ActiveSync),** **Outlook sul web**, Outlook **desktop (MAPI),** **Exchange web services**, **POP3** e **IMAP**.
4. Selezionare **Salva**.
