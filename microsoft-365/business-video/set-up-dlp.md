---
title: Evitare la perdita di dati
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
description: Informazioni su come gestire la configurazione dei criteri di prevenzione della perdita dei dati.
ms.openlocfilehash: 54cd508ef0b0cfcf8b71dc86a4903f77a5354c36
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422064"
---
# <a name="prevent-data-loss-with-dlp"></a>Prevenire la perdita di dati con DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

I criteri di prevenzione della perdita dei dati consentono di identificare e proteggere le informazioni riservate dell'azienda, ad esempio i numeri di previdenza sociale o le cartelle cliniche. 

## <a name="try-it"></a>Perché non provarlo?

1. To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup.**
1. Scorrere verso il basso **fino a Configurare la prevenzione della** perdita dei dati, quindi selezionare **Visualizza** e **quindi Gestisci.**
1. Per modificare un criterio, selezionarlo, scegliere **Modifica criterio,** quindi selezionare gli elementi da modificare. Ad esempio, selezionare **Posizioni per** modificare gli elementi analizzati.
1. Per abilitare l'analisi del contenuto in Microsoft  Teams, attivare l'interruttore Attiva e quindi selezionare **Salva.**
1. Per modificare le impostazioni dei criteri, selezionare **Modifica.**
1. Dovrai impostare regole separate che si applicano a piccole e grandi quantità di contenuti sensibili rilevati. Espandere la regola con volume ridotto. Scegliere **Modifica regola.**
1. Rivedere le impostazioni e regolarle in base alle esigenze. Ad esempio, è possibile scegliere di personalizzare il **testo del messaggio di posta elettronica** e il testo del **suggerimento per il criterio.** Selezionare **Salva**.
1. Ripetere l'operazione per la regola di volume elevato. Selezionare **Salva** e quindi **Chiudi.**
1. Per creare un nuovo criterio, selezionare **Crea un criterio.**
1. È possibile creare un criterio personalizzato o iniziare con un modello. Ad esempio, per creare un criterio HIPAA, selezionare il modello Medical **and health** e quindi selezionare **U.S. Health Insurance Act (HIPAA)**. Selezionare **Avanti**.
1. Immettere un nome e una descrizione per il criterio. Selezionare **Avanti**.
1. Scegliere i percorsi da analizzare. Selezionare **Avanti**.
1. Scegliere il tipo di contenuto che si desidera proteggere. Selezionare **Avanti**.
1. Scegli cosa vuoi che accada se vengono rilevate informazioni riservate. Selezionare **Avanti**.
1. Personalizzare le autorizzazioni di accesso e override. Selezionare **Avanti**.
1. Scegliere quando si desidera che il criterio sia attivo. Selezionare **Avanti**.
1. Rivedere le impostazioni e selezionare **Crea.** Dopo l'applicazione dei criteri, i messaggi di posta elettronica che contengono le informazioni riservate descritte verranno bloccati e il mittente che ha tentato di inviare queste informazioni verrà visualizzato un messaggio di avviso.