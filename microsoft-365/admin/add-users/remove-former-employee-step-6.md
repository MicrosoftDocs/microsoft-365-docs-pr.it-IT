---
title: Passaggio 6 - Rimuovere ed eliminare la licenza Microsoft 365 da un ex dipendente
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
description: Seguire questa procedura per rimuovere la licenza Microsoft 365 da un ex dipendente.
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244215"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>Passaggio 6 - Rimuovere la licenza Microsoft 365 da un ex dipendente

Se non si desidera pagare una licenza dopo che qualcuno ha lasciato l'organizzazione, è necessario rimuovere la licenza Microsoft 365 ed eliminarla dall'abbonamento. Puoi assegnare una licenza a un altro utente se non la elimini.
  
Quando si rimuove la licenza, tutti i dati dell'utente vengono conservati per 30 giorni. È possibile [accedere](get-access-to-and-back-up-a-former-user-s-data.md) ai dati o [ripristinare](restore-user.md) l'account se l'utente ritorna. Dopo 30 giorni, tutti i dati dell'utente (ad eccezione dei documenti archiviati in SharePoint Online) vengono eliminati definitivamente da Microsoft 365 e non possono essere ripristinati.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare il nome del dipendente che si desidera bloccare e quindi selezionare la **scheda Licenze e** app.
3. Deselezionare le caselle di controllo relative alle licenze che si desidera rimuovere e quindi selezionare **Salva modifiche.**

**Per ridurre il numero di licenze che si stanno pagando** fino a quando non si assume un'altra persona, eseguire la procedura seguente:

1. Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> e selezionare la **scheda** Prodotti.
2. Selezionare l'abbonamento da cui si desidera rimuovere le licenze.
3. Nella pagina dei dettagli seleziona **Rimuovi licenze.**
4. Nel riquadro **Rimuovi licenze,** in Nuova quantità, nella casella **Totale** licenze immettere il numero totale di licenze desiderate per la sottoscrizione. Ad esempio, se si dispone di 25 licenze e si desidera rimuoverle, immettere 24.
5. Selezionare **Salva**.

Quando aggiungi [un'altra](add-users.md) persona alla tua azienda, ti verrà richiesto di acquistare una licenza contemporaneamente, con un solo passaggio.

Per ulteriori informazioni sulla gestione delle licenze utente per Microsoft 365 per le aziende, vedere [Assegnare](../manage/assign-licenses-to-users.md)licenze agli utenti in Microsoft 365 per le aziende e Annullare l'assegnazione di licenze da utenti [in Microsoft 365 per le aziende](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Quali effetti hanno gli account dei dipendenti eliminati su Skype for Business?

Quando si rimuove una licenza utente da Office 365, il numero chiamata PSTN associato all'utente viene rilasciato e può essere assegnato a un altro utente.
  
Se l'utente appartiene a un gruppo di coda, non sarà più contattato dagli agenti della coda di chiamata. Per questo motivo, si consiglia la rimozione dell'utente anche dai gruppi associati alla coda di chiamata.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Configurare l'inoltro di chiamata agli utenti dell'organizzazione

Se è necessario configurare l'inoltro di chiamata per il numero di telefono del dipendente terminato, l'impostazione di inoltro di chiamata nei criteri di chiamata può configurare l'inoltro in cui le chiamate in arrivo possono essere inoltrate ad altri utenti o possono squillare contemporaneamente a un'altra persona. Per ulteriori informazioni, vedere [Calling policies in Microsoft Teams](/microsoftteams/teams-calling-policy).
