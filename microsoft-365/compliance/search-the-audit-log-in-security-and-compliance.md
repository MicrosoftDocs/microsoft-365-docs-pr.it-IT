---
title: Eseguire una ricerca nel log di controllo nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
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
description: Usare il Centro sicurezza e conformità di Office 365 o il Centro conformità Microsoft 365 per eseguire una ricerca nel log di controllo unificato e vedere le attività di utenti e amministratori nell'organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aa47cc0c460e77a6faadd5cb2ff7d46c62ed88ab
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376655"
---
# <a name="search-the-audit-log-in-the-compliance-center"></a>Eseguire una ricerca nel log di controllo nel Centro conformità

Se è necessario verificare se un utente ha visualizzato un documento specifico o ha eliminato un elemento dalla cassetta postale, è possibile usare il Centro conformità Microsoft 365 per eseguire una ricerca nel log di controllo unificato e visualizzare le attività di utenti e amministratori nell'organizzazione. Perché usare un log di controllo unificato? Perché è possibile cercare i tipi seguenti di [attività di utenti e amministratori](#audited-activities) in Microsoft 365:

- Attività degli utenti in SharePoint Online e OneDrive for Business

- Attività utente in Exchange Online (registrazione di controllo delle cassette postali di Exchange)

- Attività amministratore in SharePoint Online

- Attività amministratore in Azure Active Directory (servizio directory per Microsoft 365)

- Attività amministratore in Exchange Online (registrazione di controllo dell'amministratore di Exchange )

- Attività eDiscovery nel Centro sicurezza e conformità

- Attività utente e amministratore in Power BI

- Attività utente e amministratore in Microsoft Teams

- Attività utente e amministratore in Dynamics 365

- Attività utente e amministratore in Yammer

- Attività utente e amministratore in Microsoft Power Automate

- Attività utente e amministratore in Microsoft Stream

- Attività di analisti e amministratori in Microsoft Workplace Analytics

- Attività utente e amministratore in Microsoft Power Apps

- Attività utente e amministratore in Microsoft Forms

- Attività utente e amministratore per le etichette di riservatezza per siti che usano SharePoint Online o Microsoft Teams

## <a name="requirements-to-search-the-audit-log"></a>Requisiti per la ricerca nel log di controllo

Prima di iniziare la ricerca nel log di controllo, tenere presente quanto segue.

- È necessario che l'amministratore corrente o un altro amministratore attivi la registrazione di controllo prima di iniziare a eseguire ricerche nel log di controllo. Per attivare la registrazione, fare clic su **Avvia registrazione** nella pagina **Ricerca nel log di controllo** nel Centro sicurezza e conformità. Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione. Dopo l'attivazione, viene visualizzato un messaggio che indica che è in corso la preparazione del log di controllo e che sarà possibile eseguire una ricerca tra un paio d'ore, dopo il completamento della preparazione. Questa procedura deve essere eseguita una sola volta. Per ulteriori informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](turn-audit-log-search-on-or-off.md).

  > [!NOTE]
  > Microsoft sta per impostare come predefinita l'attivazione del controllo. Nel frattempo, è possibile attivarlo come descritto in precedenza.

- È necessario avere il ruolo relativo ai log di controllo di sola lettura o ai log di controllo in Exchange Online per poter eseguire ricerche nel log di controllo. Per impostazione predefinita, questi ruoli sono assegnati ai gruppi di ruoli Gestione conformità e Gestione organizzazione nella pagina **Autorizzazioni** nell'interfaccia di amministrazione di Exchange. Gli amministratori globali di Office 365 e Microsoft 365 sono aggiunti automaticamente come membri del gruppo di ruoli Gestione organizzazione in Exchange Online. Per consentire a un utente di eseguire ricerche nel log di controllo con il livello minimo di privilegi, è possibile creare un gruppo di ruoli personalizzato in Exchange Online, aggiungere il ruolo relativo ai log di controllo di sola lettura o ai log di controllo e quindi aggiungere l'utente come membro del nuovo gruppo di ruoli. Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688).

  > [!IMPORTANT]
  > Se si assegna a un utente il ruolo relativo ai log di controllo di sola lettura o ai log di controllo nella pagina **Autorizzazioni** nel Centro sicurezza e conformità, l'utente non potrà eseguire ricerche nel log di controllo. È necessario assegnare le autorizzazioni in Exchange Online. Ciò avviene perché il cmdlet sottostante usato per la ricerca nel log di controllo è un cmdlet di Exchange Online.

