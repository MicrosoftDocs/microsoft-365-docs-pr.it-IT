---
title: Introduzione a Esplora contenuto
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Esplora contenuto consente di visualizzare in modo nativo gli elementi con etichetta.
ms.openlocfilehash: 19ad68d3c32046754e366919e8c4e66336945624
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080725"
---
# <a name="get-started-with-content-explorer"></a>Introduzione a Esplora contenuto

Esplora contenuto di classificazione dei dati consente di visualizzare in modo nativo gli elementi che sono stati riepilogati nella pagina di panoramica.

![schermata compressa di Esplora contenuto](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a>Prerequisiti

A ogni account che accede e usa la classificazione dei dati deve essere assegnata una licenza da uno di questi abbonamenti:

- Microsoft 365 (E5)
- Office 365 (E5)
- Componente aggiuntivo Advanced Compliance (E5)
- Componente aggiuntivo Advanced Threat Intelligence (E5)
- Protezione delle informazioni e governance di Microsoft 365 E5/A5
- Conformità di Microsoft 365 E5/A5


### <a name="permissions"></a>Autorizzazioni

Per accedere alla scheda Esplora contenuto, è necessario che a un account sia assegnata l'appartenenza a uno di questi ruoli o gruppi di ruoli. 

**Gruppi di ruoli di Microsoft 365**

- Amministratore globale
- Amministratore di conformità
- Amministratore della sicurezza
- Amministratore dati di conformità

> [!IMPORTANT]
> L'appartenenza a questi gruppi di ruoli non consente di visualizzare l'elenco di elementi in Esplora contenuto o di visualizzare il contenuto degli elementi in Esplora contenuto.

### <a name="required-permissions-to-access-items-in-content-explorer"></a>Autorizzazioni necessarie per accedere agli elementi in Esplora contenuto

L'accesso a Esplora contenuto è estremamente limitato perché consente di leggere il contenuto dei file digitalizzati.

> [!IMPORTANT]
> Queste autorizzazioni sostituiscono le autorizzazioni assegnate in locale, che permettono di visualizzare il contenuto. 

Esistono due ruoli che permettono l'accesso a Esplora contenuto, concessi tramite il [Centro sicurezza e conformità Microsoft](https://protection.office.com/permissions):

- **Visualizzatore elenco di Esplora contenuto**: l'appartenenza a questo gruppo di ruoli consente di visualizzare ogni elemento e la relativa posizione nella visualizzazione elenco. Il ruolo `data classification list viewer` è stato preassegnato a questo gruppo di ruoli.

- **Visualizzatore contenuto di Esplora contenuto**: l'appartenenza a questo gruppo di ruolo consente di visualizzare il contenuto di ogni elemento dell'elenco. Il ruolo `data classification content viewer` è stato preassegnato a questo gruppo di ruoli.

L'account usato per accedere a Esplora contenuto deve essere presente in uno o entrambi i gruppi di ruoli. Si tratta di gruppi di ruoli indipendenti e non cumulativi. Ad esempio, se si vuole concedere a un account la possibilità di visualizzare solo gli elementi e le relative posizioni, concedere i diritti di Visualizzatore elenco di Esplora contenuto. Se si vuole che lo stesso account sia in grado di visualizzare anche il contenuto degli elementi dell'elenco, concedere anche i diritti di Visualizzatore contenuto di Esplora contenuto.

È anche possibile assegnare uno o entrambi i ruoli a un gruppo di ruoli personalizzato per personalizzare l'accesso a Esplora contenuto.

Un amministratore globale, un amministratore di conformità o un amministratore dei dati può assegnare l'appartenenza ai gruppi di ruolo Visualizzatore elenco di Esplora contenuto e Visualizzatore contenuto di Esplora contenuto necessaria.

## <a name="content-explorer"></a>Esplora contenuto

Esplora contenuto mostra uno snapshot corrente degli elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni riservate nell'organizzazione.

### <a name="sensitive-information-types"></a>Tipi di informazioni sensibili

I [criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md) aiutano a proteggere le informazioni riservate definite come **tipo di informazioni sensibili**. Microsoft 365 include le [definizioni per molti tipi di informazioni sensibili comuni](sensitive-information-type-entity-definitions.md) di diverse aree geografiche, pronte per l'uso. Ad esempio, un numero di carta di credito, numeri di conti corrente bancari, numeri di documenti di identità e numeri di servizio Windows Live ID.

> [!NOTE]
> Al momento Esplora contenuto non analizza i tipi di informazioni sensibili in Exchange Online.

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Un'[etichetta di sensibilità](sensitivity-labels.md) è semplicemente un contrassegno che indica il valore dell'elemento per l'organizzazione. Può essere applicata manualmente o automaticamente. Una volta applicata, viene incorporata nel documento e lo seguirà ovunque. Un'etichetta di riservatezza abilita varie misure protettive, ad esempio la filigrana obbligatoria o la crittografia.

Le etichetta di riservatezza devono essere abilitate per i file che si trovano in SharePoint e OneDrive affinché i dati corrispondenti vengano visualizzati nella pagina di classificazione dei dati. Per altre informazioni, vedere [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

### <a name="retention-labels"></a>Etichette di conservazione

Un'[etichetta di conservazione](retention.md) consente di definire per quanto tempo viene conservato un elemento etichettato prima di essere eliminato. Vengono applicate manualmente o automaticamente tramite criteri. Possono essere utili per favorire la conformità dell'organizzazione ai requisiti di legge e normativi.

### <a name="how-to-use-content-explorer"></a>Come usare Esplora contenuto

1. Aprire **Centro conformità Microsoft 365**  > **Classificazione dei dati** > **Esplora contenuto**.
2. Se si conosce il nome dell'etichetta o il tipo di informazioni sensibili, è possibile digitarlo nella casella filtro.
3. In alternativa, è possibile cercare l'elemento espandendo il tipo di etichetta e selezionando l'etichetta dall'elenco.
4. Selezionare una posizione in **Tutte le posizioni** ed eseguire il drill-down nella struttura di cartelle fino all'elemento.
5. Fare doppio clic per aprire l'elemento in modo nativo in Esplora contenuto.

### <a name="export"></a>Esporta
Il controllo **Esporta** crea un file .csv che contiene un elenco di tutti gli elementi visualizzati nel riquadro **Tutte le posizioni**.

![controllo esporta per classificazione dati](../media/data_classification_export_control.png)


### <a name="search"></a>Ricerca

Quando viene eseguito il drill-down in una posizione, come una cartella di Exchange o un sito SharePoint o OneDrive, si apre lo strumento di **ricerca**.

![strumento di ricerca di Esplora contenuto](../media/data_classification_search_tool.png)


L'ambito dello strumento di ricerca è il contenuto del riquadro **Tutte le posizioni** e ciò che è possibile cercare varia in base alla posizione selezionata. 

Quando la posizione selezionata è **Exchange**, è possibile effettuare la ricerca nell'intero indirizzo di posta elettronica della cassetta postale, ad esempio `user@domainname.com`.

Quando la posizione selezionata è **SharePoint** o **OneDrive**, lo strumento di ricerca si apre quando viene eseguito il drill-down dei nomi dei siti, delle cartelle e dei file. 

> [!NOTE]
> **OneDrive** Durante il programma di anteprima, abbiamo ascoltato i preziosi feedback degli utenti sull'integrazione di OneDrive. In base al feedback ricevuto, la funzionalità OneDrive rimarrà in anteprima finché non saranno disponibili tutte le correzioni. In base al tenant, alcuni clienti potrebbero non vedere OneDrive come posizione. Apprezziamo molto il continuo supporto degli utenti.

Ecco cosa è possibile cercare:


|valore|esempio  |
|---------|---------|
|nome completo del sito    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|nome della cartella radice - ricerca tutte le sottocartelle    | `/sites`        |
|nome del file    |    `RES_Resume_1234.txt`     |
|testo all'inizio del nome del file| `RES`|
|testo dopo un trattino basso (_) nel nome del file|`Resume` o `1234`| 
|estensione del file|`txt`|


## <a name="see-also"></a>Vedere anche

- [Informazioni sulle etichette di riservatezza](sensitivity-labels.md)
- [Informazioni sui criteri e sulle etichette di conservazione](retention.md)
- [Sensitive information type entity definitions.md](sensitive-information-type-entity-definitions.md)
- [Panoramica della prevenzione della perdita dei dati](data-loss-prevention-policies.md)
