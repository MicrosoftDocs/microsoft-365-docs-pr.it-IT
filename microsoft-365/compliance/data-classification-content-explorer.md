---
title: Introduzione a Esplora contenuto (anteprima)
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
description: Esplora contenuto consente di visualizzare in modo nativo gli elementi con etichetta.
ms.openlocfilehash: 3d1c938d3a9d7ff25bb66a5b344cfbb29eace84c
ms.sourcegitcommit: fa6a1e432747e150df945050a3744b4408ceb2d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "43957266"
---
# <a name="get-started-with-content-explorer-preview"></a>Introduzione a Esplora contenuto (anteprima)

Esplora contenuto di classificazione dei dati consente di visualizzare in modo nativo gli elementi che sono stati riepilogati nella pagina di panoramica.

## <a name="prerequisites"></a>Prerequisiti

A ogni account che accede e usa Esplora attività deve essere assegnata una licenza da uno di questi abbonamenti:

- Microsoft 365 (E5)
- Office 365 (E5)
- Componente aggiuntivo Advanced Compliance (E5)
- Componente aggiuntivo Advanced Threat Intelligence (E5)

## <a name="content-explorer"></a>Esplora contenuto

Esplora contenuto mostra uno snapshot corrente degli elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni riservate nell'organizzazione.

### <a name="sensitive-information-types"></a>Tipi di informazioni sensibili

I [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) aiutano a proteggere le informazioni riservate definite come **tipo di informazioni sensibili**. Microsoft 365 include le [definizioni per molti tipi di informazioni sensibili comuni](what-the-sensitive-information-types-look-for.md) in varie aree geografiche, pronte per l'uso. Ad esempio, un numero di carta di credito, numeri di conto corrente bancario, numeri di documento di identità e numeri di servizio Windows Live ID.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Un'[etichetta di sensibilità](sensitivity-labels.md) è semplicemente un contrassegno che indica il valore dell'elemento per l'organizzazione. Può essere applicata manualmente o automaticamente. Una volta applicata, viene incorporata nel documento e lo seguirà ovunque. Un'etichetta di riservatezza abilita varie misure protettive, ad esempio la filigrana obbligatoria o la crittografia. Con la protezione dell'endpoint abilitata, è anche possibile impedire a un elemento di eludere il controllo dell'organizzazione.

Le etichetta di riservatezza devono essere abilitate per i file che si trovano in SharePoint e OneDrive affinché i dati corrispondenti vengano visualizzati nella pagina di classificazione dei dati. Per altre informazioni, vedere [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

### <a name="retention-labels"></a>Etichette di conservazione

Un'[etichetta di conservazione](labels.md) consente di definire per quanto tempo viene conservato un elemento etichettato prima di essere eliminato. Vengono applicate manualmente o automaticamente tramite criteri. Possono essere utili per favorire la conformità dell'organizzazione ai requisiti di legge e normativi.

![schermata compressa di Esplora contenuto](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>Autorizzazioni

Sono due i ruoli che consentono di accedere a Esplora contenuto:

- **Visualizzatore elenco di Esplora contenuto**: l'appartenenza a questo gruppo di ruoli consente di visualizzare ogni elemento e la relativa posizione. Il ruolo `data classification list viewer` è stato preassegnato a questo gruppo di ruoli.

- **Visualizzatore contenuto di Esplora contenuto**: l'appartenenza a questo gruppo di ruolo consente di visualizzare il contenuto di ogni elemento dell'elenco. Il ruolo `data classification content viewer` è stato preassegnato a questo gruppo di ruoli.

L'account usato per accedere a Esplora contenuto deve essere presente in uno o entrambi i gruppi di ruoli. Si tratta di gruppi di ruoli indipendenti e non cumulativi. Ad esempio, se si vuole concedere a un account la possibilità di visualizzare solo gli elementi e le relative posizioni, concedere i diritti di Visualizzatore elenco di Esplora contenuto. Se si vuole che lo stesso account sia in grado di visualizzare anche il contenuto degli elementi dell'elenco, concedere anche i diritti di Visualizzatore contenuto di Esplora contenuto.

È anche possibile assegnare uno o entrambi i ruoli a un gruppo di ruoli personalizzato per personalizzare l'accesso a Esplora contenuto.

Un amministratore globale, un amministratore di conformità o un amministratore dei dati può assegnare l'appartenenza ai gruppi di ruolo Visualizzatore elenco di Esplora contenuto e Visualizzatore contenuto di Esplora contenuto necessaria.

### <a name="how-to-use-content-explorer"></a>Come usare Esplora contenuto

1. Aprire **Centro conformità Microsoft 365**  > **Classificazione dei dati** > **Esplora contenuto**.
2. Se si conosce il nome dell'etichetta o il tipo di informazioni riservate, è possibile digitarlo nella casella di ricerca.
3. In alternativa, è possibile cercare l'elemento espandendo il tipo di etichetta e selezionando l'etichetta dall'elenco. Di seguito viene mostrato un elemento della parte di etichetta di conservazione dell'elenco.
4. Selezionare una posizione in **Tutte le posizioni** ed eseguire il drill-down nella struttura di cartelle fino all'elemento.
5. Fare doppio clic per aprire l'elemento in modo nativo in Esplora contenuto.

## <a name="see-also"></a>Vedere anche

- [Etichette di riservatezza](sensitivity-labels.md)
- [Etichette di conservazione](labels.md)
- [Tipi di informazioni riservate disponibili da cercare](what-the-sensitive-information-types-look-for.md)
- [Panoramica dei criteri di conservazione](retention-policies.md)
- [Panoramica della prevenzione della perdita dei dati](data-loss-prevention-policies.md)
