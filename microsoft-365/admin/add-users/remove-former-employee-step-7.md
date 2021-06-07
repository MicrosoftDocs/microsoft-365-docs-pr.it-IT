---
title: Passaggio 7 - Eliminare l'account utente di un ex dipendente
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
description: Seguire questa procedura per eliminare l'account utente di un ex dipendente.
ms.openlocfilehash: e9f87f68650394a81c735346db929bf592e91d18
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779832"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Passaggio 7 - Eliminare l'account utente di un ex dipendente

Dopo il salvataggio e l'accesso ai dati utente dell'ex dipendente, è possibile eliminare l'account corrispondente.

> [!IMPORTANT]
> Non eliminare l'account se è stato configurato l'inoltro della posta elettronica o se l'account è stato convertito in una cassetta postale condivisa. In entrambi i casi è necessario l'account per ancorare l'inoltro o la cassetta postale condivisa.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare il nome del dipendente che si desidera eliminare.
3. Sotto il nome dell'utente, selezionare **Elimina utente.** Scegliere le opzioni desiderate per l'utente e quindi selezionare **Elimina utente.** Se hai già fornito a un altro utente l'accesso alla posta elettronica e OneDrive di questo utente, non è necessario farlo di nuovo qui.

Quando si elimina un utente, il suo account diventa inattivo per circa 30 giorni. Si ha quindi a disposizione questo periodo di tempo per ripristinare l'account prima che venga eliminato definitivamente.

## <a name="watch-delete-a-former-employees-user-account"></a>Watch: Delete a former employee's user account

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).

## <a name="does-your-organization-use-active-directory"></a>L'organizzazione usa Active Directory?

Se l'organizzazione sincronizza gli account utente Microsoft 365 da un ambiente Active Directory locale, è necessario eliminare e ripristinare tali account utente nel servizio Active Directory locale. Non è possibile eliminarli o ripristinarli in Office 365.

Per informazioni su come eliminare e ripristinare un account utente in Active Directory, vedere [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))
  
Se si usa Azure Active Directory, vedere il cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) di PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Cosa occorre sapere sulla chiusura delle sessione di posta elettronica di un dipendente

Informazioni su come rimuovere un dipendente dalla posta elettronica (Exchange).
  
|||
|:-----|:-----|
|**Cosa è possibile fare** <br/> |**Come farlo** <br/> |
|Terminare una sessione (ad esempio Outlook sul Web, Outlook, Exchange ActiveSync e così via) e forzare l'apertura di una nuova sessione  <br/> |Reimpostare la password  <br/> |
|Terminare una sessione e bloccare l'accesso a sessioni future (per tutti i protocolli)  <br/> |Disabilitare l'account. Ad esempio, (nell'interfaccia di Exchange o usando PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Terminare la sessione per un particolare protocollo, ad esempio ActiveSync  <br/> |Disabilitare il protocollo. Ad esempio, (nell'interfaccia di Exchange o usando PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

Le operazioni precedenti possono essere eseguite in tre posizioni:
  
|||
|:-----|:-----|
|**Se si termina la sessione qui** <br/> |**Quanto tempo occorre** <br/> |
|Nell'interfaccia di amministrazione di Exchange o con PowerShell  <br/> |Il ritardo massimo previsto è di 30 minuti  <br/> |
|Nell'interfaccia di amministrazione di Azure Active Directory  <br/> |Il ritardo previsto è di 60 minuti  <br/> |
|In un ambiente locale  <br/> |Il ritardo previsto è di 3 ore o più  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Come ottenere la risposta più rapida per la chiusura di un account

 **Metodo più rapido**: usare l'interfaccia di amministrazione di Exchange (usare PowerShell) oppure l'interfaccia di amministrazione di Azure Active Directory. In un ambiente locale, la sincronizzazione delle modifiche con DirSync può richiedere diverse ore.
  
 **Metodo più rapido per utenti con presenza locale e nel data center di Exchange**: terminare la sessione con l'interfaccia di amministrazione di Exchange o di Azure Active Directory E apportare le modifiche anche nell'ambiente locale. In caso contrario, le modifiche nell'interfaccia di amministrazione di Exchange o di Azure Active Directory verranno sovrascritte da DirSync.
  
## <a name="related-articles"></a>Articoli correlati

[Ripristinare un utente](restore-user.md)

[Reimpostare password](reset-passwords.md)
