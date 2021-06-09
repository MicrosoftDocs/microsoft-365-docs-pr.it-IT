---
title: Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Usa il modello di rilevamento dei privilegi avvocato-client per usare il rilevamento basato su machine learning del contenuto con privilegi durante la revisione del contenuto in un Advanced eDiscovery caso.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358042"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Configurare il rilevamento dei privilegi avvocato-client in Advanced eDiscovery

Un aspetto importante e dissario della fase di revisione di qualsiasi processo di eDiscovery è la revisione dei documenti per il contenuto con privilegi. Advanced eDiscovery consente di rilevare il contenuto con privilegi basato sull'apprendimento automatico per rendere più efficiente questo processo. Questa funzionalità è denominata *rilevamento privilegi avvocato-client.*

## <a name="how-does-it-work"></a>Come funziona?

Quando il rilevamento dei privilegi avvocato-client è abilitato, tutti i documenti [in](analyzing-data-in-review-set.md) un set di revisione verranno elaborati dal modello di rilevamento dei privilegi avvocato-client quando si analizzano i dati nel set di revisione. Il modello cerca due elementi:

- Contenuto con privilegi: il modello utilizza l'apprendimento automatico per determinare la probabilità che il documento contenga contenuto di natura legale.

- Partecipanti: nell'ambito della configurazione del rilevamento dei privilegi avvocato-client, è necessario inviare un elenco di avvocati per l'organizzazione. Il modello confronta quindi i partecipanti al documento con l'elenco degli avvocati per determinare se un documento ha almeno un partecipante avvocato.

Il modello produce le tre proprietà seguenti per ogni documento:

- **AttorneyClientPrivilegeScore:** Probabilità che il documento sia di natura legale. i valori per il punteggio sono compresi tra **0** e **1**.

- **HasAttorney:** Questa proprietà è impostata su **true** se uno dei partecipanti al documento è elencato nell'elenco degli avvocati. in caso contrario, il valore è **false**. Il valore viene impostato su **false** anche se l'organizzazione non ha caricato un elenco di avvocati.

- **IsPrivilege:** Questa proprietà è impostata su **true** se il valore di **AttorneyClientPrivilegeScore** è superiore alla soglia o se il documento ha un partecipante avvocato;  in caso contrario, il valore è impostato su **false**.

Queste proprietà (e i valori corrispondenti) vengono aggiunte ai metadati dei file dei documenti in un set di revisioni, come illustrato nello screenshot seguente:

![Proprietà dei privilegi attorney-client visualizzate nei metadati dei file](../media/AeDAttorneyClientPrivilegeMetadata.png)

Queste tre proprietà sono disponibili anche per la ricerca all'interno di un set di recensioni. Per ulteriori informazioni, vedere [Query the data in a review set](review-set-search.md).

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Configurare il modello di rilevamento dei privilegi avvocato-client

Per abilitare il modello di rilevamento dei privilegi avvocato-client, l'organizzazione deve attivarlo e quindi caricare un elenco di avvocati.

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>Passaggio 1: attivare il rilevamento dei privilegi avvocato-client

Una persona che è un amministratore di eDiscovery nell'organizzazione (membro del sottogruppo Amministratore di eDiscovery nel gruppo di ruoli Manager eDiscovery) deve rendere il modello disponibile nei casi Advanced eDiscovery.

1. Nel Centro sicurezza & conformità passare a **eDiscovery > Advanced eDiscovery**.

2. Nella home **page Advanced eDiscovery,** nel **riquadro** Impostazioni, fare clic **su Configura impostazioni di analisi globali.**

   ![Selezionare "Configura funzionalità sperimentali"](../media/AeDExperimentalFeatures.png)

3. Nella scheda **Impostazioni analisi** selezionare Gestisci **impostazione privilegio avvocato-client.**

4. Nella pagina a comparsa **Privilegio avvocato-cliente**, usare l'interruttore per attivare la funzionalità, quindi selezionare **Salva**.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Passaggio 2: Upload un elenco di avvocati (facoltativo)

Per sfruttare al meglio il modello di rilevamento dei privilegi avvocato-client e utilizzare i risultati del rilevamento Has **Attorney** o **Potentially Privileged** descritto in precedenza, è consigliabile caricare un elenco di indirizzi di posta elettronica per gli avvocati e il personale legale che lavorano per l'organizzazione. 

Per caricare un elenco di avvocati per l'utilizzo da parte del modello di rilevamento dei privilegi avvocato-client:

1. Creare un file CSV (senza una riga di intestazione) e aggiungere l'indirizzo di posta elettronica di ogni persona pertinente in una riga separata. Salvare il file nel computer locale.

