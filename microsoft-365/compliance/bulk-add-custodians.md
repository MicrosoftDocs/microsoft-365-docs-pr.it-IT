---
title: Aggiungere in blocco i depositari a un caso avanzato di eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432439"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a>Aggiungere in blocco i depositari a un caso di eDiscovery avanzato (anteprima)

Per i casi di eDiscovery avanzati che coinvolgono numerosi depositari, è possibile importare più depositari contemporaneamente in un file CSV che contiene tutte le informazioni necessarie per aggiungerle a un caso.

## <a name="bulk-add-custodians"></a>Aggiungere in blocco i depositari

1. Immettere il caso e passare alla scheda **origini** .

2. Fare clic su **Importa depositari**

3. Nella pagina riquadro a comparsa, fare clic su **Scarica un modello vuoto** per scaricare un file del modello del custode CSV.

4. Aggiungere le informazioni di custodia al file CSV e salvarlo nel computer locale. Per informazioni sulle proprietà del file CSV, vedere la sezione successiva.

5. Nella scheda **origini** fare clic di nuovo su **Importa depositari** . 
6. Nella pagina riquadro a comparsa fare clic su **Sfoglia** e caricare il file CSV.

   Dopo il caricamento del file CSV, viene creato e visualizzato un processo di BulkAddCustodian nella scheda **processi** . Il processo consente di convalidare i depositari e le origini dati corrispondenti e quindi di aggiungerli alla scheda **depositari** nella pagina **origini** del caso.

## <a name="custodian-csv-file"></a>File CSV del custode

Dopo aver scaricato il modello CSV, è possibile aggiungere depositari e l'origine dati in ogni riga. Assicurarsi di non modificare i nomi delle colonne nella riga di intestazione.

| Nome colonna|Descrizione|
|:------- |:------------------------------------------------------------|
|**ContactEmail custode**     | Indirizzo di posta elettronica UPN del custode. Esempio: sarad@onmicrosoft.contoso.com           |
|**Exchange abilitato** | Valore TRUE/FALSE se si desidera aggiungere la cassetta postale del custode.      |
|**OneDrive abilitato** | Valore vero/falso se si desidera aggiungere l'account OneDrive for business del custode. |
|**È OnHold**        | Valore TRUE/FALSE se si desidera che il custode venga premuto.       |
|**Tipo di Workload1**         | Valore stringa che indica il tipo di origine dati da associare al custode. <br />I valori possibili includono: <br />ExchangeMailbox, SitoSharePoint, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite |
|**Percorso Workload1**     | A seconda del tipo di carico di lavoro, si tratta del percorso dei dati del carico di lavoro, ad esempio l'indirizzo di posta elettronica di una cassetta postale di Exchange o l'URL di un sito di SharePoint. |
|||

Di seguito è riportato un esempio di file CSV con informazioni sul custode:  

| ContactEmail      | Exchange abilitato | OneDrive abilitato | È OnHold | Tipo di Workload1 | Percorso Workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SitoSharePoint | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Convalida del custode e dell'origine dati

Quando si carica il file CSV del custode, Advanced eDiscovery esegue le operazioni seguenti:

1. Convalida i depositari e le rispettive origini dati. 

2. Indicizza tutte le origini dati per ogni custode e le inserisce in blocco (se la proprietà è OnHold è impostata su TRUE).

### <a name="custodian-validation"></a>Convalida del custode

Attualmente, è supportata solo l'importazione di depositari che si trovano in Azure Active Directory (AAD).

È possibile convalidare e trovare i depositari utilizzando il valore UPN nella colonna **posta elettronica di contatto** nel file CSV. I depositari convalidati vengono automaticamente aggiunti al caso ed elencati nella scheda **depositaria** nella pagina **origini** del caso. Se un custode non può essere convalidato, sono elencati nel registro degli errori per il processo di BulkAddCustodian elencato nella scheda **processi** nel caso. Gli amministratori non convalidati non vengono aggiunti al caso.

### <a name="data-source-validation"></a>Convalida dell'origine dati

Dopo aver convalidato i depositari e averne aggiunto il caso, viene convalidata ogni origine dati associata a un custode. Se non è possibile trovare un'origine dati per un custode, il valore **non convalidato** verrebbe visualizzato nella colonna **convalidata** nella scheda **depositaria** per tale custode.

### <a name="remediating-unvalidated-data-sources"></a>Correzione di origini dati non convalidate

Per correggere i depositari con origini dati non convalidate: 

1. Nella scheda **custode** selezionare un custode che non è stato convalidato.

2. Nella pagina a comparsa del custode, scorrere fino alla sezione **origini dati** per visualizzare le origini dati associate al custode. Sono elencate le origini dati convalidate e non convalidate.

3. Nella sezione **origini dati** fare clic su **modifica**.

4. Nella pagina **scegliere i percorsi di custodia** rimuovere un'origine dati non convalidata.

5. Nella pagina **Seleziona percorsi aggiuntivi** fare clic su **Aggiorna** per aggiungere origini dati aggiuntive per un custode.
