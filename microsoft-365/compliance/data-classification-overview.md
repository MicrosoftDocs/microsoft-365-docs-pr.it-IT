---
title: Introduzione alla classificazione dei dati
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Il dashboard di classificazione dei dati offre visibilità sulla quantità di dati riservati che sono stati individuati e classificati nell'organizzazione.
ms.openlocfilehash: 3198a1981ed7d4d5428452b55aeb22b234712354
ms.sourcegitcommit: b812771805c8b9e92b64deb1928e265e60d80405
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2020
ms.locfileid: "46588218"
---
# <a name="know-your-data---data-classification-overview"></a>Conoscere i dati - Panoramica della classificazione dei dati

Gli amministratori Microsoft 365 e gli amministratori della conformità possono valutare e contrassegnare i contenuti dell’organizzazione per monitorarne gli spostamenti, proteggerli ovunque e fare in modo che vengano conservati e cancellati secondo le esigenze specifiche dell’organizzazione. Queste operazioni possono essere eseguite mediante l'applicazione di [etichette di riservatezza](sensitivity-labels.md), di [etichette di conservazione](retention.md#retention-labels) e tramite la classificazione della tipologia delle informazioni riservate. Esistono vari modi per eseguire l'individuazione, la valutazione e l'aggiunta di tag, ma il risultato finale è che potrebbe essere presente un numero molto elevato di documenti e messaggi di posta elettronica contrassegnati e classificati con una o entrambe le etichette. Dopo aver applicato le etichette di conservazione e le etichette di riservatezza, è opportuno verificarne l'utilizzo nel tenant e controllare le operazioni che vengono svolte con tali elementi. La pagina di classificazione dei dati consente di avere visibilità sui contenuti, in particolare:

- il numero degli elementi classificati come tipologie di informazioni riservate e quali sono le tipologie di classificazione
- le principali etichette di riservatezza applicate sia in Microsoft 365 che in Azure Information Protection
- le principali etichette di conservazione applicate
- il riepilogo delle attività che gli utenti svolgono sui contenuti riservati
- le posizioni dei dati riservati e conservati

Queste funzionalità vengono anche gestite nella pagina di classificazione dei dati:
- [classificatori sottoponibili a training](classifier-getting-started-with.md)
- [tipi di informazioni sensibili](what-the-sensitive-information-types-look-for.md)

La funzionalità Classificazione dei dati è disponibile nel **Centro conformità Microsoft 365**o nel **Centro sicurezza Microsoft 365** > **Classificazione** > **Classificazione dei dati**.

Seguire una presentazione video sulle funzionalità di classificazione dei dati.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

Classificazione dei dati consentità di analizzare il contenuto riservato e il contenuto con etichetta prima di creare criteri. Tale operazione è nota come **gestione senza modifiche**. Consente di vedere l'impatto di tutte le etichette di conservazione e di riservatezza sul proprio ambiente e permette di valutare la necessità di iniziare a usare criteri di protezione e di governance.

## <a name="prerequisites"></a>Prerequisiti

A ogni account che accede e usa la classificazione dei dati deve essere assegnata una licenza da uno di questi abbonamenti:

- Microsoft 365 (E5)
- Office 365 (E5)
- Componente aggiuntivo Advanced Compliance (E5)
- Componente aggiuntivo Advanced Threat Intelligence (E5)

### <a name="permissions"></a>Autorizzazioni

 Per accedere alla pagina di classificazione dei dati, è necessario che a un account sia assegnata l'appartenenza a uno di questi ruoli o gruppi di ruoli.

**Gruppi di ruoli di Microsoft 365**

- Amministratore globale
- Amministratore di conformità
- Amministratore della sicurezza
- Amministratore dati di conformità

## <a name="sensitive-information-types-used-most-in-your-content"></a>Tipologie di informazioni riservate usate più di frequente nei contenuti

Microsoft 365 fornisce diverse definizioni delle tipologie di informazioni riservate, ad esempio un elemento che contiene un codice di previdenza sociale o un numero di carta di credito. Per altre informazioni sui tipi di informazioni sensibili, vedere [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md).

La scheda tipologie di informazioni riservate mostra le principali tipologie di informazioni riservate individuate ed etichettate all'interno dell'organizzazione.

![tipologie principali di informazioni riservate](../media/data-classification-sens-info-types-card.png)

Per determinare il numero di elementi in una determinata categoria di classificazione, passare il puntatore del mouse sulla barra della categoria.

