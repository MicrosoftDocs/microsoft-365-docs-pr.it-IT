---
title: Usare il piano di archiviazione per gestire le etichette di conservazione per tutto il ciclo di vita del contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: Il piano di archiviazione offre funzionalità di gestione avanzate per le etichette di conservazione.
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 85160a859469a5c2dcb1aec8100eed6e25bd7597
ms.sourcegitcommit: 5e8901e7e571f20ede04f460bd3e7077dda004ca
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874906"
---
# <a name="use-file-plan-to-manage-retention-labels"></a>Usare il piano di archiviazione per gestire le etichette di conservazione

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Anche se è possibile creare e gestire le etichette di conservazione dalla **Governance delle informazioni** nel Centro conformità Microsoft 365, il piano di archiviazione di **Gestione dei record** offre funzionalità di gestione aggiuntive:

- È possibile creare etichette di conservazione in blocco importando le informazioni rilevanti da un foglio di calcolo.

- È possibile esportare le informazioni dalle etichette di conservazione esistenti per l'analisi e la collaborazione offline o per la modifica in blocco.

- Sono disponibili ulteriori informazioni sulle etichette di conservazione per semplificarne l'uso nelle varie impostazioni da una sola visualizzazione.

- I descrittori del piano di archiviazione supportano informazioni aggiuntive e facoltative per ogni etichetta.

Il piano di archiviazione può essere usato per tutte le etichette di conservazione, anche per quelle che non contrassegnano il contenuto come record.

![Pagina del piano di archiviazione](../media/compliance-file-plan.png)

Per informazioni sulle etichette di conservazione e sul loro utilizzo, vedere [Informazioni sulle etichette di conservazione](labels.md).

## <a name="accessing-file-plan"></a>Accesso al piano di archiviazione

Per accedere al piano di archiviazione, è necessario disporre di uno dei ruoli di amministratore seguenti:
    
- Responsabile della conservazione

- Responsabile della conservazione solo visualizzazione

Nel Centro conformità Microsoft 365 passare a **Soluzioni** > **Gestione record** > **Piano di archiviazione**. 

Se **Gestione record** non viene visualizzato nel pannello di navigazione, per prima cosa, scorrere verso il basso e selezionare **Mostra tutto**.

![Pagina del piano di archiviazione](../media/compliance-file-plan.png)

## <a name="navigating-your-file-plan"></a>Esplorare il piano di archiviazione

Se sono già state create etichette di conservazione da **Governance delle informazioni** nel Centro conformità Microsoft 365, queste etichette vengono visualizzate automaticamente nel piano di archiviazione. 

Analogamente, se a questo punto si creano etichette di conservazione nel piano di archiviazione, queste saranno disponibili anche in **Governance delle informazioni** se non sono configurate per contrassegnare il contenuto come record.

Nella pagina **Piano di archiviazione** sono visualizzate tutte le etichette con lo stato e le impostazioni, i descrittori facoltativi del piano di archiviazione, un'opzione di esportazione per analizzare o abilitare le revisioni offline delle etichette e un'opzione di importazione per creare etichette di conservazione. 

### <a name="label-settings-columns"></a>Colonne impostazioni etichetta

Tutte le colonne tranne l'etichetta **Nome** possono essere visualizzate o nascoste selezionando l'opzione **Personalizza colonne**. Per impostazione predefinita, tuttavia, le prime colonne mostrano le informazioni sullo stato dell'etichetta e le relative impostazioni: 

- **Stato** identifica se l'etichetta è inclusa in un criterio di etichetta o in un criterio di applicazione automatica (**Attivo**) o meno (**Inattivo**).

- **Basato su** identifica come o quando viene avviato il periodo di conservazione. Valori validi:
    - Evento
    - Momento della creazione
    - Data ultima modifica
    - Data etichettatura

- **È un record** identifica se l'elemento viene contrassegnato come record quando è applicata l'etichetta. Valori validi:
    - No
    - Sì

- **Durata di conservazione** identifica il periodo di conservazione. Valori validi:
    - Giorni
    - Mesi
    - Anni
    - Per sempre
    - Nessuno

- **Tipo di eliminazione** identifica cosa succederà al contenuto alla fine del periodo di conservazione. Valori validi:
    - Nessuna azione
    - Eliminazione automatica
    - Richiesta revisione

### <a name="file-plan-descriptors-columns"></a>Colonne dei descrittori del piano di archiviazione

Il piano di archiviazione consente di includere più informazioni nell'ambito delle etichette di conservazione. I descrittori del piano di archiviazione offrono altre opzioni per migliorare la gestibilità e l'organizzazione del contenuto che è necessario etichettare.

