---
title: Tipi di informazioni sensibili per DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Panoramica sui tipi di informazioni sensibili personalizzati per la prevenzione della perdita dei dati, ad esempio criterio principale, prossimità dei caratteri e livello di probabilità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817965"
---
# <a name="custom-sensitive-information-types"></a>Tipi di informazioni sensibili personalizzati

Microsoft 365 include molti tipi di informazioni sensibili predefinite pronte per l'uso nell'organizzazione, ad esempio per la [prevenzione della perdita dei dati](data-loss-prevention-policies.md) (DLP) o con [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security). I tipi di informazioni sensibili integrati consentono di identificare e proteggere i numeri di carata di credito, di conto corrente, di passaporto e altro, in base agli schemi che sono definiti da un'espressione regolare (regex) o da una funzione. Per altre informazioni, vedere [Elementi cercati dai tipi di informazioni sensibili](what-the-sensitive-information-types-look-for.md).

Tuttavia, cosa accade se è necessario identificare e proteggere un tipo diverso di informazioni sensibili, ad esempio gli ID dei dipendenti o i numeri di progetto che usano un formato specifico dell'organizzazione? Per farlo, è possibile creare un tipo di informazioni sensibili personalizzato.

Le parti fondamentali di un tipo di informazioni sensibili personalizzato sono:

- **Criterio principale**: ID dipendente, numeri di progetto e così via. In genere è identificato da un'espressione regolare (RegEx), ma può anche essere un elenco di parole chiave.

- **Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.

- **Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:

    ![Diagramma dell'evidenza corroborativa e della finestra di prossimità](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.

  When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:

    ![Numero di istanze e opzioni di precisione di corrispondenza](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>Creazione dei tipi di informazioni sensibili personalizzati

Per creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità, è possibile scegliere tra diverse opzioni:

- **Usare EDM** (novità!) È possibile configurare tipi di informazioni sensibili personalizzati tramite la classificazione basata su Exact Data Match (EDM). Questo metodo consente di creare un tipo di informazioni sensibili dinamico usando un database protetto che è possibile aggiornare periodicamente. Vedere [Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Usare PowerShell** È possibile configurare tipi di informazioni riservate personalizzati con PowerShell. Anche se questo metodo è più complesso rispetto all'utilizzo dell'interfaccia utente, offre più opzioni di configurazione. Vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md).

- **Usare l'interfaccia utente** È possibile configurare un tipo di informazioni sensibili personalizzato mediante l'interfaccia utente del Centro sicurezza e conformità. Con questo metodo, è possibile usare espressioni regolari, parole chiave e dizionari di parole chiave. Per saperne di più, vedere [Creare un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type.md).



