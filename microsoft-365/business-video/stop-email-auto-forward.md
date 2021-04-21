---
title: Interrompere l'inoltro automatico dei messaggi di posta elettronica
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come interrompere l'inoltro automatico dei messaggi di posta elettronica.
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903683"
---
# <a name="stop-email-auto-forward"></a>Arrestare l'inoltro automatico della posta elettronica

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Se un pirata informatico ottiene l'accesso alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie. È possibile interrompere questa operazione creando una regola del flusso di posta.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare  **Exchange,** flusso di posta **e** nella scheda regole selezionare il segno più e scegliere crea una **nuova regola.**
1. Selezionare **Altre opzioni.** Assegnare un nome alla nuova regola.
1. Aprire quindi l'elenco a discesa per **applicare questa regola se**, selezionare **il** mittente e quindi è **interno esterno.**
1. Selezionare **All'interno dell'organizzazione** e quindi **OK.**
1. Scegliere **aggiungi condizione,** aprire l'elenco a discesa, selezionare **Le proprietà del messaggio,** **quindi includere il tipo di messaggio**.
1. Aprire **l'elenco a** discesa Seleziona tipo di messaggio, scegliere **Inoltro automatico,** quindi **OK.**
1. Aprire **l'elenco** a discesa Eseguire le operazioni seguenti, selezionare **Blocca il messaggio,** quindi **rifiutare il messaggio e includere una spiegazione.**
1. Immetti il testo del messaggio per la spiegazione, quindi seleziona **OK.**
1. Scorrere verso il basso e selezionare **Salva**.

    La regola è stata creata e gli hacker non saranno più in grado di inoltrare automaticamente i messaggi.

## <a name="related-content"></a>Contenuto correlato

[Aggiungere un altro alias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) di posta elettronica per un utente (articolo) Configurare l'inoltro della posta [elettronica in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (articolo) Trovare e risolvere i problemi di recapito della posta elettronica come amministratore di [Office 365 per le](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) aziende (articolo)