- Quando un utente o un amministratore esegue un’attività soggetta a controllo, viene generato e archiviato un record di controllo nel log di controllo dell’organizzazione. Il periodo di tempo per cui il record di controllo viene conservato (ed è disponibile per la ricerca nel log di controllo) varia in base all'abbonamento a Office 365 o Microsoft 365 Enterprise e, in particolare, al tipo di licenza assegnata a un utente specifico.

  - Per gli utenti a cui è assegnata una licenza di Office 365 E5 o Microsoft 365 E5 (o gli utenti con una licenza per componente aggiuntivo Microsoft 365 E5 Compliance o Microsoft 365 E5 eDiscovery and Audit), i record di controllo per le attività di Azure Active Directory, Exchange e SharePoint vengono conservati per un anno per impostazione predefinita. Le organizzazioni, inoltre, possono creare criteri di conservazione per i log di controllo per conservare i record di controllo di attività relative ad altri servizi per un massimo di un anno. Per altre informazioni, vedere [Gestire i criteri di conservazione dei log di controllo](audit-log-retention-policies.md).

    > [!NOTE]
    > Se l'organizzazione ha partecipato al programma di anteprima privata per la conservazione dei record di controllo per un anno, la durata di conservazione per i record di controllo generati prima della data di implementazione della disponibilità generale non verrà reimpostata.

  - Per gli utenti a cui è assegnata una qualsiasi altra licenza (non E5) di Office 365 o Microsoft 365, i record di controllo vengono conservati per 90 giorni. Per un elenco degli abbonamenti di Office 365 e Microsoft 365 che supportano la registrazione di controllo unificato, vedere [la descrizione del servizio Centro sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

    > [!NOTE]
    > Anche se il controllo delle cassette postali è attivato per impostazione predefinita, per alcuni utenti gli eventi di controllo delle cassette postali potrebbero non essere trovati nelle ricerche nel log di controllo nel Centro sicurezza e conformità o nell'API Office 365 Management Activity. Per altre informazioni, vedere [Altre informazioni sulla registrazione di controllo delle cassette postali](enable-mailbox-auditing.md#more-information).

- Se si desidera disabilitare la ricerca nel log di controllo per l’organizzazione, è possibile eseguire questo comando nella sessione remota di PowerShell connessa all'organizzazione di Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    Per attivare di nuovo la ricerca nel log di controllo, è possibile eseguire il comando seguente in PowerShell di Exchange Online:

  ```powershell
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

  Per altre informazioni, vedere [Disabilitare la ricerca nel log di controllo](turn-audit-log-search-on-or-off.md).

- Come indicato in precedenza, il cmdlet sottostante usato per la ricerca nel log di controllo è un cmdlet di Exchange Online, ovvero **Search-UnifiedAuditLog**. Ciò significa che è possibile usare questo cmdlet anziché la pagina **Ricerca log di controllo** nel Centro sicurezza e conformità per eseguire una ricerca nel log di controllo. È necessario eseguire questo cmdlet in una sessione remota di PowerShell connessa all'organizzazione di Exchange Online. Per altre informazioni, vedere [Search-UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776).

  Per informazioni sull'esportazione dei risultati della ricerca restituiti dal cmdlet **Search-UnifiedAuditLog** in un file CSV, vedere la sezione "Suggerimenti per l'esportazione e la visualizzazione del log di controllo" in [Esportare, configurare e visualizzare i record del log di controllo](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- Per scaricare i dati a livello di programmazione dal log di controllo, è consigliabile usare l'API Office 365 Management Activity invece di uno script di PowerShell. L'API Office 365 Management Activity è un servizio Web REST che può essere usato per sviluppare soluzioni di monitoraggio di operazioni, sicurezza e conformità per l'organizzazione. Per altre informazioni, vedere [Riferimento API Management Activity di Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

- La restituzione del record del log di controllo nei risultati della ricerca nel log di controllo può richiedere fino a 30 minuti o 24 ore dal momento in cui si verifica l'evento. La tabella seguente mostra il tempo necessario per i diversi servizi di Office 365.

  |Servizio o funzionalità Microsoft 365|30 minuti|24 ore|
  |:-----|:-----:|:-----:|
  |Defender per Office 365 e Threat Intelligence|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Azure Active Directory (eventi di accesso utente)||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Interfaccia di amministrazione di Azure Active Directory (eventi di amministrazione)||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Prevenzione della perdita di dati|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Dynamics 365 CRM||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |eDiscovery|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Exchange Online|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Power Automate||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Microsoft Project|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Stream|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Teams|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Power Apps||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |Power BI|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Centro sicurezza e conformità|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Etichette di riservatezza||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  |SharePoint Online e OneDrive for Business|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Workplace Analytics|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Yammer||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
  |Microsoft Forms|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
  ||||

- Azure Active Directory (Azure AD) è il servizio directory per Office 365. Il log di controllo unificato contiene le attività di utenti, gruppi, applicazioni, domini e directory eseguite nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure. Per un elenco completo degli eventi di Azure AD, vedere [Eventi del report di controllo di Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).

- Per impostazione predefinita, la registrazione di controllo per Power BI non è abilitata. Per cercare le azioni di Power BI nel log di controllo, è necessario abilitare il controllo nel portale di amministrazione di Power BI. Per istruzioni, vedere la sezione "Log di controllo" nel [portale di amministrazione di Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).

## <a name="search-the-audit-log"></a>Eseguire ricerche nel log di controllo

> [!NOTE]
> Si è verificato un problema per cui le attività di Azure AD non erano disponibili nello strumento di ricerca nel log di controllo dal 22 ottobre 2020 al 6 novembre 2020. Queste attività includono le attività di Azure AD di amministrazione utenti, di amministrazione gruppi, di amministrazione applicazioni, di amministrazione ruoli e di amministrazione directory. Gli eventi mancanti per tale periodo saranno resi disponibili nei prossimi giorni. Il completamento di questa operazione è previsto entro il 20 novembre 2020. In alcuni casi, potrebbero essere visualizzati dati di eventi duplicati per gli eventi generati tra il 26 ottobre 2020 e il 05 novembre 2020.
    
Ecco la procedura per la ricerca nel log di audit in Office 365.

[Passaggio 1: Eseguire una ricerca nel log di controllo](#step-1-run-an-audit-log-search)

[Passaggio 2: Visualizzare i risultati della ricerca](#step-2-view-the-search-results)

[Passaggio 3: Filtrare i risultati della ricerca](#step-3-filter-the-search-results)

[Passaggio 4: Esportare i risultati della ricerca in un file](#step-4-export-the-search-results-to-a-file)

### <a name="step-1-run-an-audit-log-search"></a>Passaggio 1: Eseguire una ricerca nel log di controllo

1. Passare a [https://protection.office.com](https://protection.office.com).

    > [!TIP]
    > Usare una sessione di esplorazione privata (invece di una normale) per accedere al Centro sicurezza e conformità per impedire l'uso delle credenziali con cui si è attualmente connessi. Per aprire una sessione InPrivate Browsing in Internet Explorer o Microsoft Edge, premere CTRL+MAIUSC+P. Per aprire una sessione di esplorazione privata in Google Chrome (chiamata finestra di navigazione in incognito), premere CTRL+MAIUSC+N.

2. Accedere usando l'account aziendale o dell'istituto di istruzione.

3. Nel riquadro sinistro del Centro sicurezza e conformità, fare clic su **Cerca**, quindi su **Ricerca log di controllo**.

    Viene visualizzata la pagina **Ricerca log di controllo**.

    ![Configurare i criteri, quindi fare clic su Cerca per eseguire un report](../media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)

    > [!NOTE]
    > È necessario attivare la registrazione di controllo per poter eseguire una ricerca nel log di controllo. Se è visualizzato il collegamento **Avvia registrazione attività utenti e amministratori**, fare clic su di esso per attivare il controllo. Se questo collegamento non è visualizzato, il controllo è già stato attivato per l'organizzazione.

4. Configurare i criteri di ricerca seguenti: 

   1. **Attività**: Fare clic sull'elenco a discesa per visualizzare le attività che è possibile cercare. Le attività di utenti e amministratori sono organizzate in gruppi di attività correlate. È possibile selezionare attività specifiche oppure è possibile fare clic sul nome del gruppo di attività per selezionare tutte le attività del gruppo. È anche possibile fare clic su un'attività selezionata per annullare la selezione. Dopo aver eseguito la ricerca, vengono visualizzate solo le voci del log di controllo per le attività selezionate. Se si seleziona **Visualizza i risultati per tutte le attività**, vengono visualizzati i risultati per tutte le attività eseguite dall'utente o dal gruppo di utenti selezionato.

      Nel log di controllo vengono registrate più di 100 attività di utenti e amministratori. Fare clic sulla scheda **Attività controllate** in questo articolo per visualizzare le descrizioni delle singole attività per i vari servizi.

   1. **Data inizio** e **Data fine**: Per impostazione predefinita, sono selezionati gli ultimi sette giorni. Selezionare un intervallo di date e ore per visualizzare gli eventi che si sono verificati in tale periodo. La data e l'ora sono specificate in formato UTC (Coordinated Universal Time). L'intervallo di date massimo che è possibile specificare è di 90 giorni. Se l'intervallo di date selezionato è maggiore di 90 giorni, verrà visualizzato un errore.

      > [!TIP]
      > Se si usa l'intervallo di date massimo di 90 giorni, selezionare l'ora corrente per **Data inizio**. In caso contrario, verrà visualizzato un errore che indica che la data di inizio è precedente alla data di fine. Se è stato attivato il controllo negli ultimi 90 giorni, l'intervallo di date massimo non può iniziare prima della data in cui il controllo è stato attivato.

   1. **Utenti**: Fare clic in questa casella e quindi selezionare uno o più utenti per cui visualizzare i risultati della ricerca. Nell'elenco di risultati vengono visualizzate le voci del log di controllo per l'azione selezionata eseguita dagli utenti specificati in questa casella. Lasciare la casella vuota per restituire le voci per tutti gli utenti (e gli account del servizio) nell'organizzazione.

   1. **File, cartella o sito**: Digitare alcuni o tutti i nomi di file o cartelle per cercare l'attività relativa al file o alla cartella che contiene la parola chiave specificata. È anche possibile specificare l'URL di un file o di una cartella. Per usare un URL, digitare il percorso URL completo oppure, se si digita una parte dell'URL, non includere spazi o caratteri speciali.

      Lasciare questa casella vuota per restituire le voci per tutti i file e le cartelle nell'organizzazione.

      > [!TIP]
      >
      > - Se si stanno cercando tutte le attività correlate a un **sito**, aggiungere il simbolo jolly (\*) dopo l'URL per restituire tutte le voci per quel sito; ad esempio, `"https://contoso-my.sharepoint.com/personal*"`.
      >
      > - Se si stanno cercando tutte le attività correlate a un **file**, aggiungere il simbolo jolly (\*) prima del nome file per restituire tutte le voci per quel file; ad esempio, `"*Customer_Profitability_Sample.csv"`.

5. Fare clic su **Cerca** per eseguire la ricerca usando i criteri di ricerca.

   I risultati della ricerca vengono caricati e, dopo alcuni istanti, vengono visualizzati in **Risultati**. Al termine della ricerca viene visualizzato il numero di risultati trovati. Verranno visualizzati al massimo 5.000 eventi nel riquadro **Risultati**, con incrementi di 150 eventi. Se ci sono più di 5.000 eventi che soddisfano i criteri di ricerca, verranno visualizzati i 5.000 eventi più recenti.

   ![Il numero di risultati viene visualizzato al termine della ricerca](../media/986216f1-ca2f-4747-9480-e232b5bf094c.png)

#### <a name="tips-for-searching-the-audit-log"></a>Suggerimenti per la ricerca nel log di controllo

- È possibile selezionare attività specifiche da cercare facendo clic sul relativo nome. In alternativa, è possibile cercare tutte le attività in un gruppo, ad esempio **Attività su file e cartelle**, facendo clic sul nome del gruppo. Se è selezionata un'attività, è possibile fare clic su di essa per annullare la selezione. È anche possibile usare la casella di ricerca per visualizzare le attività contenenti la parola chiave digitata.

  ![Fare clic sul nome del gruppo di attività per selezionare tutte le attività](../media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)

- È necessario selezionare **Visualizza i risultati per tutte le attività** nell'elenco **Attività** per visualizzare gli eventi del log di controllo dell'amministratore di Exchange. Gli eventi di questo log di controllo mostrano un nome di cmdlet, ad esempio **Set-Mailbox**, nella colonna **Attività** dei risultati. Per altre informazioni, fare clic sulla scheda **Attività controllate** in questo argomento e quindi fare clic su **Attività di amministrazione di Exchange**.

  Allo stesso modo, esistono alcune attività di controllo che non hanno un elemento corrispondente nell'elenco **Attività**. Se si conosce il nome dell'operazione per queste attività, è possibile cercare tutte le attività, quindi filtrare i risultati digitando il nome dell'operazione nella casella per la colonna **Attività**. Vedere [Passaggio 3: Filtrare i risultati di ricerca](#step-3-filter-the-search-results) per altre informazioni su come filtrare i risultati.

- Fare clic su **Cancella** per cancellare i criteri di ricerca correnti. L'intervallo di date torna impostato sul valore predefinito corrispondente agli ultimi sette giorni. È anche possibile fare clic su **Deseleziona tutto per visualizzare i risultati per tutte le attività** per annullare tutte le attività selezionate.

- Se vengono trovati 5.000 risultati, è probabile che ci siano più di 5.000 eventi che soddisfano i criteri di ricerca. È possibile perfezionare i criteri di ricerca ed eseguire di nuovo la ricerca in modo che vengano restituiti meno risultati oppure è possibile esportare tutti i risultati della ricerca selezionando **Esporta risultati** \> **Scarica tutti i risultati**.

### <a name="step-2-view-the-search-results"></a>Passaggio 2: Visualizzare i risultati della ricerca

I risultati di una ricerca nel log di controllo vengono visualizzati in **Risultati** nella pagina **Ricerca log di controllo**. Come affermato in precedenza, vengono visualizzati al massimo 5.000 eventi (i più recenti) in incrementi di 150 eventi. Per visualizzare più eventi, è possibile usare la barra di scorrimento nel riquadro **Risultati** oppure è possibile premere **MAIUSC+FINE** per visualizzare i eventi 150 successivi.

I risultati includono le informazioni seguenti relative a ogni evento restituito dalla ricerca:

- **Data**: La data e l’ora (in formato UTC) in cui si è verificato l'evento.

- **Indirizzo IP**: Indirizzo IP del dispositivo usato quando l'attività è stata registrata. L'indirizzo IP viene visualizzato nel formato IPv4 o IPv6.

   > [!NOTE]
  > Per alcuni servizi, il valore visualizzato in questo campo può corrispondere all'indirizzo IP di un'applicazione attendibile (ad esempio Office nelle app Web) che contatta il servizio per conto dell'utente e non all'indirizzo IP del dispositivo usato dall’utente che ha eseguito l'attività. Inoltre, per le attività di amministrazione (o attività eseguite da un account di sistema) per gli eventi correlati ad Azure Active Directory, l'indirizzo IP non viene registrato e il valore visualizzato nel campo è `null`.

- **Utente**: L’utente (o account del servizio) che ha eseguito l'attività che ha attivato l'evento.

- **Attività**: L’attività eseguita dall'utente. Questo valore corrisponde alle attività selezionate nell'elenco a discesa **Attività**. Per un evento del log di controllo dell'amministratore di Exchange, il valore in questa colonna è un cmdlet di Exchange. 

- **Elemento**: L’oggetto creato o modificato come risultato dell'attività corrispondente, ad esempio il file che è stato visualizzato o modificato oppure l'account utente che è stato aggiornato. Non tutte le attività hanno un valore in questa colonna.

- **Dettagli**: Informazioni aggiuntive su un'attività. Anche in questo caso, non tutte le attività hanno un valore.

> [!TIP]
> Fare clic su un'intestazione di colonna in **Risultati** per ordinare i risultati. È possibile ordinare i risultati dalla A alla Z o dalla Z alla A. Fare clic sull'intestazione **Data** per ordinare i risultati dal meno recente al più recente o viceversa.

#### <a name="view-the-details-for-a-specific-event"></a>Visualizzare i dettagli di un evento specifico

È possibile visualizzare altri dettagli di un evento facendo clic sul record dell'evento nell'elenco dei risultati della ricerca. Verrà visualizzata una pagina **Dettagli** contenente le proprietà dettagliate del record dell'evento. Le proprietà visualizzate dipendono dal servizio in cui si verifica l'evento. Per visualizzare questi dettagli, fare clic su **Altre informazioni**. Per le descrizioni, vedere [Proprietà dettagliate nel log di controllo](detailed-properties-in-the-office-365-audit-log.md).

![Fare clic su Altre informazioni per visualizzare le proprietà dettagliate del record dell'evento del log di controllo](../media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

### <a name="step-3-filter-the-search-results"></a>Passaggio 3: Filtrare i risultati della ricerca

Oltre a ordinare i risultati di una ricerca nel log di controllo, è anche possibile filtrarli. Questa funzionalità è molto utile perché consente di filtrare rapidamente i risultati per un'attività o un utente specifico. È possibile iniziare da una ricerca più ampia e quindi filtrare rapidamente i risultati per visualizzare eventi specifici. È quindi possibile restringere i criteri ed eseguire di nuovo la ricerca affinché venga restituito un set di risultati più piccolo e conciso.

Per filtrare i risultati:

1. Eseguire una ricerca nel log di controllo.

2. Quando vengono visualizzati i risultati, fare clic su **Filtra risultati**.

   Sotto ogni intestazione di colonna vengono visualizzate le caselle delle parole chiave.

3. Fare clic su una delle caselle sotto un'intestazione di colonna e digitare una parola o una frase, a seconda della colonna in cui si sta eseguendo il filtro. I risultati verranno riorganizzati dinamicamente per visualizzare gli eventi corrispondenti al filtro.

   ![Digitare una parola nel filtro per visualizzare gli eventi corrispondenti al filtro](../media/542dc323-a997-402c-934b-cc5e218e50bc.png)

4. Per cancellare un filtro, fare clic su **X** nella casella del filtro oppure fare clic su **Nascondi filtro**.

> [!TIP]
> Per visualizzare gli eventi del log di controllo dell'amministratore di Exchange, digitare un **-**(trattino) nella casella del filtro **Attività**. In questo modo, verranno visualizzati i nomi dei cmdlet, che sono indicati nella colonna **Attività** per gli eventi di amministrazione di Exchange. È anche possibile disporre i nomi dei cmdlet in ordine alfabetico.

### <a name="step-4-export-the-search-results-to-a-file"></a>Passaggio 4: Esportare i risultati della ricerca in un file

È possibile esportare i risultati di una ricerca nel log di controllo in un file con valori delimitati da virgole (CSV) nel computer locale. È possibile aprire il file in Microsoft Excel e usare funzionalità come ricerca, ordinamento, filtro e divisione di una singola colonna (che contiene più proprietà) in più colonne.

1. Eseguire una ricerca nel log di controllo e quindi modificare i criteri di ricerca fino a ottenere i risultati desiderati.

2. Fare clic su **Esporta risultati** e selezionare una delle opzioni seguenti:

   - **Salva i risultati caricati**: Scegliere questa opzione per esportare solo le voci visualizzate in **Risultati** nella pagina **Ricerca log di controllo**. Il file CSV che viene scaricato contiene le stesse colonne e gli stessi dati presenti nella pagina (Data, Utente, Attività, Elemento e Dettagli). Contiene anche una colonna supplementare denominata **Altro** con altre informazioni sulla voce del log di controllo. Visto che si stanno esportando gli stessi risultati caricati (e visualizzabili) nella pagina **Ricerca log di controllo**, verranno esportate al massimo 5,000 voci.

   - **Scarica tutti i risultati**: Scegliere questa opzione per esportare tutte le voci del log di controllo che soddisfano i criteri di ricerca. Per un ampio set di risultati di ricerca, scegliere questa opzione per scaricare tutte le voci del log di controllo oltre ai 5.000 record di controllo che possono essere visualizzati nella pagina **Ricerca log di controllo**. Questa opzione consente di scaricare i dati non elaborati dal log di controllo in un file CSV e include informazioni aggiuntive sulle voci del log di controllo in una colonna denominata **Dati di controllo**. Se si sceglie questa opzione di esportazione potrebbe essere necessario più tempo per scaricare il file, in quanto il file potrebbe essere molto più grande di quello scaricato scegliendo l'altra opzione.

     > [!IMPORTANT]
     > È possibile scaricare al massimo 50.000 voci in un file CSV da una singola ricerca nel log di controllo. Se vengono scaricate 50.000 voci nel file CSV, è probabile che ci siano più di 50.000 eventi che soddisfano i criteri di ricerca. Per eseguire l'esportazione oltre questo limite, provare a usare un intervallo di date per ridurre il numero di voci del log di controllo. Potrebbe essere necessario eseguire più ricerche con intervalli di date più piccoli per esportare più di 50.000 voci.

3. Dopo aver selezionato un'opzione di esportazione, nella parte inferiore della finestra viene visualizzato un messaggio che chiede se aprire il file CSV, salvarlo nella cartella Download o salvarlo in una cartella specifica.

#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>Altre informazioni sull'esportazione e la visualizzazione dei risultati della ricerca nel log di controllo

- Se si scaricano tutti i risultati della ricerca, il file CSV contiene una colonna denominata **Dati di controllo**, che include informazioni aggiuntive su ogni evento. I dati contenuti in questa colonna sono rappresentati da un oggetto JSON contenente più proprietà del record del log di controllo. Ogni coppia *proprietà: valore* nell'oggetto JSON è separata da una virgola. È possibile usare lo strumento di trasformazione JSON nell'editor di Power Query in Excel per dividere la colonna **Dati di controllo** in più colonne, in modo che ogni proprietà dell'oggetto JSON abbia una colonna specifica. In questo modo è possibile ordinare e filtrare una o più di queste proprietà. Per istruzioni dettagliate sull'uso dell'editor di Power Query per trasformare l'oggetto JSON, vedere [Esportare, configurare e visualizzare i record del log di controllo](export-view-audit-log-records.md).

  Dopo avere diviso la colonna **Dati di controllo**, è possibile filtrare la colonna **Operazioni** per visualizzare le proprietà dettagliate per un tipo di attività specifico.

- L'opzione **Scarica tutti i risultati** scarica i dati non elaborati dal log di controllo in un file CSV. Il file contiene nomi di colonne (Data di creazione, ID utente, Operazione, Dati di controllo) diversi rispetto a quelli nel file scaricato selezionando l'opzione **Salva i risultati caricati**. Anche i valori per una stessa attività potrebbero essere diversi nei due diversi file CSV. Ad esempio, l'attività nella colonna **Attività** nel file CSV può avere un valore diverso rispetto al nome descrittivo visualizzato nella colonna **Attività** nella pagina **Ricerca log di controllo**. I due valori potrebbero ad esempio essere MailboxLogin e Utente connesso a cassetta postale.

- Quando si scaricano tutti i risultati di una query di ricerca che contiene eventi di diversi servizi, la colonna **Dati di controllo** nel file CSV contiene proprietà diverse a seconda del servizio in cui è stata eseguita l'azione. Le voci dei log di controllo di Exchange e Azure Ad, ad esempio, contengono una proprietà denominata **ResultStatus** che indica se l'azione è riuscita o meno. Questa proprietà non è inclusa per gli eventi di SharePoint. Analogamente, gli eventi di SharePoint hanno una proprietà che identifica l'URL del sito per le attività correlate a file e cartelle. Per ovviare a questo comportamento, è consigliabile usare ricerche diverse per esportare i risultati per le attività da un unico servizio.

  Per una descrizione delle numerose proprietà elencate nella colonna **Dati di controllo** del file CSV quando si scaricano tutti i risultati, con l'indicazione del servizio a cui si riferiscono, vedere [Proprietà dettagliate nel log di controllo](detailed-properties-in-the-office-365-audit-log.md).

## <a name="audited-activities"></a>Attività controllate

Le tabelle in questa sezione descrivono le attività che vengono controllate in Office 365. È possibile cercare questi eventi eseguendo una ricerca nel log di controllo nel Centro sicurezza e conformità.

Queste tabelle raggruppano le attività correlate o le attività di un determinato servizio. Le tabelle includono il nome descrittivo visualizzato nell'elenco a discesa **Attività** e il nome dell'operazione corrispondente visualizzato nelle informazioni dettagliate di un record di controllo e nel file CSV quando si esportano i risultati della ricerca. Per le descrizioni sulle informazioni dettagliate, vedere [Proprietà dettagliate nel log di controllo](detailed-properties-in-the-office-365-audit-log.md).

Fare clic su uno dei collegamenti seguenti per passare a una tabella specifica.

:::row:::
    :::column:::
        [Attività su file e pagine](#file-and-page-activities)
    :::column-end:::
    :::column:::
        [Attività su cartelle](#folder-activities)
    :::column-end:::
    :::column:::
        [Attività dell'elenco di SharePoint](#sharepoint-list-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di richiesta di accesso e condivisione](#sharing-and-access-request-activities)
    :::column-end:::
    :::column:::
        [Attività di sincronizzazione](#synchronization-activities)
    :::column-end:::
    :::column:::
        [Attività relative alle autorizzazioni del sito](#site-permissions-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di amministrazione siti](#site-administration-activities)
    :::column-end:::
    :::column:::
        [Attività su cassette postali di Exchange](#exchange-mailbox-activities)
    :::column-end:::
    :::column:::
        [Attività di amministrazione utenti](#user-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di amministrazione gruppi di Azure AD](#azure-ad-group-administration-activities)
    :::column-end:::
    :::column:::
        [Attività di amministrazione applicazioni](#application-administration-activities)
    :::column-end:::
    :::column:::
        [Attività di amministrazione ruoli](#role-administration-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di amministrazione directory](#directory-administration-activities)
    :::column-end:::
    :::column:::
        [Attività di eDiscovery](#ediscovery-activities)
    :::column-end:::
    :::column:::
        [Attività di Advanced eDiscovery](#advanced-ediscovery-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di Power BI](#power-bi-activities)
    :::column-end:::
    :::column:::
        [Microsoft Workplace Analytics](#microsoft-workplace-analytics-activities)
    :::column-end:::
    :::column:::
        [Attività di Microsoft Teams](#microsoft-teams-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di Microsoft Teams per il settore sanitario](#microsoft-teams-healthcare-activities)
    :::column-end:::
    :::column:::
        [Attività di Turni di Microsoft Teams](#microsoft-teams-shifts-activities)
    :::column-end:::
    :::column:::
        [Attività di Yammer](#yammer-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di Microsoft Power Automate](#microsoft-power-automate-activities)
    :::column-end:::
    :::column:::
        [Attività di Microsoft Power Apps](#microsoft-power-apps-activities)
    :::column-end:::
    :::column:::
        [Attività di Microsoft Stream](#microsoft-stream-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività di Esplora contenuto](#content-explorer-activities)
    :::column-end:::
    :::column:::
        [Attività in quarantena](#quarantine-activities)
    :::column-end:::
    :::column:::
        [Attività di Microsoft Forms](#microsoft-forms-activities)
    :::column-end:::
:::row-end:::

:::row:::
    :::column:::
        [Attività sulle etichette di riservatezza](#sensitivity-label-activities)
    :::column-end:::
    :::column:::
        [Attività su criteri di conservazione ed etichette di conservazione](#retention-policy-and-retention-label-activities)
    :::column-end:::
    :::column:::
        [Attività di amministrazione di Exchange](#exchange-admin-audit-log)
    :::column-end:::
:::row-end:::

### <a name="file-and-page-activities"></a>Attività su file e pagine

La tabella seguente descrive le attività su file e pagine in SharePoint Online e OneDrive for Business.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|File aperto|FileAccessed|Un utente o un account di sistema esegue l'accesso a un file.|
|(nessuno)|FileAccessedExtended|Evento correlato all’attività "File aperto" (FileAccessed). Un evento FileAccessedExtended viene registrato quando la stessa persona accede in modo continuativo a un file per un periodo prolungato (fino a 3 ore). <br/><br/> Lo scopo della registrazione di eventi FileAccessedExtended è di ridurre il numero di eventi FileAccessed registrati quando si accede a un file in modo continuativo. Ciò consente di ridurre il numero di record FileAccessed per un'azione utente sostanzialmente identica e consente di concentrarsi sull'evento FileAccessed iniziale (e più importante).|
|Etichetta di conservazione modificata per un file|ComplianceSettingChanged|È stata applicata o rimossa dal documento un’etichetta di conservazione. Questo evento viene generato quando un'etichetta di conservazione viene applicata manualmente o automaticamente a un messaggio.|
|Stato del record modificato in bloccato|LockRecord|Lo stato del record di un'etichetta di conservazione che classifica un documento come record è stato bloccato. Ciò significa che non è possibile modificare o eliminare il documento. Solo gli utenti che hanno almeno l'autorizzazione come collaboratori per un sito possono cambiare lo stato del record di un documento.|
|Stato del record modificato in sbloccato|UnlockRecord|Lo stato del record di un'etichetta di conservazione che classifica un documento come record è stato sbloccato. Ciò significa che è possibile modificare o eliminare il documento. Solo gli utenti che hanno almeno l'autorizzazione come collaboratori per un sito possono cambiare lo stato del record di un documento.|
|File archiviato|FileCheckedIn|Un utente archivia un documento estratto da una raccolta documenti.|
|File estratto|FileCheckedOut|Un utente estrae un documento da una raccolta documenti. Gli utenti possono estrarre e modificare i documenti che sono stati condivisi con loro.|
|File copiato|FileCopied|Un utente copia un documento da un sito. Il file copiato può essere salvato in un'altra cartella nel sito.|
|File eliminato|FileDeleted|Un utente elimina un documento da un sito.|
|File eliminato dal Cestino|FileDeletedFirstStageRecycleBin|L'utente elimina un file dal Cestino di un sito.|
|File eliminato dal Cestino di secondo livello|FileDeletedSecondStageRecycleBin|L'utente elimina un file dal Cestino di secondo livello di un sito.|
|File eliminato contrassegnato come record|RecordDelete|Un documento contrassegnato come record è stato eliminato. Un documento viene considerato un record se al documento è applicata un'etichetta di conservazione che contrassegna il contenuto come record.|
|È stata rilevata una mancata corrispondenza della riservatezza del documento|DocumentSensitivityMismatchDetected|Un utente carica un documento in un sito protetto con un'etichetta di riservatezza e il documento ha un'etichetta di riservatezza con priorità più elevata rispetto all'etichetta di riservatezza applicata al sito. Ad esempio, un documento etichettato come Riservato viene caricato in un sito etichettato come Generale.<br/><br/> Questo evento non viene generato se il documento ha un'etichetta di riservatezza con priorità inferiore rispetto all'etichetta di riservatezza applicata al sito. Ad esempio, un documento etichettato come Generale viene caricato in un sito etichettato come Riservato. Per altre informazioni sulla priorità delle etichette di riservatezza, vedere [Priorità delle etichette (l’ordine è rilevante)](sensitivity-labels.md#label-priority-order-matters).|
|Malware rilevato nel file|FileMalwareDetected|Il motore antivirus di SharePoint rileva malware in un file.|
|Estrazione file rimossa|FileCheckOutDiscarded|Un utente elimina (o annulla) l'estrazione di un file. Ciò significa che le modifiche apportate al file dopo l'estrazione vengono eliminate e non salvate nella versione del documento nella raccolta documenti.|
|File scaricato|FileDownloaded|Un utente scarica un documento da un sito.|
|File modificato|FileModified|Un utente o un account di sistema modifica il contenuto o le proprietà di un documento in un sito.|
|(nessuno)|FileModifiedExtended|Evento correlato all’attività "File modificato" (FileModified). Un evento FileModifiedExtended viene registrato quando la stessa persona modifica in modo continuativo un file per un periodo prolungato (fino a 3 ore). <br/><br/> Lo scopo della registrazione di eventi FileModifiedExtended è di ridurre il numero di eventi FileModified registrati quando si modifica un file in modo continuativo. Ciò consente di ridurre il numero di record FileModified per un'azione utente sostanzialmente identica e consente di concentrarsi sull'evento FileModified iniziale (e più importante).|
|File spostato|FileMoved|Un utente sposta un documento dalla posizione corrente in un sito a una nuova posizione.|
|(nessuno)|FilePreviewed|L’utente visualizza in anteprima i file in un sito di SharePoint o OneDrive for Business. Questi eventi si verificano in genere in volumi elevati in base a una singola attività, ad esempio la visualizzazione di una raccolta immagini.|
|Query di ricerca eseguita|SearchQueryPerformed|L’utente o l’account di sistema esegue una ricerca in SharePoint o OneDrive for Business. Alcuni scenari comuni in cui un account del servizio esegue una query di ricerca includono l'applicazione di criteri di conservazione o blocchi di eDiscovery a siti e account di OneDrive e l'applicazione automatica di etichette di conservazione o riservatezza al contenuto del sito.|
|Tutte le versioni secondarie di un file vengono spostate nel Cestino|FileVersionsAllMinorsRecycled|L'utente elimina tutte le versioni secondarie dalla cronologia delle versioni di un file. Le versioni eliminate vengono spostate nel Cestino del sito.|
|Tutte le versioni di un file vengono spostate nel Cestino|FileVersionsAllRecycled|L'utente elimina tutte le versioni dalla cronologia delle versioni di un file. Le versioni eliminate vengono spostate nel Cestino del sito.|
|La versione di un file viene spostata nel Cestino|FileVersionRecycled|L'utente una versione dalla cronologia delle versioni di un file. La versione eliminata viene spostata nel Cestino del sito.|
|File rinominato|FileRenamed|Un utente rinomina un documento in un sito.|
|File ripristinato|FileRestored|Un utente ripristina un documento dal Cestino di un sito.|
|File caricato|FileUploaded|Un utente carica un documento in una cartella in un sito.|
|Pagina visualizzata|PageViewed|Utente visualizza una pagina in un sito, ma non usa un Web browser per visualizzare i file presenti in una raccolta documenti.|
|(nessuno)|PageViewedExtended|Questo evento è correlato all’attività "Pagina visualizzata" (PageViewed). Un evento PageViewedExtended viene registrato quando la stessa persona visualizza in modo continuativo una pagina Web per un periodo prolungato (fino a 3 ore). <br/><br/> Lo scopo della registrazione di eventi PageViewedExtended è di ridurre il numero di eventi PageViewed registrati quando una pagina viene visualizzata in modo continuativo. Ciò consente di ridurre il numero di record PageViewed per un'azione utente sostanzialmente identica e consente di concentrarsi sull'evento PageViewed iniziale (e più importante).|
|Visualizzazione segnalata dal client|ClientViewSignaled|Il client di un utente, ad esempio un sito Web o un'app per dispositivi mobili, ha segnalato che la pagina indicata viene visualizzata dall'utente. Questa attività viene spesso registrata in seguito a un evento PagePrefetched per una pagina. <br/><br/>**Nota**: Poiché gli eventi ClientViewSignaled sono segnalati dal client, anziché dal server, è possibile che l’evento non sia registrato dal server e quindi non venga visualizzato nel log di controllo. È anche possibile che le informazioni nel record di controllo non siano attendibili. Tuttavia, poiché l'identità dell'utente viene convalidata dal token usato per creare il segnale, l'identità dell'utente riportata nel record di controllo corrispondente è accurata. |
|(nessuno)|PagePrefetched|Il client di un utente, ad esempio un sito Web o un'app per dispositivi mobili, ha richiesto un miglioramento delle prestazioni per la pagina indicata, quando l’utente esplora tale pagina. Questo evento viene registrato per indicare che il contenuto della pagina è stato reso disponibile al client dell'utente. Questo evento non indica in modo definitivo se l'utente ha esplorato la pagina. <br/><br/> Quando il contenuto della pagina viene visualizzato dal client (come da richiesta dell’utente), viene generato un evento ClientViewSignaled. Non tutti i client supportano l'indicazione di prelettura. Per questo alcune attività di prelettura potrebbero essere registrate come eventi PageViewed.|
||||

#### <a name="frequently-asked-questions-about-fileaccessed-and-filepreviewed-events"></a>Domande frequenti sugli eventi FileAccessed e FilePreviewed

**È possibile che attività non utente attivino record di controllo FilePreviewed che contengono un agente utente come "OneDriveMpc-Transform_Thumbnail"?**

Non siamo a conoscenza di scenari in cui attività non utente generano eventi di questo tipo. Attività utente come l'apertura di una scheda del profilo utente (facendo clic sul nome o sull'indirizzo di posta elettronica in un messaggio in Outlook sul web) genererebbero eventi simili.

**Le chiamate a OneDriveMpc-Transform_Thumbnail vengono sempre attivate intenzionalmente dall'utente?**

No. Tuttavia, eventi simili possono essere registrati in conseguenza della prelettura del browser.

**Se viene visualizzato un evento FilePreviewed derivante da un indirizzo IP registrato Microsoft, significa che l'anteprima è stata visualizzata sullo schermo del dispositivo dell'utente?**

No. L'evento potrebbe essere stato registrato in conseguenza della prelettura del browser.

**Esistono scenari in cui un utente che visualizza l'anteprima di un documento genera eventi FileAccessed?**

Sia gli eventi FilePreviewed che FileAccessed indicano che la chiamata di un utente ha generato una lettura del file (o una lettura di un rendering di anteprima del file). Anche se questi eventi dovrebbero essere allineati all’anteprima ovvero all’intento di accesso, la distinzione dell’evento non è una garanzia dell'intento dell'utente.

#### <a name="the-appsharepoint-user-in-audit-records"></a>Utente app\@sharepoint nei record di controllo

Nei record di controllo per alcune attività dei file (e altre attività correlate a SharePoint), l'utente che ha eseguito l'attività, identificato nei campi Utente e ID utente, può essere indicato come app@sharepoint. Ciò significa che l'utente che ha eseguito l'attività era un'applicazione. In questo caso, l'applicazione aveva le autorizzazioni di SharePoint per eseguire azioni a livello di organizzazione, ad esempio cercare un sito di SharePoint o un account di OneDrive, per conto di un utente, di un amministratore o di un servizio. Questo processo in cui sono assegnate autorizzazioni a un'applicazione è definito accesso *solo in-app di SharePoint*. Ciò indica che l'autenticazione presentata a SharePoint per eseguire un'azione è stata eseguita da un'applicazione, anziché da un utente. Questo è il motivo per cui app@sharepoint viene identificato come utente in alcuni record di controllo. Per altre informazioni, vedere [Concedere l'accesso solo in-app di SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/security-apponly-azureacs).

Ad esempio, app@sharepoint viene spesso identificato come utente per gli eventi "Query di ricerca eseguita” e “File aperto”. Il motivo è che un'applicazione con accesso di tipo solo in-app di SharePoint nell'organizzazione esegue query di ricerca e accede ai file durante l'applicazione di criteri di conservazione a siti e account di OneDrive.

Ecco alcuni altri scenari in cui è possibile identificare app@sharepoint in un record di controllo come utente che ha eseguito un'attività:

- Gruppi di Microsoft 365. Quando un utente o un amministratore crea un nuovo gruppo, vengono generati record di controllo per la creazione di una raccolta siti, l'aggiornamento di elenchi e l'aggiunta di membri a un gruppo di SharePoint. Queste attività vengono eseguite da un'applicazione per conto dell'utente che ha creato il gruppo.

- Microsoft Teams. Analogamente a Gruppi di Microsoft 365, vengono generati record di controllo per la creazione di una raccolta siti, l'aggiornamento di elenchi e l'aggiunta di membri a un gruppo di SharePoint quando si crea un team.

- Funzionalità di conformità. Quando un amministratore implementa funzionalità di conformità, come i criteri di conservazione, i blocchi di eDiscovery e l'applicazione automatica delle etichette di sensitività.

In questi e altri scenari si noterà anche che più record di controllo con app@sharepoint indicato come utente sono stati creati in un breve intervallo di tempo, spesso in pochi secondi. Ciò indica anche che probabilmente tali record sono stati attivati dalla stessa attività avviata dall'utente. Inoltre, i campi ApplicationDisplayName e EventData nel record di controllo consentono di identificare lo scenario o l'applicazione che ha generato l'evento.

### <a name="folder-activities"></a>Attività su cartelle

La tabella seguente descrive le attività su cartelle in SharePoint Online e OneDrive for Business. Come descritto in precedenza, i record di controllo per alcune attività di SharePoint indicheranno che l'utente app@sharepoint ha eseguito l'attività per conto dell'utente o dell'amministratore che ha avviato l'attività. Per altre informazioni, vedere [L'utente app\@sharepoint nei record di controllo](#the-appsharepoint-user-in-audit-records).

|Nome descrittivo|Operazione|Descrizione|
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

La tabella seguente descrive le attività in cui gli utenti interagiscono con elenchi e voci di elenco in SharePoint Online. Come descritto in precedenza, i record di controllo per alcune attività di SharePoint indicheranno che l'utente app@sharepoint ha eseguito l'attività per conto dell'utente o dell'amministratore che ha avviato l'attività. Per altre informazioni, vedere [L'utente app\@sharepoint nei record di controllo](#the-appsharepoint-user-in-audit-records).

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Elenco creato|ListCreated|Un utente ha creato un elenco SharePoint.|
|Colonna elenco creata|ListColumnCreated|Un utente ha creato una colonna elenco di SharePoint. Una colonna elenco è una colonna associata a uno o più elenchi SharePoint.|
|Tipo di contenuto elenco creato|ListContentTypeCreated|Un utente ha creato un tipo di contenuto elenco. Un tipo di contenuto elenco è un tipo di contenuto associato a uno o più elenchi SharePoint.|
|Elemento elenco creato|ListItemCreated|Un utente ha creato un elemento in un elenco di SharePoint esistente.|
|Colonna sito creata|SiteColumnCreated|Un utente ha creato una colonna del sito di SharePoint. Una colonna del sito è una colonna non associata a un elenco. Una colonna del sito è anche una struttura di metadati che può essere usata da qualsiasi elenco in un determinato Web.|
|Tipo di contenuto del sito creato|ContentType del sito creato|Un utente ha creato un tipo di contenuto del sito. Un tipo di contenuto del sito è un tipo di contenuto associato al sito padre.|
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

La tabella seguente descrive le attività dell'utente di richiesta di accesso e condivisione in SharePoint Online e OneDrive for Business. Per gli eventi di condivisione, la colonna **Dettagli** in **Risultati** identifica il nome dell'utente o del gruppo con cui l'elemento è stato condiviso e indica se l'utente o il gruppo è un membro o un guest nell'organizzazione. Per altre informazioni, vedere [Usare il controllo della condivisione nel log di controllo](use-sharing-auditing.md).

> [!NOTE]
> Gli utenti possono essere  *membri*  o  *guest*  in base alla proprietà UserType dell'oggetto utente. Un membro è in genere un dipendente, mentre un guest è in genere un collaboratore esterno all'organizzazione. Quando un utente accetta un invito alla condivisione (e non fa già parte dell'organizzazione), viene creato un account guest per tale utente nella directory dell'organizzazione. Dopo che l'utente guest ha ottenuto un account nella directory, le risorse possono essere condivise direttamente con lui, senza che sia necessario un invito.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|È stato aggiunto un livello di autorizzazione alla raccolta siti|PermissionLevelAdded|Un livello di autorizzazione è stato aggiunto a una raccolta siti.|
|Richiesta di accesso approvata|AccessRequestAccepted|Una richiesta di accesso a un sito, una cartella o un documento è stata accettata e all'utente richiedente è stato concesso l'accesso.|
|Invito alla condivisione accettato|SharingInvitationAccepted|Un utente (membro o guest) ha accettato un invito alla condivisione e ha ottenuto l'accesso a una risorsa. Questo evento include informazioni sull'utente che è stato invitato e sull'indirizzo di posta elettronica usato per accettare l'invito (i due elementi potrebbero essere diversi). Questa attività è spesso accompagnata da un secondo evento che descrive come è stato concesso all'utente l'accesso alla risorsa, ad esempio aggiungendo l'utente a un gruppo che ha accesso alla risorsa. |
|Invito alla condivisione bloccato|SharingInvitationBlocked|Un invito alla condivisione inviato da un utente dell'organizzazione viene bloccato da criteri di condivisione esterna che consentono o impediscono la condivisione esterna in base al dominio dell'utente di destinazione. In questo caso, l'invito alla condivisione è stato bloccato perché: <br/> Il dominio dell'utente di destinazione non è incluso nell'elenco dei domini consentiti. <br/> Oppure <br/> Il dominio dell'utente di destinazione è incluso nell'elenco dei domini bloccati. <br/> Per altre informazioni su come consentire o bloccare la condivisione esterna in base ai domini, vedere [Condivisione di domini con restrizioni in SharePoint Online e OneDrive for Business](https://docs.microsoft.com/sharepoint/restricted-domains-sharing).|
|Richiesta di accesso creata|AccessRequestCreated|Un utente richiede l'accesso a un sito, una cartella o un documento per il quale non ha le autorizzazioni.|
|Creato un collegamento condivisibile nell'organizzazione |CompanyLinkCreated|Un utente ha creato un collegamento a livello aziendale a una risorsa. I collegamenti a livello aziendale possono essere usati solo dai membri dell'organizzazione. Non possono essere usati dai guest.|
|Collegamento anonimo creato|AnonymousLinkCreated|Un utente ha creato un collegamento anonimo a una risorsa. Chiunque usi questo collegamento può accedere alla risorsa senza necessità di autenticazione.|
|Collegamento sicuro creato|SecureLinkCreated|È stato creato un collegamento di condivisione sicuro per questo elemento.|
|Invito alla condivisione creato|SharingInvitationCreated|Un utente ha condiviso una risorsa in SharePoint Online o OneDrive for Business con un utente che non fa parte della directory dell'organizzazione.|
|Collegamento sicuro eliminato|SecureLinkDeleted|È stato eliminato un collegamento di condivisione sicuro.|
|Richiesta di accesso rifiutata |AccessRequestDenied|Una richiesta di accesso a un sito, una cartella o un documento è stata negata.|
|Rimosso un collegamento condivisibile nell'organizzazione|CompanyLinkRemoved|Un utente ha rimosso un collegamento a livello aziendale a una risorsa. Il collegamento non può più essere usato per accedere alla risorsa.|
|Rimosso un collegamento anonimo|AnonymousLinkRemoved|Un utente ha rimosso un collegamento anonimo a una risorsa. Il collegamento non può più essere usato per accedere alla risorsa.|
|File, cartella o sito condiviso|SharingSet|Un utente (membro o guest) ha condiviso un file, una cartella o un sito di SharePoint o OneDrive for Business con un altro utente nella directory dell'organizzazione. Il valore nella colonna **Dettagli** per questa attività identifica il nome dell'utente con cui la risorsa è stata condivisa e indica se l'utente è un membro o un guest. <br/><br/> Questa attività è spesso accompagnata da un secondo evento che descrive come è stato concesso all'utente l'accesso alla risorsa. Ad esempio aggiungendo l'utente a un gruppo che ha accesso alla risorsa.|
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

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Computer autorizzato a sincronizzare i file|ManagedSyncClientAllowed|L'utente ha correttamente stabilito una relazione di sincronizzazione con un sito. La relazione di sincronizzazione è riuscita perché il computer dell'utente è membro di un dominio che è stato aggiunto all'elenco di domini (il cosiddetto *elenco Destinatari attendibili*) che possono accedere alle raccolte documenti dell'organizzazione. <br/><br/> Per altre informazioni su questa funzionalità, vedere [Usare i cmdlet di Windows PowerShell per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco Destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).|
|Computer non autorizzato a sincronizzare i file|UnmanagedSyncClientBlocked|L'utente prova a stabilire una relazione di sincronizzazione con un sito da un computer che non è membro del dominio dell'organizzazione o è membro di un dominio che non è stato aggiunto all'elenco dei domini (il cosiddetto *elenco Destinatari attendibili*) che possono accedere alle raccolte documenti dell'organizzazione. La relazione di sincronizzazione non è consentita e al computer dell'utente viene impedito di sincronizzare, scaricare o caricare file in una raccolta documenti. <br/><br/> Per informazioni su questa funzionalità, vedere [Usare i cmdlet di Windows PowerShell per abilitare la sincronizzazione di OneDrive per i domini presenti nell'elenco Destinatari attendibili](https://go.microsoft.com/fwlink/p/?LinkID=534609).|
|File scaricati nel computer|FileSyncDownloadedFull|Un utente stabilisce una relazione di sincronizzazione e scarica i file per la prima volta nel suo computer da una raccolta documenti.|
|Modifiche ai file scaricate nel computer|FileSyncDownloadedPartial |Un utente scarica le modifiche ai file da una raccolta documenti. Questa azione indica che le modifiche apportate ai file nella raccolta documenti sono state scaricate nel computer dell'utente. Sono state scaricate solo le modifiche perché la raccolta documenti è stata scaricata dall'utente in precedenza (come indicato dall'azione **File scaricati nel computer**).|
|File caricati nella raccolta documenti|FileSyncUploadedFull|Un utente stabilisce una relazione di sincronizzazione e carica i file per la prima volta dal suo computer in una raccolta documenti.|
|Modifiche ai file caricate nella raccolta documenti|FileSyncUploadedPartial|Un utente carica le modifiche ai file in una raccolta documenti. Questo evento indica che le modifiche apportate alla versione locale di un file di una raccolta documenti sono state caricate nella raccolta documenti. Vengono caricate solo le modifiche perché i file sono stati caricati dall'utente in precedenza (come indicato dall'azione **File caricati nella raccolta documenti**).|
||||

### <a name="site-permissions-activities"></a>Attività relative alle autorizzazioni del sito

La tabella seguente elenca gli eventi correlati all’assegnazione di autorizzazioni in SharePoint e all’utilizzo di gruppi per concedere e revocare l’accesso ai siti. Come descritto in precedenza, i record di controllo per alcune attività di SharePoint indicheranno che l'utente app@sharepoint ha eseguito l'attività per conto dell'utente o dell'amministratore che ha avviato l'attività. Per altre informazioni, vedere [L'utente app\@sharepoint nei record di controllo](#the-appsharepoint-user-in-audit-records).

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Amministratore raccolta siti aggiunto|SiteCollectionAdminAdded|Un proprietario o un amministratore della raccolta siti aggiunge una persona come amministratore della raccolta siti per un sito. Gli amministratori della raccolta siti hanno autorizzazioni di controllo completo per la raccolta siti e tutti i siti secondari. Questa attività viene registrata anche quando un amministratore concede a se stesso l'accesso all'account OneDrive di un utente, modificando il profilo utente nell'interfaccia di amministrazione di SharePoint o [usando l'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data).|
|Utente o gruppo aggiunto al gruppo di SharePoint|AddedToGroup|Un utente ha aggiunto un membro o un guest a un gruppo di SharePoint. Questa operazione può essere stata intenzionale oppure è il risultato di un'altra azione, ad esempio un evento di condivisione.|
|Ereditarietà dei livelli di autorizzazione interrotta|PermissionLevelsInheritanceBroken|Un elemento è stato modificato in modo che non erediti più i livelli di autorizzazione dal relativo padre.|
|L'ereditarietà di condivisione è stata interrotta|SharingInheritanceBroken|Un elemento è stato modificato in modo che non erediti più le autorizzazioni di condivisione dal relativo padre.|
|Gruppo creato|GroupAdded|Un proprietario o un amministratore del sito crea un gruppo per un sito oppure esegue un'attività che comporta la creazione di un gruppo. Ad esempio, la prima volta che un utente crea un collegamento per condividere un file, viene aggiunto un gruppo di sistema al sito di OneDrive for Business dell'utente. Questo evento può anche risultare dalla creazione, da parte di un utente, di un collegamento con autorizzazioni di modifica per un file condiviso.|
|Gruppo eliminato|GroupRemoved|Un utente elimina un gruppo da un sito.|
|Impostazioni richieste di accesso modificate|WebRequestAccessModified|Le impostazioni richieste di accesso sono state modificate in un sito.|
|Impostazione "I membri possono condividere" modificata|WebMembersCanShareModified|L'impostazione **I membri possono condividere** è stata modificata in un sito.|
|È stato modificato un livello di autorizzazione in una raccolta siti|PermissionLevelModified|Un livello di autorizzazione è stato modificato in una raccolta siti.|
|Autorizzazioni sito modificate|SitePermissionsModified|Un proprietario o un amministratore del sito (o un account di sistema) modifica il livello di autorizzazione assegnato a un gruppo in un sito. Questa azione viene registrata anche se vengono rimosse tutte le autorizzazioni da un gruppo.<br/><br/> **NOTA**: Questa operazione è deprecata in SharePoint Online. Per trovare gli eventi correlati, è possibile cercare altre attività relative alle autorizzazioni, ad esempio **Amministratore raccolta siti aggiunto**, **Utente o gruppo aggiunto a gruppo di SharePoint**, **Utente autorizzato a creare gruppi**, **Gruppo creato** e **Gruppo eliminato.**|
|Livello di autorizzazione rimosso dalla raccolta siti|PermissionLevelRemoved|Un livello di autorizzazione è stato rimosso da una raccolta siti.|
|Amministratore raccolta siti rimosso|SiteCollectionAdminRemoved|Un proprietario o un amministratore della raccolta siti rimuove una persona come amministratore della raccolta siti per un sito. Questa attività viene registrata anche quando un amministratore rimuove se stesso dall’elenco degli amministratori della raccolta siti per l'account OneDrive di un utente, modificando il profilo utente nell'interfaccia di amministrazione di SharePoint. Perché questa attività sia restituita nei risultati di ricerca nel log di controllo, è necessario fare una ricerca di tutte le attività.|
|Utente o gruppo rimosso dal gruppo di SharePoint|RemovedFromGroup|Un utente ha rimosso un membro o un guest da un gruppo di SharePoint. Questa operazione può essere stata intenzionale oppure è il risultato di un'altra azione, ad esempio un evento di annullamento della condivisione.|
|Richiesta di autorizzazioni come amministratore del sito|SiteAdminChangeRequest|L'utente richiede di essere aggiunto come amministratore di una raccolta siti, che ha autorizzazioni di controllo completo per la raccolta siti e per tutti i siti secondari.|
|Ereditarietà di condivisione ripristinata|SharingInheritanceReset|È stata apportata una modifica che consente a un elemento di ereditare le autorizzazioni di condivisione dal relativo padre.|
|Gruppo aggiornato|GroupUpdated|Un proprietario o un amministratore del sito modifica le impostazioni di un gruppo per un sito. Questo può includere la modifica del nome del gruppo, degli utenti autorizzati a visualizzare o modificare l'appartenenza al gruppo e della modalità di gestione delle richieste di appartenenza.|
||||

### <a name="site-administration-activities"></a>Attività di amministrazione siti

La tabella seguente elenca gli eventi generati da attività di amministrazione del sito in SharePoint Online. Come descritto in precedenza, i record di controllo per alcune attività di SharePoint indicheranno che l'utente app@sharepoint ha eseguito l'attività per conto dell'utente o dell'amministratore che ha avviato l'attività. Per altre informazioni, vedere [L'utente app\@sharepoint nei record di controllo](#the-appsharepoint-user-in-audit-records).

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Aggiunta la posizione dei dati consentita|AllowedDataLocationAdded|Un amministratore globale o di SharePoint ha aggiunto una posizione di dati consentita in un ambiente multi-geografico.|
|Agente utente esente aggiunto|ExemptUserAgentSet|L'amministratore di SharePoint o l'amministratore globale aggiunge un agente utente all'elenco di agenti utente esenti nell'interfaccia di amministrazione di SharePoint.|
|Amministratore dell'area geografica aggiunto|GeoAdminAdded|Un amministratore globale o di SharePoint ha aggiunto un utente come amministratore geografico di una posizione.|
|Utente autorizzato a creare gruppi|AllowGroupCreationSet|Un proprietario o un amministratore del sito aggiunge un livello di autorizzazione a un sito che consente a un utente a cui viene assegnata tale autorizzazione di creare un gruppo per tale sito.|
|È stato annullato lo spostamento geografico di un sito|SiteGeoMoveCancelled|Un amministratore di SharePoint o globale annulla lo spostamento geografico di un sito di SharePoint o OneDrive. La funzionalità Multi-Geo consente a un'organizzazione di utilizzare più aree geografiche di centri dati, note anche come geo. Per ulteriori informazioni, vedere [Multi-Geo Capabilities in OneDrive e SharePoint Online](https://go.microsoft.com/fwlink/?linkid=860840).|
|Criterio di condivisione cambiato|SharingPolicyChanged|Un amministratore di SharePoint o globale ha modificato un criterio di condivisione di SharePoint tramite il portale di amministrazione di Microsoft 365, il portale di amministrazione di SharePoint oppure SharePoint Online Management Shell. Qualsiasi modifica apportata alle impostazioni del criterio di condivisione dell'organizzazione verrà registrata. I criteri cambiati sono identificati nel campo **ModifiedProperties** nelle proprietà dettagliate del record dell'evento.|
|Criteri di accesso ai dispositivi modificati|DeviceAccessPolicyChanged|Un amministratore di SharePoint o globale ha cambiato i criteri dei dispositivi non gestiti per l'organizzazione. Questo criterio controlla l'accesso a SharePoint, OneDrive e Microsoft 365 da dispositivi che non fanno parte dell'organizzazione. La configurazione di questo criterio richiede un abbonamento Enterprise Mobility + Security. Per altre informazioni, vedere [Controllare l'accesso da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).|
|Agenti utente esenti cambiati|CustomizeExemptUsers|Un amministratore di SharePoint o globale ha personalizzato l'elenco di agenti utente esenti nell'interfaccia di amministrazione di SharePoint. È possibile specificare quali agenti utente esentare dalla ricezione di un'intera pagina Web da indicizzare. Questo significa che quando un agente utente specificato come esente riscontra un modulo di InfoPath, tale modulo verrà restituito come file XML invece che come intera pagina Web. In questo modo, l'indicizzazione dei moduli di InfoPath sarà più veloce.|
|Criteri di accesso alla rete modificati|NetworkAccessPolicyChanged|Un amministratore di SharePoint o globale ha cambiato i criteri di accesso basati sulla posizione, denominati anche limite di rete attendibile, nell'interfaccia di amministrazione di SharePoint oppure usando SharePoint Online PowerShell. Questi criteri controllano chi può accedere alle risorse di SharePoint e OneDrive nell'organizzazione in base a intervalli di indirizzi IP specificati dall'utente. Per altre informazioni, vedere [Controllare l'accesso ai dati di SharePoint Online e OneDrive in base a determinati percorsi di rete](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location).|
|Spostamento geografico di un sito completato|SiteGeoMoveCompleted|È stato completato lo spostamento geografico di un sito programmato da un amministratore globale dell’organizzazione. La funzionalità Multi-Geo consente a un'organizzazione di utilizzare più aree geografiche di centri dati, note anche come geo. Per ulteriori informazioni, vedere [Multi-Geo Capabilities in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).|
|Connessione Inviato a creata|SendToConnectionAdded|L'amministratore di SharePoint o globale crea una nuova connessione Invia a nella pagina di gestione dei record dell'interfaccia di amministrazione di SharePoint. Una connessione Invia a specifica le impostazioni per un archivio documenti o un centro record. Quando si crea una connessione di questo tipo, un Content Organizer può inviare documenti alla posizione specificata.|
|Raccolta siti creata|SiteCollectionCreated|Un amministratore SharePoint o globale crea una raccolta siti nell'organizzazione di SharePoint Online o un utente esegue il provisioning del sito di OneDrive for Business.|
|Sito hub orfano eliminato|HubSiteOrphanHubDeleted|Un amministratore di SharePoint o globale ha eliminato un sito hub orfano, ossia un sito hub a cui non sono associati siti. Un hub orfano è generato probabilmente dall’eliminazione del sito hub originale.|
|Connessione Inviato a eliminata|SendToConnectionRemoved|L'amministratore SharePoint o globale elimina una nuova connessione Invia a nella pagina Gestione record nell'interfaccia di amministrazione di SharePoint.|
|Sito eliminato|SiteDeleted|L'amministratore del sito elimina un sito.|
|Anteprima documento abilitata|PreviewModeEnabledSet|Un amministratore del sito abilita l'anteprima dei documenti per un sito.|
|Flusso di lavoro legacy abilitato|LegacyWorkflowEnabledSet|Un proprietario o un amministratore del sito aggiunge il tipo di contenuto Attività flusso di lavoro di SharePoint 2013 al sito. Gli amministratori globali possono anche abilitare i flussi di lavoro per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.|
|Office su richiesta abilitato|OfficeOnDemandSet|Un amministratore del sito abilita Office su richiesta, che consente agli utenti di accedere all'ultima versione delle applicazioni desktop di Office. Office su richiesta viene abilitato nell'interfaccia di amministrazione di SharePoint e richiede un abbonamento a Microsoft 365 che include le applicazioni di Office complete installate.|
|Origine dei risultati abilitata per ricerche in Persone|PeopleResultsScopeSet|Un amministratore del sito crea l'origine dei risultati per le ricerche in Persone per un sito.|
|Feed RSS abilitati|NewsFeedEnabledSet|Un proprietario o un amministratore del sito abilita i feed RSS per un sito. Gli amministratori globali possono abilitare i feed RSS per l'intera organizzazione nell'interfaccia di amministrazione di SharePoint.|
|Sito unito al sito hub|HubSiteJoined|Il proprietario di un sito associa il sito a un sito hub.|
|Sito hub registrato|HubSiteRegistered|Un amministratore di SharePoint o globale crea un sito hub. Come conseguenza il sito è registrato come un sito hub.|
|Rimossa la posizione dei dati consentita|AllowedDataLocationDeleted|Un amministratore SharePoint o globale ha rimosso una posizione di dati consentita in un ambiente multi-geografico.|
|Amministratore dell'area geografica rimosso|GeoAdminDeleted|Un amministratore SharePoint o globale ha aggiunto un utente come amministratore geografico di una posizione.|
|Sito rinominato|SiteRenamed|Un proprietario o un amministratore del sito rinomina un sito.|
|Spostamento geografico di un sito pianificato|SiteGeoMoveScheduled|Un amministratore di SharePoint o globale programma lo spostamento geografico di un sito di SharePoint o OneDrive. La funzionalità Multi-Geo consente a un'organizzazione di utilizzare più aree geografiche di centri dati, note anche come geo. Per ulteriori informazioni, vedere [Multi-Geo Capabilities in OneDrive e SharePoint Online in Office 365](https://go.microsoft.com/fwlink/?linkid=860840).|
|Sito host impostato|HostSiteSet|Un amministratore di SharePoint o globale cambia il sito designato per ospitare siti di OneDrive for Business o personali.|
|Impostare una quota di archiviazione per una posizione geografica|GeoQuotaAllocated|Un amministratore SharePoint o globale ha configurato una quota di archiviazione per una posizione geografica in un ambiente multi-geografico.|
|Sito separato dal sito hub|HubSiteUnjoined|Il proprietario di un sito annulla l'associazione del sito a un sito hub.|
|Registrazione sito hub annullata|HubSiteUnregistered|Un amministratore di SharePoint o globale annulla la registrazione di un sito come sito hub. Quando viene annullata la registrazione di un sito come sito hub, questo non funziona più come sito hub.|
||||

### <a name="exchange-mailbox-activities"></a>Attività su cassette postali di Exchange

La tabella seguente elenca le attività che è possibile registrare con la registrazione di controllo delle cassette postali. Le attività su cassetta postale eseguite dal proprietario della cassetta postale, da un utente delegato o da un amministratore vengono registrate automaticamente nel log di controllo per un massimo di 90 giorni. Un amministratore può disabilitare la registrazione di controllo delle cassette postali per tutti gli utenti dell’organizzazione. In questo caso per nessun utente vengono registrate attività su cassetta postale. Per altre informazioni, vedere [Gestire controllo delle cassette postali](enable-mailbox-auditing.md).

 È anche possibile cercare le attività su cassette postali utilizzando il cmdlet [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) in PowerShell per Exchange Online.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Elementi delle cassette postali accessibili|MailItemsAccessed|Sono stati letti o aperti messaggi in una cassetta postale. I record di controllo per questa attività vengono attivati in uno dei due modi seguenti: quando un client di posta elettronica, come Outlook, esegue un'operazione di binding sui messaggi o quando i protocolli di posta elettronica, come Exchange ActiveSync o IMAP, sincronizzano elementi in una cartella di posta elettronica. Questa attività viene registrata solo per gli utenti con una licenza di Office 365 o Microsoft 365 E5. L'analisi dei record di controllo per questa attività è utile quando si esamina un account di posta elettronica compromesso. Per altre informazioni, vedere la sezione "Accesso a eventi cruciali per le indagini" in [Controllo avanzato](advanced-audit.md#access-to-crucial-events-for-investigations). |
|Aggiunte autorizzazioni delegate per le cassette postali|AddMailboxPermissions|Un amministratore ha assegnato l'autorizzazione FullAccess per la cassetta postale a un utente (noto come delegato) alla cassetta postale di un'altra persona. L'autorizzazione FullAccess consente al delegato di aprire la cassetta postale di un'altra persona e di leggere e gestire il contenuto della cassetta postale.|
|Aggiunto o rimosso un utente con accesso delegato alla cartella del calendario|UpdateCalendarDelegation|Un utente è stato aggiunto o rimosso come delegato al calendario della cassetta postale di un altro utente. La delega per il calendario assegna a un’altra persona nella stessa organizzazione le autorizzazioni per gestire il calendario del proprietario della cassetta postale.|
|Aggiunte autorizzazioni alla cartella|AddFolderPermissions|Un'autorizzazione per una cartella è stata aggiunta. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|
|Messaggi copiati in un'altra cartella|Copy|Un messaggio è stato copiato in un'altra cartella.|
|Elemento della cassetta postale creato|Creare|È stato creato un elemento nella cartella Calendario, Contatti, Note o Attività della cassetta postale. Ad esempio è stata creata una nuova convocazione riunione. La creazione, l'invio o la ricezione di un messaggio non viene controllata, così come la creazione di una cartella della cassetta postale.|
|Creata una nuova regola della posta in arrivo in Outlook Web App|New-InboxRule|Il proprietario di una cassetta postale o un altro utente con accesso alla cassetta postale ha creato una regola di posta in arrivo in Outlook Web App.|
|Messaggi eliminati dalla cartella Posta eliminata|SoftDelete|Un messaggio è stato eliminato definitivamente oppure è stato eliminato dalla cartella Posta eliminata. Questi elementi vengono spostati nella cartella Elementi ripristinabili. I messaggi vengono spostati nella cartella Elementi ripristinabili anche quando un utente li seleziona e preme **MAIUSC+CANC**.|
|Messaggio con etichetta come record|ApplyRecordLabel|Un messaggio è stato classificato con record. Questa situazione si verifica quando un'etichetta di conservazione che classifica il contenuto come record viene applicata manualmente o automaticamente a un messaggio.|
|Messaggi spostati in un'altra cartella|Move|Un messaggio è stato spostato in un'altra cartella.|
|Messaggi spostati nella cartella Posta eliminata|MoveToDeletedItems|Un messaggio è stato eliminato e spostato nella cartella Posta eliminata.|
|Autorizzazione cartella modificata|UpdateFolderPermissions|Un'autorizzazione per una cartella è stata cambiata. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|
|Regola della posta in arrivo modificata da Outlook Web App|Set-InboxRule|Il proprietario di una cassetta postale o un altro utente con accesso alla cassetta postale ha modificato una regola di posta in arrivo in Outlook Web App.|
|Messaggi ripuliti dalla cassetta postale|HardDelete|Un messaggio è stato eliminato dalla cartella Elementi ripristinabili (eliminato in modo definitivo dalla cassetta postale).|
|Rimosse autorizzazioni delegate per le cassette postali|Remove-MailboxPermission|Un amministratore ha rimosso l'autorizzazione FullAccess (che era assegnata a un delegato) dalla cassetta postale di una persona. Dopo aver rimosso l'autorizzazione FullAccess, il delegato non riesce ad aprire la cassetta postale dell'altra persona o ad accedere a qualsiasi suo contenuto.|
|Autorizzazioni rimosse dalla cartella|RemoveFolderPermissions|Un'autorizzazione per una cartella è stata rimossa. Le autorizzazioni per le cartelle determinano quali utenti dell'organizzazione possono accedere alle cartelle di una cassetta postale e ai messaggi che contengono.|
|Messaggio inviato|Inviare|Un messaggio è stato inviato, inoltrato o ha ricevuto risposta. Questa attività viene registrata solo per gli utenti con una licenza di Office 365 o Microsoft 365 E5. Per altre informazioni, vedere la sezione "Accesso a eventi cruciali per le indagini" in [Controllo avanzato](advanced-audit.md#access-to-crucial-events-for-investigations).|
|Messaggio inviato con autorizzazioni Invia come|SendAs|Messaggio inviato utilizzando l'autorizzazione SendAs. Ciò significa che un altro utente ha inviato il messaggio come se provenisse dal proprietario della cassetta postale.|
|Messaggio inviato con autorizzazioni Invia per conto di|SendOnBehalf|Messaggio inviato utilizzando l'autorizzazione SendOnBehalf. Ciò significa che un altro utente ha inviato il messaggio per conto del proprietario della cassetta postale. Il messaggio indica al destinatario la persona per conto della quale è stato inviato il messaggio e l’utente che ha effettivamente inviato il messaggio.|
|Regole della posta in arrivo aggiornate dal client di Outlook|UpdateInboxRules|Il proprietario di una cassetta postale o un altro utente con accesso alla cassetta postale ha modificato una regola di posta in arrivo nel client di Outlook.|
|Messaggio aggiornato|Update|Un messaggio o le relative proprietà sono state modificate.|
|Utente connesso a cassetta postale|MailboxLogin|Accesso effettuato dall'utente alla propria cassetta postale.|
|Messaggio con etichetta come record||Un utente ha applicato un'etichetta di conservazione a un messaggio di posta elettronica e tale etichetta è configurata in modo da contrassegnare l'elemento come record. |
||||

### <a name="user-administration-activities"></a>Attività di amministrazione utenti

La tabella seguente elenca le attività di amministrazione utenti registrate quando un amministratore aggiunge o modifica un account utente usando l'interfaccia di amministrazione di Microsoft 365 o il portale di gestione di Azure.

|Attività|Operazione|Descrizione|
|:-----|:-----|:-----|
|Utente aggiunto|Aggiungi utente|È stato creato un account utente.|
|Licenza utente modificata|Modifica della licenza utente|La licenza assegnata a un utente è stata modificata. Per visualizzare le licenze modificate, vedere l'azione **Utente aggiornato** corrispondente.|
|Password utente cambiata|Modifica della password utente|Un utente cambia la propria password. La reimpostazione della password self-service deve essere abilitata, per tutti gli utenti o alcuni selezionati, nell'organizzazione per consentire agli utenti di reimpostare la password. È anche possibile tenere traccia delle attività di reimpostazione della password self-service in Azure Active Directory. Per altre informazioni, vedere [Opzioni di segnalazione per la gestione delle password di Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting).
|Utente eliminato|Elimina utente|È stato eliminato un account utente.|
|Reimpostazione della password utente|Reimpostazione della password utente|Un amministratore ha reimpostato la password per un utente.|
|Impostata una proprietà che impone all'utente di cambiare la password|Impostazione forzatura per la modifica delle password utente|Un amministratore ha impostato la proprietà che forza l'utente a cambiare la password al successivo accesso a Office 365.|
|Impostazione delle proprietà della licenza|Impostazione delle proprietà della licenza|Un amministratore modifica le proprietà di una licenza assegnata a un utente.|
|Utente aggiornato|Aggiornamento di un utente|Un amministratore modifica una o più proprietà di un account utente. Per un elenco delle proprietà utente che possono essere aggiornate, vedere la sezione "Aggiornamento attributi utente" in [Eventi del report di controllo di Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkID=616549).|
||||

### <a name="azure-ad-group-administration-activities"></a>Attività di amministrazione gruppi di Azure AD

La tabella seguente elenca le attività di amministrazione gruppi registrate quando un amministratore o un utente crea o modifica un gruppo di Microsoft 365 oppure quando un amministratore crea un gruppo di sicurezza usando l'interfaccia di amministrazione di Microsoft 365 o il portale di gestione di Azure. Per altre informazioni sui gruppi in Office 365, vedere [Visualizzare, creare ed eliminare gruppi nell'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups).

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Gruppo aggiunto|Aggiunta di un gruppo|È stato creato un gruppo.|
|Membro aggiunto a gruppo|Aggiunta di un membro al gruppo|È stato aggiunto un membro a un gruppo.|
|Gruppo eliminato|Eliminazione di un gruppo|È stato eliminato un gruppo.|
|Membro rimosso da gruppo|Rimozione di un membro dal gruppo|È stato rimosso un membro da un gruppo.|
|Gruppo aggiornato|Aggiornamento di un gruppo|È stata modificata una proprietà di un gruppo.|
||||

### <a name="application-administration-activities"></a>Attività di amministrazione applicazioni

La tabella seguente elenca le attività di amministrazione applicazioni registrate quando un amministratore aggiunge o modifica un'applicazione registrata in Azure AD. Qualsiasi applicazione che si basa su Azure AD per l'autenticazione deve essere registrata nella directory.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Voce di delega aggiunta|Aggiunta di una voce di delega|Un'autorizzazione di autenticazione è stata creata/concessa a un'applicazione in Azure AD.|
|Entità servizio aggiunta|Aggiunta di un'entità servizio|Un'applicazione è stata registrata in Azure AD. Un'applicazione è rappresentata da un'entità servizio nella directory.|
|Credenziali aggiunte a un'entità servizio |Aggiunta delle credenziali dell'entità servizio|Le credenziali sono state aggiunte a un'entità servizio in Azure AD. Un'entità servizio rappresenta un'applicazione nella directory.|
|Voce di delega rimossa|Rimozione della voce di delega|Un'autorizzazione di autenticazione è stata rimossa da un'applicazione in Azure AD.|
|Entità servizio rimossa dalla directory|Rimozione di un'entità servizio|Un'applicazione è stata eliminata o ne è stata annullata la registrazione in Azure AD. Un'applicazione è rappresentata da un'entità servizio nella directory.|
|Credenziali rimosse da un'entità servizio |Rimozione delle credenziali dell'entità servizio|Le credenziali sono state rimosse da un'entità servizio in Azure AD. Un'entità servizio rappresenta un'applicazione nella directory.|
|Impostazione della voce di delega|Impostazione della voce di delega|Un'autorizzazione di autenticazione è stata aggiornata per un'applicazione in Azure AD.|
||||

### <a name="role-administration-activities"></a>Attività di amministrazione ruoli

La tabella seguente elenca le attività di amministrazione ruoli di Azure AD registrate quando un amministratore gestisce i ruoli di amministrazione nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Membro aggiunto a ruolo|Aggiunta di un membro del ruolo al ruolo|È stato aggiunto un utente a un ruolo di amministratore in Microsoft 365.|
|Utente rimosso da un ruolo della directory|Rimozione di un membro del ruolo dal ruolo|È stato rimosso un utente da un ruolo di amministratore in Microsoft 365.|
|Impostazione delle informazioni di contatto aziendali|Impostazione delle informazioni di contatto aziendali|Sono state aggiornate le preferenze di contatto a livello aziendale per l'organizzazione. Le informazioni includono indirizzi di posta elettronica per messaggi correlati all'abbonamento inviati da Microsoft 365, nonché notifiche tecniche relative ai servizi.|
||||

### <a name="directory-administration-activities"></a>Attività di amministrazione directory

La tabella seguente elenca le attività correlate a dominio e directory di Azure AD registrate quando un amministratore gestisce l'organizzazione nell'interfaccia di amministrazione di Microsoft 365 o nel portale di gestione di Azure.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Dominio aggiunto a società|Aggiunta di un dominio alla società|È stato aggiunto un dominio all'organizzazione.|
|Partner aggiunto alla directory|Aggiunta di un partner alla società|È stato aggiunto un partner (amministratore delegato) all'organizzazione.|
|Dominio rimosso da società|Rimozione di un dominio dalla società|È stato rimosso un dominio dall'organizzazione.|
|Partner rimosso dalla directory|Rimozione di un partner dalla società|È stato rimosso un partner (amministratore delegato) dall'organizzazione.|
|Informazioni sulla società impostate|Impostazione delle informazioni sulla società|Sono state aggiornate le informazioni sulla società per l'organizzazione. Le informazioni includono indirizzi di posta elettronica per messaggi correlati all'abbonamento inviati da Microsoft 365, nonché notifiche tecniche relative ai servizi di Microsoft 365.|
|Impostazione dell'autenticazione del dominio|Impostazione dell'autenticazione del dominio|È stata modificata l'impostazione di autenticazione del dominio per l'organizzazione.|
|Impostazioni della federazione aggiornate per un dominio|Configurazione delle impostazioni di federazione nel dominio|Sono state modificate le impostazioni di federazione (condivisione esterna) per l'organizzazione.|
|Criteri password impostati|Criteri password impostati|Sono stati modificati i vincoli di lunghezza e caratteri per le password utente nell'organizzazione.|
|Attivata la sincronizzazione di Azure AD|Impostazione del flag DirSyncEnabled per la società|È stata impostata la proprietà che abilita una directory per Azure AD Sync.|
|Dominio aggiornato|Aggiornamento di un dominio|Sono state aggiornate le impostazioni di un dominio nell'organizzazione.|
|Dominio verificato|Verifica di un dominio|È stato verificato che l'organizzazione è il proprietario di un dominio.|
|Posta elettronica verificata in dominio verificato|Verifica del dominio tramite la verifica di posta elettronica|È stata usata la verifica tramite posta elettronica per verificare che l'organizzazione sia il proprietario di un dominio.|
||||

### <a name="ediscovery-activities"></a>Attività di eDiscovery

Le attività correlate a Ricerca contenuto ed eDiscovery eseguite nel centro sicurezza e conformità o tramite i cmdlet di PowerShell corrispondenti vengono registrate nel log di controllo. Questa operazione include le seguenti attività:

- Creazione e gestione di casi eDiscovery

- Creazione, avvio e modifica di ricerche di contenuto

- Esecuzione di operazioni di ricerca di contenuto, ad esempio visualizzazione in anteprima, esportazione ed eliminazione dei risultati della ricerca

- Configurazione del filtro delle autorizzazioni per Ricerca contenuto

- Gestione del ruolo di amministratore di eDiscovery

Per un elenco e una descrizione dettagliata delle attività di eDiscovery registrate, vedere [Cercare attività di eDiscovery nel log di controllo](search-for-ediscovery-activities-in-the-audit-log.md).

> [!NOTE]
> Sono necessari fino a 30 minuti per visualizzare nei risultati della ricerca gli eventi collegati alle attività elencate in **Attività di eDiscovery** e in attività di **Advanced eDiscovery** nell'elenco a discesa **Attività**. Invece, per visualizzare nei risultati della ricerca gli eventi corrispondenti provenienti dalle attività dei cmdlet di eDiscovery sono necessarie fino a 24 ore.

### <a name="advanced-ediscovery-activities"></a>Attività di Advanced eDiscovery 

È anche possibile eseguire una ricerca delle attività di Advanced eDiscovery nel log di controllo. Per una descrizione di tali attività, vedere la sezione "Attività di Advanced eDiscovery" in [Cercare attività di eDiscovery nel log di controllo](search-for-ediscovery-activities-in-the-audit-log.md#advanced-ediscovery-activities).

### <a name="power-bi-activities"></a>Attività di Power BI

È possibile eseguire una ricerca delle attività di Power BI nel log di controllo. Per informazioni sulle attività di Power BI, vedere la sezione "Attività controllate da Power BI" in [Uso del controllo all'interno dell'organizzazione](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi).

Per impostazione predefinita, la registrazione di controllo per Power BI non è abilitata. Per cercare le azioni di Power BI nel log di controllo, è necessario abilitare il controllo nel portale di amministrazione di Power BI. Per istruzioni, vedere la sezione "Log di controllo" nel [portale di amministrazione di Power BI](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs).

### <a name="microsoft-workplace-analytics-activities"></a>Attività di Microsoft Workplace Analytics

Workplace Analytics fornisce informazioni dettagliate sulla collaborazione dei gruppi all’interno dell’organizzazione. Nella tabella seguente sono elencate le attività eseguite dagli utenti a cui è assegnato il ruolo di amministratore o di analista in Workplace Analytics. Gli utenti con il ruolo di analista hanno accesso completo a tutte le caratteristiche del servizio e usano il prodotto per eseguire l'analisi. Gli utenti con il ruolo di amministratore possono configurare le impostazioni di privacy e le impostazioni predefinite del sistema e possono preparare, caricare e verificare i dati dell’organizzazione in Workplace Analytics. Per altre informazioni, vedere [Workplace Analytics](https://docs.microsoft.com/workplace-analytics/index-orig).

|Nome descrittivo|Operazione|Descrizione|
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

È possibile eseguire una ricerca nel log di controllo delle attività di utenti e amministratori in Microsoft Teams. Teams è un'area di lavoro basata su chat di Office 365. Raggruppa conversazioni, riunioni, file e note di un team in un'unica posizione. Per una descrizione delle attività di Teams controllate, vedere [Eseguire una ricerca nel log di controllo degli eventi di Microsoft Teams](https://docs.microsoft.com/microsoftteams/audit-log-events#teams-activities).

### <a name="microsoft-teams-healthcare-activities"></a>Attività di Microsoft Teams per il settore sanitario

Se l'organizzazione usa l’[applicazione Pazienti](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-app-overview) in Microsoft Teams, è possibile eseguire una ricerca nel log di controllo delle attività correlate all'utilizzo dell'app Pazienti. Se l'ambiente è configurato per supportare l'app Pazienti, è disponibile un altro gruppo di attività per queste attività nell’elenco di selezione **Attività**.

![Attività di Microsoft Teams per il settore sanitario nell'elenco di selezione Attività](../media/TeamsHealthcareAuditActivities.png)

Per una descrizione delle attività dell'app Pazienti, vedere [Log di controllo per l'app Pazienti](https://docs.microsoft.com/MicrosoftTeams/expand-teams-across-your-org/healthcare/patients-audit).

### <a name="microsoft-teams-shifts-activities"></a>Attività di Turni di Microsoft Teams

Se l'organizzazione usa l’applicazione Turni in Microsoft Teams, è possibile eseguire una ricerca nel log di controllo delle attività correlate all'utilizzo dell'app Turni. Se l'ambiente è configurato per supportare l'app Turni, è disponibile un altro gruppo di attività per queste attività nell’elenco di selezione **Attività**.

Per una descrizione delle attività relative alle app Turni, vedere [Eseguire ricerche nel log di controllo degli eventi di Microsoft Teams](https://docs.microsoft.com/microsoftteams/audit-log-events#shifts-in-teams-activities).

### <a name="yammer-activities"></a>Attività di Yammer

La tabella seguente elenca le attività degli utenti e degli amministratori di Yammer registrate nel log di controllo. Per restituire le attività correlate a Yammer dal log di controllo, è necessario selezionare **Visualizza i risultati per tutte le attività** nell'elenco **Attività**. Usare le caselle dell'intervallo di date e l'elenco **Utenti** per limitare i risultati della ricerca.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Criteri di conservazione dei dati modificati|SoftDeleteSettingsUpdated|L'amministratore verificato aggiorna l'impostazione per i criteri di conservazione dei dati di rete per l'eliminazione definitiva o l'eliminazione temporanea. Solo gli amministratori verificati possono eseguire questa operazione.|
|Configurazione di rete modificata|NetworkConfigurationUpdated|L'amministratore di rete o verificato modifica la configurazione della rete Yammer. Imposta anche l'intervallo per l'esportazione dei dati e l'abilitazione della chat.|
|Impostazioni del profilo di rete modificate|ProcessProfileFields|L'amministratore di rete o verificato modifica le informazioni visualizzate nei profili dei membri per gli utenti della rete.|
|Modalità per il contenuto privato modificata|SupervisorAdminToggled|L'amministratore verificato attiva o disattiva la *modalità contenuto privato*. Questa modalità consente a un amministratore di visualizzare i post nei gruppi privati e i messaggi privati scambiati tra singoli utenti o gruppi di utenti. Solo gli amministratori verificati possono eseguire questa operazione.|
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

### <a name="microsoft-power-automate-activities"></a>Attività di Microsoft Power Automate

È possibile eseguire una ricerca nel log di controllo delle attività di Power Automate, in precedenza chiamato Microsoft Flow. Queste attività includono la creazione, la modifica e l'eliminazione di flussi e la modifica delle autorizzazioni di flusso. Per informazioni sul controllo delle attività di Power Automate, vedere il blog  [Eventi di controllo di Microsoft Flow disponibili nel centro sicurezza e conformità](https://flow.microsoft.com/blog/security-and-compliance-center).

### <a name="microsoft-power-apps-activities"></a>Attività di Microsoft Power Apps

È possibile eseguire una ricerca nel log di controllo delle attività correlate all’app di Power Apps. Queste attività includono la creazione, l'avvio e la pubblicazione di un'app. Anche l’assegnazione di autorizzazioni per le app è soggetta a controllo. Per una descrizione di tutte le attività di Power Apps, vedere [Registrazione delle attività per Power Apps](https://docs.microsoft.com/power-platform/admin/logging-powerapps#what-events-are-audited).

### <a name="microsoft-stream-activities"></a>Attività di Microsoft Stream

È possibile eseguire una ricerca nel log di controllo delle attività di Microsoft Stream. Queste attività includono le attività su video eseguite dagli utenti, le attività su canali di gruppo e le attività di amministrazione, ad esempio la gestione degli utenti, la gestione delle impostazioni dell'organizzazione e l’esportazione di report. Per una descrizione di queste attività, vedere la sezione "Azioni registrate in Stream" in [Log di controllo in Microsoft Stream](https://docs.microsoft.com/stream/audit-logs#actions-logged-in-stream).

### <a name="content-explorer-activities"></a>Attività di Esplora contenuto

Nella tabella seguente sono elencate le attività in Esplora contenuto registrate nel log di controllo. Esplora contenuto è utilizzato con lo strumento Classificazioni dei dati nel Centro conformità Microsoft 365. Per altre informazioni, vedere [Utilizzo di Esplora contenuto in classificazioni dei dati](data-classification-content-explorer.md).

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Elemento a cui è stato effettuato l'accesso|LabelContentExplorerAccessedItem|Un amministratore o un utente che fa parte del gruppo di ruoli Visualizzatore contenuto di Esplora contenuto usa Esplora contenuto per visualizzare un messaggio di posta elettronica o un documento di SharePoint/OneDrive.|
||||

### <a name="quarantine-activities"></a>Attività in quarantena

Nella tabella seguente sono elencate le attività in quarantena che è possibile cercare nel log di controllo. Per altre informazioni sulla quarantena, vedere [Messaggi di posta elettronica in quarantena in Office 365](../security/office-365-security/quarantine-email-messages.md).

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Messaggio in quarantena eliminato|QuarantineDelete|Un utente ha eliminato un messaggio di posta elettronica considerato dannoso.|
|Messaggio in quarantena esportato|QuarantineExport|Un utente ha esportato un messaggio di posta elettronica considerato dannoso.|
|Messaggio in quarantena in anteprima|QuarantinePreview|Un utente ha visualizzato in anteprima un messaggio di posta elettronica considerato dannoso.|
|Messaggio di quarantena rilasciato|QuarantineRelease|Un utente ha rilasciato dalla quarantena un messaggio di posta elettronica considerato dannoso.|
|Intestazione del messaggio di quarantena visualizzata|QuarantineViewHeader|Un utente ha visualizzato l'intestazione di un messaggio di posta elettronica considerato dannoso.|
||||

### <a name="microsoft-forms-activities"></a>Attività di Microsoft Forms

La tabella seguente elenca le attività degli utenti e degli amministratori in Microsoft Forms registrate nel log di controllo. Microsoft Forms è uno strumento con moduli, quiz e sondaggi usato per la raccolta di dati per l'analisi. 

Dove indicato di seguito nelle descrizioni, alcune operazioni contengono parametri di attività aggiuntivi.

> [!NOTE]
> Se un'attività di Forms viene eseguita da un coautore o da intervistato anonimo, viene registrata in modo leggermente diverso. Per altre informazioni, vedere la sezione [Attività di Forms eseguite dai coautori e dagli intervistati anonimi](#forms-activities-performed-by-coauthors-and-anonymous-responders).

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Commento creato|CreateComment|Il proprietario del modulo aggiunge un commento o il punteggio a un test.|
|Modulo creato|CreateForm|Il proprietario del modulo crea un nuovo modulo.|
|Modulo modificato|EditForm|Il proprietario del modulo modifica un modulo, ad esempio per creare, rimuovere o modificare una domanda. La proprietà *EditOperation:string* indica il nome dell'operazione di modifica. Le operazioni possibili sono:<br/>- CreateQuestion<br/>- CreateQuestionChoice <br/>- DeleteQuestion <br/>- DeleteQuestionChoice <br/>- DeleteFormImage <br/>- DeleteQuestionImage <br/>- UpdateQuestion <br/>- UpdateQuestionChoice <br/>- UploadFormImage/Bing/Onedrive <br/>- UploadQuestionImage <br/>- ChangeTheme <br><br>FormImage include qualsiasi posizione all'interno di Forms in cui l'utente può caricare un'immagine, ad esempio in una query o come tema di sfondo.|
|Modulo spostato|MoveForm|Il proprietario del modulo sposta un modulo. <br><br>La proprietà DestinationUserId:string indica l'ID utente della persona che ha spostato il modulo. La proprietà NewFormId:string è il nuovo ID per il modulo appena copiato.|
|Modulo eliminato|DeleteForm|Il proprietario del modulo elimina un modulo. Questa operazione include SoftDelete (uso dell'opzione Elimina e spostamento del modulo nel Cestino) e HardDelete (svuotamento del Cestino).|
|Modulo visualizzato (fase di progettazione)|ViewForm|Il proprietario del modulo apre un modulo esistente per la modifica.|
|Modulo visualizzato in anteprima|PreviewForm|Il proprietario del modulo visualizza un modulo in anteprima usando la funzione Anteprima.|
|Modulo esportato|ExportForm|Il proprietario del modulo esporta i risultati in Excel. <br><br>La proprietà ExportFormat:stringa indica se il file di Excel è scaricato oppure online.|
|Condivisione del modulo per la copia consentita|AllowShareFormForCopy|Il proprietario del modulo crea un collegamento al modulo per condividere il modulo con altri utenti. Questo evento viene registrato quando il proprietario del modulo fa clic per generare l'URL del modulo.|
|Condivisione del modulo per la copia non consentita|DisallowShareFormForCopy|Il proprietario del modulo elimina il collegamento al modello.|
|Coautore del modulo aggiunto|AddFormCoauthor|Un utente usa un collegamento per contribuire alla progettazione o visualizzare le risposte. Questo evento viene registrato quando un utente usa un URL di collaborazione (non quando viene generato l'URL di collaborazione).|
|Coautore del modulo rimosso|RemoveFormCoauthor|Il proprietario del modulo elimina un collegamento per la collaborazione.|
|Pagina di risposta visualizzata|ViewRuntimeForm|Un utente ha aperto una pagina di risposta per la visualizzazione. Questo evento viene registrato indipendentemente dal fatto che l'utente invii o meno una risposta.|
|Risposta creata|CreateResponse|Simile alla ricezione di una nuova risposta. Un utente ha inviato una risposta a un modulo. <br><br>Le proprietà ResponseId:stringa e ResponderId:stringa indicano quale risultato viene visualizzato. <br><br>Per un partecipante anonimo, la proprietà ResponderId sarà Null.|
|Risposta aggiornata|UpdateResponse|Il proprietario del modulo ha aggiornato un commento o il punteggio di un test. <br><br>Le proprietà ResponseId:stringa e ResponderId:stringa indicano quale risultato viene visualizzato. <br><br>Per un partecipante anonimo, la proprietà ResponderId sarà Null.|
|Tutte le risposte eliminate|DeleteAllResponses|Il proprietario del modulo elimina tutti i dati delle risposte.|
|Risposta eliminata|DeleteResponse|Il proprietario del modulo elimina una risposta. <br><br>La proprietà ResponseId:stringa indica la risposta eliminata.|
|Risposte visualizzate|ViewResponses|Il proprietario del modulo visualizza l'elenco aggregato di risposte. <br><br>La proprietà ViewType:stringa indica se il proprietario del modulo visualizza i dati in dettaglio o in forma aggregata|
|Risposta visualizzata|ViewResponse|Il proprietario del modulo visualizza una risposta specifica. <br><br>Le proprietà ResponseId:stringa e ResponderId:stringa indicano quale risultato viene visualizzato. <br><br>Per un partecipante anonimo, la proprietà ResponderId sarà Null.|
|Collegamento di riepilogo creato|GetSummaryLink|Il proprietario del modulo crea un collegamento ai risultati di riepilogo per condividere i risultati.|
|Collegamento di riepilogo eliminato|DeleteSummaryLink|Il proprietario del modulo elimina il collegamento ai risultati di riepilogo.|
|Stato di phishing modulo aggiornato|UpdatePhishingStatus|Questo evento viene registrato ogni volta che viene modificato il valore dettagliato dello stato di sicurezza interno, indipendentemente dal fatto che sia stato modificato lo stato di sicurezza finale, ad esempio il modulo ora è chiuso o aperto. Ciò significa che è possibile visualizzare eventi duplicati senza un cambiamento dello stato di sicurezza finale. I possibili valori di stato per questo evento sono:<br/>- Rimozione <br/>- Rimuovi da amministratore <br/>- Amministratore sbloccato <br/>- Bloccato automaticamente <br/>- Sbloccato automaticamente <br/>- Cliente segnalato <br/>- Reimposta cliente segnalato|
|Stato di phishing utente aggiornato|UpdateUserPhishingStatus|Questo evento viene registrato ogni volta che viene modificato il valore dello stato di sicurezza utente. Il valore dello stato utente nel record di controllo viene **Confermato come truffatore** quando l'utente ha creato un modulo di phishing che è stato rimosso dal team di sicurezza di Microsoft Online. Se un amministratore sblocca l'utente, il valore dello stato utente è impostato su **Reimpostato come utente normale**.|
|Invito a Forms Pro inviato|ProInvitation|L'utente fa clic per attivare una versione di valutazione Pro.|
|Impostazione modulo aggiornata|UpdateFormSetting|Il proprietario del modulo aggiorna un'impostazione del modulo. <br><br>La proprietà FormSettingName:stringa indica il nome e il nuovo valore dell'impostazione.|
|Impostazione utente aggiornata|UpdateUserSetting|Il proprietario del modulo aggiorna un'impostazione utente. <br><br>La proprietà UserSettingName:stringa indica il nome e il nuovo valore dell'impostazione|
|Moduli elencati|ListForms|Il proprietario del modulo sta visualizzando un elenco di moduli. <br><br>La proprietà ViewType:stringa indica la visualizzazione esaminata dal proprietario del modulo: tutti i moduli, condivisi con l'utente o moduli dei gruppi|
|Risposta inviata|SubmitResponse|Un utente invia una risposta a un modulo. <br><br>La proprietà IsInternalForm:booleano indica se il partecipante si trova nella stessa organizzazione del proprietario del modulo.|
||||

#### <a name="forms-activities-performed-by-coauthors-and-anonymous-responders"></a>Attività di Forms eseguite da coautori e partecipanti anonimi

Forms supporta la collaborazione nella progettazione dei moduli e nell'analisi delle risposte. Un collaboratore del modulo è noto come *coautore*. I coautori possono eseguire tutte le operazioni che può eseguire il proprietario del modulo, tranne eliminare o spostare un modulo. Forms consente anche di creare moduli a cui è possibile rispondere in modo anonimo. Ciò significa che non è necessario che l’intervistato sia connesso all'organizzazione per rispondere a un modulo.

La tabella seguente descrive le attività di controllo e le informazioni del record di controllo relative alle attività eseguite dai coautori e dai partecipanti anonimi.

|Tipo di attività|Utente interno o esterno|ID utente registrato|Organizzazione a cui si è connessi|Tipo di utente Forms|
|:-----|:-----|:-----|:-----|:-----|
|Attività di creazione condivisa|Interno|UPN|Organizzazione del proprietario del modulo|Coautore|
|Attività di creazione condivisa|Esterno|UPN<br>|Organizzazione del coautore<br>|Coautore|
|Attività di creazione condivisa|Esterno|`urn:forms:coauthor#a0b1c2d3@forms.office.com`<br>La seconda parte dell'ID è un hash, che varia in base ai diversi utenti|Organizzazione del proprietario del modulo<br>|Coautore|
|Attività di risposta|Esterno|UPN<br>|Organizzazione del partecipante<br>|Partecipante|
|Attività di risposta|Esterno|`urn:forms:external#a0b1c2d3@forms.office.com`<br>La seconda parte dell'ID utente è un hash, che varia in base ai diversi utenti|Organizzazione del proprietario del modulo|Partecipante|
|Attività di risposta|Anonimo|`urn:forms:anonymous#a0b1c2d3@forms.office.com`<br>La seconda parte dell'ID utente è un hash, che varia in base ai diversi utenti|Organizzazione del proprietario del modulo|Partecipante|
||||

### <a name="sensitivity-label-activities"></a>Attività sulle etichette di riservatezza

La tabella seguente elenca gli eventi risultanti dalle attività di etichettatura per i siti di SharePoint Online e di Teams.

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
|Etichetta di riservatezza applicata al sito|SensitivityLabelApplied|È stata applicata un'etichetta di riservatezza a un sito di SharePoint o di Teams.|
|Etichetta di riservatezza rimossa dal sito|SensitivityLabelRemoved|È stata rimossa un'etichetta di riservatezza da un sito di SharePoint o di Teams.|
|Etichetta di riservatezza applicata al file|FileSensitivityLabelApplied|È stata applicata un'etichetta di riservatezza a un documento tramite Office sul web o un criterio di aggiunta automatica dell'etichetta.|
|Etichetta di riservatezza applicata a un file modificata|FileSensitivityLabelChanged|È stata applicata un'etichetta di riservatezza diversa a un documento tramite Office sul web o un criterio di aggiunta automatica dell'etichetta.|
|Etichetta di riservatezza rimossa dal file|FileSensitivityLabelRemoved|È stata rimossa un'etichetta di riservatezza da un documento tramite Office sul web, con un criterio di applicazione automatica delle etichette o tramite il cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](https://docs.microsoft.com/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile).|
||||

### <a name="retention-policy-and-retention-label-activities"></a>Attività su criteri di conservazione ed etichette di conservazione

|Nome descrittivo|Operazione|Descrizione|
|:-----|:-----|:-----|
| Impostazioni configurate per un criterio di conservazione |NewRetentionComplianceRule |Un amministratore ha configurato le impostazioni di conservazione per un nuovo criterio di conservazione. Le impostazioni di conservazione consentono di specificare il periodo di conservazione degli elementi e cosa succede agli elementi al termine del periodo di conservazione, ad esempio l'eliminazione degli elementi, la conservazione degli elementi o la conservazione e successiva eliminazione degli elementi. Questa attività corrisponde anche all'esecuzione del cmdlet [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule).|
| Etichetta di conservazione creata |NewComplianceTag |L'amministratore ha creato una nuova etichetta di conservazione.|
| Criterio di conservazione creato |NewRetentionCompliancePolicy|L'amministratore ha creato un nuovo criterio di conservazione.|
| Impostazioni eliminate per un criterio di conservazione| RemoveRetentionComplianceRule<br/>| Un amministratore ha eliminato le impostazioni di configurazione di un criterio di conservazione. Molto probabilmente, questa attività viene registrata quando un amministratore elimina un criterio di conservazione o esegue il cmdlet [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/Remove-RetentionComplianceRule).|
| Etichetta di conservazione eliminata |RemoveComplianceTag | L'amministratore ha eliminato un'etichetta di conservazione.|
| Criterio di conservazione eliminato |RemoveRetentionCompliancePolicy<br/> |L'amministratore ha eliminato un criterio di conservazione. |
| Opzione del record normativo abilitata per le etichette di conservazione<br/> |SetRestrictiveRetentionUI |L'amministratore ha eseguito il cmdlet [set-RegulatoryComplianceUI](https://docs.microsoft.com/powershell/module/exchange/set-regulatorycomplianceui) in modo che un amministratore possa selezionare l'opzione di configurazione dell'interfaccia utente per un'etichetta di conservazione che consente di contrassegnare il contenuto come record normativo.|
| Impostazioni aggiornate per un criterio di conservazione | SetRetentionComplianceRule | Un amministratore ha modificato le impostazioni di conservazione per un criterio di conservazione esistente. Le impostazioni di conservazione consentono di specificare il periodo di conservazione degli elementi e cosa succede agli elementi al termine del periodo di conservazione, ad esempio l'eliminazione degli elementi, la conservazione degli elementi o la conservazione e successiva eliminazione degli elementi. Questa attività corrisponde anche all'esecuzione del cmdlet [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule). |
| Etichetta di conservazione aggiornata |SetComplianceTag  | L'amministratore ha aggiornato un'etichetta di conservazione esistente.|
| Criterio di conservazione aggiornato |SetRetentionCompliancePolicy |Un amministratore ha aggiornato un criterio di conservazione esistente. Gli aggiornamenti che attivano questo evento includono l'aggiunta o l'esclusione di percorsi di contenuto ai quali applicare il criterio di conservazione.|

### <a name="exchange-admin-audit-log"></a>Log di controllo dell'amministratore di Exchange

La registrazione di controllo dell'amministratore di Exchange, abilitata per impostazione predefinita in Office 365, registra un evento nel log di controllo quando un amministratore (o un utente a cui sono state assegnate autorizzazioni amministrative) apporta una modifica nell'organizzazione di Exchange Online. Le modifiche apportate usando l'interfaccia di amministrazione di Exchange o eseguendo un cmdlet in Exchange Online PowerShell vengono registrate nel log di controllo dell'amministratore di Exchange. I cmdlet che cominciano con i verbi **Get-**, **Search-** o **Test-** non sono registrati nel log di controllo. Per informazioni dettagliate sulla registrazione di controllo dell’amministratore di Exchange, vedere [Registrazione di controllo dell'amministratore](https://go.microsoft.com/fwlink/p/?LinkID=619225).

> [!IMPORTANT]
> Alcuni cmdlet di Exchange Online non sono registrati nel log di controllo dell’amministratore di Exchange (o nel log di controllo). Molti di questi cmdlet sono correlati alla gestione del servizio Exchange Online e sono eseguiti dal personale del data center di Microsoft o dagli account di servizio. Questi cmdlet non vengono registrati perché comporterebbero un numero eccessivo di eventi di controllo. Se è presente un cmdlet di Exchange Online che non è oggetto di controllo, inviare un suggerimento al [Forum per la sicurezza e conformità di User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance) e chiedere che sia abilitato per il controllo. È anche possibile inviare una richiesta di modifica della struttura al supporto tecnico Microsoft.

Di seguito sono forniti alcuni suggerimenti per la ricerca delle attività dell’amministratore di Exchange durante la ricerca nel log di controllo:

- Per restituire le voci dal log di controllo dell'amministratore di Exchange, è necessario selezionare **Visualizza i risultati per tutte le attività** nell'elenco **Attività**. Usare le caselle relative all'intervallo di date e l'elenco **Utenti** per limitare i risultati della ricerca per i cmdlet eseguiti da uno specifico amministratore di Exchange in un determinato intervallo di date. 

- Per visualizzare gli eventi del log di controllo dell'amministratore di Exchange, filtrare i risultati della ricerca e digitare un **-** (trattino) nella casella del filtro **Attività**. In questo modo, vengono visualizzati i nomi dei cmdlet, che sono indicati nella colonna **Attività** per gli eventi di amministrazione di Exchange. È anche possibile disporre i nomi dei cmdlet in ordine alfabetico.

  ![Digitare un trattino nella casella Attività per filtrare gli eventi di amministrazione di Exchange](../media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)

- Per ottenere informazioni sul cmdlet eseguito, sui parametri e sui valori dei parametri usati e sugli oggetti interessati, è possibile esportare i risultati della ricerca e selezionare l'opzione **Scarica tutti i risultati**. Per altre informazioni, vedere [Esportare, configurare e visualizzare i record del log di controllo](export-view-audit-log-records.md).

- È anche possibile usare il comando `Search-UnifiedAuditLog -RecordType ExchangeAdmin` in Exchange Online PowerShell per restituire solo i record di controllo dal log di controllo dell'amministratore di Exchange. Dopo l'esecuzione di un cmdlet di Exchange, potrebbero essere necessari fino a 30 minuti perché la voce del log di controllo corrispondente sia restituita nei risultati della ricerca. Per altre informazioni, vedere [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog). Per informazioni sull'esportazione dei risultati di ricerca restituiti dal cmdlet **Search-UnifiedAuditLog** in un file CSV, vedere la sezione "Suggerimenti per l'esportazione e la visualizzazione del log di controllo" in [Esportare, configurare e visualizzare i record del log di controllo](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log).

- È anche possibile visualizzare gli eventi nel log di controllo dell'amministratore di Exchange usando l'interfaccia di amministrazione di Exchange o tramite l’esecuzione di **Search-AdminAuditLog** in Exchange Online PowerShell. Si tratta di un ottimo metodo per cercare in modo specifico le attività eseguite dagli amministratori di Exchange Online. Per istruzioni, vedere:

  - [Visualizzare il registro di controllo dell'amministratore](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx)

  - [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)

   Tenere presente che le stesse attività dell'amministratore di Exchange sono registrate sia nel log di controllo di amministrazione di Exchange che nel log di controllo.

## <a name="frequently-asked-questions"></a>Domande frequenti

**Quali sono i diversi servizi di Microsoft 365 attualmente controllati?**

Sono controllati i servizi più usati come Exchange Online, SharePoint Online, OneDrive for Business, Azure Active Directory, Microsoft Teams, Dynamics 365, Defender per Office 365 e Power BI. Vedere l’[inizio di questo articolo](search-the-audit-log-in-security-and-compliance.md) per una lista dei servizi controllati.

**Quali attività sono controllate dal servizio di controllo in Office 365?**

Per un elenco e una descrizione delle attività controllate, vedere la sezione [Attività controllate](#audited-activities) in questo articolo.

**Quanto tempo è necessario affinché un record di controllo sia disponibile dopo il verificarsi di un evento?**

La maggior parte dei dati di controllo è disponibile entro 30 minuti, ma potrebbero essere necessarie fino a 24 ore dopo il verificarsi dell’evento per visualizzare la voce del log di controllo corrispondente nei risultati della ricerca. Vedere la tabella nella sezione [Requisiti per eseguire ricerche nel log di controllo](#requirements-to-search-the-audit-log) di questo articolo che mostra il tempo necessario perché siano disponibili gli eventi nei diversi servizi.

**Per quanto tempo vengono conservati i record di controllo?**

Come spiegato in precedenza, i record di controllo per le attività eseguite dagli utenti con una licenza Office 365 E5 o Microsoft E5 (o utenti con una licenza per il componente aggiuntivo Microsoft 365 E5) vengono conservati per un anno. Per tutti gli altri abbonamenti che supportano la registrazione di controllo unificato, i record di controllo sono conservati per 90 giorni.

**È possibile accedere ai dati di controllo a livello di programmazione?**

Sì. L'API Office 365 Management Activity consente di recuperare i log di controllo a livello di programmazione.  Per un’introduzione, vedere [Introduzione alle API Office 365 Management](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

**Esistono altri modi diversi dall'uso del Centro sicurezza e conformità o dall'API Office 365 Management Activity per ottenere log di controllo?**

No. Questi sono gli unici due modi per ottenere dati dal servizio di controllo.

**È necessario abilitare singolarmente il controllo in ogni servizio di cui si vogliono acquisire i log di controllo?**

Nella maggior parte dei servizi, il controllo è abilitato per impostazione predefinita dopo l'attivazione del controllo per l'organizzazione (come descritto nella sezione [Requisiti per la ricerca nel log di controllo](#requirements-to-search-the-audit-log) di questo articolo).

**Il servizio di controllo supporta la deduplicazione dei record?**

No. La pipeline dei servizi di controllo è quasi in tempo reale, pertanto non supporta la deduplicazione.

**I dati di controllo vengono trasportati nelle diverse aree geografiche?**

No. Attualmente vengono effettuate distribuzioni di pipeline di controllo nelle aree del Nord America, di Europa, Medio Oriente, Africa (EMEA) e Asia Pacifico (APAC). Tuttavia, i dati possono essere trasferiti tra queste aree geografiche per bilanciamento del carico e solo nel momento in cui si verificano problemi per un sito live. Durante l'esecuzione di queste attività, i dati in transito sono crittografati.

**I dati di controllo sono crittografati?**

I dati di controllo sono archiviati nelle cassette postali di Exchange (dati inattivi) nella stessa area geografica in cui è distribuita la pipeline di controllo unificato. I dati inattivi delle cassette postali non sono crittografati da Exchange. Tuttavia, la crittografia a livello di servizio crittografa tutti i dati delle cassette postali perché i server di Exchange nei data center di Microsoft vengono crittografati tramite BitLocker. Per altre informazioni, vedere [Crittografia di Office 365 per Skype for Business, OneDrive for Business, SharePoint Online ed Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md).

I dati di posta elettronica in transito sono sempre crittografati.
