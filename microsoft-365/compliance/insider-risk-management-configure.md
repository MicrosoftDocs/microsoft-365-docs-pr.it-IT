---
title: Informazioni introduttive sulla gestione dei rischi Insider (Preview)
description: Configurare la gestione dei rischi Insider nell'organizzazione.
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: aea8c4a8dff0581b9286880d646728eb9a8dd555
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41590667"
---
# <a name="get-started-with-insider-risk-management-preview"></a>Informazioni introduttive sulla gestione dei rischi Insider (Preview)

Utilizzare i criteri di gestione dei rischi Insider per identificare le attività rischiose e gli strumenti di gestione per eseguire azioni sugli avvisi di rischio nell'organizzazione. Per ulteriori informazioni su come i criteri di rischio Insider consentono di gestire i rischi nell'organizzazione, vedere [Insider Risk Management in Microsoft 365](insider-risk-management.md).

>[!IMPORTANT]
>La soluzione Microsoft 365 Insider Risk Management fornisce un'opzione tenant level per consentire ai clienti di facilitare la governance interna a livello di utente. Gli amministratori a livello di tenant possono configurare le autorizzazioni per consentire l'accesso a questa soluzione per i membri dell'organizzazione e configurare i connettori di dati nel centro conformità di Microsoft 365 per importare i dati rilevanti a supporto dell'identificazione a livello di utente potenzialmente attività rischiosa. I clienti possono essere calcolati dall'amministratore e resi disponibili ad altri utenti dell'organizzazione, in base al comportamento, al carattere o alle prestazioni del singolo utente.

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare a utilizzare la gestione dei rischi Insider, è necessario confermare l'abbonamento a Microsoft 365. Gli utenti inclusi nei criteri di gestione dei rischi Insider devono disporre di una licenza di conformità Microsoft 365 E5 o essere inclusi in un abbonamento a Microsoft 365 E5.

Se non si dispone di un piano Microsoft 365 Enterprise E5 esistente e si desidera tentare la gestione dei rischi Insider, è possibile [aggiungere microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) all'abbonamento a Office 365 esistente oppure [iscriversi a una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Microsoft 365 Enterprise E5.

Completare questi passaggi per configurare e usare gestione dei rischi Insider nell'organizzazione Microsoft 365:

## <a name="step-1-required-enable-permissions-for-insider-risk-management"></a>Passaggio 1 (obbligatorio): abilitare le autorizzazioni per la gestione dei rischi Insider

Sono disponibili quattro ruoli di autorizzazione che consentono di configurare e gestire la gestione dei rischi Insider. Per continuare con questi passaggi di configurazione, gli amministratori dei tenant devono prima assegnare il ruolo di **amministratore di gestione dei rischi Insider** .

| **Ruolo** | **Autorizzazioni di ruolo** |
| ---- | ---------------- |
| **Amministratore di gestione dei rischi Insider** | Creare, leggere, aggiornare ed eliminare i criteri di gestione dei rischi Insider <br> Creare, leggere, aggiornare ed eliminare le autorizzazioni e i ruoli di gestione dei rischi Insider |
| **Analisti di gestione dei rischi Insider** | Accesso a tutti gli avvisi, i casi e le notifiche di gestione dei rischi Insider |
| **Investigatori della gestione dei rischi Insider** | Accesso a tutti gli avvisi di gestione dei rischi Insider, casi, notifiche e Esplora contenuto per tutti i casi |
| **Visualizzatore di gestione dei rischi Insider** | Accesso in sola visualizzazione a tutti gli avvisi, casi, notifiche e Esplora contenuti di gestione dei rischi Insider per tutti i casi |

A seconda della struttura del team di gestione della conformità, sono disponibili due opzioni di autorizzazione per configurare i ruoli per gestire le funzionalità di gestione dei rischi Insider. Scegliere una delle seguenti opzioni di gestione dei ruoli quando si configura la gestione dei rischi Insider:

1. **Utilizzare il gruppo di ruoli di gestione dei rischi Insider predefinito**: utilizzare questo gruppo di ruoli per gestire la gestione dei rischi Insider per la propria organizzazione aggiungendo tutti gli account utente per gli amministratori, gli analisti e gli investigatori designati in un singolo gruppo. Questo gruppo di ruoli contiene tutti i ruoli di autorizzazione di gestione dei rischi Insider. Questo è il modo più semplice per iniziare rapidamente con la gestione dei rischi Insider ed è una buona misura per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti separati.
2. **Creare gruppi diversi per diversi ruoli di gestione**: per le organizzazioni che devono separare le autorizzazioni per la configurazione e la gestione dei rischi Insider Management, è necessario creare nuovi gruppi di ruoli e assegnare i ruoli e gli utenti adatti ai nuovi gruppi. Ad esempio, se si desiderano autorizzazioni diverse per l'analisi e le indagini di gestione dei rischi Insider, è necessario creare un gruppo per gli analisti e un gruppo separato per gli investigatori. Per ogni gruppo, è possibile assegnare i ruoli necessari per queste responsabilità e quindi aggiungere gli utenti che devono essere assegnati al gruppo.

