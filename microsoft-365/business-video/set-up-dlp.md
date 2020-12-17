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
description: Informazioni su come gestire i criteri di prevenzione della perdita dei dati.
ms.openlocfilehash: 93c06af0203a5eb590d22d86e597d7485d7af238
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702907"
---
# <a name="prevent-data-loss-with-dlp"></a>Prevenire la perdita di dati con DLP

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

I criteri di prevenzione della perdita di dati consentono di identificare e proteggere le informazioni riservate dell'azienda, come i numeri di previdenza sociale o i record medici. 

## <a name="try-it"></a>Perché non provarlo?

1. Per iniziare, passare all'interfaccia di [Amministrazione](https://admin.microsoft.com)e selezionare **Setup**.
1. Scorrere verso il basso per **impostare la prevenzione della perdita di dati**, quindi selezionare **Visualizza** e quindi **Gestisci**.
1. Per modificare un criterio, selezionarlo, scegliere **modifica criterio** e quindi selezionare le modifiche desiderate. Ad esempio, selezionare **percorsi** per modificare ciò che viene analizzato.
1. Per abilitare l'analisi del contenuto in Microsoft teams, impostare l'interruttore toggle **sulla posizione attivata** e quindi selezionare **Salva**.
1. Per modificare le impostazioni del criterio, selezionare **modifica**.
1. Sarà necessario impostare regole distinte che si applicano a piccole e grandi quantità di contenuto sensibile rilevate. Espandi la regola del volume basso. Scegliere **Modifica regola**.
1. Rivedere le impostazioni e modificarle in base alle esigenze. Ad esempio, è possibile scegliere di **personalizzare il testo del messaggio di posta elettronica** e **personalizzare il testo del suggerimento per i criteri**. Selezionare **Salva**.
1. Ripetere la regola per il volume alto. Selezionare **Salva** e quindi **Chiudi**.
1. Per creare un nuovo criterio, selezionare **Crea un criterio**.
1. È possibile creare un criterio personalizzato o iniziare con un modello. Ad esempio, per creare un criterio HIPAA, selezionare il modello di **integrità e medicale** , quindi selezionare **U.S. Health Insurance Act (HIPAA)**. Selezionare **Avanti**.
1. Immettere un nome e una descrizione per i criteri. Selezionare **Avanti**.
1. Scegliere le posizioni da analizzare. Selezionare **Avanti**.
1. Scegliere il tipo di contenuto che si desidera proteggere. Selezionare **Avanti**.
1. Scegliere ciò che si desidera verificare se vengono rilevate informazioni riservate. Selezionare **Avanti**.
1. Personalizzare le autorizzazioni di accesso e di sostituzione. Selezionare **Avanti**.
1. Scegliere quando si desidera che il criterio abbia effetto. Selezionare **Avanti**.
1. Rivedere le impostazioni e selezionare **Crea**. Dopo che il criterio è stato applicato, la posta elettronica contenente le informazioni riservate descritte verrà bloccata e il mittente che ha tentato di inviare tali informazioni visualizzerà un messaggio di avviso.