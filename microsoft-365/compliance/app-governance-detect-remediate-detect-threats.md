---
title: Risolvere le minacce dell’app
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Risolvere le minacce dell’app.
ms.openlocfilehash: 73776621ef86523d64b2a216538412bb46ab5586
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420352"
---
# <a name="remediate-app-threats"></a>Risolvere le minacce dell’app

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

È possibile risolvere le minacce dell'app al tenant di Microsoft 365 tramite la pagina **Avvisi** della sezione Governance delle app Microsoft del Centro conformità Microsoft 365.

![La pagina di riepilogo degli avvisi relativi alla governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

La pagina **Avvisi** elenca per impostazione predefinita i nuovi avvisi di minaccia generati dagli avvisi relativi alla governance delle app e basati su criteri generati dai criteri delle app attivi. È possibile visualizzare i dettagli di un avviso specifico selezionandolo che apre un riquadro di avviso con informazioni aggiuntive sull'avviso e la possibilità di modificarne lo stato.

![La pagina dei dettagli degli avvisi relativi alla governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-alerts-alert.png)

Da questo riquadro è possibile ottenere le seguenti informazioni aggiuntive:

- Ulteriori dettagli sull'avviso dal campo **Descrizione**.
- Nome dei criteri dell'app che hanno generato l'avviso dal campo **Nome criteri**. È anche possibile selezionare **Visualizza criteri** per passare al criteri dell'app che hanno generato l'avviso.

I criteri dell'app configurati per la correzione automatica da **Azione** avranno lo stato **Risolto**.

È possibile correggere un avviso dell'app seguendo la procedura seguente:

1. Indagine: esaminare le informazioni dell'avviso e modificarne lo stato in **Segnare come In corso**.
2. Soluzione: dopo l'indagine e, se necessario, la determinazione delle modifiche dei criteri dell’app o il supporto continuativo dell’app nel tenant, modificarne lo stato in **Risolto**.

In base ai modelli di avviso dell'app, è possibile aggiornare i criteri dell'app appropriati e modificare l’impostazione **Azione** per eseguire la correzione automatica. Ciò elimina la necessità di analizzare e risolvere manualmente gli avvisi futuri generati dai criteri dell'app. Per ulteriori informazioni, vedere [Gestire i criteri dell’app](app-governance-app-policies-manage.md).
