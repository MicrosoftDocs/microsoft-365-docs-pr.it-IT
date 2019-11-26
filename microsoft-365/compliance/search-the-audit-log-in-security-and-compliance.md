---
title: Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: "Usa il Centro sicurezza e conformità per eseguire una ricerca nel log di controllo unificato e visualizzare l'attività degli utenti e degli amministratori nella tua organizzazione di Office 365. "
ms.openlocfilehash: 43ab1083ad028ee53ad355a84fda17b02decbc70
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "39233519"
---
# <a name="search-the-audit-log-in-the-security--compliance-center"></a>Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità

## <a name="introduction"></a>Introduzione

Se è necessario verificare se un utente ha visualizzato un documento specifico o ha eliminato un elemento dalla cassetta postale, si può usare il Centro sicurezza e conformità di Office 365 per eseguire una ricerca nel log di controllo unificato e vedere le attività di utenti e amministratori nell'organizzazione di Office 365. Perché usare un log di controllo unificato? Perché è possibile cercare i tipi seguenti di attività di utenti e amministratori in Office 365:

- Attività utente in SharePoint Online e OneDrive for Business

- Attività utente in Exchange Online (registrazione di controllo delle cassette postali di Exchange)

- Attività amministratore in SharePoint Online

- Attività amministratore in Azure Active Directory (servizio directory per Office 365)

