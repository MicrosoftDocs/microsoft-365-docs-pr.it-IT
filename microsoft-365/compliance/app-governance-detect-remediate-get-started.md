---
title: Introduzione al rilevamento e alla correzione delle minacce dell'app
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
description: Introduzione al rilevamento e alla correzione delle minacce dell'app.
ms.openlocfilehash: 77de3676a9a486bbed572a4a16bf62ad4d038406
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430721"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>Introduzione al rilevamento e alla correzione delle minacce dell'app

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

La governance delle app Microsoft raccoglie gli avvisi delle minacce generati dai metodi predefiniti di rilevamento della governance delle app basati sulle attività dannose delle app e da avvisi basati su criteri generati dai criteri attivi delle app creati dall'utente.

Per visualizzare gli avvisi delle app, è necessario iniziare dalla dashboard di governance delle app in [https://aka.ms/appgovernance](https://aka.ms/appgovernance).

![La pagina di panoramica della governance delle app nel Centro conformità Microsoft 365 con la sezione Rilevamento e avvisi dei criteri evidenziata](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

Nella pagina di panoramica, nella sezione **Rilevamento e avvisi dei criteri** sono elencati gli avvisi più recenti. È possibile utilizzare la pagina per visualizzare rapidamente l'attività relativa all’avviso dell'app corrente per il tenant.

Per visualizzare tutti gli avvisi, selezionare la scheda **Avvisi**.

## <a name="whats-available-on-the-alerts-page"></a>Elementi disponibili nella pagina Avvisi

Nella pagina **Avvisi** sono elencati tutti gli avvisi basati sulla governance delle app per il tenant.

![La pagina di riepilogo degli avvisi relativi alla governance delle app nel Centro conformità Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

Gli avvisi presenti nell’elenco includono le informazioni seguenti:

- **Nome dell’avviso**: il tipo di comportamento anomalo.
- **Nome dell’app**: l'app che ha generato l'avviso.
- **Gravità**: la gravità assegnata dalla governance dell'app per gli avvisi creati o la gravità dei criteri dell'app che hanno generato l'avviso.
- **Origine**: l’origine dell'avviso, che può derivare da criteri (criteri creati dall'utente), rilevamento (criteri di rilevamento predefiniti) o MCAS.
- **Stato**: **Nuovo** indica un avviso a cui non è stato assegnato uno stato. Una volta assegnato, lo stato è **In corso** durante la fase di analisi o **Risolto** per gli avvisi che sono stati risolti tramite correzione automatica o manuale.
- **Data di creazione**: la data in cui l'avviso è stato generato dal rilevamento della governance dell'app o tramite un criterio dell'app. Tutte le date sono indicate nei fusi orari locali del Centro conformità Microsoft 365.
- **Ultima attività**: la data dell'ultima modifica dello stato dell'avviso. Tutte le date sono indicate nei fusi orari locali del Centro conformità Microsoft 365.

Per impostazione predefinita, l'elenco di avvisi viene ordinato per **Data di creazione**. Per ordinare l'elenco in base a un altro attributo, selezionare il nome dell'attributo.

È anche possibile esportare l'elenco di avvisi corrente in un file con valori delimitati da virgole (Comma-Separated Value, CSV). Ad esempio, è possibile aprire il file CVS in Microsoft Excel, ordinare l'elenco di avvisi per **Gravità**, quindi per **Data di creazione**.

## <a name="next-step"></a>Passaggio successivo

[Risolvere le minacce dell’app.](app-governance-detect-remediate-detect-threats.md)
