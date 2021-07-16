---
title: Archiviare i dati dalla piattaforma CellTrust SL2 a Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Informazioni su come configurare e usare un connettore dati CellTrust SL2 per importare e archiviare i dati delle comunicazioni mobili.
ms.openlocfilehash: 191160921c9e949aa7b82520d72dc7a18bfb26ef
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453973"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365"></a>Archiviare i dati da CellTrust SL2 a Microsoft 365

CellTrust SL2 acquisisce i dati delle comunicazioni mobili e si integra con le tecnologie di archiviazione leader per soddisfare i requisiti di individuazione elettronica per normative come FINRA, HIPAA, FOIA e TCPA. Il connettore dati SL2 importa gli elementi di comunicazione mobile Microsoft 365. In questo articolo viene descritto il processo di integrazione di SL2 con Microsoft 365 utilizzando cellTrust SL2 Data Connector per l'archiviazione. Il completamento di questo processo presuppone che tu abbia sottoscritto il servizio CellTrust SL2 e abbia familiarità con l'architettura SL2. Per informazioni su SL2, vedere <www.celltrust.com>.

Dopo l'importazione dei dati nelle cassette postali degli utenti in Microsoft 365, è possibile applicare funzionalità di conformità Microsoft 365 quali conservazione per controversia legale, eDiscovery, criteri di conservazione Microsoft 365 e conformità delle comunicazioni. L'utilizzo di CellTrust SL2 Data Connector per importare e archiviare i dati in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>Panoramica dell'archiviazione con cellTrust SL2 Data Connector

La piattaforma SL2 di CellTrust acquisisce i dati di comunicazione da più origini. Le origini dati SL2 sono P2P (Person-to-Person) o Application-to-Person (A2P). Il processo descritto in questo articolo riguarda solo le origini dati P2P. Per tutte le origini dati P2P, almeno una parte della collaborazione è un utente SL2 sottoscritto al servizio SL2. Nella panoramica seguente viene illustrato il processo di utilizzo del connettore dati SL2 CellTrust in Microsoft 365.

![Flusso di lavoro di archiviazione per il servizio CellTrust SL2](../media/CellTrustSL2ConnectorWorkflow.png)

1. Gli utenti SL2 inviano e ricevono dati da e verso i servizi SL2 nel cloud Microsoft Azure cloud.

2. L'organizzazione ha un dominio SL2 nell'ambiente del servizio cloud SL2 di CellTrust. Il dominio può avere una o più unità organizzative. Il servizio cloud SL2 trasferisce i dati in un'area altamente sicura nella piattaforma Microsoft Azure, in modo che i dati non lascino mai l'Microsoft Azure ambiente. A seconda del piano SL2 (Enterprise, SMB o Government), il dominio è ospitato in Microsoft Azure Global o Microsoft Azure Government.

3. Dopo aver creato il connettore dati SL2 CellTrust, il dominio e le unità organizzative (indipendentemente dal piano SL2), iniziare a inviare dati Microsoft 365. Il feed di dati è strutturato per supportare la creazione di report in base alle origini dati, alle unità organizzative o al dominio da solo. Di conseguenza, l'organizzazione ha bisogno di un solo connettore per alimentare tutte le origini dati Microsoft 365.

4. Il connettore crea una cartella in ogni utente mappato con una licenza Office 365 appropriata intitolata **CellTrust SL2.** Questo mapping connette un utente di CellTrust SL2 a una Office 365 cassetta postale utilizzando un indirizzo di posta elettronica. Se un ID utente in CellTrust SL2 non ha alcuna corrispondenza in Office 365, i dati dell'utente non verranno archiviati.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

- Verificare di disporre di un dominio nell'ambiente del servizio cloud CellTrust SL2. Per ulteriori informazioni su come ottenere un dominio SL2 di produzione o di prova, [contattare CellTrust.](https://www.celltrust.com/contact-us/#form)

- Ottenere le credenziali per accedere all'account amministratore per il dominio SL2.

- L'utente che crea il connettore di dati CellTrust SL2 nel passaggio 1 (e lo completa nel passaggio 3) deve essere assegnato al ruolo Esportazione importazione cassette postali in Exchange Online. Questo ruolo è necessario per aggiungere connettori nella pagina **Connettori** dati nell'Centro conformità Microsoft 365. Per impostazione predefinita, questo ruolo non viene assegnato a un gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-create-a-celltrust-sl2-connector"></a>Passaggio 1: Creare un connettore SL2 CellTrust

Il primo passaggio consiste nel creare un connettore dati nell'Centro conformità Microsoft 365.

1. Passare a <https://compliance.microsoft.com> e fare clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella scheda **Panoramica** fare clic su **Filtro** e selezionare **Per CellTrust** e quindi applicare il filtro.

   ![Configurare il filtro per visualizzare i connettori CellTrust](../media/DataConnectorsFilter.png)

3. Fare **clic su CellTrust SL2 (anteprima).**

4. Nella pagina **Descrizione del prodotto CellTrust SL2 (anteprima)** fare clic **su Aggiungi connettore**.

5. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