Per impostazione predefinita, a partire da **ID riferimento**, le colonne successive mostrano i descrittori del piano di archiviazione che è possibile specificare quando si crea un'etichetta di conservazione o si modifica un'etichetta esistente. 

Per iniziare, esistono alcuni valori preesistenti per i seguenti descrittori del piano di archiviazione: 
- Funzione/reparto aziendale
- Categoria
- Tipo di autorità
- Provisioning/citazione 

Esempio di descrittori del piano di archiviazione quando si crea o si modifica un'etichetta di conservazione:

![Descrittori del piano di archiviazione](../media/file-plan-descriptors.png)

Esempio di come vengono visualizzate le colonne dei descrittori del piano di archiviazione:

![file-plan-descriptors-on-labels-tab.png](../media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-retention-labels-to-analyze-or-enable-offline-reviews"></a>Esportare tutte le etichette di conservazione per analizzare o abilitare le revisioni offline

Dal piano di archiviazione, è possibile esportare i dettagli di tutte le etichette di conservazione in un file CSV per agevolare le analisi di conformità periodiche con le parti interessate responsabili della governance dei dati all'interno dell'organizzazione.

Per esportare tutte le etichette di conservazione, nella pagina **Piano di archiviazione** fare clic su **Esporta**:

![Opzione per esportare il piano di archiviazione](../media/compliance-file-plan-export-labels.png)

Viene visualizzato un file CSV che contiene tutte le etichette di conservazione esistenti. Ad esempio:

![File CSV con tutte le etichette di conservazione](../media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a>Importare le etichette di conservazione nel piano di archiviazione

Nel piano di archiviazione è possibile importare in blocco nuove etichette di conservazione, nonché modificare le etichette di conservazione esistenti usando lo stesso metodo.

Per importare nuove etichette di conservazione e modificare le etichette di conservazione esistenti: 

1. Nella pagina **Piano di archiviazione**, fare clic su **Importa** per usare la pagina **Compila e importa il piano di archiviazione**:

   ![Opzione per importare il piano file](../media/compliance-file-plan-import-labels.png)

   ![Opzione per scaricare un modello di piano file vuoto](../media/file-plan-blank-template-option.png)

2. Scaricare un modello vuoto per importare le nuove etichette di conservazione. In alternativa, è possibile iniziare con il file CSV esportato durante l'esportazione delle etichette di conservazione esistenti nell'organizzazione.

   ![Modello di piano di archiviazione vuoto aperto in Excel](../media/file-plan-blank-template.png)

3. Compilare il modello in base alle informazioni seguenti che descrivono le proprietà e i valori validi per ogni proprietà. Per l'importazione, ogni valore può contenere 64 caratteri al massimo. <br/>

   |Proprietà|Tipo|Valori validi|
   |:-----|:-----|:-----|
   |LabelName|Stringa|Questa proprietà specifica il nome dell'etichetta di conservazione.|
   |Comment|Stringa|Usare questa proprietà per aggiungere una descrizione relativa all'etichetta di conservazione per gli amministratori. Questa descrizione viene visualizzata solo dagli amministratori che gestiscono l'etichetta di conservazione nel centro conformità.|
   |Notes|Stringa|Usare questa proprietà per aggiungere una descrizione relativa all'etichetta di conservazione per gli utenti. Questa descrizione viene visualizzata quando gli utenti passano con il mouse sull'etichetta in app quali Outlook, SharePoint e OneDrive. Se si lascia vuota questa proprietà, viene visualizzata una descrizione predefinita, che illustra le impostazioni di conservazione dell'etichetta. |
   |IsRecordLabel|Stringa|Questa proprietà specifica se l'etichetta contrassegna il contenuto come record. I valori validi sono: </br>**TRUE**: l'etichetta contrassegna l'elemento come record e, di conseguenza, l'elemento non può essere eliminato. </br>**FALSE**: l'etichetta non contrassegna il contenuto come record. Questo è il valore predefinito.|
   |RetentionAction|Stringa|Questa proprietà specifica l'azione da intraprendere dopo la scadenza del valore specificato dalla proprietà RetentionDuration. I valori validi sono: </br>**Delete**: gli elementi più vecchi del valore specificato dalla proprietà RetentionDuration vengono eliminati.</br>**Keep**: gli elementi vengono mantenuti per la durata specificata dalla proprietà RetentionDuration e non viene eseguita alcuna azione alla scadenza del periodo definito per la durata. </br>**KeepAndDelete**: gli elementi vengono mantenuti per la durata specificata dalla proprietà RetentionDuration e quindi vengono eliminati alla scadenza del periodo definito per la durata.   |
   |RetentionDuration|Stringa|La proprietà specifica per quanti giorni mantenere il contenuto. I valori validi sono: </br>**Unlimited**: gli elementi verranno mantenuti a tempo indeterminato. </br>***n***: un numero intero positivo, ad esempio **365**. 
   |RetentionType|Stringa|Questa proprietà specifica se la durata del periodo di conservazione è stata calcolata a partire dalla data di creazione del contenuto, dalla data dell'evento, dalla data di etichettatura o dalla data dell'ultima modifica. I valori validi sono: </br>**CreationAgeInDays**</br>**EventAgeInDays**</br>**TaggedAgeInDays**</br>**ModificationAgeInDays** |
   |ReviewerEmail|SmtpAddress|Quando questa proprietà è popolata, verrà attivata una revisione delle clausole alla scadenza della durata della conservazione. Questa proprietà consente di specificare l'indirizzo di posta elettronica del revisore per l'azione di conservazione **KeepAndDelete**. È possibile includere l'indirizzo di posta elettronica di singoli utenti, gruppi di distribuzione o gruppi di sicurezza. È possibile indicare più indirizzi di posta elettronica separati da punto e virgola.|
   |ReferenceId|Stringa|Questa proprietà specifica il valore visualizzato nel descrittore **ID riferimento** del piano di archiviazione, che è possibile utilizzare come valore univoco per l'organizzazione.| 
   |DepartmentName|Stringa|Questa proprietà specifica il valore visualizzato nel descrittore **Funzione/reparto** del piano di archiviazione.|
   |Category|Stringa|Questa proprietà specifica il valore visualizzato nel descrittore **Categoria** del piano di archiviazione.|
   |SubCategory|Stringa|Questa proprietà specifica il valore visualizzato nel descrittore **Sottocategoria** del piano di archiviazione.|
   |AuthorityType|Stringa|Questa proprietà specifica il valore visualizzato nel descrittore **Tipo di autorità** del piano di archiviazione.|
   |CitationName|Stringa|Questa proprietà specifica il nome della citazione visualizzata nel descrittore **Clausola/citazione** del piano di archiviazione. Ad esempio, "Sarbanes-Oxley Act del 2002". |
   |CitationUrl|Stringa|Questa proprietà specifica l'URL visualizzato nel descrittore **Clausola/citazione** del piano di archiviazione.|
   |CitationJurisdiction|Stringa|Questa proprietà specifica il settore di competenza o agenzia visualizzati nel descrittore **Clausola/citazione** del piano di archiviazione. Ad esempio, "U.S. Securities and Exchange Commission (SEC)".|
   |Regulatory|Stringa|Lasciare vuota. Questa proprietà non viene usata al momento.|
   |EventType|Stringa|Questa proprietà specifica la regola di conservazione associata all'etichetta. È possibile utilizzare qualsiasi valore che identifichi la regola in modo univoco. Ad esempio:</br>**Nome**</br>**Nome distinto (DN)**</br>**GUID** </br>È possibile usare il cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule?view=exchange-ps) per visualizzare le regole di conservazione disponibili. Tenere presente che, poiché i valori EventType sono univoci per l'organizzazione, se si esportano etichette da un'organizzazione, non è possibile usare i valori per la proprietà EventType di tale organizzazione durante l'importazione delle etichette in un'altra organizzazione.|
   |||

   Ecco un esempio di modello che contiene informazioni sulle etichette di conservazione.

   ![Modello del piano di archiviazione compilato con le informazioni](../media/file-plan-filled-out-template.png)

4. Al passaggio 3 della pagina **Compila e importa il piano di archiviazione**, fare clic su **Cerca file** per caricare il modello compilato. 

   Il piano di archiviazione convaliderà le voci e visualizzerà le statistiche di importazione.

   ![Statistiche di importazione del piano di archiviazione](../media/file-plan-import-statistics.png)

   Se è presente un errore di convalida, l'importazione del piano di archiviazione continuerà a convalidare ogni voce nel file di importazione e mostrerà tutti gli errori che fanno riferimento ai numeri di linea e di riga del file di importazione. Copiare i risultati di errore visualizzati per correggerli nel file di importazione.

Una volta completata l'importazione, è possibile aggiungere le etichette di conservazione a un nuovo criterio di etichetta di conservazione oppure applicarle automaticamente. È possibile eseguire questa operazione direttamente nella pagina **Piano di archiviazione**, selezionando l'elenco a discesa da **+ Crea un'etichetta**, quindi **Criteri per la pubblicazione di etichette** o **Criteri per l'applicazione automatica di un'etichetta**.

## <a name="next-steps"></a>Passaggi successivi

Per ulteriori informazioni sulla creazione e la modifica di etichette di conservazione e sui relativi criteri, vedere [Creare, pubblicare e applicare automaticamente etichette di conservazione](create-retention-labels.md).
