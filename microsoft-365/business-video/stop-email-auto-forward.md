---
title: Interrompere l'inoltro automatico dei messaggi di posta elettronica
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come interrompere l'inoltro automatico dei messaggi di posta elettronica.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925887"
---
# <a name="stop-email-auto-forward"></a>Arrestare l'inoltro automatico della posta elettronica

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Se un pirata informatico ottiene l'accesso alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie. È possibile interrompere questa operazione creando una regola del flusso di posta.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare  **Exchange,** flusso di posta e, nella scheda delle regole, selezionare il segno più e scegliere **crea una nuova regola.** 
1. Selezionare **Altre opzioni.** Assegnare un nome alla nuova regola.
1. Aprire quindi l'elenco a discesa per **applicare questa regola se**, selezionare **il** mittente e quindi è **interno esterno.**
1. Selezionare **Interno all'organizzazione** e quindi **OK.**
1. Scegliere **aggiungi condizione,** aprire l'elenco a discesa, selezionare **Le proprietà del** messaggio, quindi includere il tipo di **messaggio.**
1. Aprire **l'elenco a** discesa Seleziona tipo di messaggio, scegliere **Inoltro automatico,** quindi **OK.**
1. Aprire **l'elenco** a discesa Fare quanto segue, selezionare **Blocca il messaggio,** quindi **rifiutare il messaggio e includere una spiegazione.**
1. Immettere il testo del messaggio per la spiegazione, quindi selezionare **OK.**
1. Scorrere verso il basso e selezionare **Salva.**

    La regola è stata creata e i pirati informatici non saranno più in grado di inoltrare automaticamente i messaggi.