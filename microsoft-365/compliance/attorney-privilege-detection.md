---
title: Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
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
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Utilizzare il modello di rilevamento dei privilegi avvocato-client per utilizzare il rilevamento basato sull'apprendimento automatico del contenuto con privilegi quando si esaminano i contenuti in un caso avanzato di eDiscovery.
ms.openlocfilehash: 8fb635e429af2ae4d796e9c847a34d949d8dd6d9
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079268"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery

Un aspetto importante e costoso della fase di revisione di un processo di eDiscovery consiste nell'esaminare i documenti per il contenuto con privilegi. Advanced eDiscovery fornisce il rilevamento basato sull'apprendimento automatico del contenuto con privilegi per rendere più efficiente questo processo. Questa funzionalità è denominata *rilevamento dei privilegi di avvocato-client*.

## <a name="how-does-it-work"></a>Come funziona

Quando è abilitato il rilevamento dei privilegi di avvocato-client, tutti i documenti in un set di revisione verranno elaborati dal modello di rilevamento del privilegio avvocato-client quando si [analizzano i dati](analyzing-data-in-review-set.md) nel set di revisione. Il modello cerca due elementi:

- Contenuto con privilegi: il modello utilizza l'apprendimento automatico per determinare la probabilità che il documento contenga contenuti di natura legale.

- Partecipanti – nell'ambito della configurazione del rilevamento dei privilegi del procuratore-client, è necessario inviare un elenco di avvocati per la propria organizzazione. Il modello confronta quindi i partecipanti del documento con l'elenco degli avvocati per determinare se un documento ha almeno un partecipante al procuratore.

Il modello produce le tre proprietà seguenti per ogni documento:

- **AttorneyClientPrivilegeScore:** La probabilità che il documento sia di natura legale; i valori per il punteggio sono compresi tra **0** e **1**.

- **HasAttorney:** Questa proprietà è impostata su **true** se uno dei partecipanti al documento è elencato nell'elenco procuratore; in caso contrario, il valore è **false**. Il valore viene impostato su **false** anche se l'organizzazione non ha caricato un elenco di avvocati.

- **Privilegio:** Questa proprietà è impostata su **true** se il valore di **AttorneyClientPrivilegeScore** è al di sopra della soglia *o* se il documento ha un partecipante al procuratore; in caso contrario, il valore è impostato su **false**.

Queste proprietà e i relativi valori corrispondenti vengono aggiunte ai metadati del file dei documenti in un set di revisione, come illustrato nella schermata seguente:

![Proprietà del privilegio avvocato-client mostrate nei metadati dei file](../media/AeDAttorneyClientPrivilegeMetadata.png)

Queste tre proprietà sono anche ricercabili all'interno di un set di revisione. Per ulteriori informazioni, vedere [eseguire una query sui dati in un set di revisione](review-set-search.md).

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Configurare il modello di rilevamento dei privilegi avvocato-client

Per abilitare il modello di rilevamento dei privilegi avvocato-client, è necessario che l'organizzazione lo accenda e quindi carichi un elenco di avvocati.

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>Passaggio 1: attivazione del rilevamento dei privilegi di avvocato-client

Una persona che è un amministratore di eDiscovery nell'organizzazione (un membro del sottogruppo di amministratore di eDiscovery nel gruppo di ruoli di gestione di eDiscovery) deve rendere disponibile il modello nei casi di eDiscovery avanzati.

1. Nel centro sicurezza & conformità, accedere a **eDiscovery > Advanced eDiscovery**.

2. Nella Home page di **Advanced eDiscovery** , nel riquadro **Impostazioni** , fare clic su **Configura impostazioni di analisi globali**.

   ![Selezionare "Configura funzionalità sperimentali"](../media/AeDExperimentalFeatures.png)

3. Nella scheda **impostazioni di analisi** , selezionare **Gestisci impostazione privilegio avvocato-client**.

4. Nella pagina del riquadro a comparsa dei **privilegi avvocato-client** , utilizzare l'interruttore per attivare la funzionalità e quindi selezionare **Salva**.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Passaggio 2: caricare un elenco di avvocati (facoltativo)

Per sfruttare al meglio il modello di rilevamento dei privilegi avvocato-client e utilizzare i risultati del **procuratore** o del rilevamento **potenzialmente privilegiato** descritto in precedenza, si consiglia di caricare un elenco di indirizzi di posta elettronica per gli avvocati e gli addetti legali che lavorano per la propria organizzazione. 

Per caricare un elenco di avvocati per l'utilizzo da parte del modello di rilevamento dei privilegi avvocato-client:

1. Creare un file. csv (senza una riga di intestazione) e aggiungere l'indirizzo di posta elettronica per ogni persona appropriata su una riga distinta. Salvare il file nel computer locale.