2. Nella **home page Advanced eDiscovery,** nel riquadro **Impostazioni,** selezionare **Configura** funzionalità sperimentali e quindi selezionare **Gestisci impostazione privilegio avvocato-client.**

   Viene **visualizzata la pagina Privilegi avvocato-client** e l'interruttore rilevamento privilegi **avvocato-client** è attivato.

   ![Pagina a comparsa privilegi avvocato-client](../media/AeDUploadAttorneyList.png)

3. Selezionare **Sfoglia** e quindi individuare e selezionare il file .csv creato nel passaggio 1.

4. Seleziona **Salva** per caricare l'elenco degli avvocati.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Usare il modello di rilevamento dei privilegi avvocato-client

Seguire i passaggi descritti in questa sezione per usare il rilevamento dei privilegi avvocato-client per i documenti in un set di revisione.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Passaggio 1: Creare un gruppo di smart tag con il modello di rilevamento dei privilegi avvocato-client

Uno dei modi principali per visualizzare i risultati del rilevamento del privilegio avvocato-cliente nel processo di revisione consiste nell'utilizzare un gruppo di smart tag. Un gruppo di smart tag indica i risultati del rilevamento del privilegio avvocato-cliente e mostra i risultati in linea accanto ai tag nel gruppo di smart tag. Ciò consente di identificare rapidamente i documenti potenzialmente privilegiati durante la revisione dei documenti. Inoltre, è anche possibile usare i tag nel gruppo di smart tag per contrassegnare i documenti come con privilegi o senza privilegi. Per ulteriori informazioni sugli smart tag, vedere [Set up smart tags in Advanced eDiscovery](smart-tags.md).

1. Nel set di revisioni contenente i documenti analizzati nel passaggio 1, selezionare **Gestisci** set di revisioni e quindi **Selezionare Gestisci tag.**
 
2. In **Tag** selezionare l'elenco a discesa accanto a **Aggiungi gruppo** e quindi selezionare Aggiungi gruppo di smart **tag.**

   ![Selezionare "Aggiungi gruppo di smart tag"](../media/AeDCreateSmartTag.png)

3. Nella pagina **Scegliere un modello per lo smart tag** scegliere **Seleziona** accanto a **Privilegio avvocato-client.**

   Viene visualizzato un gruppo **di tag denominato Attorney-client privilege.** Contiene due tag figlio denominati **Positive** e **Negative**, che corrispondono ai possibili risultati prodotti dal modello.

   ![Gruppo di smart tag privilegi avvocato-client](../media/AeDAttorneyClientSmartTagGroup.png)

3. Rinominare il gruppo di tag e i tag in base alle esigenze della revisione. Ad esempio, è possibile rinominare **Positivo** in **Privilegiato** e **Negativo** in **Non privilegiato**.

### <a name="step-2-analyze-a-review-set"></a>Passaggio 2: analizzare un set di recensioni

Quando si analizzano i documenti in un set di revisione, verrà eseguito anche il modello di rilevamento dei privilegi avvocato-client e le proprietà corrispondenti (descritte in [Come funziona?](#how-does-it-work) verranno aggiunte a ogni documento nel set di revisioni. Per ulteriori informazioni sull'analisi dei dati nel set di revisioni, vedere [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Passaggio 3: Utilizzare il gruppo di smart tag per la revisione del contenuto con privilegi

Dopo aver analizzato il set di revisione e aver configurato gli smart tag, il passaggio successivo consiste nel rivedere i documenti. Se il modello ha determinato che il documento è potenzialmente privilegiato, lo smart tag corrispondente nel pannello **Tagging** indicherà i risultati seguenti prodotti dal rilevamento dei privilegi avvocato-client:

- Se il documento ha contenuto che può  essere di natura legale, l'etichetta Contenuto legale viene visualizzata accanto al corrispondente smart tag (che in questo caso è il tag **Positivo** predefinito).

- Se il documento include un partecipante che si trova  nell'elenco degli avvocati dell'organizzazione, l'etichetta Avvocato viene visualizzata accanto allo smart tag corrispondente (che in questo caso è anche il tag **Positivo** predefinito).

- Se il documento contiene contenuto che può essere di natura legale e  che  un partecipante è presente nell'elenco degli avvocati, vengono visualizzati sia il contenuto legale che le etichette dell'avvocato.  

Se il modello determina che un documento non contiene contenuto di natura legale o che non contiene un partecipante nell'elenco degli avvocati, nel riquadro di tagging non viene visualizzata alcuna etichetta.

Ad esempio, le schermate seguenti mostrano due documenti. Il primo contiene contenuti di natura legale e con un partecipante presente nell'elenco degli avvocati. Il secondo non contiene nessuno dei due e pertanto non visualizza alcuna etichetta.

![Documento con etichette di contenuto legale e legale](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento senza etichette](../media/AeDTaggingPanelNegative.png)

Dopo aver esaminato un documento per verificare se contiene contenuto con privilegi, è possibile contrassegnarlo con il tag appropriato.
