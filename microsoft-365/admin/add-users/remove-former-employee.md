---
title: Rimuovere un ex dipendente - Panoramica
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
description: Seguire i passaggi descritti in questa soluzione per rimuovere un ex dipendente Microsoft 365 e proteggere i dati dell'organizzazione.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241737"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Panoramica: rimuovere un ex dipendente e proteggere i dati

Una domanda che spesso ci viene data è: "Cosa devo fare per proteggere i dati e proteggere l'accesso quando un dipendente lascia l'organizzazione?" In questa serie di articoli viene illustrato come bloccare l'accesso a Microsoft 365, i passaggi da eseguire per proteggere i dati e come consentire ad altri dipendenti di accedere ai dati.

Guarda un breve video sulla rimozione di un dipendente. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../../business-video/index.yml).

Per impedire a un dipendente di accedere:

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
2. Selezionare la casella accanto al nome dell'utente e quindi selezionare **Reimposta password.**
3. Immettere una nuova password e quindi selezionare **Reimposta**. Non inviarlo a loro.
4. Selezionare il nome dell'utente per passare al riquadro delle proprietà e nella **scheda Account** selezionare **Avvia disconnessione.**

> [!NOTE]
> È necessario essere un amministratore globale per avviare la disconnessione.

Entro un'ora o dopo aver lasciato la pagina Microsoft 365 corrente in cui si trova, viene richiesto di accedere di nuovo. Un token di accesso è valido per un'ora, quindi la sequenza temporale dipende dal tempo che rimane su quel token e dal fatto che si snavigare fuori dalla pagina Web corrente.

> [!IMPORTANT]
> Anche se i passaggi di questa soluzione sono stati numerati e non è necessario completare la soluzione utilizzando l'ordine esatto, è consigliabile eseguire la procedura in questo modo.

## <a name="before-you-begin"></a>Prima di iniziare

Per completare i passaggi di questa soluzione, è necessario essere un amministratore globale.

|||
|:-----|:-----|
|**Passaggio** <br/> |**Perché eseguire questa operazione** <br/> |
|[Passaggio 1 - Impedire a un ex dipendente di accedere e bloccare l'accesso Microsoft 365 servizi](remove-former-employee-step-1.md) <br/> |Questo impedisce all'ex dipendente di accedere a Microsoft 365 e impedisce all'utente di accedere Microsoft 365 servizi. <br/> |
|[Passaggio 2 - Salvare il contenuto della cassetta postale di un ex dipendente](remove-former-employee-step-2.md) <br/> |Ciò è utile per la persona che prenderà il controllo del lavoro del dipendente o in caso di controversia legale. <br/> |
|[Passaggio 3 - Inoltrare la posta elettronica di un ex dipendente a un altro dipendente o convertirlo in una cassetta postale condivisa](remove-former-employee-step-3.md) <br/> |Consente di mantenere attivo l'indirizzo di posta elettronica dell'ex dipendente. Se i clienti o i partner continuano a inviare la posta elettronica all'indirizzo dell'ex dipendente, questa operazione consente di inoltrare i messaggi alla persona che ne prende il posto. <br/> |
|[Passaggio 4 - Concedere a un altro dipendente l'accesso OneDrive e Outlook dati](remove-former-employee-step-6.md) <br/> |Se si rimuove solo la licenza di un utente, senza eliminare l'account, il contenuto del suo OneDrive rimarrà accessibile anche dopo i 30 giorni. <br/><br/> Prima di eliminare l'account, è consigliabile concedere l'accesso OneDrive e Outlook a un altro utente. Dopo aver eliminato l'account di un dipendente, il contenuto OneDrive e Outlook viene conservato per **30** giorni. Durante questi 30 giorni, tuttavia, è possibile ripristinare l'account dell'utente e ottenere l'accesso al contenuto. Se si ripristina l'account dell'utente, il contenuto OneDrive e Outlook rimarrà accessibile anche dopo 30 giorni. <br/> |
|[Passaggio 5 - Cancellare e bloccare il dispositivo mobile di un ex dipendente](remove-former-employee-step-4.md) <br/> |Rimuove i dati aziendali dal telefono o dal tablet.  <br/> |
|[Passaggio 6 - Rimuovere ed eliminare la licenza Microsoft 365 da un ex dipendente](remove-former-employee-step-7.md) <br/> |Quando si rimuove una licenza, è possibile assegnarla a un'altra persona. In alternativa, è possibile eliminare la licenza in modo da interromperne il pagamento finché non si assume un'altra persona.  <br/><br/> Quando si rimuove o si elimina una licenza, la posta elettronica, i contatti e il calendario dell'utente vengono conservati per **30 giorni**, quindi eliminati definitivamente. Se si rimuove o si elimina la licenza di un utente, senza eliminare l'account, il contenuto del suo OneDrive rimarrà accessibile anche dopo i 30 giorni.  <br/> |
|[Passaggio 7 - Eliminare l'account utente di un ex dipendente](remove-former-employee-step-7.md) <br/> |In questo modo l'account viene rimosso dall'interfaccia di amministrazione. Consente di tenere tutto in ordine. <br/> |

## <a name="related-articles"></a>Articoli correlati

[Ripristinare un utente](restore-user.md)
