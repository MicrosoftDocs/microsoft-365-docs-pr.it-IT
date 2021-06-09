---
title: Importare i custodi in Advanced eDiscovery caso
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Utilizzare lo strumento di importazione d per aggiungere rapidamente più custodi e le origini dati associate a un caso in Advanced eDiscovery.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421613"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importare i custodi in Advanced eDiscovery caso

Per Advanced eDiscovery casi che coinvolgono molti custodi, è possibile importare più custodi contemporaneamente utilizzando un file CSV contenente le informazioni necessarie per aggiungerli a un caso.

## <a name="import-custodians"></a>Importare i custodi

1. Aprire il Advanced eDiscovery e selezionare la **scheda Origini** dati.

2. Fare **clic su Aggiungi origine dati** Importa  >  **custodi.**

3. Nella pagina **a comparsa Importa i** custodi fare clic su Scarica un modello **vuoto** per scaricare un file CSV del modello di depositario.

   ![Scaricare un modello CSV dalla pagina a comparsa Importa i custodi](../media/ImportCustodians1.png)

4. Aggiungere le informazioni di custodia al file CSV e salvarle nel computer locale. Per informazioni sulle proprietà necessarie nel [file CSV,](#custodian-csv-file) vedere la sezione File CSV del responsabile.

5. Dopo aver preparato il file CSV con le informazioni  del responsabile, tornare alla scheda Origini dati e fare di nuovo clic **su** Aggiungi origine dati  >  **Importare i depositnti.**

6. Nella pagina **a comparsa Importa custodi** fare clic su **Sfoglia** e quindi caricare il file CSV contenente le informazioni sul responsabile.

   Dopo il caricamento del file CSV, viene creato e visualizzato un processo denominato **BulkAddCustodian** nella **scheda** Processi. Il processo convalida i custodi e le origini dati associate e quindi li aggiunge alla **pagina Origini** dati del caso.

## <a name="custodian-csv-file"></a>File CSV di custodia

Dopo aver scaricato il modello di responsabile CSV, è possibile aggiungere i custodi e la relativa origine dati in ogni riga. Assicurarsi di non modificare i nomi delle colonne nella riga di intestazione. Utilizzare le colonne tipo di carico di lavoro e posizione del carico di lavoro per associare altre origini dati a un responsabile.

| Nome colonna|Descrizione|
|:------- |:------------------------------------------------------------|
|**Contatto responsabileEmail**     |Indirizzo di posta elettronica UPN del responsabile. Ad esempio, sarad@contoso.onmicrosoft.com.           |
|**Exchange Abilitato** | Valore TRUE/FALSE per includere o meno la cassetta postale del responsabile.      |
|**OneDrive Abilitato** | Valore TRUE/FALSE per includere o non includere l'account OneDrive for Business del responsabile. |
|**Is OnHold**        | Valore TRUE/FALSE per indicare se mettere in attesa le origini dati del responsabile. <sup>1</sup>     |
|**Tipo Carico di lavoro1**         |Valore stringa che indica il tipo di origine dati da associare al responsabile. I valori possibili includono: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Posizione carico di lavoro1**     | A seconda del tipo di carico di lavoro, si tratta del percorso dell'origine dati. Ad esempio, l'indirizzo di posta elettronica per una Exchange o l'URL di un SharePoint sito. |
|||

> [!NOTE]
> <sup>1</sup> È possibile mettere in attesa un massimo di 1.000 cassette postali e 100 siti utilizzando il processo di importazione del responsabile e il file CSV. È possibile utilizzare questo processo per aggiungere più di 1.000 custodi a un caso, ma i limiti di blocco sono ancora applicabili. Per ulteriori informazioni sui limiti di blocco, vedere [Limiti in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).

Ecco un esempio di file CSV con informazioni sul responsabile:<br/><br/>

|Contatto responsabileEmail      | Exchange Abilitato | OneDrive Abilitato | Is OnHold | Tipo Carico di lavoro1 | Posizione carico di lavoro1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Convalida dell'origine dati e del responsabile

Dopo aver caricato il file CSV del responsabile, Advanced eDiscovery le operazioni seguenti:

1. Convalida i custodi e le relative origini dati.

2. Indicizza tutte le origini dati per ogni responsabile e le mette in attesa (se la proprietà **Is OnHold** nel file CSV è impostata su TRUE).

### <a name="custodian-validation"></a>Convalida del responsabile

Attualmente, supportiamo solo l'importazione di custodi inclusi nell'organizzazione Azure Active Directory (Azure AD).

Lo strumento di importazione dei depositati trova e convalida i depositati utilizzando il valore UPN nella colonna **Custodian contactEmail** nel file CSV. I custodi convalidati vengono aggiunti automaticamente al caso ed elencati nella **scheda Origini** dati del caso. Se un responsabile non può essere convalidato, viene elencato nel registro degli errori per  il processo BulkAddCustodian elencato nella scheda Processi nel caso. I custodi non convalidati non vengono aggiunti al caso o elencati nella **scheda Origini** dati.

### <a name="data-source-validation"></a>Convalida dell'origine dati

Dopo che i custodi sono stati convalidati e aggiunti al caso, vengono aggiunti ogni cassetta postale principale e OneDrive account associato a un responsabile.

Tuttavia, se non è possibile trovare altre origini dati (ad esempio siti di SharePoint, Microsoft Teams, gruppi di Microsoft 365 o gruppi di Yammer) associate a un responsabile, nessuna di esse viene assegnata  al responsabile e il valore  Non convalidato viene visualizzato nella colonna Stato accanto al responsabile nella scheda Origini dati. 

Per aggiungere origini dati convalidate per un responsabile:

1. Nella scheda **Origini dati** selezionare un responsabile che contiene origini dati non convalidate.

2. Nella pagina del riquadro a comparsa del responsabile scorrere fino alla sezione **Posizioni** di custodia per visualizzare sia le origini dati convalidate che non convalidate associate al responsabile.

3. Fare **clic su** Modifica nella parte superiore della pagina a comparsa per rimuovere origini dati non valide o aggiungerne di nuove.

4. Dopo aver rimosso le origini dati non convalidate o averne aggiunta una nuova, il valore **Attivo** viene visualizzato nella colonna **Stato** del responsabile della scheda **Origini** dati. Per aggiungere origini che in precedenza non erano valide, segui i passaggi di correzione seguenti per aggiungerle manualmente a un responsabile.

### <a name="remediating-invalid-data-sources"></a>Correzione di origini dati non valide

Per aggiungere e associare manualmente un'origine dati non valida in precedenza:

1. Nella scheda **Origini dati** selezionare un responsabile per aggiungere e associare manualmente un'origine dati precedentemente non valida.

2. Fare **clic** su Modifica nella parte superiore della pagina a comparsa per associare cassette postali, siti, Teams o Yammer gruppi al responsabile. A tale scopo, fare **clic su** Modifica accanto al tipo di percorso dati appropriato.

3. Fare **clic su** Avanti per visualizzare la pagina Impostazioni **di** blocco e configurare l'impostazione di blocco per le origini dati aggiunte.

4. Fare **clic su** Avanti per visualizzare la pagina **Rivedi** i revisori e quindi fare clic su **Invia** per salvare le modifiche.
