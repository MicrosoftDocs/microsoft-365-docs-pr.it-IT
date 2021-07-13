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
- AdminTemplateSet
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Scopri come interrompere l'inoltro automatico dei messaggi di posta elettronica creando una regola del flusso di posta per evitare il furto di informazioni proprietarie.
ms.openlocfilehash: 23b1afa7a851c0b00fb9fca574ca0bb32057ea42
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394798"
---
# <a name="stop-email-auto-forward"></a>Arrestare l'inoltro automatico della posta elettronica

## <a name="watch-stop-auto-forwarding-emails"></a>Watch: Stop auto-forwarding emails

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Se un pirata informatico ottiene l'accesso alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie. È possibile interrompere questa operazione creando una regola del flusso di posta.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Exchange** **,** flusso di posta e  nella scheda regole selezionare il segno più e scegliere crea **una nuova regola**.
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

[Aggiungere un altro alias di posta elettronica per un utente](../admin/email/add-another-email-alias-for-a-user.md) (articolo)\
[Configurare l'inoltro della posta elettronica in Microsoft 365](../admin/email/configure-email-forwarding.md) (articolo)\
[Trovare e risolvere i problemi di recapito della posta elettronica come Office 365 per le aziende](/exchange/troubleshoot/email-delivery/email-delivery-issues) (articolo)