Se si decide di configurare diversi gruppi per ruoli diversi, utilizzare la tabella seguente per assegnare i ruoli necessari a ciascun gruppo di ruoli:

| **Esempio di gruppo** | **Ruoli necessari** |
| ---- | ---------------- |
| **Amministratori** | Ruolo di *amministratore di gestione dei rischi Insider* |
| **Analisti** | Ruolo degli *analisti di gestione dei rischi Insider* <br> Ruolo di *gestione dei casi* |
| **Investigatori** | Ruolo *investigatori di gestione dei rischi Insider* <br> Ruolo di *gestione dei casi* |

### <a name="option-1-add-users-to-the-insider-risk-management-role-group"></a>Opzione 1: aggiungere gli utenti al gruppo di ruoli di gestione dei rischi Insider

Se si desidera utilizzare un gruppo di ruoli per tutti gli utenti che configurano e gestiscono Insider Risk Management, completare i passaggi seguenti per aggiungere gli utenti al gruppo di ruoli di **gestione dei rischi Insider** predefinito:

1. Accedere [https://protection.office.com/permissions](https://protection.office.com/permissions) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro sicurezza e conformità di Microsoft Office 365 accedere a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare il gruppo di ruoli *gestione dei rischi Insider* , quindi selezionare **modifica gruppo di ruoli**.

4. Selezionare **Scegli membri** nel riquadro di spostamento a sinistra, quindi selezionare **modifica**.

5. Selezionare **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Selezionare **Aggiungi**, quindi fare clic su **fine**.

7. Selezionare **Salva** per aggiungere gli utenti al gruppo di ruoli. Selezionare **Chiudi** per completare la procedura.

### <a name="option-2-create-a-new-role-group"></a>Opzione 2: creare un nuovo gruppo di ruoli

Se è necessario creare gruppi di ruoli distinti per ruoli di gestione diversi, completare i passaggi seguenti per creare ogni nuovo gruppo:

1. Accedere [https://protection.office.com/permissions](https://protection.office.com/permissions) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro sicurezza e conformità di Microsoft Office 365 accedere a **autorizzazioni**. Selezionare il collegamento per visualizzare e gestire i ruoli in Office 365.

3. Selezionare **Crea**.

4. Nel campo **nome** assegnare un nome descrittivo al nuovo gruppo di ruoli.  Select **Next**. 

5. Selezionare **Scegli ruoli** e quindi **Aggiungi**. Selezionare la casella di controllo per i ruoli che è necessario assegnare. Ad esempio, se questo gruppo è per gli analisti dei rischi Insider, selezionare il ruolo degli *analisti di gestione dei rischi Insider* e il ruolo di *gestione dei casi* , quindi fare clic su **Aggiungi** e **fatti**.  Select **Next**. 

6. Selezionare **Scegli membri** e quindi **Aggiungi**. Selezionare la casella di controllo per tutti gli utenti e i gruppi che si desidera creare criteri e gestire i messaggi con le corrispondenze di criteri, quindi fare clic su **Aggiungi** e **Chiudi**.  Select **Next**. 

7. Selezionare **Crea gruppo di ruoli** per terminare.

Per ulteriori informazioni sui gruppi di ruoli e sulle autorizzazioni, vedere [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-optional-configure-the-microsoft-365-human-resources-data-connector"></a>Passaggio 2 (facoltativo): configurare il connettore dei dati per le risorse umane di Microsoft 365

Gestione dei rischi Insider supporta l'importazione di dati di utenti e log importati da piattaforme di gestione dei rischi di terze parti. Il connettore dati risorse umane (HR) di Microsoft 365 consente di inserire i dati delle risorse umane da file CSV, tra cui la terminazione degli utenti e le date dell'ultima occupazione. Questi dati consentono di guidare gli indicatori di avviso nei criteri di gestione dei rischi Insider ed è una parte importante della configurazione della copertura di gestione a rischio completo nell'organizzazione.

Vedere l'argomento [set up a Connector to Import HR data](import-hr-data.md) for Step-by-Step Guide to configure the Microsoft 365 HR Connector for Your Organization. Dopo aver configurato il connettore HR, tornare a questi passaggi di configurazione.

>[!IMPORTANT]
>Se si prevede di configurare un criterio utilizzando il modello di *furto dei dati* per i dipendenti in partenza, è necessario configurare il connettore HR per utilizzare le funzionalità di rilevamento completo del segnale del modello di criteri. Se si configurano più connettori HR per la propria organizzazione, la gestione dei rischi Insider tirerà automaticamente gli indicatori da tutti i connettori HR.

## <a name="step-3-optional-configure-data-loss-prevention-dlp-policies"></a>Passaggio 3 (facoltativo): configurare i criteri di prevenzione della perdita di dati (DLP)

Gestione dei rischi Insider supporta l'utilizzo di criteri DLP per identificare l'esposizione intenzionale o accidentale di informazioni riservate a parti indesiderate. Quando si configura un criterio di gestione dei rischi Insider con il modello di *perdita di dati* , è necessario assegnare un criterio DLP specifico al criterio. Questo criterio consente di guidare gli indicatori di avviso per le informazioni riservate è una parte importante della configurazione della copertura di gestione a rischio completo nell'organizzazione.

Per informazioni dettagliate su come configurare i criteri DLP per la propria organizzazione, vedere l'argomento [creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) . Dopo aver configurato un criterio DLP, tornare a questi passaggi di configurazione.

>[!IMPORTANT]
>Se si prevede di configurare un criterio utilizzando il modello di *perdita di dati* , sarà necessario configurarne almeno uno per l'utilizzo delle funzionalità di rilevamento completo del segnale del modello di criteri. Se si configurano più criteri DLP per l'organizzazione, sarà necessario assegnare un criterio di gestione dei rischi Insider per ogni criterio DLP.

## <a name="step-4-required-create-an-insider-risk-management-policy"></a>Passaggio 4 (obbligatorio): creare un criterio di gestione dei rischi Insider

I criteri di gestione dei rischi Insider includono gli utenti assegnati e definiscono i tipi di indicatori di rischio configurati per gli avvisi. Prima che le attività possano attivare gli avvisi, è necessario configurare un criterio.

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Selezionare **create Policy** per aprire la procedura guidata per i criteri
3. Nella pagina **nuovo criterio di rischio Insider** completare i seguenti campi:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il criterio
    - **Description (facoltativo)**: immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio)**: selezionare uno dei [modelli di criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio sono monitorati dal criterio.

    >[!IMPORTANT]
    >Se si seleziona il modello per le *perdite di dati* , sarà necessario configurare almeno un criterio DLP che verrà assegnato in un secondo momento nella procedura guidata. Se si seleziona il modello di *furto dei dati* per i dipendenti in partenza, è necessario configurare il connettore HR per utilizzare le funzionalità di rilevamento completo del segnale del modello di criteri.

4. Fare clic su **Avanti** per continuare.
5. Nella pagina **utenti** selezionare **Aggiungi utente o gruppo** per definire quali utenti sono inclusi nel criterio oppure selezionare **tutti gli utenti e i gruppi abilitati alla posta elettronica** . Fare clic su **Avanti** per continuare.
6. Nella pagina **specificare il contenuto di cui definire la priorità (facoltativa)** , è possibile assegnare le origini a priorità per le attività degli utenti a rischio:
    - **Siti di SharePoint**: selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo di informazioni riservate**: selezionare **Aggiungi tipo di informazioni riservate** e selezionare i tipi di sensibilità che si desidera impostare come priorità. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - **Etichette di riservatezza**: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette che si desidera impostare come priorità. Ad esempio, *"confidenziale"* e *"segreto"*.
7. Fare clic su **Avanti** per continuare.
8. Nella pagina **Scegli** gli indicatori di avviso verranno visualizzati gli indicatori inclusi nel modello scelto per questo criterio. Se all'inizio della procedura guidata è stato selezionato il modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** .
9. Nella pagina **selezione finestra di monitoraggio** vengono definite le condizioni per la [finestra di monitoraggio](insider-risk-management-policies.md#monitoring-windows) per il criterio. Configurare le finestre di monitoraggio in base alle esigenze.
10. Fare clic su **Avanti** per continuare.
11. Nella pagina **Revisione** rivedere le impostazioni selezionate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per creare e attivare il criterio.

Dopo aver completato questa procedura per creare il primo criterio di gestione dei rischi Insider, si inizierà a ricevere avvisi da indicatori di attività dopo circa 24 ore. Configurare ulteriori criteri in base alle istruzioni fornite nel passaggio 4 di questo argomento o la procedura descritta in [creare un nuovo criterio di rischio Insider](insider-risk-management-policies.md#create-a-new-policy).
