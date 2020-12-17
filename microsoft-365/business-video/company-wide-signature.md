---
title: Creare una firma a livello di società
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Informazioni su come creare una firma di posta elettronica a livello aziendale.
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703027"
---
# <a name="create-a-company-wide-email-signature"></a>Creare una firma di posta elettronica a livello aziendale

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

Una firma di posta elettronica a livello aziendale viene visualizzata su tutti i messaggi di posta elettronica inviati da persone dell'organizzazione. È possibile utilizzarlo per visualizzare i dettagli importanti, come le informazioni di contatto dell'azienda o una dichiarazione di non responsabilità legale. 

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Exchange**.
1. Selezionare **flusso di posta**.
1. Selezionare **Aggiungi +**, quindi fare clic su **applica dichiarazioni** di non responsabilità.
1. Nella pagina **nuova regola** :
    1. Immettere un nome per la regola.
    1. Nell'elenco a discesa **applica questa regola** , selezionare **applica a tutti i messaggi**.
    1. Nell'elenco a discesa **procedere come segue** , verificare che venga visualizzata **la dichiarazione** di non responsabilità.
    1. Nella parte destra della pagina, selezionare **Immetti testo** e quindi immettere il testo per la firma di posta elettronica nella casella di testo **specifica dichiarazione** di non responsabilità. È possibile migliorare l'aspetto della firma formattando il testo in formato HTML.
    1. Se si desidera che un'immagine venga visualizzata nella firma, è necessario utilizzare un URL pubblico disponibile per l'immagine. Passare all'immagine sul Web, fare clic con il pulsante destro del mouse su di essa e scegliere **Copia indirizzo immagine**. Incollare l'indirizzo nella casella di testo **specifica dichiarazione** di non responsabilità. Selezionare **OK**, quindi scorrere verso il basso.
    1. Per assicurarsi che la firma funzioni con i messaggi di posta elettronica crittografati, aggiungere un'opzione di fallback. Nella parte destra della pagina scegliere **Seleziona uno**, quindi seleziona a **capo** e quindi **OK**.
    1. Scorrere verso il basso e lasciare la modalità impostata su **applica**, quindi selezionare **Salva**.
1. Verrà visualizzato un messaggio di avviso. Selezionare **Sì** per applicare la regola a tutti i messaggi futuri.

    La firma è stata creata. Quando si invia un messaggio di posta elettronica successivo, non verrà visualizzata la firma appena creata, ma verranno visualizzati i destinatari della posta elettronica.