- Attività amministratore in Exchange Online (registrazione di controllo dell'amministratore di Exchange )

- Attività utente e amministratore in Sway

- Attività eDiscovery nel Centro sicurezza e conformità

- Attività utente e amministratore in Power BI

- Attività utente e amministratore in Microsoft Teams

- Attività utente e amministratore in Dynamics 365

- Attività utente e amministratore in Yammer

- Attività utente e amministratore in Microsoft Flow

- Attività utente e amministratore in Microsoft Stream

- Attività di analisti e amministratori in Microsoft Workplace Analytics

- Attività utente e amministratore in Microsoft PowerApps

## <a name="before-you-begin"></a>Prima di iniziare

Accertarsi di leggere i seguenti elementi prima di iniziare la ricerca del registro di controllo di Office 365.

- È necessario che l'amministratore corrente o un altro amministratore attivi la registrazione di controllo prima di iniziare a eseguire ricerche nel log di controllo di Office 365. Per attivare la registrazione, fare clic su **Avvia registrazione attività utenti e amministratore** nella pagina **Ricerca log di controllo** nella pagina Centro sicurezza e conformità. Se questo collegamento non è visibile, il controllo è stato già attivato per la propria organizzazione. Dopo l'attivazione, verrà visualizzato un messaggio che indica che è in corso la preparazione del log di controllo e che sarà possibile eseguire una ricerca in un paio d'ore, dopo il completamento della preparazione. Questa procedura deve essere eseguita una sola volta.

  > [!NOTE]
  > Microsoft sta per impostare come predefinita l'attivazione del controllo. Nel frattempo, è possibile attivarlo come descritto in precedenza.

- È necessario avere il ruolo relativo ai log di controllo di sola lettura o ai log di controllo in Exchange Online per poter eseguire ricerche nel log di controllo di Office 365. Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella pagina **Autorizzazioni** nell'Interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 e Microsoft 365 vengono aggiunti automaticamente come membri del gruppo di ruoli Gestione organizzazione in Exchange Online. Per consentire a un utente di eseguire ricerche nel log di controllo di Office 365 con il livello minimo di privilegi, è possibile creare un gruppo di ruoli personalizzato in Exchange Online, aggiungere il ruolo relativo ai log di controllo di sola lettura o ai log di controllo e quindi aggiungere l'utente come membro del nuovo gruppo di ruoli. Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

  > [!IMPORTANT]
  > Se si assegna a un utente il ruolo relativo ai log di controllo di sola lettura o ai log di controllo nella pagina **Autorizzazioni** del Centro sicurezza e conformità, l'utente non potrà eseguire ricerche nel log di controllo di Office 365. È necessario assegnare le autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante usato per la ricerca nel log di controllo è un cmdlet di Exchange Online.

- Quando un'attività di controllo viene eseguita da un utente o da un amministratore, viene generato un record di controllo che viene archiviato nel log di controllo di Office 365 per l'organizzazione. Il periodo di tempo per il quale viene conservato il record di controllo (ed disponibile per la ricerca nel log di controllo) varia in base all'abbonamento a Office 365 e, in particolare, al tipo di licenza assegnata a un utente specifico.

  - **Office 365 E3:** i record di controllo vengono conservati per 90 giorni. Ciò significa che è possibile cercare nel log di controllo le attività eseguite negli ultimi 90 giorni.

    > [!NOTE]
    > Anche se il controllo delle cassette postali è attivato per impostazione predefinita, si potrebbe notare che gli eventi di controllo delle cassette postali per alcuni utenti non sono inclusi nelle ricerche nei log di controllo nel Centro sicurezza e conformità o nell'API Office 365 Management Activity. Vedere la sezione [Altre informazioni sulla registrazione di controllo delle cassette postali](enable-mailbox-auditing.md#more-information).

  - **Office 365 E5:** i record di controllo vengono conservati per 90 giorni. Il mantenimento dei record di controllo per un anno potrebbe essere disponibile per gli utenti E5 e gli utenti con una licenza E3 e una licenza per il componente aggiuntivo Office 365 Advanced Compliance.

    > [!NOTE]
    > Il programma di anteprima privata per il periodo di conservazione di un anno per i record di controllo per le organizzazioni E5 (o per gli utenti delle organizzazioni E3 con licenza per i componenti aggiuntivi per la conformità avanzata) è chiuso alle nuove iscrizioni. Questo articolo verrà aggiornato quando il periodo di conservazione di un anno sarà disponibile in anteprima pubblica o rilasciato per la disponibilità generale.

- Se si desidera disattivare la ricerca nel log di controllo in Office 365 per la propria organizzazione, è possibile eseguire questo comando nell'istanza di PowerShell remota connessa all'organizzazione di Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Per attivare di nuovo la ricerca nel log di controllo, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

  Per altre informazioni, vedere [Disattivare la ricerca nel log di controllo in Office 365](turn-audit-log-search-on-or-off.md).

- Come indicato in precedenza, il cmdlet sottostante usato per la ricerca nel log di controllo è un cmdlet di Exchange Online, ovvero **Search-UnifiedAuditLog**. Ciò significa che è possibile usare questo cmdlet anziché la pagina **Ricerca log di controllo** in Centro sicurezza e conformità per eseguire una ricerca nel log di controllo di Office 365. È necessario eseguire questo cmdlet in una sessione remota di PowerShell connessa all'organizzazione di Exchange Online. Per altre informazioni, vedere [Search-UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776).

  Per informazioni sull'esportazione dei risultati della ricerca restituiti dal cmdlet **Search-UnifiedAuditLog** in un file CSV, vedere la sezione "Suggerimenti per l'esportazione e la visualizzazione del log di controllo in [Esportare, configurare e visualizzare i record del log di controllo ](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- Per scaricare i dati a livello di programmazione dal log di controllo di Office 365, è consigliabile usare l'API Office 365 Management Activity, invece di uno script di PowerShell. L'API Office 365 Management Activity è un servizio Web REST che è possibile utilizzare per sviluppare operazioni e soluzioni per la sicurezza e il monitoraggio della conformità per l'organizzazione. Per altre informazioni, vedere [Riferimento API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

- La visualizzazione della voce del log di controllo nei risultati della ricerca può richiedere fino a 30 minuti o a 24 ore dal momento in cui si verifica l'evento. La tabella seguente mostra il tempo necessario per i diversi servizi in Office 365.

  |**Servizio Office 365**|**30 minuti**|**24 ore**|
  |:-----|:-----:|:-----:|
  |Advanced Threat Protection e Threat Intelligence|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Azure Active Directory (eventi di accesso utente)||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Interfaccia di amministrazione di Azure Active Directory (eventi di amministrazione)||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Prevenzione della perdita di dati|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Dynamics 365 CRM|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |eDiscovery|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Exchange Online|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Flow|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Project|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Stream|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Teams|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Power BI|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Centro sicurezza e conformità|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |SharePoint Online e OneDrive for Business|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Sway||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Workplace Analytics|![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Yammer||![Segno di spunta](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

- Azure Active Directory (Azure AD) è il servizio directory per Office 365. Il log di controllo unificato contiene le attività di utenti, gruppi, applicazioni, domini e directory eseguite nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure. Per un elenco completo degli eventi di Azure AD, vedere [Eventi del report di controllo di Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).

- La registrazione di controllo per Power BI non è abilitata per impostazione predefinita. Per cercare le attività di Power BI nel log di controllo di Office 365, è necessario abilitare il controllo nel portale di amministrazione di Power BI. Per le istruzioni, vedere la sezione "Log di controllo" nel [portale di amministrazione di Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).

## <a name="search-the-audit-log"></a>Eseguire ricerche nel log di controllo

Ecco il processo per la ricerca nel log di controllo in Office 365.

[Passaggio 1: Eseguire una ricerca nel log di controllo](#step-1-run-an-audit-log-search)

[Passaggio 2: Visualizzare i risultati della ricerca](#step-2-view-the-search-results)

[Passaggio 3: Filtrare i risultati della ricerca](#step-3-filter-the-search-results)

[Passaggio 4: Esportare i risultati della ricerca in un file](#step-4-export-the-search-results-to-a-file)

### <a name="step-1-run-an-audit-log-search"></a>Passaggio 1: Eseguire una ricerca nel log di controllo

1. Passare a [https://protection.office.com](https://protection.office.com).

    > [!TIP]
    > Usare una sessione di esplorazione privata (invece di una normale) per accedere al Centro sicurezza e conformità, per impedire che le credenziali con cui si è attualmente connessi vengano utilizzate. Per aprire una finestra InPrivate Browsing in Internet Explorer o in Microsoft Edge, premere CTRL + MAIUSC + P. Per aprire una sessione di esplorazione privata in Google Chrome (denominata finestra di navigazione in incognito), premere CTRL + MAIUSC + N.

2. Accedere a Office 365 usando l'account aziendale o dell'istituto di istruzione.

3. Nel riquadro sinistro del Centro sicurezza e conformità, fare clic su **Cerca**, quindi su **Ricerca log di controllo**.

    Viene visualizzata la pagina **Ricerca log di controllo**.

    ![Configurare i criteri, quindi fare clic su Cerca per eseguire un report](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)

    > [!NOTE]
    > È necessario attivare la registrazione di controllo per poter eseguire una ricerca nel log di controllo. Se è visualizzato il collegamento **Avviare la registrazione delle attività di utenti e amministratori**, fare clic su di esso per attivare il controllo. Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione.

4. Configurare i criteri di ricerca seguenti: 

    a. **Attività**: fare clic sull'elenco a discesa per visualizzare le attività che è possibile cercare. Le attività di utenti e amministratori sono organizzate in gruppi di attività correlate. È possibile selezionare attività specifiche oppure è possibile fare clic sul nome del gruppo di attività per selezionare tutte le attività del gruppo. È anche possibile fare clic su un'attività selezionata per annullare la selezione. Dopo aver eseguito la ricerca, vengono visualizzate solo le voci del log di controllo per le attività selezionate. Se si seleziona **Visualizza i risultati per tutte le attività**, vengono visualizzati i risultati per tutte le attività eseguite dall'utente o dal gruppo di utenti selezionato.

    Nel log di controllo di Office 365 vengono registrate più di 100 attività di utenti e amministratori. Fare clic sulla scheda **Attività controllate** in questo articolo per visualizzare le descrizioni delle singole attività per i vari servizi di Office 365.

    b. **Data inizio** e **Data fine**: per impostazione predefinita, sono selezionati gli ultimi sette giorni. Selezionare un intervallo di date e ore per visualizzare gli eventi che si sono verificati in quel periodo. La data e l'ora sono specificate in formato UTC (Coordinated Universal Time). L'intervallo massimo che è possibile specificare è 90 giorni. Se l'intervallo di date selezionato è maggiore di 90 giorni, verrà visualizzato un errore.

    > [!TIP]
    > Se si usa l'intervallo di date massimo di 90 giorni, selezionare l'ora corrente per **Data inizio**. In caso contrario, verrà visualizzato un errore che indica che la data di inizio è precedente alla data di fine. Se è stato attivato il controllo negli ultimi 90 giorni, l'intervallo di date massimo non può iniziare prima della data in cui il controllo è stato attivato.

    c. **Utenti**: fare clic in questa casella e quindi selezionare uno o più utenti per cui visualizzare i risultati della ricerca. Nell'elenco di risultati vengono visualizzate le voci del log di controllo per l'attività selezionata eseguita dagli utenti specificati in questa casella. Lasciare la casella vuota per restituire le voci per tutti gli utenti (e gli account del servizio) nell'organizzazione.

    d. **File, cartella o sito**: digitare alcuni o tutti i nomi di file o cartelle per cercare l'attività relativa al file o alla cartella che contiene la parola chiave specificata. È anche possibile specificare un URL di un file o una cartella. Se si utilizza un URL, assicurarsi di digitare il percorso URL completo oppure, se si digita solo una parte dell'URL, di non includere spazi o caratteri speciali.

    Lasciare questa casella vuota per restituire le voci per tutti i file e le cartelle nell'organizzazione.

   **SUGGERIMENTI**

   - Se si stanno cercando tutte le attività correlate a un **sito**, aggiungere il simbolo jolly (\*) dopo l'URL per restituire tutte le voci per quel sito; ad esempio, **"https://contoso-my.sharepoint.com/personal/*"**.

   - Se si stanno cercando tutte le attività correlate a un **file**, aggiungere il simbolo jolly (\*) prima del nome file per restituire tutte le voci per quel file; ad esempio, **"*Customer_Profitability_Sample.csv"**.

5. Fare clic su **Cerca** per eseguire la ricerca usando i criteri di ricerca.

   I risultati della ricerca vengono caricati e, dopo alcuni istanti, vengono visualizzati in **Risultati**. Al termine della ricerca, viene visualizzato il numero di risultati trovati. Nel riquadro **Risultati** verranno visualizzati al massimo 5.000 eventi in incrementi di 150 eventi. Se sono presenti più di 5.000 eventi che soddisfano i criteri di ricerca, verranno visualizzati i 5.000 eventi più recenti.

   ![Il numero di risultati viene visualizzato al termine della ricerca](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)

#### <a name="tips-for-searching-the-audit-log"></a>Suggerimenti per la ricerca nel log di controllo

- È possibile selezionare attività specifiche da cercare facendo clic sul relativo nome. In alternativa, è possibile cercare tutte le attività in un gruppo (ad esempio **Attività su file e cartelle**) facendo clic sul nome del gruppo. Se è selezionata un'attività, è possibile fare clic su di essa per annullare la selezione. È anche possibile usare la casella di ricerca per visualizzare le attività contenenti la parola chiave digitata.

  ![Fare clic sul nome del gruppo di attività per selezionare tutte le attività](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)

- È necessario selezionare **Visualizza i risultati per tutte le attività** nell'elenco **Attività** per visualizzare gli eventi del log di controllo dell'amministratore di Exchange. Gli eventi di questo log di controllo mostrano un nome di cmdlet (ad esempio, **Set-Mailbox**) nella colonna **Attività** dei risultati. Per altre informazioni, fare clic sulla scheda **Attività controllate** in questo argomento, quindi fare clic su **Attività di amministrazione di Exchange**.

  Allo stesso modo, esistono alcune attività di controllo che non hanno un elemento corrispondente nell'elenco **Attività**. Se si conosce il nome dell'operazione per queste attività, è possibile cercare tutte le attività, filtrare i risultati digitando il nome dell'operazione nella casella per la colonna **Attività**. Vedere [Passaggio 3: Filtrare i risultati della ricerca](#step-3-filter-the-search-results) per altre informazioni su come filtrare i risultati.

- Fare clic su **Cancella** per cancellare i criteri di ricerca correnti. L'intervallo di date torna impostato sul valore predefinito corrispondente agli ultimi sette giorni. È anche possibile fare clic su **Deseleziona tutto per visualizzare i risultati per tutte le attività** per annullare tutte le attività selezionate.

- Se vengono trovati 5.000 risultati, è probabile che ci siano più di 5.000 eventi che soddisfano i criteri di ricerca. È possibile perfezionare i criteri di ricerca ed eseguire di nuovo la ricerca in modo che vengano restituiti meno risultati oppure è possibile esportare tutti i risultati della ricerca selezionando **Esporta risultati** \> **Scarica tutti i risultati**.

### <a name="step-2-view-the-search-results"></a>Passaggio 2: Visualizzare i risultati della ricerca

I risultati di una ricerca nel log di controllo vengono visualizzati in **Risultati** nella pagina **Ricerca log di controllo**. Come affermato in precedenza, vengono visualizzati al massimo 5.000 eventi (i più recenti) in incrementi di 150 eventi. Per visualizzare più eventi, è possibile usare la barra di scorrimento nel riquadro **Risultati** oppure è possibile premere **MAIUSC+FINE** per visualizzare i 150 eventi successivi.

I risultati includono le informazioni seguenti relative a ogni evento restituito dalla ricerca:

- **Data**: data e ora (in formato UTC) in cui si è verificato l'evento.

- **Indirizzo IP**: indirizzo IP del dispositivo usato durante la registrazione dell'attività. L'indirizzo IP viene visualizzato in formato IPv4 o IPv6.

   > [!NOTE]
  > Per alcuni servizi, il valore visualizzato in questo campo potrebbe corrispondere all'indirizzo IP di un'applicazione attendibile, ad esempio un'app di Office sul Web, che chiama il servizio per conto di un utente e non l'indirizzo IP del dispositivo usato dalla persona che ha eseguito l'attività. Inoltre, per le attività amministratore (o attività eseguite da un account di sistema) per gli eventi correlati ad Azure Active Directory, l'indirizzo IP non viene registrato e il valore visualizzato nel campo è `null`.

- **Utente**: utente (o account del servizio) che ha eseguito l'azione che ha attivato l'evento.

- **Attività**: attività eseguita dall'utente. Questo valore corrisponde alle attività selezionate nell'elenco a discesa **Attività**. Per un evento del log di controllo dell'amministratore di Exchange, il valore in questa colonna è un cmdlet di Exchange.

- **Elemento**: oggetto creato o modificato come risultato dell'attività corrispondente. Ad esempio, il file che è stato visualizzato o modificato oppure l'account utente che è stato aggiornato. Non tutte le attività presentano un valore in questa colonna.

- **Dettagli**: dettagli aggiuntivi su un'attività. Anche in questo caso, non tutte le attività hanno un valore.

> [!TIP]
> Fare clic su un'intestazione di colonna in **Risultati** per ordinare i risultati. È possibile ordinare i risultati dalla A alla Z o dalla Z alla A. Fare clic sull'intestazione **Data** per ordinare i risultati dal meno recente al più recente o viceversa.

#### <a name="view-the-details-for-a-specific-event"></a>Visualizzare i dettagli di un evento specifico

È possibile visualizzare altri dettagli di un evento facendo clic sul record dell'evento nell'elenco dei risultati della ricerca. Verrà visualizzata una pagina **Dettagli** contenente le proprietà dettagliate del record dell'evento. Le proprietà visualizzate dipendono dal servizio di Office 365 in cui si verifica l'evento. Per visualizzare questi dettagli, fare clic su **Altre informazioni**. Per le descrizioni, vedere [Proprietà dettagliate nel log di controllo di Office 365](detailed-properties-in-the-office-365-audit-log.md).

![Fare clic su Altre informazioni per visualizzare le proprietà dettagliate del record dell'evento del log di controllo](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

### <a name="step-3-filter-the-search-results"></a>Passaggio 3: Filtrare i risultati della ricerca

Oltre a ordinare i risultati di una ricerca nel log di controllo, è anche possibile filtrarli. Questa caratteristica è molto utile perché consente di filtrare rapidamente i risultati per un'attività o un utente specifico. È possibile iniziare da una ricerca più ampia e quindi filtrare rapidamente i risultati per visualizzare eventi specifici. È quindi possibile restringere i criteri ed eseguire di nuovo la ricerca affinché venga restituito un set di risultati più piccolo e conciso.

Per filtrare i risultati:

1. Eseguire una ricerca nel log di controllo.

2. Quando vengono visualizzati i risultati, fare clic su **Filtra risultati**.

   Sotto ogni intestazione di colonna vengono visualizzate le caselle delle parole chiave.

3. Fare clic su una delle caselle sotto un'intestazione di colonna e digitare una parola o una fase, a seconda della colonna in base a cui si sta filtrando. I risultati verranno riorganizzati dinamicamente per visualizzare gli eventi corrispondenti al filtro.

   ![Digitare una parola nel filtro per visualizzare gli eventi corrispondenti al filtro](media/542dc323-a997-402c-934b-cc5e218e50bc.png)

4. Per cancellare un filtro, fare clic su **X** nella casella del filtro oppure fare clic su **Nascondi filtro**.

> [!TIP]
> Per visualizzare gli eventi del log di controllo dell'amministratore di Exchange, digitare **-** (trattino) nella casella del filtro **Attività**. In questo modo, verranno visualizzati i nomi dei cmdlet, che sono indicati nella colonna **Attività** per gli eventi di amministrazione di Exchange. È anche possibile disporre i nomi dei cmdlet in ordine alfabetico.

### <a name="step-4-export-the-search-results-to-a-file"></a>Passaggio 4: Esportare i risultati della ricerca in un file

È possibile esportare i risultati di una ricerca nel log di controllo in un file con valori delimitati da virgole (CSV) nel computer locale. È possibile aprire il file in Microsoft Excel e usare caratteristiche come ricerca, ordinamento, filtro e divisione di una singola colonna (con più proprietà) in più colonne.

1. Eseguire una ricerca nel log di controllo e quindi modificare i criteri di ricerca fino a ottenere i risultati desiderati.

2. Fare clic su **Esporta risultati** e selezionare una delle opzioni seguenti:

   - **Salva i risultati caricati**: scegliere questa opzione per esportare solo le voci visualizzate in **Risultati** nella pagina **Ricerca log di controllo**. Il file CSV che viene scaricato contiene le stesse colonne (e gli stessi dati) presenti nella pagina (Data, Utente, Attività, Elemento e Dettagli). Il file CSV contiene una colonna aggiuntiva (denominata **Altro**) con altre informazioni sulla voce del log di controllo. Poiché si stanno esportando gli stessi risultati caricati (e visualizzabili) nella pagina **Ricerca log di controllo**, verranno esportate al massimo 5.000 voci.

   - **Scarica tutti i risultati**: scegliere questa opzione per esportare tutte le voci del log di controllo di Office 365 che soddisfano i criteri di ricerca. Per un ampio set di risultati della ricerca, scegliere questa opzione per scaricare tutte le voci del log di controllo oltre ai 5.000 risultati che possono essere visualizzati nella pagina **Ricerca log di controllo**. Questa opzione consente di scaricare i dati non elaborati dal log di controllo in un file CSV e include informazioni aggiuntive sulle voci del log di controllo in una colonna denominata **AuditData**. Se si sceglie questa opzione di esportazione potrebbe essere necessario più tempo per scaricare il file, in quanto il file potrebbe essere molto più grande di quello scaricato scegliendo l'altra opzione.

     > [!IMPORTANT]
     > È possibile scaricare al massimo 50.000 voci in un file CSV da una singola ricerca nel log di controllo. Se vengono scaricate 50.000 voci nel file CSV, è probabile che ci siano più di 50.000 eventi che soddisfano i criteri di ricerca. Per eseguire l'esportazione oltre questo limite, provare a usare un intervallo di date per ridurre il numero di voci del log di controllo. Potrebbe essere necessario eseguire più ricerche con intervalli di date più piccoli per esportare più di 50.000 voci.

3. Dopo aver selezionato un'opzione di esportazione, nella parte inferiore della finestra viene visualizzato un messaggio che chiede se aprire il file CSV, salvarlo nella cartella Download o salvarlo in una cartella specifica.

#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>Altre informazioni sull'esportazione e la visualizzazione dei risultati della ricerca nel log di controllo

- Se si scaricano tutti i risultati della ricerca, il file CSV contiene una colonna denominata **AuditData** con informazioni aggiuntive su ogni evento. I dati contenuti in questa colonna sono costituiti da un oggetto JSON che contiene più proprietà del record del log di controllo. Ogni coppia *property:value* dell'oggetto JSON è separata da una virgola. È possibile usare lo strumento di trasformazione JSON nell'editor di Power Query in Excel per dividere la colonna **AuditData** in più colonne, in modo che ogni proprietà dell'oggetto JSON disponga di una colonna specifica. In questo modo è possibile ordinare e filtrare in base a una o più di queste proprietà. Per le istruzioni dettagliate sull'uso dell'editor di Power Query per trasformare l'oggetto JSON, vedere [Esportare, configurare e visualizzare i record del log di controllo](export-view-audit-log-records.md).

  Dopo avere diviso la colonna **AuditData**, è possibile filtrare in base alla colonna **Operazioni** per visualizzare le proprietà dettagliate per un tipo di attività specifico.

- L'opzione **Scarica tutti i risultati** scarica i dati non elaborati dal log di controllo di Office 365 in un file CSV. Il file contiene nomi di colonna (CreationDate, UserIds, Operation, AuditData) diversi rispetto a quelli nel file scaricato selezionando l'opzione **Salva i risultati caricati**. Anche i valori per la stessa attività potrebbero essere diversi nei due diversi file CSV. Ad esempio, l'attività nella colonna **Azione** nel file CSV può avere un valore diverso rispetto alla versione descrittiva visualizzata nella colonna **Attività** nella pagina **Ricerca log di controllo**. I due valori potrebbero ad esempio essere MailboxLogin e Utente connesso a cassetta postale.

- Quando si scaricano tutti i risultati di una query di ricerca che contiene eventi di diversi servizi di Office 365, la colonna **AuditData** nel file CSV contiene proprietà diverse a seconda del servizio in cui è stata eseguita l'azione. Le voci dei log di controllo di Exchange e Azure AD, ad esempio, contengono una proprietà denominata **ResultStatus** che indica se l'azione è riuscita o meno. Questa proprietà non è inclusa per gli eventi di SharePoint. Analogamente, gli eventi di SharePoint hanno una proprietà che identifica l'URL del sito per le attività correlate a file e cartelle. Per ovviare a questo comportamento, è consigliabile usare ricerche diverse per esportare i risultati per le attività da un unico servizio.

  Per una descrizione delle numerose proprietà elencate nella colonna **AuditData** del file CSV quando si scaricano tutti i risultati, con l'indicazione del servizio a cui si riferiscono, vedere [Proprietà dettagliate nel log di controllo di Office 365](detailed-properties-in-the-office-365-audit-log.md).

## <a name="audited-activities"></a>Attività controllate

Le tabelle in questa sezione descrivono le attività che vengono controllate in Office 365. È possibile cercare questi eventi eseguendo una ricerca nel log di controllo nel Centro sicurezza e conformità.

Queste tabelle raggruppano le attività correlate o le attività di un determinato servizio di Office 365. Le tabelle includono il nome descrittivo visualizzato nell'elenco a discesa **Attività** e il nome dell'operazione corrispondente visualizzato nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca. Per le descrizioni delle informazioni dettagliate, vedere [Proprietà dettagliate nel log di controllo di Office 365](detailed-properties-in-the-office-365-audit-log.md).

Fare clic su uno dei collegamenti seguenti per passare a una tabella specifica.

||||
|:-----|:-----|:-----|
|[Attività su file e pagine](#file-and-page-activities)|[Attività su cartelle](#folder-activities)|[Attività dell'elenco di SharePoint](#sharepoint-list-activities)|
|[Attività di richiesta di accesso e condivisione](#sharing-and-access-request-activities)|[Attività di sincronizzazione](#synchronization-activities)|[Attività relative alle autorizzazioni del sito](#site-permissions-activities)|
|[Attività di amministrazione siti](#site-administration-activities)|[Attività su cassette postali di Exchange](#exchange-mailbox-activities)|[Attività con Sway](#sway-activities)|
|[Attività di amministrazione utenti](#user-administration-activities)|[Attività di amministrazione gruppi di Azure AD](#azure-ad-group-administration-activities)|[Attività di amministrazione applicazioni](#application-administration-activities)|
|[Attività di amministrazione ruoli](#role-administration-activities)|[Attività di amministrazione directory](#directory-administration-activities)|[Attività di eDiscovery](#ediscovery-activities)|
|[Attività di Advanced eDiscovery](#advanced-ediscovery-activities)|[Attività di Power BI](#power-bi-activities)|[Microsoft Workplace Analytics](#microsoft-workplace-analytics-activities)|
|[Attività di Microsoft Teams](#microsoft-teams-activities)|[Attività di Microsoft Teams per il settore sanitario](#microsoft-teams-healthcare-activities)|[Attività di Yammer](#yammer-activities)|
|[Attività di Microsoft Flow](#microsoft-flow-activities)|[Attività di Microsoft PowerApps](#microsoft-powerapps)|[Attività di Microsoft Stream](#microsoft-stream-activities)|
[Attività di amministrazione di Exchange](#exchange-admin-audit-log)|||
||||

### <a name="file-and-page-activities"></a>Attività su file e pagine

La tabella seguente descrive le attività su file e pagine in SharePoint Online e OneDrive for Business.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|File aperto|FileAccessed|Un utente o un account di sistema esegue l'accesso a un file.|
|(nessuno)|FileAccessedExtended|Elemento correlato all'attività "File aperto" (FileAccessed). Un evento FileAccessedExtended viene registrato quando la stessa persona accede in modo continuativo a un file per un periodo prolungato (fino a 3 ore). <br/><br/> Lo scopo della registrazione di eventi FileAccessedExtended è di ridurre il numero di eventi FileAccessed registrati quando si accede a un file in modo continuativo. Ciò consente di ridurre il numero di record FileAccessed per un'attività utente sostanzialmente identica e consente di concentrarsi sull'evento FileAccessed iniziale (e più importante).|
|Etichetta dei criteri di conformità modificata|ComplianceSettingChanged|È stata applicata o rimossa un'etichetta di conservazione da un documento. Questo evento viene generato quando un'etichetta di conservazione viene applicata manualmente o automaticamente a un messaggio.|
|Stato del record modificato in bloccato|LockRecord|Lo stato del record di un'etichetta di conservazione che classifica un documento come record è stato bloccato. Ciò significa che non è possibile modificare o eliminare il documento. Solo gli utenti a cui è assegnata almeno l'autorizzazione di collaboratore per un sito possono cambiare lo stato di un documento.|
|Stato del record modificato in sbloccato|UnlockRecord|Lo stato del record di un'etichetta di conservazione che classifica un documento come record è stato sbloccato. Ciò significa che è possibile modificare o eliminare il documento. Solo gli utenti a cui è assegnata almeno l'autorizzazione di collaboratore per un sito possono cambiare lo stato di un documento.|
|File archiviato|FileCheckedIn|Un utente archivia un documento estratto da una raccolta documenti.|
|File estratto|FileCheckedOut|Un utente estrae un documento da una raccolta documenti. Gli utenti possono estrarre e apportare modifiche ai documenti condivisi con loro.|
|File copiato|FileCopied|Un utente copia un documento da un sito. Il file copiato può essere salvato in un'altra cartella nel sito.|
|File eliminato|FileDeleted|Un utente elimina un documento da un sito.|
|File eliminato dal Cestino|FileDeletedFirstStageRecycleBin|L'utente elimina un file dal Cestino di un sito.|
|File eliminato dal Cestino di secondo livello|FileDeletedSecondStageRecycleBin|L'utente elimina un file dal Cestino di secondo livello di un sito.|
|Etichetta dei criteri di conformità dei record eliminata|ComplianceRecordDelete|Un documento classificato come record è stato eliminato. Un documento viene considerato record se al documento è applicata un'etichetta di conservazione che classifica il contenuto come record.|
|È stata rilevata una mancata corrispondenza della riservatezza del documento|DocumentSensitivityMismatchDetected|Un utente carica un documento classificato con un'etichetta di riservatezza che presenta una priorità più alta dell'etichetta di riservatezza applicata al sito in cui viene caricato il documento. <br/><br/> Questo evento non viene attivato se l'etichetta di riservatezza applicata a un sito presenta una priorità più alta di quella applicata a un documento caricato nel sito. Per altre informazioni sulla priorità dell'etichetta di riservatezza, vedere la sezione "Priorità dell'etichetta" in [Panoramica delle etichette di riservatezza](sensitivity-labels.md#label-priority-order-matters).|
|Malware rilevato nel file|FileMalwareDetected|Il motore antivirus di SharePoint rileva malware in un file.|
|Estrazione file rimossa|FileCheckOutDiscarded|Un utente elimina (o annulla) l'estrazione di un file. Ciò significa che le modifiche apportate al file dopo l'estrazione vengono eliminate e non salvate nella versione del documento nella raccolta documenti.|
|File scaricato|FileDownloaded|Un utente scarica un documento da un sito.|
|File modificato|FileModified|Un utente o un account di sistema modifica il contenuto o le proprietà di un documento in un sito.|
|(nessuno)|FileModifiedExtended|Elemento correlato all'attività "File modificato" (FileModified). Un evento FileModifiedExtended viene registrato quando la stessa persona modifica in modo continuativo un file per un periodo prolungato (fino a 3 ore). <br/><br/> Lo scopo della registrazione di eventi FileModifiedExtended è di ridurre il numero di eventi FileModified registrati quando si modifica un file in modo continuativo. Ciò consente di ridurre il numero di record FileModified per un'attività utente sostanzialmente identica e consente di concentrarsi sull'evento FileModified iniziale (e più importante).|
|File spostato|FileMoved|Un utente sposta un documento dalla posizione corrente in un sito a una nuova posizione.|
|(nessuno)|FilePreviewed|L'utente visualizza in anteprima i file in un sito di SharePoint Online o di OneDrive for Business. Questi eventi si verificano in genere in volumi elevati in base a una singola attività, ad esempio la visualizzazione di una raccolta immagini.|
|Tutte le versioni secondarie di un file vengono spostate nel Cestino|FileVersionsAllMinorsRecycled|L'utente elimina tutte le versioni secondarie dalla cronologia delle versioni di un file. Le versioni eliminate vengono spostate nel Cestino del sito.|
|Tutte le versioni di un file vengono spostate nel Cestino|FileVersionsAllRecycled|L'utente elimina tutte le versioni dalla cronologia delle versioni di un file. Le versioni eliminate vengono spostate nel Cestino del sito.|
|La versione di un file viene spostata nel Cestino|FileVersionRecycled|L'utente una versione dalla cronologia delle versioni di un file. La versione eliminata viene spostata nel Cestino del sito.|
|File rinominato|FileRenamed|Un utente rinomina un documento in un sito.|
|File ripristinato|FileRestored|Un utente ripristina un documento dal Cestino di un sito.|
|File caricato|FileUploaded|Un utente carica un documento in una cartella in un sito.|
|Pagina visualizzata|PageViewed|Utente visualizza una pagina in un sito, ma non usa un Web browser per visualizzare i file presenti in una raccolta documenti.|
|(nessuno)|PageViewedExtended|Elemento correlato all'attività "Pagina visualizzata" (PageViewed). Un evento PageViewedExtended viene registrato quando la stessa persona visualizza in modo continuativo una pagina Web per un periodo prolungato (fino a 3 ore). <br/><br/> Lo scopo della registrazione di eventi PageViewedExtended è di ridurre il numero di eventi PageViewed registrati quando si visualizza una pagina Web in modo continuativo. Ciò consente di ridurre il numero di record PageViewed per un'attività utente sostanzialmente identica e consente di concentrarsi sull'evento PageViewed iniziale (e più importante).|
|Visualizzazione segnalata dal client|ClientViewSignaled|Il client di un utente (ad esempio un sito Web o un'app per dispositivi mobili), ha segnalato che la pagina indicata è stata visualizzata dall'utente. Questa attività viene spesso registrata dopo un evento PagePrefetched per una pagina. <br/><br/>**NOTA**: poiché gli eventi ClientViewSignaled sono segnalati dal client, anziché dal server, è possibile che l'evento non sia registrato dal server e che quindi non compaia nel log di controllo. È anche possibile che le informazioni nel record di controllo non siano attendibili. Tuttavia, dato che l'identità dell'utente viene convalidata mediante il token usato per creare il segnale, l'identità dell'utente riportata nel record di controllo corrispondente è accurata. |
|(nessuno)|PagePrefetched|Il client di un utente (ad esempio un sito Web o un'app per dispositivi mobili) ha richiesto la pagina indicata per migliorare le prestazioni in caso di esplorazione da parte dell'utente. Questo evento viene registrato per indicare che il contenuto della pagina è stato servito al client dell'utente. Questo evento non indica definitivamente che l'utente è passato alla pagina. <br/><br/> Quando il contenuto della pagina viene visualizzato dal client (come richiesto dall'utente), è necessario generare un evento ClientViewSignaled. Non tutti i client supportano l'indicazione di caricamento in background, pertanto alcune attività predefinite potrebbero essere registrate come eventi PageViewed.|
||||

### <a name="folder-activities"></a>Attività su cartelle

La tabella seguente descrive le attività di cartella in SharePoint Online e OneDrive for Business.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Cartella copiata|FolderCopied|L'utente copia una cartella da un sito in un'altra posizione in SharePoint o OneDrive for Business.|
|Cartella creata|FolderCreated|L'utente crea una cartella in un sito.|
|Cartella eliminata|FolderDeleted|L'utente elimina una cartella da un sito.|
|Cartella eliminata dal Cestino|FolderDeletedFirstStageRecycleBin|L'utente elimina una cartella dal Cestino di un sito.|
|Cartella eliminata dal Cestino di secondo livello|FolderDeletedSecondStageRecycleBin|L'utente elimina una cartella dal Cestino di secondo livello di un sito.|
|Cartella modificata|FolderModified|L'utente modifica una cartella in un sito. Vengono modificati anche i metadati della cartella, ad esempio tag e proprietà.|
|Cartella spostata|FolderMoved|L'utente sposta una cartella in una posizione diversa in un sito.|
|Cartella rinominata|FolderRenamed|L'utente rinomina una cartella in un sito.|
|Cartella ripristinata|FolderRestored|L'utente ripristina una cartella eliminata dal Cestino di un sito.|
||||

### <a name="sharepoint-list-activities"></a>Attività dell'elenco di SharePoint

La tabella seguente descrive le attività correlate al momento in cui gli utenti interagiscono con gli elenchi e gli elementi elenco in SharePoint Online.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Elenco creato|ListCreated|Un utente ha creato un elenco SharePoint.|
|Colonna elenco creata|ListColumnCreated|Un utente ha creato una colonna elenco di SharePoint. Una colonna elenco è una colonna associata a uno o più elenchi SharePoint.|
|Tipo di contenuto elenco creato|ListContentTypeCreated|Un utente ha creato un tipo di contenuto elenco. Un tipo di contenuto elenco è un tipo di contenuto associato a uno o più elenchi SharePoint.|
|Elemento elenco creato|ListItemCreated|Un utente ha creato un elemento in un elenco di SharePoint esistente.|
|Colonna sito creata|SiteColumnCreated|Un utente ha creato una colonna sito di SharePoint. Una colonna sito è una colonna non associata a un elenco. Una colonna sito è anche una struttura di metadati che può essere usata da qualsiasi elenco in un determinato Web.|
|Tipo di contenuto del sito creato|Sito ContentType creato|Un utente ha creato un tipo di contenuto del sito. Un tipo di contenuto del sito è un tipo di contenuto associato al sito padre.|
|Elenco eliminato|ListDeleted|Un utente ha eliminato un elenco SharePoint.|
|Colonna elenco eliminata|Colonna elenco eliminata|Un utente ha eliminato una colonna elenco SharePoint.|
|Tipo di contenuto elenco eliminato|ListContentTypeDeleted|Un utente ha eliminato un tipo di contenuto elenco.|
|Elemento elenco eliminato|Elemento elenco eliminato|Un utente ha eliminato un elemento elenco SharePoint.|
|Colonna sito eliminata|SiteColumnDeleted|Un utente ha eliminato una colonna sito SharePoint.|
|Tipo di contenuto del sito eliminato|SiteContentTypeDeleted|Un utente ha eliminato un tipo di contenuto del sito.|
|Elemento elenco riciclato|ListItemRecycled|Un utente ha spostato una elemento elenco di SharePoint nel Cestino.|
|Elenco ripristinato|ListRestored|Un utente ha ripristinato un elenco di SharePoint dal Cestino.|
|Elemento elenco ripristinato|ListItemRestored|Un utente ha ripristinato un elemento elenco di SharePoint dal Cestino.|
|Elenco aggiornato|ListUpdated|Un utente ha aggiornato un elenco di SharePoint modificando una o più proprietà.|
|Colonna elenco aggiornata|ListColumnUpdated|Un utente ha aggiornato una colonna elenco di SharePoint modificando una o più proprietà.|
|Tipo di contenuto elenco aggiornato|ListContentTypeUpdated|Un utente ha aggiornato un tipo di contenuto elenco modificando una o più proprietà.|
|Elemento elenco aggiornato|ListItemUpdated|Un utente ha aggiornato un elemento elenco di SharePoint modificando una o più proprietà.|
|Colonna sito aggiornata|SiteColumnUpdated|Un utente ha aggiornato una colonna sito di SharePoint modificando una o più proprietà.|
|Tipo di contenuto del sito aggiornato|SiteContentTypeUpdated|Un utente ha aggiornato un tipo di contenuto del sito modificando una o più proprietà.|
||||

### <a name="sharing-and-access-request-activities"></a>Attività di richiesta di accesso e condivisione

La tabella seguente descrive le attività di richiesta di condivisione e accesso dell'utente in SharePoint Online e OneDrive for Business. Per gli eventi di condivisione, la colonna **Dettagli** in **Risultati** identifica il nome dell'utente o del gruppo con cui l'elemento è stato condiviso e indica se l'utente o il gruppo è un membro o un guest nell'organizzazione. Per altre informazioni, vedere [Usare il controllo della condivisione nel log di controllo di Office 365](use-sharing-auditing.md).

> [!NOTE]
> Gli utenti possono essere *membri* o *guest* in base alla proprietà UserType dell'oggetto utente. Un membro è in genere un dipendente, mentre un guest è in genere un collaboratore esterno all'organizzazione. Quando un utente accetta un invito alla condivisione (e non fa già parte dell'organizzazione), viene creato un account guest per tale utente nella directory dell'organizzazione. Dopo che l'utente guest ha ottenuto un account nella directory, le risorse possono essere condivise direttamente con lui, senza che sia necessario un invito.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|È stato aggiunto un livello di autorizzazione alla raccolta siti|PermissionLevelAdded|Un livello di autorizzazione è stato aggiunto a una raccolta siti.|
|Richiesta di accesso approvata|AccessRequestAccepted|Una richiesta di accesso a un sito, una cartella o un documento è stata accettata e all'utente richiedente è stato concesso l'accesso.|
|Invito alla condivisione accettato|SharingInvitationAccepted|Un utente (membro o guest) ha accettato un invito alla condivisione e ha ottenuto l'accesso a una risorsa. Questo evento include informazioni sull'utente che è stato invitato e sull'indirizzo di posta elettronica usato per accettare l'invito (i due elementi potrebbero essere diversi). Questa attività è spesso accompagnata da un secondo evento che descrive come è stato concesso all'utente l'accesso alla risorsa, ad esempio aggiungendo l'utente a un gruppo che ha accesso alla risorsa.|
|Invito alla condivisione bloccato|SharingInvitationBlocked|Un invito alla condivisione inviato da un utente dell'organizzazione viene bloccato da criteri di condivisione esterna che consentono o impediscono la condivisione esterna in base al dominio dell'utente di destinazione. In questo caso, l'invito alla condivisione è stato bloccato perché: <br/> Il dominio dell'utente di destinazione non è incluso nell'elenco dei domini consentiti. <br/> Oppure <br/> Il dominio dell'utente di destinazione è incluso nell'elenco dei domini bloccati. <br/> Per altre informazioni su come consentire o bloccare la condivisione esterna in base ai domini, vedere [Condivisione di domini con restrizioni in SharePoint Online e OneDrive for Business](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9).|
|Richiesta di accesso creata|AccessRequestCreated|Un utente richiede l'accesso a un sito, una cartella o un documento per il quale non ha le autorizzazioni.|
|Creato un collegamento condivisibile nell'organizzazione |CompanyLinkCreated|Un utente ha creato un collegamento a livello aziendale a una risorsa. i collegamenti a livello aziendale possono essere usati solo dai membri dell'organizzazione. Non possono essere usati dai guest.|
|Creato un collegamento anonimo|AnonymousLinkCreated|Un utente ha creato un collegamento anonimo a una risorsa. Chiunque usi questo collegamento può accedere alla risorsa senza necessità di autenticazione.|
|Collegamento sicuro creato|SecureLinkCreated|È stato creato un collegamento di condivisione sicuro per questo elemento.|
|Invito alla condivisione creato|SharingInvitationCreated|Un utente ha condiviso una risorsa in SharePoint Online o OneDrive for Business con un utente che non fa parte della directory dell'organizzazione.|
|Collegamento sicuro eliminato|SecureLinkDeleted|È stato eliminato un collegamento di condivisione sicuro.|
|Richiesta di accesso rifiutata |AccessRequestDenied|Una richiesta di accesso a un sito, una cartella o un documento è stata negata.|
|Rimosso un collegamento condivisibile nell'organizzazione|CompanyLinkRemoved|Un utente ha rimosso un collegamento a livello aziendale a una risorsa. Il collegamento non può più essere usato per accedere alla risorsa.|
|Rimosso un collegamento anonimo|AnonymousLinkRemoved|Un utente ha rimosso un collegamento anonimo a una risorsa. Il collegamento non può più essere usato per accedere alla risorsa.|
|File, cartella o sito condiviso|SharingSet|Un utente (membro o guest) ha condiviso un file, una cartella o un sito in SharePoint o OneDrive for Business con un utente che fa parte della directory dell'organizzazione. Il valore nella colonna **Dettagli** per questa attività identifica il nome dell'utente con cui la risorsa è stata condivisa e indica se l'utente è un membro o un guest. <br/><br/> Questa attività è spesso accompagnata da un secondo evento che descrive come è stato concesso all'utente l'accesso alla risorsa, ad esempio, aggiungendo l'utente a un gruppo che ha accesso alla risorsa.|
|Richiesta di accesso aggiornata|AccessRequestUpdated|Una richiesta di accesso a un elemento è stata aggiornata.|
|Aggiornato un collegamento anonimo|AnonymousLinkUpdated|Un utente ha aggiornato un collegamento anonimo a una risorsa. Il campo aggiornato è incluso nella proprietà EventData quando si esportano i risultati della ricerca.|
|Invito alla condivisione aggiornato|SharingInvitationUpdated|È stato aggiornato un invito alla condivisione esterna.|
|Usato un collegamento anonimo|AnonymousLinkUsed|Un utente anonimo ha eseguito l'accesso a una risorsa usando un collegamento anonimo. L'identità dell'utente potrebbe essere sconosciuta, ma è possibile ottenere altri dettagli, ad esempio il suo indirizzo IP.|
|File, cartella o sito non più condiviso|SharingRevoked|Un utente (membro o guest) ha annullato la condivisione di un file, una cartella o un sito che in precedenza era stato condiviso con un altro utente.|
|Usato un collegamento condivisibile nell'organizzazione|CompanyLinkUsed|Un utente ha eseguito l'accesso a una risorsa usando un collegamento a livello aziendale.|
|Collegamento sicuro utilizzato|SecureLinkUsed|Un utente ha usato un collegamento sicuro.|
|Utente aggiunto al collegamento sicuro|AddedToSecureLink|Un utente è stato aggiunto all'elenco di entità che possono usare un collegamento di condivisione sicuro.|
|Utente rimosso dal collegamento sicuro|RemovedFromSecureLink|Un utente è stato rimosso dall'elenco di entità che possono usare un collegamento di condivisione sicuro.|
|Invito alla condivisione ritirato|SharingInvitationRevoked|Un utente ha ritirato un invito alla condivisione per una risorsa. |
||||

### <a name="synchronization-activities"></a>Attività di sincronizzazione

La tabella seguente descrive le attività di sincronizzazione file in SharePoint Online e OneDrive for Business.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Computer autorizzato a sincronizzare i file|ManagedSyncClientAllowed|Un utente ha stabilito una relazione di sincronizzazione con un sito. La relazione di sincronizzazione viene eseguita correttamente perché il computer dell'utente fa parte di un dominio che è stato aggiunto all'elenco dei domini (denominato *elenco destinatari attendibili*) che possono accedere alle raccolte documenti all'interno dell'organizzazione. <br/><br/> Per altre informazioni su questa funzionalità, vedere [Usare i cmdlet di Windows PowerShell per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco Destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).|
|Computer non autorizzato a sincronizzare i file|UnmanagedSyncClientBlocked|L'utente prova a stabilire una relazione di sincronizzazione con un sito da un computer che non è membro del dominio dell'organizzazione o è membro di un dominio che non è stato aggiunto all'elenco dei domini (denominato *elenco Destinatari attendibili*) che possono accedere alle raccolte documenti dell'organizzazione. La relazione di sincronizzazione non è consentita e il computer dell'utente non può sincronizzare, scaricare o caricare file in una raccolta documenti. <br/><br/> Per informazioni su questa funzionalità, vedere [Usare i cmdlet di Windows PowerShell per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco Destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).|
|File scaricati nel computer|FileSyncDownloadedFull|Un utente stabilisce una relazione di sincronizzazione e scarica i file per la prima volta nel suo computer da una raccolta documenti.|
|Modifiche ai file scaricate nel computer|FileSyncDownloadedPartial|Un utente scarica le modifiche ai file da una raccolta documenti. Questa attività indica che le modifiche apportate ai file nella raccolta documenti sono state scaricate nel computer dell'utente. Sono state scaricate solo le modifiche perché la raccolta documenti è stata scaricata dall'utente in precedenza (come indicato dall'attività **File scaricati nel computer**).|
|File caricati nella raccolta documenti|FileSyncUploadedFull|Un utente stabilisce una relazione di sincronizzazione e carica i file per la prima volta dal suo computer in una raccolta documenti.|
|Modifiche ai file caricate nella raccolta documenti|FileSyncUploadedPartial|Un utente carica le modifiche ai file in una raccolta documenti. Questo evento indica che le modifiche apportate alla versione locale di un file di una raccolta documenti sono state caricate nella raccolta documenti. Vengono caricate solo le modifiche perché i file sono stati caricati dall'utente in precedenza (come indicato dall'attività **File caricati nella raccolta documenti**).|
||||

### <a name="site-permissions-activities"></a>Attività relative alle autorizzazioni del sito

La tabella seguente elenca gli eventi correlati all'assegnazione di autorizzazioni in SharePoint e all'uso dei gruppi per concedere (e revocare) l'accesso ai siti.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Amministratore raccolta siti aggiunto|SiteCollectionAdminAdded|Un proprietario o un amministratore della raccolta siti aggiunge una persona come amministratore della raccolta siti per un sito. Gli amministratori della raccolta siti hanno autorizzazioni di controllo completo per la raccolta siti e tutti i siti secondari. Questa attività viene registrata anche quando un amministratore concede a se stesso l'accesso all'account OneDrive di un utente (modificando il profilo utente nell'interfaccia di amministrazione di SharePoint o [usando l'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data)).|
|Utente o gruppo aggiunto al gruppo di SharePoint|AddedToGroup|Un utente ha aggiunto un membro o un guest a un gruppo di SharePoint. Questa operazione può essere stata intenzionale oppure è il risultato di un'altra attività, ad esempio un evento di condivisione.|
|L'ereditarietà dei livelli di autorizzazione è stata interrotta|PermissionLevelsInheritanceBroken|Un elemento è stato modificato in modo che non erediti più i livelli di autorizzazione dal relativo padre.|
|L'ereditarietà di condivisione è stata interrotta|SharingInheritanceBroken|Un elemento è stato modificato in modo che non erediti più le autorizzazioni di condivisione dal relativo padre.|
|Gruppo creato|GroupAdded|Un proprietario o un amministratore del sito crea un gruppo per un sito oppure esegue un'attività che comporta la creazione di un gruppo. Ad esempio, la prima volta che un utente crea un collegamento per condividere un file, un gruppo di sistema viene aggiunto al sito OneDrive for Business dell'utente. Questo evento può anche risultare dalla creazione, da parte di un utente, di un collegamento con autorizzazioni di modifica per un file condiviso.|
|Gruppo eliminato|GroupRemoved|Un utente elimina un gruppo da un sito.|
|Impostazioni richieste di accesso modificate|WebRequestAccessModified|Le impostazioni richieste di accesso sono state modificate in un sito.|
|Impostazione "I membri possono condividere" modificata|WebMembersCanShareModified|L'impostazione **I membri possono condividere** è stata modificata in un sito.|
|È stato modificato un livello di autorizzazione nella raccolta siti|PermissionLevelModified|Un livello di autorizzazione è stato modificato in una raccolta siti.|
|Autorizzazioni sito modificate|SitePermissionsModified|Un proprietario o un amministratore del sito (o un account di sistema) modifica il livello di autorizzazioni assegnato a un gruppo in un sito. Questa attività viene registrata anche se vengono rimosse tutte le autorizzazioni da un gruppo. <br/><br/> **NOTA**: questa operazione è deprecata in SharePoint Online. Per trovare gli eventi correlati, è possibile cercare altre attività relative alle autorizzazioni, ad esempio **Amministratore raccolta siti aggiunto**, **Utente o gruppo aggiunto a gruppo di SharePoint**, **Utente autorizzato a creare gruppi**, **Gruppo creato** e **Gruppo eliminato**.|
|È stato rimosso un livello di autorizzazione dalla raccolta siti|PermissionLevelRemoved|Un livello di autorizzazione è stato rimosso da una raccolta siti.|
|Amministratore raccolta siti rimosso|SiteCollectionAdminRemoved|Un proprietario o un amministratore della raccolta siti rimuove una persona come amministratore della raccolta siti per un sito. Anche questa attività viene registrata quando un amministratore rimuove se stesso dall'elenco degli amministratori per l'account OneDrive di un utente (modificando il profilo utente nell'interfaccia di amministrazione di SharePoint).  Per riportare questa attività nei risultati della ricerca nel log di controllo, è necessario cercare tutte le attività.|
|Utente o gruppo rimosso dal gruppo di SharePoint|RemovedFromGroup|Un utente ha rimosso un membro o un guest da un gruppo di SharePoint. Questa operazione può essere stata intenzionale oppure è il risultato di un'altra attività, ad esempio un evento di annullamento della condivisione.|
|Autorizzazioni di amministrazione sito richieste|SiteAdminChangeRequest|Un utente richiede di essere aggiunto come amministratore della raccolta siti per una raccolta. Gli amministratori della raccolta siti hanno autorizzazioni di controllo completo per la raccolta siti e tutti i siti secondari.|
|L'ereditarietà di condivisione è stata ripristinata|SharingInheritanceReset|È stata apportata una modifica che consente a un elemento di ereditare le autorizzazioni di condivisione dal relativo padre.|
|Gruppo aggiornato|GroupUpdated|Un proprietario o un amministratore del sito modifica le impostazioni di un gruppo per un sito. Questo può includere la modifica del nome del gruppo, degli utenti autorizzati a visualizzare o modificare l'appartenenza al gruppo e della modalità di gestione delle richieste di appartenenza.|
||||

### <a name="site-administration-activities"></a>Attività di amministrazione siti

Nella tabella seguente sono elencati gli eventi derivanti da attività di amministrazione in SharePoint Online.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta la posizione dei dati consentita|AllowedDataLocationAdded|Un amministratore globale o di SharePoint ha aggiunto una posizione di dati consentita in un ambiente multi-geografico.|
|Agente utente esente aggiunto|ExemptUserAgentSet|L'amministratore di SharePoint o l'amministratore globale aggiunge un agente utente all'elenco di agenti utente esenti nell'interfaccia di amministrazione di SharePoint.|
|Amministratore dell'area geografica aggiunto|GeoAdminAdded|Un amministratore globale o di SharePoint ha aggiunto un utente come amministratore geografico di una posizione.|
|Utente autorizzato a creare gruppi|AllowGroupCreationSet|Un proprietario o un amministratore del sito aggiunge un livello di autorizzazione a un sito che consente a un utente a cui viene assegnata tale autorizzazione di creare un gruppo per tale sito.|
|È stato annullato lo spostamento geografico di un sito|SiteGeoMoveCancelled|Un amministratore globale o di SharePoint annulla correttamente uno spostamento geografico di un sito SharePoint o OneDrive. La funzionalità Multi-Geo consente a un'organizzazione di Office 365 di utilizzare più aree geografiche di centri dati Office 365, note anche come geo. Per altre informazioni, vedere [Multi-Geo Capabilities in OneDrive and SharePoint Online in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).|
|Criterio di condivisione cambiato|SharingPolicyChanged|Un amministratore globale o di SharePoint ha modificato i criteri di condivisione di SharePoint usando il portale di amministrazione di Office 365, il portale di amministrazione di SharePoint o SharePoint Online Management Shell. Qualsiasi modifica alle impostazioni dei criteri di condivisione dell'organizzazione verrà registrata. Il criterio modificato viene identificato nel campo **ModifiedProperties** nelle proprietà dettagliate del record dell'evento.|
|I criteri di accesso per i dispositivi sono stati modificati|DeviceAccessPolicyChanged|Un amministratore di SharePoint o globale ha cambiato i criteri dei dispositivi non gestiti per l'organizzazione. Questo criterio controlla l'accesso a SharePoint, OneDrive e Office 365 da dispositivi che non fanno parte dell'organizzazione. La configurazione di questo criterio richiede un abbonamento Enterprise Mobility + Security. Per altre informazioni, vedere [Controllare l'accesso da dispositivi non gestiti](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622).|
|Agenti utente esenti cambiati|CustomizeExemptUsers|L'amministratore globale o SharePoint ha personalizzato l'elenco di agenti utente esenti nell'interfaccia di amministrazione di SharePoint. È possibile specificare quali agenti utente esentare dalla ricezione di un'intera pagina Web da indicizzare. Ciò significa che quando un agente utente specificato come esente rileva un modulo di InfoPath, il modulo verrà restituito come file XML, invece che come pagina Web intera. In questo modo l'indicizzazione dei moduli di InfoPath risulta più veloce.|
|Sono stati modificati i criteri di accesso alla rete|NetworkAccessPolicyChanged|Un amministratore di SharePoint o globale ha cambiato i criteri di accesso basati sulla posizione, denominati anche limite di rete attendibile, nell'interfaccia di amministrazione di SharePoint oppure usando PowerShell di SharePoint Online. Questi criteri controllano chi può accedere alle risorse di SharePoint e OneDrive nell'organizzazione in base a intervalli di indirizzi IP specificati dall'utente. Per altre informazioni, vedere [Controllare l'accesso ai dati di SharePoint Online e OneDrive in base a determinati percorsi di rete](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f).|
|Spostamento geografico di un sito completato|SiteGeoMoveCompleted|Uno spostamento geografico di un sito, pianificato da un amministratore globale dell'organizzazione, è stato completato correttamente. La funzionalità Multi-Geo consente a un'organizzazione di Office 365 di utilizzare più aree geografiche di centri dati Office 365, note anche come geo. Per altre informazioni, vedere [Multi-Geo Capabilities in OneDrive and SharePoint Online in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).|
|Connessione Inviato a creata|SendToConnectionAdded|L'amministratore di SharePoint o globale crea una nuova connessione Invia a nella pagina Gestione record nell'interfaccia di amministrazione di SharePoint. Una connessione di invio specifica le impostazioni per un archivio documenti o un centro record. Quando si crea una connessione di invio, un Content Organizer può inviare documenti alla posizione specificata.|
|Raccolta siti creata|SiteCollectionCreated|Un amministratore SharePoint o globale crea una raccolta siti nell'organizzazione di SharePoint Online o un utente esegue il provisioning del sito di OneDrive for Business.|
|Sito hub orfano eliminato|HubSiteOrphanHubDeleted|Un amministratore SharePoint o globale ha eliminato un sito hub orfano, ossia un sito hub a cui non sono associati siti. È probabile che l'hub orfano sia causato dall'eliminazione del sito hub originale.|
|Connessione Inviato a eliminata|SendToConnectionRemoved|L'amministratore SharePoint o globale elimina una nuova connessione Invia a nella pagina Gestione record nell'interfaccia di amministrazione di SharePoint.|
|Sito eliminato|SiteDeleted|L'amministratore del sito elimina un sito.|
|Anteprima documento abilitata|PreviewModeEnabledSet|Un amministratore del sito abilita l'anteprima dei documenti per un sito.|
|Flusso di lavoro legacy abilitato|LegacyWorkflowEnabledSet|Un proprietario o un amministratore del sito aggiunge il tipo di contenuto Attività flusso di lavoro di SharePoint 2013 al sito. Gli amministratori globali possono anche abilitare i flussi di lavoro per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.|
|Office su richiesta abilitato|OfficeOnDemandSet|Un amministratore del sito abilita Office su richiesta, che consente agli utenti di accedere alla versione più recente delle applicazioni desktop di Office. Office su richiesta viene abilitato nell'interfaccia di amministrazione di SharePoint e richiede un abbonamento a Office 365, che include le applicazioni Office complete installate.|
|Origine dei risultati abilitata per ricerche in Persone|PeopleResultsScopeSet|Un amministratore del sito crea l'origine dei risultati per le ricerche in Persone per un sito.|
|Feed RSS abilitati|NewsFeedEnabledSet|Un proprietario o un amministratore del sito abilita i feed RSS per un sito. Gli amministratori globali possono abilitare i feed RSS per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.|
|Sito unito al sito hub|HubSiteJoined|Il proprietario di un sito associa il sito a un sito hub.|
|Sito hub registrato|HubSiteRegistered|Un amministratore SharePoint o globale crea un sito hub. Il risultato è che il sito viene registrato come sito hub.|
|Rimossa la posizione dei dati consentita|AllowedDataLocationDeleted|Un amministratore SharePoint o globale ha rimosso una posizione di dati consentita in un ambiente multi-geografico.|
|Amministratore dell'area geografica rimosso|GeoAdminDeleted|Un amministratore SharePoint o globale ha aggiunto un utente come amministratore geografico di una posizione.|
|Sito rinominato|SiteRenamed|Un proprietario o un amministratore del sito rinomina un sito.|
|Spostamento geografico di un sito pianificato|SiteGeoMoveScheduled|Un amministratore SharePoint o globale programma correttamente uno spostamento geografico di un sito SharePoint o OneDrive. La funzionalità Multi-Geo consente a un'organizzazione di Office 365 di utilizzare più aree geografiche di centri dati Office 365, note anche come geo. Per altre informazioni, vedere [Multi-Geo Capabilities in OneDrive and SharePoint Online in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).|
|Sito host impostato|HostSiteSet|Un amministratore di SharePoint o globale cambia il sito designato per ospitare siti di OneDrive for Business o personali.|
|Impostare una quota di archiviazione per una posizione geografica|GeoQuotaAllocated|Un amministratore SharePoint o globale ha configurato una quota di archiviazione per una posizione geografica in un ambiente multi-geografico.|
|Sito separato dal sito hub|HubSiteUnjoined|Il proprietario di un sito annulla l'associazione del sito a un sito hub.|
|Registrazione sito hub annullata|HubSiteUnregistered|Un amministratore SharePoint o globale annulla la registrazione di un sito come sito hub. Quando si annulla la registrazione di un sito hub, quest'ultimo non funziona più come sito hub.|
||||

### <a name="exchange-mailbox-activities"></a>Attività su cassette postali di Exchange

La tabella seguente elenca le attività che possono essere registrate tramite la registrazione di controllo delle cassette postali. Le attività sulle cassette postali eseguite dal proprietario della cassetta postale, da un utente delegato o da un amministratore vengono registrate automaticamente nel log di controllo di Office 365 per un massimo di 90 giorni. L'amministratore può disattivare la registrazione di controllo delle cassette postali per tutti gli utenti dell'organizzazione. In questo caso non vengono registrate azioni di cassette postali per alcun utente. Per altre informazioni, vedere [Gestire il controllo delle cassette postali](enable-mailbox-auditing.md).

 È anche possibile cercare le attività delle cassette postali utilizzando il cmdlet [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) in PowerShell per Exchange Online.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunte autorizzazioni delegate per le cassette postali|AddMailboxPermissions|Un amministratore ha assegnato l'autorizzazione FullAccess per la cassetta postale a un utente (noto come delegato) alla cassetta postale di un'altra persona. L'autorizzazione FullAccess consente al delegato di aprire la cassetta postale di un'altra persona e di leggere e gestire il contenuto della cassetta postale.|
|Aggiunto o rimosso un utente con accesso delegato alla cartella del calendario|UpdateCalendarDelegation|Un utente è stato aggiunto o rimosso come delegato al calendario della cassetta postale di un altro utente. La delega del calendario assegna a un altro utente nella stessa organizzazione le autorizzazioni per la gestione del calendario del proprietario della cassetta postale.|
|Aggiunte autorizzazioni alla cartella|AddFolderPermissions|È stata aggiunta un'autorizzazione per una cartella. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|
|Messaggi copiati in un'altra cartella|Copy|Un messaggio è stato copiato in un'altra cartella.|
|Elemento della cassetta postale creato|Creare|Viene creato un elemento nella cartella Calendario, Contatti, Note o Attività nella cassetta postale; ad esempio, viene creata una nuova convocazione di riunione. La creazione, l'invio o la ricezione di un messaggio non viene controllata, così come la creazione di una cartella della cassetta postale.|
|Creata una nuova regola della posta in arrivo in Outlook Web App|New-InboxRule|Il proprietario di una cassetta postale o un altro utente con accesso alla cassetta postale ha creato una regola di posta in arrivo in Outlook Web App.|
|Messaggi eliminati dalla cartella Posta eliminata|SoftDelete|Un messaggio è stato eliminato definitivamente oppure è stato eliminato dalla cartella Posta eliminata. Questi elementi vengono spostati nella cartella Elementi ripristinabili. I messaggi vengono spostati nella cartella Elementi ripristinabili anche quando un utente li seleziona e preme **MAIUSC+CANC**.|
|Messaggio con etichetta come record|ApplyRecordLabel|Un messaggio è stato classificato come record. Questa situazione si verifica quando un'etichetta di conservazione che classifica il contenuto come record viene applicata manualmente o automaticamente a un messaggio.|
|Messaggi spostati in un'altra cartella|Move|Un messaggio è stato spostato in un'altra cartella.|
|Messaggi spostati nella cartella Posta eliminata|MoveToDeletedItems|Un messaggio è stato eliminato e spostato nella cartella Posta eliminata.|
|Autorizzazione cartella modificata|UpdateFolderPermissions|Un'autorizzazione per una cartella è stata cambiata. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|
|Regola della posta in arrivo modificata da Outlook Web App|Set-InboxRule|Il proprietario di una cassetta postale o un altro utente con accesso alla cassetta postale ha modificato una regola di posta in arrivo in Outlook Web App.|
|Messaggi ripuliti dalla cassetta postale|HardDelete|Un messaggio è stato eliminato dalla cartella Elementi ripristinabili (eliminato in modo definitivo dalla cassetta postale).|
|Rimosse autorizzazioni delegate per le cassette postali|Remove-MailboxPermission|Un amministratore ha rimosso l'autorizzazione FullAccess (che era assegnata a un delegato) dalla cassetta postale di una persona. Dopo aver rimosso l'autorizzazione FullAccess, il delegato non riesce ad aprire la cassetta postale dell'altra persona o ad accedere a qualsiasi suo contenuto.|
|Autorizzazioni rimosse dalla cartella|RemoveFolderPermissions|Un'autorizzazione per una cartella è stata rimossa. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|
|Messaggio inviato con autorizzazioni Invia come|SendAs|Un messaggio è stato inviato con l'autorizzazione SendAs, Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.|
|Messaggio inviato con autorizzazioni Invia per conto di|SendOnBehalf|Un messaggio è stato inviato con l'autorizzazione SendOnBehalf, Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario per conto di chi è stato inviato e chi effettivamente lo ha inviato.|
|Regole della posta in arrivo aggiornate dal client di Outlook|UpdateInboxRules|Il proprietario di una cassetta postale o un altro utente con accesso alla cassetta postale ha modificato una regola di posta in arrivo nel client di Outlook.|
|Messaggio aggiornato|Update|Un messaggio o le relative proprietà sono state modificate.|
|Utente connesso a cassetta postale|MailboxLogin|Accesso effettuato dall'utente alla propria cassetta postale.|
||||

### <a name="sway-activities"></a>Attività con Sway

La tabella seguente elenca le attività utente e amministratore in Sway. Sway è un'app di Office 365 che consente di raccogliere, formattare e condividere idee, storie e presentazioni in un'area di disegno interattiva basata sul Web. Per altre informazioni, vedere [Domande frequenti su Sway - Guida per l'amministratore](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075).

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Cambiato il livello di condivisione di Sway|SwayChangeShareLevel|Un utente modifica il livello di condivisione di uno Sway. Questo evento acquisisce la modifica dell'ambito della condivisione associata a uno Sway, ad esempio da pubblico a interno all'organizzazione.|
|Sway creato|SwayCreate|Un utente crea uno Sway.|
|Sway eliminato|SwayDelete|L'utente elimina uno Sway.|
|Duplicazione Sway disabilitata|SwayDisableDuplication|Un utente disabilita la duplicazione di uno Sway.|
|Sway duplicato|SwayDuplicate|L'utente duplica uno Sway.|
|Sway modificato|SwayEdit|L'utente modifica uno Sway.|
|Duplicazione Sway abilitata|EnableDuplication|L'utente abilita la duplicazione di uno Sway. La capacità di abilitare la duplicazione di un Sway è abilitata per impostazione predefinita.|
|Condivisione di Sway revocata|SwayRevokeShare|Un utente interrompe la condivisione di uno Sway revocando l'accesso. La revoca dell'accesso comporta la modifica dei collegamenti associati a uno Sway.|
|Sway condiviso|SwayShare|L'utente desidera condividere uno Sway. Questo evento acquisisce l'azione dell'utente di clic su una destinazione di condivisione specifica nel menu di condivisione di Sway. L'evento non indica se l'utente ha completato l'azione di condivisione.|
|Disattivata condivisione esterna di Sway|SwayExternalSharingOff|Un amministratore disabilita la condivisione esterna di Sway per l'intera organizzazione usando l'interfaccia di amministrazione di Microsoft 365.|
|Attivata condivisione esterna di Sway|SwayExternalSharingOn|Un amministratore abilita la condivisione esterna di Sway per l'intera organizzazione usando l'interfaccia di amministrazione di Microsoft 365.|
|Disattivato servizio Sway|SwayServiceOff|Un amministratore disabilita Sway per l'intera organizzazione usando l'interfaccia di amministrazione di Microsoft 365.|
|Attivato servizio Sway|SwayServiceOn|Un amministratore abilita Sway per l'intera organizzazione usando l'interfaccia di amministrazione di Microsoft 365 (il servizio Sway è abilitato per impostazione predefinita).|
|Sway visualizzato|SwayView|L'utente visualizza uno Sway.|
||||

### <a name="user-administration-activities"></a>Attività di amministrazione utenti

La tabella seguente elenca le attività di amministrazione utenti registrate quando un amministratore aggiunge o modifica un account utente usando l'interfaccia di amministrazione di Microsoft 365 o il portale di gestione di Azure.

|**Attività**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Utente aggiunto|Aggiungi utente|È stato creato un account utente di Office 365.|
|Licenza utente modificata|Modifica della licenza utente|La licenza assegnata a un utente è stata modificata. Per visualizzare le licenze modificate, vedere l'attività **Utente aggiornato** corrispondente.|
|Password utente cambiata|Modifica della password utente|Un amministratore ha cambiato la password per un utente.|
|Utente eliminato|Elimina utente|È stato eliminato un account utente di Office 365.|
|Reimpostazione della password utente|Reimpostazione della password utente|Un amministratore ha reimpostato la password per un utente.|
|Impostata una proprietà che impone all'utente di cambiare la password|Impostazione forzatura per la modifica delle password utente|Un amministratore ha impostato la proprietà che forza l'utente a cambiare la password al successivo accesso a Office 365.|
|Impostazione delle proprietà della licenza|Impostazione delle proprietà della licenza|Un amministratore modifica le proprietà di una licenza assegnata a un utente.|
|Utente aggiornato|Aggiornamento di un utente|Un amministratore modifica una o più proprietà di un account utente. Per un elenco delle proprietà utente che possono essere aggiornate, vedere la sezione "Aggiornare gli attributi utente" in [Eventi del report di controllo di Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).|
||||

### <a name="azure-ad-group-administration-activities"></a>Attività di amministrazione gruppi di Azure AD

La tabella seguente elenca le attività di amministrazione gruppi registrate quando un amministratore o un utente crea o modifica un gruppo di Office 365 oppure quando un amministratore crea un gruppo di sicurezza usando l'interfaccia di amministrazione di Microsoft 365 o il portale di gestione di Azure. Per altre informazioni sui gruppi in Office 365, vedere [Visualizzare, creare ed eliminare gruppi nell'interfaccia di amministrazione di Microsoft 365](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7).

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Gruppo aggiunto|Aggiunta di un gruppo|È stato creato un gruppo.|
|Membro aggiunto a gruppo|Aggiunta di un membro al gruppo|È stato aggiunto un membro a un gruppo.|
|Gruppo eliminato|Eliminazione di un gruppo|È stato eliminato un gruppo.|
|Membro rimosso da gruppo|Rimozione di un membro dal gruppo|È stato rimosso un membro da un gruppo.|
|Gruppo aggiornato|Aggiornamento di un gruppo|È stata modificata una proprietà di un gruppo.|
||||

### <a name="application-administration-activities"></a>Attività di amministrazione applicazioni

La tabella seguente elenca le attività di amministrazione applicazioni registrate quando un amministratore aggiunge o modifica un'applicazione registrata in Azure AD. Qualsiasi applicazione che si basa su Azure AD per l'autenticazione deve essere registrata nella directory.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Voce di delega aggiunta|Aggiunta di una voce di delega|Un'autorizzazione di autenticazione è stata creata/concessa a un'applicazione in Azure AD.|
|Entità servizio aggiunta|Aggiunta di un'entità servizio|Un'applicazione è stata registrata in Azure AD. Un'applicazione è rappresentata da un'entità servizio nella directory.|
|Credenziali aggiunte a un'entità servizio |Aggiunta delle credenziali dell'entità servizio|Sono state aggiunte delle credenziali a un'entità servizio in Azure AD. Un'entità servizio rappresenta un'applicazione nella directory.|
|Voce di delega rimossa|Rimozione della voce di delega|Un'autorizzazione di autenticazione è stata rimossa da un'applicazione in Azure AD.|
|Entità servizio rimossa dalla directory|Rimozione di un'entità servizio|Un'applicazione è stata eliminata o ne è stata annullata la registrazione in Azure AD. Un'applicazione è rappresentata da un'entità servizio nella directory.|
|Credenziali rimosse da un'entità servizio |Rimozione delle credenziali dell'entità servizio|Le credenziali sono state rimosse da un'entità servizio in Azure AD. Un'entità servizio rappresenta un'applicazione nella directory.|
|Voce di delega impostata|Impostazione della voce di delega|Un'autorizzazione di autenticazione è stata aggiornata per un'applicazione in Azure AD.|
||||

### <a name="role-administration-activities"></a>Attività di amministrazione ruoli

La tabella seguente elenca le attività di amministrazione ruoli di Azure AD registrate quando un amministratore gestisce i ruoli di amministrazione nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Membro aggiunto a ruolo|Aggiunta di un membro del ruolo al ruolo|È stato aggiunto un utente a un ruolo di amministratore in Office 365.|
|Utente rimosso da un ruolo della directory|Rimozione di un membro del ruolo dal ruolo|È stato rimosso un utente da un ruolo di amministratore in Office 365.|
|Impostazione delle informazioni di contatto aziendali|Impostazione delle informazioni di contatto aziendali|Sono state aggiornare le preferenze di contatto a livello aziendale per l'organizzazione di Office 365. Le informazioni includono indirizzi di posta elettronica per messaggi correlati all'abbonamento inviati da Office 365, nonché notifiche tecniche relative ai servizi di Office 365.|
||||

### <a name="directory-administration-activities"></a>Attività di amministrazione directory

La tabella seguente elenca le attività correlate a dominio e directory di Azure AD registrate quando un amministratore gestisce l'organizzazione di Office 365 nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Dominio aggiunto a società|Aggiunta di un dominio alla società|Aggiunto un dominio all'organizzazione Office 365.|
|Partner aggiunto alla directory|Aggiunta di un partner alla società|È stato aggiunto un partner (amministratore delegato) all'organizzazione di Office 365.|
|Dominio rimosso da società|Rimozione di un dominio dalla società|È stato rimosso un dominio dall'organizzazione di Office 365.|
|Partner rimosso dalla directory|Rimozione di un partner dalla società|È stato rimosso un partner (amministratore delegato) dall'organizzazione di Office 365.|
|Informazioni sulla società impostate|Informazioni sulla società impostate|Sono state aggiornare le informazioni sulla società per l'organizzazione di Office 365. Le informazioni includono indirizzi di posta elettronica per messaggi correlati all'abbonamento inviati da Office 365, nonché notifiche tecniche relative ai servizi di Office 365.|
|Impostazione dell'autenticazione del dominio|Impostazione dell'autenticazione del dominio|È stata modificata l'impostazione di autenticazione del dominio per l'organizzazione di Office 365.|
|Impostazioni della federazione aggiornate per un dominio|Configurazione delle impostazioni di federazione nel dominio|Sono state modificate le impostazioni di federazione (condivisione esterna) per l'organizzazione di Office 365.|
|Criteri password impostati|Criteri password impostati|Sono stati modificati i vincoli di lunghezza e caratteri per le password utente nell'organizzazione di Office 365.|
|Attivata la sincronizzazione di Azure AD|Impostazione del flag DirSyncEnabled per la società|È stata impostata la proprietà che abilita una directory per Azure AD Sync.|
|Dominio aggiornato|Aggiornamento di un dominio|Sono state aggiornate le impostazioni di un dominio nell'organizzazione di Office 365.|
|Dominio verificato|Verifica di un dominio|È stato verificato che l'organizzazione è il proprietario di un dominio.|
|Posta elettronica verificata in dominio verificato|Verifica del dominio tramite la verifica di posta elettronica|È stata usata la verifica tramite posta elettronica per verificare che l'organizzazione sia il proprietario di un dominio.|
||||

### <a name="ediscovery-activities"></a>Attività di eDiscovery

Le attività correlate a Ricerca contenuto ed eDiscovery eseguite nel centro sicurezza e conformità o tramite i cmdlet di PowerShell corrispondenti vengono registrate nel log di controllo. Sono incluse le attività seguenti:

- Creazione e gestione di casi eDiscovery

- Creazione, avvio e modifica di ricerche di contenuto

- Esecuzione di operazioni di ricerca di contenuto, ad esempio visualizzazione in anteprima, esportazione ed eliminazione dei risultati della ricerca

- Configurazione del filtro delle autorizzazioni per Ricerca contenuto

- Gestione del ruolo di amministratore di eDiscovery

Per un elenco e una descrizione dettagliata delle attività di eDiscovery registrate, vedere [Cercare attività di eDiscovery nel log di controllo di Office 365](search-for-ediscovery-activities-in-the-audit-log.md).

> [!NOTE]
> Sono necessari fino a 30 minuti per visualizzare nei risultati della ricerca gli eventi collegati alle attività elencate in **Attività di eDiscovery** nell'elenco a discesa **Attività**. Invece, per visualizzare nei risultati della ricerca gli eventi corrispondenti provenienti dalle attività dei cmdlet di eDiscovery sono necessarie fino a 24 ore.

### <a name="advanced-ediscovery-activities"></a>Attività di Advanced eDiscovery 

Nella tabella seguente sono elencate le attività dall'esecuzione di attività in Advanced eDiscovery in Microsoft 365 dai professionisti dei settori IT e legale. Per altre informazioni, vedere [Panoramica della soluzione Advanced eDiscovery in Microsoft 365.](overview-ediscovery-20.md)

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiungere dati a un altro insieme da rivedere|AddWorkingSetQueryToWorkingSet|L'utente ha aggiunto i documenti di un insieme da rivedere a un altro insieme da rivedere.|
|Aggiunti dati a un insieme da rivedere|AddQueryToWorkingSet|L'utente ha aggiunto i risultati della ricerca da una ricerca di contenuto associata a un caso di Advanced eDiscovery a un insieme da rivedere.|
|Aggiunti dati non-Office 365 a un insieme da rivedere|AddNonOffice365DataToWorkingSet|L'utente ha aggiunto dati non-Office 365 a un insieme da rivedere.|
|Aggiunta di documenti con correzione a un insieme da rivedere|AddRemediatedData|L'utente carica i documenti con errori di indicizzazione corretti in un insieme da rivedere.|
|Dati analizzati nell'insieme da rivedere|RunAlgo|L'utente ha eseguito analisi sui documenti in un insieme da rivedere.|
|Documento con annotazioni nell'insieme da rivedere|AnnotateDocument|L'utente ha annotato un documento in un insieme da rivedere. L'annotazione include la correzione del contenuto di un documento.|
|Set di carichi confrontati|LoadComparisonJob|L'utente ha confrontato due set di carichi diversi in insieme da rivedere. Un set di carichi si verifica quando i dati di una ricerca di contenuto associata al caso vengono aggiunti a un insieme da rivedere.|
|Documenti corretti convertiti in PDF|BurnJob|L'utente ha convertito in file PDF tutti i documenti corretti di un insieme da rivedere.|
|Creato insieme da rivedere|CreateWorkingSet|L'utente ha creato un insieme da rivedere.|
|Ricerca insieme da rivedere creata|CreateWorkingSetSearch|L'utente ha creato una query di ricerca che consente di cercare i documenti in un insieme da rivedere.|
|Creato tag|CreateTag|L'utente ha creato un gruppo di tag in un insieme da rivedere. Un gruppo di tag può contenere uno o più tag figlio. Questi tag vengono usati per contrassegnare i documenti nell'insieme da rivedere.|
|Ricerca insieme da rivedere eliminata|DeleteWorkingSetSearch|Un utente ha eliminato una query di ricerca in un insieme da rivedere.|
|Tag eliminato|DeleteTag|L'utente ha eliminato un tag o un gruppo di tag in un insieme da rivedere.|
|Documento scaricato|DownloadDocument|L'utente ha scaricato un documento da un insieme da rivedere.|
|Tag modificato|DownloadDocument|L'utente ha modificato un tag in un insieme da rivedere.|
|Esportati documenti da un insieme da rivedere|ExportJob|L'utente ha esportato dei documenti da un insieme da rivedere.|
|Impostazione caso modificata|UpdateCaseSettings|L'utente ha modificato le impostazioni per un caso. Le impostazioni per il caso includono le informazioni sul caso, le autorizzazioni di accesso e le impostazioni che controllano il comportamento di ricerca e analisi.|
|Ricerca insieme da rivedere modificata|UpdateWorkingSetSearch|Un utente ha modificato una query di ricerca in un insieme da rivedere.|
|Visualizzazione dell'anteprima della ricerca dell'insieme da rivedere|PreviewWorkingSetSearch|Un utente ha visualizzato in anteprima i risultati di una query di ricerca in un insieme da rivedere.|
|Corretti i documenti con errori|ErrorRemediationJob|L'utente corregge i file che contengono errori di indicizzazione.|
|Documento con tag|TagFiles|L'utente contrassegna un documento in un insieme da rivedere.|
|Contrassegnati i risultati di una query|TagJob|Un utente contrassegna tutti i documenti che corrispondono ai criteri della query di ricerca in un insieme da rivedere.|
|Documento visualizzato nell'insieme da rivedere|ViewDocument|L'utente ha visualizzato un documento in un insieme da rivedere.|
|||

### <a name="power-bi-activities"></a>Attività di Power BI

È possibile eseguire una ricerca nel log di controllo per le attività in Power BI. Per informazioni sulle attività di Power BI, vedere la sezione "Attività controllate da Power BI" in [Uso del controllo all'interno dell'organizzazione](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi).

La registrazione di controllo per Power BI non è abilitata per impostazione predefinita. Per cercare le attività di Power BI nel log di controllo di Office 365, è necessario abilitare il controllo nel portale di amministrazione di Power BI. Per le istruzioni, vedere la sezione "Log di controllo" nel [portale di amministrazione di Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).

### <a name="microsoft-workplace-analytics-activities"></a>Attività di Microsoft Workplace Analytics

Workplace Analytics offre informazioni dettagliate sul modo in cui i gruppi collaborano nell'organizzazione di Office 365. La tabella seguente elenca le attività eseguite dagli utenti a cui è assegnato il ruolo di amministratore o i ruoli di analista in Workplace Analytics. Gli utenti a cui è stato assegnato il ruolo di analista hanno accesso completo a tutte le caratteristiche del servizio e usano il prodotto per eseguire l'analisi. Gli utenti a cui è stato assegnato il ruolo di amministratore possono configurare le impostazioni di privacy e le impostazioni predefinite del sistema e possono preparare, caricare e verificare i dati aziendali in Workplace Analytics. Per ulteriori informazioni, vedere [Workplace Analytics](https://docs.microsoft.com/workplace-analytics/index-orig).

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Collegamento OData accessibile|AccessedOdataLink|L'analista ha avuto accesso al collegamento a OData per una query.|
|Query annullata|CanceledQuery|L'analista ha annullato una query in esecuzione.|
|Esclusione riunione creata|MeetingExclusionCreated|L'analista ha creato una regola di esclusione delle riunioni.|
|Risultato eliminato|DeletedResult|L'analista ha eliminato il risultato di una query.|
|Report scaricato|DownloadedReport|L'analista ha scaricato il file dei risultati di una query.|
|Query eseguita|ExecutedQuery|L'analista ha eseguito una query.|
|Impostazione di accesso ai dati aggiornata|UpdatedDataAccessSetting|L'amministratore ha aggiornato le impostazioni di accesso ai dati.|
|Impostazione privacy aggiornata|UpdatedPrivacySetting|L'amministratore ha aggiornato le impostazioni relative alla privacy, ad esempio, le dimensioni minime del gruppo.|
|Dati dell'organizzazione caricati|UploadedOrgData|L'amministratore ha caricato il file di dati dell'organizzazione.|
|Pagina Esplora visualizzata|ViewedExplore|L'analista ha visualizzato le visualizzazioni in una o più schede della pagina Esplora.|
||||

### <a name="microsoft-teams-activities"></a>Attività di Microsoft Teams

La tabella seguente elenca le attività degli utenti e degli amministratori di Microsoft Teams registrate nel log di controllo di Office 365. Microsoft Teams è un'area di lavoro basata su chat di Office 365. Raggruppa conversazioni, riunioni, file e note in un'unica posizione. Per altre informazioni e collegamenti ad argomenti della Guida, vedere:

- [Domande frequenti su Microsoft Teams - Guida per gli amministratori](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)

- [Guida di Microsoft Teams](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Aggiunta di un bot al team|BotAddedToTeam|Un utente aggiunge un bot al team.|
|Aggiunta di un canale|ChannelAdded|Un utente aggiunge un canale al team.|
|Aggiunta di un connettore|ConnectorAdded|Un utente aggiunge un connettore a un canale.|
|Membri aggiunti al team|MemberAdded|Il proprietario di un team aggiunge membri a un team.|
|Aggiunta di una scheda|TabAdded|Un utente aggiunge una scheda a un canale.|
|Impostazione del canale cambiata|ChannelSettingChanged|L'operazione ChannelSettingChanged viene registrata quando vengono eseguite le attività seguenti dal membro di un team. Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata (tra parentesi) nella colonna **Elemento** nei risultati della ricerca nel log di controllo. <br/><br/>• Cambia il nome di un canale del team (**nome del canale**). <br/><br/>• Cambia la descrizione di un canale del team (**descrizione del canale**).|
|Impostazione dell'organizzazione cambiata|TeamsTenantSettingChanged|L'operazione TeamsTenantSettingChanged viene registrata quando le attività seguenti vengono eseguite da un amministratore globale (mediante l'interfaccia di amministrazione di Microsoft 365). Tenere presente che queste attività hanno effetto sulle impostazioni di Microsoft Teams dell'intera organizzazione. Per altre informazioni, vedere [Impostazioni dell'amministratore per Microsoft Teams](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2). <br/> Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata (tra parentesi) nella colonna **Elemento** nei risultati della ricerca nel log di controllo. <br/><br/>• Abilita o disabilita Microsoft Teams per l'organizzazione (**Microsoft Teams**). <br/><br/>• Abilita o disabilita l'interoperabilità tra Microsoft Teams e Skype for Business per l'organizzazione (**interoperabilità di Skype for Business**). <br/><br/>• Abilita o disabilita la visualizzazione organigramma nei client di Microsoft Teams (visualizzazione organigramma **). <br/><br/>• Abilita o disabilita la capacità dei membri del team di pianificare riunioni private (** Pianificazione di riunioni private **). <br/><br/>• Abilita o disabilita la capacità dei membri del team di pianificare riunioni di canale (Pianificazione di riunioni di canale**). <br/><br/>• Abilita o disabilita le chiamate video nelle riunioni di Teams (video per le riunioni Skype **). <br/><br/>• Abilita o disabilita la condivisione dello schermo nelle riunioni di Microsoft Teams per l'organizzazione (** condivisione dello schermo per le riunioni Skype **). <br/><br/>• Abilita o disabilita l'aggiunta di immagini animate (denominate Giphy) alle conversazioni di Teams (immagini animate**). <br/><br/>• Modifica l'impostazione di classificazione del contenuto per l'organizzazione (**classificazione del contenuto**). La classificazione del contenuto limita il tipo di immagini animate che possono essere visualizzate nelle conversazioni. <br/><br/>• Abilita o disabilita la capacità dei membri del team di aggiungere immagini personalizzabili (denominate meme personalizzati) da Internet alle conversazioni del team (immagini personalizzabili da Internet **). <br/><br/>• Abilita o disabilita la capacità dei membri del team di aggiungere immagini modificabili (denominate adesivi) alle conversazioni del team (** immagini modificabili **).<br/><br/>• Abilita o disabilita la capacità dei membri del team di usare i bot nelle chat e nei canali di Microsoft Teams (bot a livello di organizzazione **). <br/><br/>• Abilita bot specifici per Microsoft Teams. Non include T-Bot, vale a dire il bot di supporto di Teams che è disponibile quando i bot sono abilitati per l'organizzazione (**bot singoli**). <br/><br/>• Abilita o disabilita la capacità dei membri del team di aggiungere estensioni o schede (**estensioni o schede**). <br/><br/>• Abilita o disabilita il caricamento laterale dei Bot proprietari per Microsoft Teams (**caricamento laterale di bot**). <br/><br/>• Abilita o disabilita la capacità degli utenti di inviare messaggi di posta elettronica a un canale di Microsoft Teams (**canale di posta elettronica**).|
|Ruolo modificato dei membri del team|MemberRoleChanged|Un proprietario del team cambia il ruolo dei membri di un team. I valori seguenti indicano il tipo di ruolo assegnato all'utente. <br/><br/> **1** - Indica il ruolo Proprietario.<br/>**2** - Indica il ruolo Membro. <br/>**3** - Indica il ruolo Guest. <br/><br/> La proprietà Members include anche il nome dell'organizzazione e l'indirizzo di posta elettronica del membro.|
|Impostazione del team cambiata|TeamSettingChanged|L'operazione TeamSettingChanged viene registrata quando vengono eseguite le attività seguenti dal proprietario di un team. Per ognuna di queste attività viene visualizzata una descrizione dell'impostazione modificata (tra parentesi) nella colonna **Elemento** nei risultati della ricerca nel log di controllo. <br/><br/>• Cambia il tipo di accesso per un team. I team possono essere impostati come pubblici o privati (**Tipo di accesso del team**). Quando un team è privato (impostazione predefinita), gli utenti possono accedervi solo su invito. Quando un team è pubblico, è individuabile da tutti gli utenti. <br/><br/>• Cambia la classificazione delle informazioni di un team (**classificazione del team**). <br/> Ad esempio, i dati del team possono essere classificati come a impatto aziendale elevato, medio o basso.<br/><br/>• Cambia il nome di un team (**nome del team**). <br/><br/>• Cambia la descrizione del team (descrizione del team**). <br/><br/>• Modifiche apportate alle impostazioni del team. I proprietari dei team possono accedere a queste impostazioni in un client di Teams facendo clic con il pulsante destro del mouse su un team, selezionando **Gestisci team** e quindi scegliendo la scheda **Impostazioni**. Per queste attività viene visualizzato il nome dell'impostazione modificata nella colonna **Elemento** nei risultati della ricerca nel log di controllo.|
|Team creato|TeamCreated|Un utente crea un team.|
|Canale eliminato|ChannelDeleted|Un utente elimina un canale da un team.|
|Team eliminato|TeamDeleted|Un proprietario del team elimina un team.|
|Rimozione del bot dal team|BotRemovedFromTeam|Un utente rimuove un bot dal team.|
|Rimozione di un connettore|ConnectorRemoved|Un utente rimuove un connettore da un canale.|
|Membri rimossi dal team|MemberRemoved|Il proprietario di un team rimuove i membri da un team.|
|Rimozione di una scheda|TabRemoved|Un utente rimuove una scheda da un canale.|
|Connettore aggiornato|ConnectorUpdated|Un utente ha modificato un connettore in un canale.|
|Scheda aggiornata|TabUpdated|Un utente ha modificato una scheda in un canale.|
|Utente connesso a Teams|TeamsSessionStarted|Un utente accede a un client di Microsoft Teams. Questo evento non acquisisce le attività di aggiornamento del token.|
||||

### <a name="microsoft-teams-healthcare-activities"></a>Attività di Microsoft Teams per il settore sanitario

Se l'organizzazione usa l'[applicazione Pazienti](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-app-overview) in Microsoft Teams, è possibile cercare nel log di controllo le attività correlate all'utilizzo dell'app. Se l'ambiente è configurato per supportare l'app Pazienti, nell'elenco di selezione **Attività** è disponibile un altro gruppo di attività correlato.

![Attività di Microsoft Teams per il settore sanitario nell'elenco di selezione Attività](media/TeamsHealthcareAuditActivities.png)

Per una descrizione delle attività dell'app Pazienti, vedere [Log di controllo per l'app Pazienti](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit).

### <a name="yammer-activities"></a>Attività di Yammer

La tabella seguente elenca le attività degli utenti e degli amministratori di Yammer registrate nel log di controllo di Office 365. Per restituire le attività correlate a Yammer dal log di controllo di Office 365, è necessario selezionare **Visualizza i risultati per tutte le attività** nell'elenco **Attività**. Usare le caselle dell'intervallo di date e l'elenco **Utenti** per limitare i risultati della ricerca.

|**Nome descrittivo**|**Operazione**|**Descrizione**|
|:-----|:-----|:-----|
|Criteri di conservazione dei dati modificati|SoftDeleteSettingsUpdated|L'amministratore verificato aggiorna l'impostazione per i criteri di conservazione dei dati di rete per l'eliminazione definitiva o l'eliminazione temporanea. Solo gli amministratori verificati possono eseguire questa operazione.|
|Configurazione di rete modificata|NetworkConfigurationUpdated|L'amministratore di rete o verificato modifica la configurazione della rete Yammer. Imposta anche l'intervallo per l'esportazione dei dati e l'attivazione della chat.|
|Impostazioni del profilo di rete modificate|ProcessProfileFields|L'amministratore di rete o verificato modifica le informazioni visualizzate nei profili dei membri per gli utenti della rete.|
|Modalità per il contenuto privato modificata|SupervisorAdminToggled|L'amministratore verificato attiva o disattiva la *Modalità contenuto privato*. Questa modalità consente a un amministratore di visualizzare i post nei gruppi privati e i messaggi privati scambiati tra singoli utenti o gruppi di utenti. Solo gli amministratori verificati possono eseguire questa operazione.|
|Configurazione della sicurezza modificata|NetworkSecurityConfigurationUpdated|L'amministratore verificato aggiorna la configurazione di sicurezza della rete Yammer. Imposta anche i criteri di scadenza della password e le limitazioni per gli indirizzi IP. Solo gli amministratori verificati possono eseguire questa operazione.|
|File creato|FileCreated|L'utente carica un file.|
|Gruppo creato|GroupCreation|Un utente crea un gruppo.|
|Gruppo eliminato|GroupDeletion|Un gruppo viene eliminato da Yammer.|
|Messaggio eliminato|MessageDeleted|L'utente elimina un messaggio.|
|File scaricato|FileDownloaded|L'utente scarica un file.|
|Dati esportati|DataExport|L'amministratore verificato esporta i dati della rete Yammer. Solo gli amministratori verificati possono eseguire questa operazione.|
|File condiviso|FileShared|L'utente condivide un file con un altro utente.|
|Utente di rete sospeso|NetworkUserSuspended|L'amministratore di rete o verificato sospende (disattiva) un utente da Yammer.|
|Utente sospeso|UserSuspension|L'account utente viene sospeso (disattivato).|
|Descrizione del file aggiornata|FileUpdateDescription|L'utente modifica la descrizione di un file.|
|Nome file aggiornato|FileUpdateName|L'utente modifica il nome di un file.|
|File visualizzato|FileVisited|L'utente visualizza un file.|
||||

### <a name="microsoft-flow-activities"></a>Attività di Microsoft Flow

È possibile eseguire una ricerca nel log di controllo per le attività in Microsoft Flow. Queste attività includono la creazione, la modifica e l'eliminazione di flussi e la modifica delle autorizzazioni di flusso. Per informazioni sul controllo delle attività di Flow, vedere il blog [Eventi di controllo di Microsoft Flow disponibili nel Centro sicurezza e conformità](https://flow.microsoft.com/blog/security-and-compliance-center).

### <a name="microsoft-powerapps"></a>Microsoft PowerApps

È possibile eseguire una ricerca nel log di controllo per le attività in PowerApps. Queste attività includono la creazione, l'avvio e la pubblicazione di un'app. Anche l'assegnazione di autorizzazioni alle app è controllata. Per una descrizione di tutte le attività di PowerApps vedere [Registrazione delle attività per PowerApps](https://docs.microsoft.com/power-platform/admin/logging-powerapps#what-events-are-audited).

### <a name="microsoft-stream-activities"></a>Attività di Microsoft Stream

È possibile eseguire una ricerca nel log di controllo per le attività in Microsoft Stream. Queste attività includono le attività video eseguite dagli utenti, le attività dei canali del gruppo e le attività amministrative, ad esempio la gestione degli utenti, la gestione delle impostazioni dell'organizzazione e l'esportazione dei report. Per una descrizione di queste attività, vedere la sezione "Attività registrate in Microsoft Stream" in [Log di controllo di Microsoft Stream](https://docs.microsoft.com/stream/audit-logs).

### <a name="exchange-admin-audit-log"></a>Log di controllo dell'amministratore di Exchange

La registrazione di controllo dell'amministratore di Exchange, abilitata per impostazione predefinita in Office 365, registra un evento nel log di controllo di Office 365 quando un amministratore (o un utente a cui sono state assegnate autorizzazioni amministrative) apporta una modifica nell'organizzazione di Exchange Online. Le modifiche apportate mediante l'interfaccia di amministrazione di Exchange o eseguendo un cmdlet in PowerShell per Exchange Online vengono registrate nel log di controllo di amministrazione di Exchange. I cmdlet che iniziano con **Get-**, **Search-** o **Test-** non vengono registrati nel log di controllo di Office 365. Per informazioni dettagliate sulla registrazione di controllo dell'amministratore in Exchange, vedere [Registrazione di controllo dell'amministratore](https://go.microsoft.com/fwlink/p/?LinkID=619225).

> [!IMPORTANT]
> Alcuni cmdlet di Exchange Online che non sono stati registrati nel log di controllo di amministrazione di Exchange o nel log di controllo di Office 365. Molti di questi cmdlet sono correlati alla gestione del servizio Exchange Online e sono eseguiti dal personale del centro dati Microsoft o dagli account di servizio. Questi cmdlet non vengono registrati perché comportano un gran numero di eventi di controllo "fastidiosi". Se è presente un cmdlet di Exchange Online che non viene controllato, inviare un suggerimento al [Forum Office 365 Security & Compliance User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance) e chiedere che sia abilitato per il controllo. È anche possibile inviare una richiesta di modifica della progettazione al supporto tecnico Microsoft.

Di seguito sono forniti alcuni suggerimenti per la ricerca delle attività di amministrazione di Exchange durante la ricerca nel log di controllo di Office 365:

- Per restituire le voci dal log di controllo dell'amministratore di Exchange, è necessario selezionare **Visualizza i risultati per tutte le attività** nell'elenco **Attività**. Usare le caselle relative all'intervallo di date e l'elenco **Utenti** per limitare i risultati della ricerca per i cmdlet eseguiti da uno specifico amministratore di Exchange in un determinato intervallo di date.

- Per visualizzare gli eventi del log di controllo dell'amministratore di Exchange, filtrare i risultati della ricerca e digitare **-** (trattino) nella casella del filtro **Attività**. In questo modo, vengono visualizzati i nomi dei cmdlet, che sono indicati nella colonna **Attività** per gli eventi di amministrazione di Exchange. È anche possibile disporre i nomi dei cmdlet in ordine alfabetico.

  ![Digitare un trattino nella casella Attività per filtrare gli eventi di amministrazione di Exchange](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)

- Per ottenere informazioni sul cmdlet eseguito, sui parametri e sui valori dei parametri usati e sugli oggetti interessati, è possibile esportare i risultati della ricerca e selezionare l'opzione **Scarica tutti i risultati**. Per ulteriori informazioni, vedere [Esportare, configurare e visualizzare i record del log di controllo](export-view-audit-log-records.md).

- È anche possibile usare il comando `Search-UnifiedAuditLog -RecordType ExchangeAdmin`in PowerShell di Exchange Online per restituire solo i record di controllo del log di controllo dell'amministratore di Exchange. Dopo l'esecuzione di un cmdlet di Exchange per la voce del log di controllo corrispondente, la restituzione dei risultati della ricerca potrebbe richiedere fino a 30 minuti. Per altre informazioni, vedere [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog). Per informazioni sull'esportazione dei risultati della ricerca restituiti dal cmdlet **Search-UnifiedAuditLog** in un file CSV, vedere la sezione "Suggerimenti per l'esportazione e la visualizzazione del log di controllo in [Esportare, configurare e visualizzare i record del log di controllo ](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- È inoltre possibile visualizzare gli eventi nel log di controllo dell'amministratore di Exchange mediante l'interfaccia di amministrazione di Exchange o eseguendo **Search-AdminAuditLog** in PowerShell per Exchange Online. Si tratta di un ottimo metodo per cercare in modo specifico l'attività eseguita dagli amministratori di Exchange Online. Per istruzioni, vedere:

  - [Visualizzare il registro di controllo dell'amministratore](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx)

  - [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)

   Tenere presente che le stesse attività dell'amministratore di Exchange sono registrate sia nel log di controllo di amministrazione di Exchange che nel log di controllo di Office 365.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Dove è possibile trovare informazioni sulle caratteristiche offerte dal servizio di controllo in Office 365?**

Per altre informazioni sulle caratteristiche di controllo e creazione di report disponibili in Office 365, vedere [Controllo e creazione di report in Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-auditing-and-reporting-overview).

**Quali sono i diversi servizi di Office 365 attualmente controllati?**

Sono controllati i servizi di Office 365 più usati come Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Dynamics 365, Advanced Threat Protection e Power BI. Vedere l' [inizio di questo articolo](search-the-audit-log-in-security-and-compliance.md) per un elenco dei servizi che vengono controllati.

**Quali attività sono controllate dal servizio di controllo in Office 365?**

Per un elenco e una descrizione delle attività controllate in Office 365, vedere la sezione [Attività controllate](#audited-activities) in questo articolo.

**Quanto tempo è necessario affinché un record di controllo sia disponibile dopo il verificarsi di un evento?**

La maggior parte dei dati di controllo è disponibile nel giro di 30 minuti ma la visualizzazione della voce del registro di controllo corrispondente nei risultati della ricerca può richiedere fino a 24 ore. Vedere la tabella nella sezione [Prima di iniziare](#before-you-begin) di questo articolo, che mostra il tempo necessario affinché gli eventi dei diversi servizi di Office 365 divengano disponibili.

**Per quanto tempo vengono conservati i record di controllo?**

Come descritto in precedenza, il periodo di conservazione per i record di controllo varia in base all'abbonamento a Office 365 dell'organizzazione.

- **Office 365 E3:** i record di controllo vengono conservati per 90 giorni.

- **Office 365 E5:** anche i record di controllo vengono conservati per 90 giorni. Il mantenimento dei record di controllo per un anno potrebbe essere disponibile per gli utenti E5 e gli utenti con una licenza E3 e una licenza per il componente aggiuntivo Office 365 Advanced Compliance.

  > [!NOTE]
  > Come illustrato in precedenza, il programma di anteprima privata per il periodo di conservazione di un anno per i record di controllo per le organizzazioni E5 (o per gli utenti delle organizzazioni E3 con licenza per i componenti aggiuntivi per la conformità avanzata) è chiuso alle nuove iscrizioni. Questo articolo verrà aggiornato quando il periodo di conservazione di un anno sarà disponibile in anteprima pubblica o rilasciato per la disponibilità generale.

Si noti inoltre che la durata del periodo di conservazione per i record di controllo si basa sulle licenze per utente. Ad esempio, se a un utente dell'organizzazione viene assegnata una licenza di Office 365 E3 o E5, i record di controllo per le attività eseguite dall'utente vengono conservati per 90 giorni.

**È possibile accedere ai dati di controllo a livello di programmazione?**

Sì. L'API Office 365 Management Activity consente di recuperare i log di controllo a livello di programmazione.  Per iniziare, vedere [Introduzione alle API Office 365 Management Activity](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

**Esistono altri modi diversi dall'uso del Centro sicurezza e conformità o dall'API Office 365 Management Activity per ottenere log di controllo?**

No. Questi sono gli unici due modi per ottenere dati dal servizio di controllo di Office 365.

**È necessario abilitare singolarmente il controllo in ogni servizio di cui si vogliono acquisire i log di controllo?**

Nella maggior parte dei servizi di Office 365, il controllo è abilitato per impostazione predefinita dopo l'attivazione del controllo per l'organizzazione di Office 365 (come descritto nella sezione [Prima di iniziare](#before-you-begin) in questo articolo).

**Il servizio di controllo di Office 365 supporta la deduplicazione dei record?**

No. La pipeline dei servizi di controllo è quasi in tempo reale, pertanto non supporta la deduplicazione.

**I dati di controllo di Office 365 vengono trasportati nelle diverse aree geografiche?**

No. Attualmente sono presenti distribuzioni di pipeline di controllo nelle aree NA (Nord America), EMEA (Europa, Medio Oriente e Africa) ed APAC (Asia Pacifico). Tuttavia, i dati possono essere trasportati in queste aree geografiche per il bilanciamento del carico e solo durante i problemi del sito live. Durante l'esecuzione di queste attività, i dati in transito sono crittografati.

**I dati di controllo sono crittografati?**

I dati di controllo sono archiviati nelle cassette postali di Exchange (dati archiviati) nella stessa area geografica in cui è distribuita la pipeline di controllo. I dati non sono crittografati. Tuttavia, i dati in transito sono sempre crittografati.
