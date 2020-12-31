---
title: Importare i depositari in un caso avanzato di eDiscovery
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
description: Utilizzare lo strumento di importazione dto aggiungere rapidamente più depositari e le origini dati associate a un caso in Advanced eDiscovery.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740303"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importare i depositari in un caso avanzato di eDiscovery

Per i casi di eDiscovery avanzati che coinvolgono numerosi depositari, è possibile importare più depositari contemporaneamente utilizzando un file CSV che contiene le informazioni necessarie per aggiungerle a un caso.

## <a name="import-custodians"></a>Importare i depositari

1. Aprire il caso Advanced eDiscovery e selezionare la scheda **origini dati** .

2. Fare clic su Aggiungi depositari di importazione di **origine dati**  >  .

3. Nella pagina **Importa** riquadro a comparsa dei depositari, fare clic su **Scarica un modello vuoto** per scaricare un file CSV del modello di custode.

   ![Scaricare un modello CSV dalla pagina importazione a comparsa dei depositari](../media/ImportCustodians1.png)

4. Aggiungere le informazioni di custodia al file CSV e salvarlo nel computer locale. Per informazioni sulle proprietà obbligatorie nel file CSV, vedere la sezione [file CSV del custode](#custodian-csv-file) .

5. Dopo aver preparato il file CSV con le informazioni sul custode, tornare alla scheda **origini dati** e fare di nuovo clic su Aggiungi depositari di importazione di **origine dati**  >   .

6. Nella pagina **Importa** riquadro a comparsa dei depositari fare clic su **Sfoglia** e quindi caricare il file CSV che contiene le informazioni sul custode.

   Dopo il caricamento del file CSV, viene creato e visualizzato un processo denominato **BulkAddCustodian** nella scheda **processi** . Il processo consente di convalidare i depositari e le origini dati associate e quindi di aggiungerli alla pagina **origini dati** del caso.

## <a name="custodian-csv-file"></a>File CSV del custode

Dopo aver scaricato il modello del custode CSV, è possibile aggiungere depositari e l'origine dati in ogni riga. Assicurarsi di non modificare i nomi delle colonne nella riga di intestazione. Per associare altre origini dati a un custode, utilizzare le colonne del tipo di carico di lavoro e del percorso del carico di lavoro.

| Nome colonna|Descrizione|
|:------- |:------------------------------------------------------------|
|**ContactEmail custode**     |L'indirizzo di posta elettronica UPN del custode. Ad esempio, sarad@contoso.onmicrosoft.com.           |
|**Exchange abilitato** | Valore TRUE/FALSE per includere o meno la cassetta postale del custode.      |
|**OneDrive abilitato** | Valore TRUE/FALSE per includere o meno l'account OneDrive for business del custode. |
|**È OnHold**        | Valore TRUE/FALSE per indicare se inserire le origini dati del custode in attesa.       |
|**Tipo di Workload1**         |Valore stringa che indica il tipo di origine dati da associare al custode. I valori possibili includono: <br/>- ExchangeMailbox<br/> -SitoSharePoint<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Percorso Workload1**     | A seconda del tipo di carico di lavoro, si tratta del percorso dell'origine dati. Ad esempio, l'indirizzo di posta elettronica di una cassetta postale di Exchange o l'URL di un sito di SharePoint. |
|||

Di seguito è riportato un esempio di file CSV con informazioni sul custode:<br/><br/>

|ContactEmail custode      | Exchange abilitato | OneDrive abilitato | È OnHold | Tipo di Workload1 | Percorso Workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SitoSharePoint | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Convalida del custode e dell'origine dati

Dopo aver caricato il file CSV del custode, Advanced eDiscovery esegue le operazioni seguenti:

1. Convalida i depositari e le rispettive origini dati.

2. Indicizza tutte le origini dati per ogni custode e le inserisce in blocco (se la proprietà **è OnHold** nel file CSV è impostata su true).

### <a name="custodian-validation"></a>Convalida del custode

Attualmente, è supportata solo l'importazione di custodi che sono inclusi nell'Azure Active Directory (Azure AD) dell'organizzazione.

Lo strumento di importazione depositaria consente di individuare e convalidare i depositari utilizzando il valore UPN nella colonna **ContactEmail depositaria** nel file CSV. I depositari convalidati vengono automaticamente aggiunti al caso ed elencati nella scheda **origini dati** del caso. Se un custode non può essere convalidato, sono elencati nel registro degli errori per il processo di BulkAddCustodian elencato nella scheda **processi** nel caso. Gli amministratori non convalidati non vengono aggiunti al caso o sono elencati nella scheda **origini dati** .

### <a name="data-source-validation"></a>Convalida dell'origine dati

Dopo aver convalidato e aggiunto i depositari al caso, viene aggiunta ogni cassetta postale principale e l'account OneDrive associato a un custode.

Tuttavia, se non è possibile trovare una delle altre origini dati (ad esempio, siti di SharePoint, Microsoft teams, gruppi di Microsoft 365 o gruppi di Yammer) associati a un custode, nessuno di essi viene assegnato al custode e il valore **non convalidato** viene visualizzato nella colonna **stato** accanto al custode nella scheda **origini dati** .

Per aggiungere origini dati convalidate per un custode:

1. Nella scheda **origini dati** selezionare un custode che contiene origini dati che non vengono convalidate.

2. Nella pagina riquadro a comparsa custode, scorrere fino alla sezione **percorsi custodia** per visualizzare le origini dati convalidate e non convalidate associate al custode.

3. Fare clic su **modifica** nella parte superiore della pagina a comparsa per rimuovere origini dati non valide o aggiungerne di nuove.

4. Dopo aver rimosso le origini dati non convalidate o averne aggiunto uno nuovo, il valore **attivo** viene visualizzato nella colonna **stato** per il custode nella scheda **origini dati** . Per aggiungere fonti che in precedenza risultavano non valide, seguire i passaggi di correzione riportati di seguito per aggiungerli manualmente a un custode.

### <a name="remediating-invalid-data-sources"></a>Correzione di origini dati non valide

Per aggiungere e associare manualmente un'origine dati precedentemente non valida:

1. Nella scheda **origini dati** selezionare un custode per aggiungere manualmente e associare un'origine dati precedentemente non valida.

2. Fare clic su **modifica** nella parte superiore della pagina a comparsa per associare le cassette postali, i siti, i team o i gruppi di Yammer al custode. A tale scopo, fare clic su **modifica** accanto al tipo di percorso dati appropriato.

3. Fare clic su **Avanti** per visualizzare la pagina **impostazioni di blocco** e configurare l'impostazione di blocco per le origini dati aggiunte.

4. Fare clic su **Avanti** per visualizzare la pagina **revisione dei custodi** e quindi fare clic su **Submit** per salvare le modifiche.