![principali tipologie di informazioni riservate visualizzate al passaggio del mouse](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> Se la scheda mostra il messaggio "Nessun dato trovato per le informazioni riservate". Questo significa che non sono presenti elementi nell'organizzazione classificati come tipologia di informazioni riservate o sottoposti a ricerca per indicizzazione. Per iniziare a usare le etichette, vedere:
>- [Iniziare a usare le etichette di riservatezza](get-started-with-sensitivity-labels.md)
>- [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md)
>- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a>Principali etichette di riservatezza applicate ai contenuti

Quando si applica un'etichetta di riservatezza a un elemento tramite Microsoft 365 o Azure Information Protection (AIP), si verificano le seguenti situazioni:

- il tag che indica il valore dell'elemento per l'organizzazione viene incorporato nel documento e lo seguirà ovunque
- la presenza del tag permette varie misure protettive, ad esempio la filigrana obbligatoria o la crittografia. Con la protezione dell'endpoint abilitata, è anche possibile impedire a un elemento di eludere il controllo dell'organizzazione.

Per ulteriori informazioni sulle etichette di riservatezza, vedere [Informazioni sulle etichette di riservatezza](sensitivity-labels.md)

Le etichetta di riservatezza devono essere abilitate per i file che si trovano in SharePoint e OneDrive affinché i dati corrispondenti vengano visualizzati nella pagina di classificazione dei dati. Per altre informazioni, vedere [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

La scheda etichetta di riservatezza mostra il numero di elementi (e-mail o documenti) in base al livello di riservatezza.

![schermata della scomposizione dei contenuti in base al segnaposto di classificazione delle etichette di riservatezza](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> Se non sono state create o pubblicate etichette di riservatezza o non è stata applicata alcuna etichetta di riservatezza ai contenuti, la scheda visualizzerà il messaggio "Non sono state rilevate etichette di riservatezza". Per iniziare a usare le etichette di riservatezza vedere:
>- [Iniziare ad usare le etichette di riservatezza](get-started-with-sensitivity-labels.md) oppure per AIP [Configurare i criteri di protezione delle informazioni in Azure](https://docs.microsoft.com/azure/information-protection/configure-policy)

## <a name="top-retention-labels-applied-to-content"></a>Principali etichette di conservazione applicate ai contenuti

Le etichette di conservazione vengono usate per gestire la conservazione dei contenuti all'interno dell'organizzazione. Possono essere usate per controllare il periodo di conservazione di un documento prima dell'eliminazione, se deve essere esaminato prima dell'eliminazione, quando scade il periodo di conservazione oppure se deve essere contrassegnato come record che non deve essere eliminato. Per altre informazioni, vedere [Informazioni sui criteri e sulle etichette di conservazione](retention.md).

Le scheda delle principali etichette di conservazione applicate mostra il numero di elementi con una determinata etichetta di conservazione.

![schermata segnaposto delle principali etichette di conservazione](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> Se la scheda mostra il messaggio "Non sono state rilevate etichette di conservazione" significa che non sono state create o pubblicate etichette di conservazione o non è stata applicata alcuna etichetta di conservazione ai contenuti. Per iniziare a usare le etichette di conservazione, vedere:
>- [Familiarizza con i criteri e le etichette di conservazione](get-started-with-retention.md)

## <a name="top-activities-detected"></a>Attività principali rilevate

Questa scheda offre un breve riepilogo delle azioni più comuni eseguite dagli utenti con gli elementi con etichette di riservatezza. È possibile usare [Esplora attività](data-classification-activity-explorer.md) per eseguire il drill-down avanzato su otto diverse attività di cui Microsoft 365 tiene traccia sui contenuti etichettati e su contenuti presenti negli endpoint di Windows 10.

> [!NOTE]
> Se la scheda visualizza il messaggio "Non è stata rilevata alcuna attività", significa che non sono state rilevate attività sui file o che non è stato attivato il controllo da parte dell'utente e dell'amministratore. Per attivare i log di controllo, vedere:
>- [Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a>Dati con etichette di riservatezza e conservazione in base alla posizione

Il motivo della classificazione dei dati consiste nel fornire visibilità sul numero di elementi etichettati e della relativa posizione. Queste schede consentono di conoscere il numero di elementi etichettati in Exchange, SharePoint, OneDrive e così via.

> [!NOTE]
> Se la scheda visualizza il messaggio "Non sono state rilevate posizioni" significa che non sono state create o pubblicate etichette di riservatezza o che non è stata applicata alcuna etichetta di conservazione ai contenuti. Per iniziare a usare le etichette di riservatezza vedere:
>- [Etichette di riservatezza](sensitivity-labels.md)

## <a name="see-also"></a>Vedere anche

- [Visualizzare le attività con etichette](data-classification-activity-explorer.md)
- [Visualizzare il contenuto con etichetta](data-classification-content-explorer.md)
- [Informazioni sulle etichette di riservatezza](sensitivity-labels.md)
- [Informazioni sui criteri e sulle etichette di conservazione](retention.md)
- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)
- [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-getting-started-with.md)
