---
title: Interrompere l'inoltro automatico di messaggi di posta elettronica
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
description: Informazioni su come interrompere l'inoltro automatico di messaggi di posta elettronica.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702021"
---
# <a name="stop-email-auto-forward"></a>Interrompere l'inoltro automatico della posta elettronica

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Se un pirata informatico accede alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie. Questa operazione può essere interrotta creando una regola del flusso di posta.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Exchange**, **flusso di posta** e nella scheda **regole** selezionare il segno più e scegliere **Crea nuova regola**.
1. Selezionare **altre opzioni**. Assegnare un nome alla nuova regola.
1. Aprire quindi il menu a discesa per **applicare la regola se**, selezionare **il mittente** e quindi **interno esterno**.
1. Selezionare **all'interno dell'organizzazione** e quindi fare clic su **OK**.
1. Scegliere **Aggiungi condizione**, aprire l'elenco a discesa, selezionare **le proprietà del messaggio** e quindi **includere il tipo di messaggio**.
1. Aprire l'elenco a discesa **Seleziona tipo di messaggio** , scegliere **inoltro automatico** e quindi **OK**.
1. Aprire l'elenco a discesa **procedere come segue** , selezionare **blocca il messaggio**, quindi **rifiutare il messaggio e includere una spiegazione**.
1. Immettere il testo del messaggio per la spiegazione, quindi fare clic su **OK**.
1. Scorrere fino alla fine e selezionare **Salva**.

    La regola è stata creata e gli hacker non saranno più in grado di inoltrare automaticamente i messaggi.