2. Nella Home page di **Advanced eDiscovery** fare clic su **Configura caratteristiche sperimentali**nella sezione **Impostazioni** e quindi selezionare **Gestisci impostazione privilegio avvocato-client**.

   Viene visualizzata la pagina **Privilege avvocato-client** e l'interruttore di **rilevamento dei privilegi del procuratore-client** è attivato.

   ![Pagina del riquadro a comparsa dei privilegi avvocato-cliente](../media/AeDUploadAttorneyList.png)

3. Selezionare **Sfoglia** e quindi individuare e selezionare il file. csv creato nel passaggio 1.

4. Selezionare **Salva** per caricare l'elenco degli avvocati.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Utilizzare il modello di rilevamento dei privilegi avvocato-client

Seguire la procedura descritta in questa sezione per utilizzare il rilevamento dei privilegi di avvocato-client per i documenti in un set di revisione.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Passaggio 1: creare un gruppo di smart tag con il modello di rilevamento dei privilegi avvocato-client

Uno dei modi principali per visualizzare i risultati del rilevamento dei privilegi del procuratore-client nel processo di revisione consiste nell'utilizzare un gruppo di smart tag. Un gruppo di smart tag indica i risultati del rilevamento dei privilegi avvocato-client e Visualizza i risultati in linea accanto ai tag in un gruppo di smart tag. In questo modo è possibile identificare rapidamente i documenti potenzialmente privilegiati durante la revisione del documento. Inoltre, è possibile utilizzare i tag del gruppo smart tag per contrassegnare i documenti come privilegiati o non privilegiati. Per ulteriori informazioni sugli smart tag, vedere [configurare gli smart tag in Advanced eDiscovery](smart-tags.md).

1. Nel set di revisione che contiene i documenti analizzati nel passaggio 1, selezionare **Gestisci Revisione set** e quindi selezionare **Gestisci Tag**.
 
2. In **tag**selezionare l'elenco a discesa accanto a **Aggiungi gruppo** e quindi fare clic su **Aggiungi gruppo smart tag**.

   ![Seleziona "Aggiungi gruppo smart tag"](../media/AeDCreateSmartTag.png)

3. Nella pagina **scegliere un modello per la smart tag** scegliere **Seleziona** accanto a **privilegio avvocato-client**.

   Viene visualizzato un gruppo di tag denominato **procuratore-Client Privilege** . Contiene due tag figlio denominati **positivi** e **negativi**, che corrispondono ai possibili risultati prodotti dal modello.

   ![Gruppo smart tag del privilegio avvocato-cliente](../media/AeDAttorneyClientSmartTagGroup.png)

3. Rinominare il gruppo e i tag dei tag in base alle proprie esigenze per la revisione. Ad esempio, è possibile rinominare **positivamente** con **privilegi** e **negativi** a **non privilegiati**.

### <a name="step-2-analyze-a-review-set"></a>Passaggio 2: analizzare un set di Revisione

Quando si analizzano i documenti in un set di revisione, viene eseguito anche il modello di rilevamento dei privilegi di avvocato-client e le proprietà corrispondenti (descritte in [modalità di funzionamento?](#how-does-it-work) verranno aggiunte a tutti i documenti del set di revisione. Per ulteriori informazioni sull'analisi dei dati nel set di revisione, vedere [analyze data in a Review set in Advanced eDiscovery](analyzing-data-in-review-set.md).

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Passaggio 3: utilizzare il gruppo smart tag per la revisione dei contenuti con privilegi

Dopo aver analizzato il set di revisione e aver configurato gli smart tag, il passaggio successivo consiste nel rivedere i documenti. Se il modello ha determinato che il documento è potenzialmente privilegiato, lo smart tag corrispondente nel **Pannello di tagging** indicherà i risultati seguenti ottenuti dal rilevamento dei privilegi avvocato-client:

- Se il documento contiene contenuto che potrebbe essere di natura legale, il **contenuto legale** dell'etichetta viene visualizzato accanto allo smart tag corrispondente, che in questo caso è il tag **positivo** predefinito.

- Se il documento ha un partecipante che si trova nell'elenco di avvocati dell'organizzazione, viene visualizzato il **procuratore** di etichette accanto allo smart tag corrispondente (che in questo caso è anche il tag **positivo** predefinito).

- Se il documento contiene contenuto che potrebbe essere di natura legale *e* ha un partecipante trovato nell'elenco degli avvocati, vengono visualizzati sia il **contenuto legale** che le etichette del **procuratore** . 

Se il modello determina che un documento non contiene contenuto di natura legale o che non contiene un partecipante all'elenco degli avvocati, non viene visualizzata alcuna etichetta nel pannello di tagging.

Ad esempio, nelle schermate seguenti vengono visualizzati due documenti. Il primo contiene contenuto di natura legale e ha un partecipante trovato nell'elenco degli avvocati. La seconda non contiene né e pertanto non Visualizza etichette.

![Documento con etichette legali e di contenuto legale](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento senza etichette](../media/AeDTaggingPanelNegative.png)

Dopo aver esaminato un documento per verificare se contiene contenuto con privilegi, è possibile contrassegnare il documento con il tag appropriato.
