---
title: Creare regole di posta elettronica per ransomware
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
description: Informazioni su come creare regole di posta elettronica per impedire il ransomware.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701932"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Creare regole di posta elettronica per impedire ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 aiuta a proteggere la propria azienda dal ransomware impedendo l'apertura di file potenzialmente pericolosi, come JavaScript, batch e eseguibili, in Outlook. Per aumentare questo livello di protezione aggiungendo regole che bloccano o avvertono altri tipi di file, attenersi alla seguente procedura.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione [https://admin.microsoft.com](https://admin.microsoft.com) scegliere **Exchange** in interfaccia di **Amministrazione**.
1. Scegliere **flusso di posta** dal menu a sinistra.
1. Nella scheda regole scegliere la freccia accanto al simbolo più (+) e quindi fare clic su **Crea una nuova regola**.
1. Nella pagina **nuova regola** , immettere un nome per la regola, scorrere fino alla fine e quindi scegliere **altre opzioni**.
1. In **applica la regola se**, selezionare **qualsiasi allegato**, quindi selezionare **estensione file include queste parole**.
1. Nella casella in **specificare parole o frasi**, immettere le estensioni di file a cui si desidera applicare la regola, ad esempio le estensioni di file che possono contenere macro. Utilizzare il segno più (+) per aggiungerne uno alla volta.

    Per ulteriori informazioni sui tipi di file, leggere [Protect Against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).

1. Scorrere verso il basso per esaminare l'elenco e quindi fare clic su **OK**.
1. Nella pagina **nuova regola** scegliere **Aggiungi condizione** e quindi fare clic su una condizione in **eseguire le operazioni seguenti**.
1. È possibile scegliere tra molte opzioni di regola, ma in questo esempio si sceglie di **notificare al destinatario un messaggio**.
1. Immettere il testo del messaggio per la notifica e quindi scegliere **OK**.
1. Facoltativo: nella pagina **nuova regola** scegliere **Aggiungi eccezione** e immettere tutti i dettagli relativi alle eccezioni alla regola, ad esempio i messaggi provenienti da mittenti attendibili.
1. Nella pagina nuova regola scegliere **Salva** ed esaminare le informazioni di riepilogo delle regole fornite.