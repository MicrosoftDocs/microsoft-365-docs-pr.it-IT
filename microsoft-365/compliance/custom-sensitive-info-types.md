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
ms.openlocfilehash: 621c7be728f772e113ef5cd65d5b79a2526ec7c5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035748"
---
# <a name="custom-sensitive-information-types"></a>Tipi di informazioni sensibili personalizzati

## <a name="overview"></a>Panoramica

Microsoft 365 include molti tipi di informazioni sensibili predefinite pronte per l'uso nell'organizzazione, ad esempio per la [prevenzione della perdita dei dati](data-loss-prevention-policies.md) (DLP) o con [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security). I tipi di informazioni sensibili integrati consentono di identificare e proteggere i numeri di carata di credito, di conto corrente, di passaporto e altro, in base agli schemi che sono definiti da un'espressione regolare (regex) o da una funzione. Per altre informazioni, vedere [Elementi cercati dai tipi di informazioni sensibili](what-the-sensitive-information-types-look-for.md).

Tuttavia, cosa accade se è necessario identificare e proteggere un tipo diverso di informazioni sensibili, ad esempio gli ID dei dipendenti o i numeri di progetto che usano un formato specifico dell'organizzazione? Per farlo, è possibile creare un tipo di informazioni sensibili personalizzato.

Le parti fondamentali di un tipo di informazioni sensibili personalizzato sono:

- **Criterio principale**: ID dipendente, numeri di progetto e così via. In genere è identificato da un'espressione regolare (RegEx), ma può anche essere un elenco di parole chiave.

- **Evidenza aggiuntiva**: si supponga di cercare un numero ID dipendente di nove cifre. Non tutti i numeri di nove cifre sono numeri ID dipendente, quindi è possibile cercare testo aggiuntivo: parole chiave come "dipendente", "badge", "ID" o altri criteri di testo basati su ulteriori espressioni regolari. Questa evidenza di supporto (denominata anche evidenza__ _corroborativa_) consente di aumentare la probabilità che il numero di nove cifre individuato nel contenuto sia davvero un numero ID dipendente.

- **Prossimità dei caratteri**: è logico che più il criterio principale e l'evidenza di supporto sono vicini tra loro, più è probabile che il contenuto rilevato sia quello che si sta cercando. È possibile specificare la distanza dei caratteri tra il criterio principale e l'evidenza di supporto (nota anche come _finestra di prossimità_) come mostrato nel diagramma seguente:

    ![Diagramma dell'evidenza corroborativa e della finestra di prossimità](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Livello di probabilità**: più evidenze di supporto si hanno, più alta è la probabilità che una corrispondenza contenga le informazioni sensibili che si stanno cercando. È possibile assegnare livelli di probabilità più elevati per le corrispondenze rilevate con altre evidenze.

  Quando viene soddisfatto, un criterio restituisce un numero e un livello di probabilità che è possibile utilizzare nelle condizioni nei criteri DLP. Quando si aggiunge una condizione per il rilevamento di un tipo di informazione riservata a un criterio DLP, è possibile modificare il numero e il livello di probabilità, come illustrato nel diagramma seguente:

    ![Numero di istanze e opzioni di precisione di corrispondenza](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>Creazione dei tipi di informazioni sensibili personalizzati

Per creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità, è possibile scegliere tra diverse opzioni:

- **Usare EDM** (novità!) È possibile configurare tipi di informazioni sensibili personalizzati tramite la classificazione basata su Exact Data Match (EDM). Questo metodo consente di creare un tipo di informazioni sensibili dinamico usando un database protetto che è possibile aggiornare periodicamente. Vedere [Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Usare PowerShell** È possibile configurare tipi di informazioni riservate personalizzati con PowerShell. Anche se questo metodo è più complesso rispetto all'utilizzo dell'interfaccia utente, offre più opzioni di configurazione. Vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md).

- **Usare l'interfaccia utente** È possibile configurare un tipo di informazioni sensibili personalizzato mediante l'interfaccia utente del Centro sicurezza e conformità. Con questo metodo, è possibile usare espressioni regolari, parole chiave e dizionari di parole chiave. Per saperne di più, vedere [Creare un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type.md).



