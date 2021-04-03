---
title: Creare regole di posta elettronica per i ransomware
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
description: Informazioni su come creare regole di posta elettronica per impedire ransomware.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580499"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Creare regole di posta elettronica per impedire ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 consente di proteggere l'azienda da ransomware impedendo l'apertura di file potenzialmente pericolosi, come JavaScript, batch ed eseguibili, in Outlook. Per aumentare questo livello di protezione aggiungendo regole che bloccano o avvisano l'utente di altri tipi di file, eseguire la procedura seguente.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di [https://admin.microsoft.com](https://admin.microsoft.com) , scegliere **Exchange** in Interfaccia **di amministrazione**.
1. Scegliere Flusso di posta dal menu **a sinistra.**
1. Nella scheda regole scegliere la freccia accanto al simbolo più (+), quindi scegliere **Crea una nuova regola.**
1. Nella pagina **nuova regola** immettere un nome per la regola, scorrere verso il basso e quindi scegliere **Altre opzioni.**
1. In **Applica questa regola se**, selezionare Qualsiasi **allegato** e quindi selezionare **Estensione file include queste parole.**
1. Nella casella in **specificare parole** o frasi immettere le estensioni di file a cui si desidera applicare la regola, ad esempio le estensioni di file che possono contenere macro. Usa il simbolo più (+) per aggiungerli uno alla volta.

    Per ulteriori informazioni sui tipi di file, vedere [Protezione da ransomware.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)

1. Scorrere verso il basso per esaminare l'elenco e quindi scegliere **OK.**
1. Nella pagina **nuova regola** scegliere **aggiungi condizione** e quindi una condizione in Eseguire le **operazioni seguenti.**
1. Sono disponibili molte opzioni tra cui scegliere, ma in questo esempio si sceglie di inviare una notifica al destinatario **con un messaggio.**
1. Immettere il testo del messaggio per la notifica e quindi scegliere **OK**.
1. Facoltativo: nella **pagina** nuova regola scegliere Aggiungi eccezione e immettere eventuali dettagli per le eccezioni alla regola, ad esempio i messaggi provenienti da mittenti attendibili.
1. Nella pagina nuova regola scegliere **Salva** ed esaminare le informazioni di riepilogo della regola fornite.