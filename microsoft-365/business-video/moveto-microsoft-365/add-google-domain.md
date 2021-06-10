---
title: Aggiungere il dominio di Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Scopri come spostare il dominio da Google Workspace a Microsoft 365 per le aziende.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578772"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a>Aggiungere il dominio di Google Workspace a Microsoft 365

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

Aggiungi il dominio google workspace a Microsoft 365 per le aziende in modo da poter continuare a usare il tuo indirizzo di posta elettronica aziendale.

## <a name="try-it"></a>Perché non provarlo?

1. Passare [all'Microsoft 365 di amministrazione .](https://admin.microsoft.com)
1. Nell'Microsoft 365 admin center, nel riquadro di spostamento sinistro, selezionare **Mostra tutto**, **Impostazioni** e quindi **Domini**.
1. Scegliere **Aggiungi dominio,** immettere il nome del dominio e quindi **selezionare Usa questo dominio.** 
1. Scegliere Aggiungi **un record TXT ai** record DNS dei domini, selezionare **Continua** e copiare il valore TXT. 
1. Torna alla Console di amministrazione [di Google,](https://admin.google.com)scegli **Domini,** Gestisci **domini,** Visualizza **dettagli,** **Gestisci** dominio, **DNS** e quindi scorri verso il basso fino a Record di **risorse personalizzati.** 
1. Aprire l'elenco a discesa tipo di record, scegliere **TXT,** incollare il valore TXT copiato e quindi **selezionare Aggiungi**. 

    L'aggiornamento in genere richiede alcuni minuti, ma può richiedere fino a 48 ore. 
1. Tornare all'Microsoft 365 di amministrazione, selezionare **Verifica** e quindi **Chiudi.** 
1. Per impostare il dominio come posta elettronica principale per gli utenti, nel riquadro di spostamento sinistro selezionare **Utenti**  >  **Utenti attivi**. 
1. Scegliere un utente, selezionare **Gestisci nome utente e posta** elettronica , Modifica , selezionare il dominio dall'elenco a discesa, quindi selezionare Fatto e salva le **modifiche**.   
1. Ripetere questo processo per ogni utente. 

    Al termine, sarai pronto per installare le app Office ed eseguire la migrazione della posta elettronica e degli elementi del calendario a Microsoft 365. 