6. Immettere un nome univoco che identifichi il connettore e quindi fare clic su **Avanti.** Il nome immesso identificherà il connettore nella **pagina Connettori dati** dopo la creazione.

7. Nella pagina **Accedi al tuo account CellTrust** fai clic su Accedi a **CellTrust.** Verrà reindirizzato al portale **CellTrust** per Microsoft 365 in una nuova finestra del browser.

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>Passaggio 2: Selezionare i domini o le unità organizzative da archiviare

Il passaggio successivo consiste nell'accedere a un account amministratore per il dominio CellTrust SL2 e selezionare i domini e le unità organizzative da archiviare in Microsoft 365.

1. Nella pagina CellTrust **Microsoft 365 Connector** selezionare l'ambiente nel servizio cloud SL2 per visualizzare una pagina di accesso.

   In genere dovrebbe essere visualizzata un'opzione che rappresenta l'ambiente. Tuttavia, se si dispone di domini in più di un ambiente, saranno disponibili opzioni per ogni ambiente. Dopo aver fatto una selezione, sarai reindirizzato alla pagina di accesso SL2.

2. Accedere con le credenziali dell'account di amministratore di dominio o di unità organizzativa.

   Se si accede come amministratore di dominio SL2, verranno visualizzati il nome del dominio e le unità organizzative in tale dominio. Se non si dispone di unità organizzative, viene visualizzato solo il nome del dominio. Se si accede come amministratore dell'unità organizzativa, viene visualizzato solo il nome dell'unità organizzativa.

3. Abilitare le unità aziendali che si desidera archiviare. La selezione del dominio non selezionerà automaticamente le unità organizzative. È necessario abilitare separatamente ogni unità organizzativa per archiviarla.

   ![Abilitare le unità organizzative per l'archiviazione](../media/EnableCellTrustOUs.png)

4. Al termine delle selezioni, chiudere la finestra del browser e tornare alla pagina della procedura guidata in Centro conformità Microsoft 365. Dopo alcuni secondi, la procedura guidata passa automaticamente al passaggio successivo del mapping degli utenti.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Passaggio 3: mappare gli utenti e completare la configurazione del connettore

L'ultimo passaggio consiste nel mappare gli utenti e completare la configurazione del connettore nella Centro conformità Microsoft 365.

1. Nella pagina **Mapping utenti** selezionare **Abilita** mapping automatico utenti se l'indirizzo di posta elettronica per gli utenti è lo stesso sia in SL2 che Microsoft 365. In caso contrario, è consigliabile caricare manualmente gli indirizzi di posta elettronica degli utenti caricando un file CSV che mappa l'indirizzo SL2 degli utenti al Microsoft 365 indirizzo.

2. Fare **clic su** Avanti, rivedere le impostazioni e quindi fare clic su **Fine** per creare il connettore.

   Il nuovo connettore viene aggiunto all'elenco nella **pagina Connettori dati.**

## <a name="get-help-from-celltrust"></a>Ottenere assistenza da CellTrust

Per informazioni dettagliate sulla configurazione di un connettore dati CellTrust SL2, vedere la pagina [CellTrust Customer Support.](https://www.celltrust.com/contact-us/#support)

## <a name="more-information"></a>Altre informazioni

- Un amministratore di dominio può configurare un connettore per il dominio o qualsiasi unità organizzativa in tale dominio. Se si utilizza l'account amministratore dell'unità organizzativa, è possibile configurare solo un connettore per tale unità organizzativa specifica.

- Per completare correttamente i passaggi precedenti, devi disporre di una licenza Microsoft 365 E5 e disporre dei diritti di amministratore Microsoft Office appropriati.

- Per testare il nuovo connettore, invia un SMS usando l'app per dispositivi mobili SL2 o dal portale SL2. Passare alla cassetta Microsoft 365 e aprire la **cartella CellTrust SL2** nella cartella Posta in arrivo. La visualizzazione dei messaggi di testo nella cassetta postale potrebbe richiedere alcuni minuti.

- Molte leggi e normative richiedono che la comunicazione elettronica sia conservata in modo tale che, quando richiesto, possa essere prodotto come prova. Electronic Discovery (eDiscovery) viene utilizzato per conformarsi alla produzione di comunicazioni elettroniche. Enterprise Le soluzioni di archiviazione delle informazioni sono progettate per eseguire eDiscovery e offrono funzionalità quali la gestione dei criteri di conservazione, la classificazione dei dati e la supervisione del contenuto. Microsoft 365 offre una soluzione di conservazione a lungo termine per la conformità alle normative e agli standard che influiscono sull'organizzazione.

- Il termine *archiviazione* utilizzato in questo documento si riferisce all'archiviazione nel contesto di utilizzo all'interno di una soluzione Enterprise Information Archiving (EIA). Le soluzioni EIA dispongono di funzionalità di eDiscovery che producono documenti per procedimenti legali, controversie legali, controlli e indagini. L'archiviazione nel contesto del backup e del ripristino utilizzato per il ripristino di emergenza e la continuità aziendale non è l'uso previsto del termine in questo documento.
