---
title: Creare regole di posta elettronica per i ransomware
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Informazioni su come creare regole di posta elettronica per prevenire ransomware.
ms.openlocfilehash: 0d8b4a9de881f47752ac0bfbf778453d6ee73046
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422255"
---
# <a name="create-email-rules-to-prevent-ransomware"></a>Creare regole di posta elettronica per impedire ransomware

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

Microsoft 365 consente di proteggere l'azienda da ransomware impedendo l'apertura in Outlook di file potenzialmente pericolosi, come JavaScript, batch ed eseguibili. Per aumentare questo livello di protezione aggiungendo regole che bloccano o avvisano l'utente di tipi aggiuntivi di file, attenersi alla seguente procedura.

## <a name="try-it"></a>Perché non provarlo?

1. Nell'interfaccia di amministrazione di [https://admin.microsoft.com](https://admin.microsoft.com) , scegliere **Exchange** in Interfaccia **di amministrazione.**
1. Scegliere Flusso di posta dal menu **a sinistra.**
1. Nella scheda delle regole fare clic sulla freccia accanto al simbolo più (+) e quindi **scegliere Crea una nuova regola.**
1. Nella pagina **nuova regola** immettere un nome per la regola, scorrere verso il basso e quindi scegliere **Altre opzioni.**
1. In **Applica questa regola se**, selezionare Qualsiasi **allegato** e quindi selezionare l'estensione **del file che include queste parole.**
1. Nella casella **in** specificare parole o frasi immettere le estensioni di file a cui si desidera applicare la regola, ad esempio le estensioni di file che possono contenere macro. Usa il simbolo più (+) per aggiungerli uno alla volta.

    Per ulteriori informazioni sui tipi di file, vedere [Proteggere da ransomware.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)

1. Scorrere verso il basso per esaminare l'elenco e quindi scegliere **OK.**
1. Nella pagina **nuova regola** scegliere **aggiungi condizione** e quindi scegliere una condizione in Eseguire le **operazioni seguenti.**
1. Sono disponibili molte opzioni tra cui scegliere, ma in questo esempio si sceglie di inviare una notifica **al destinatario con un messaggio.**
1. Immettere il testo del messaggio per la notifica e quindi scegliere **OK.**
1. Facoltativo: nella pagina **nuova** regola scegliere Aggiungi eccezione e immettere eventuali dettagli per le eccezioni alla regola, ad esempio i messaggi provenienti da mittenti attendibili. 
1. Nella pagina nuova regola scegliere **Salva** ed esaminare le informazioni di riepilogo della regola fornite.