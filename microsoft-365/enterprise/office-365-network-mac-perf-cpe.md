---
title: Routing di rete informato di Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Routing di rete informato di Microsoft 365
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717588"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Routing di rete informato di Microsoft 365 (anteprima)

Il routing di rete informato è una funzionalità che integra varie applicazioni di Microsoft 365 con soluzioni SD-WAN (Software Defined Network) di terze parti per ottimizzare e migliorare la connettività di rete agli endpoint del servizio Microsoft. La connettività SD-WAN ottimizzata può comportare un miglioramento delle prestazioni e delle esperienze utente.

>[!IMPORTANT]
>Il routing di rete informato di Microsoft 365 è attualmente in stato di anteprima. Per altre informazioni su questa anteprima, incluse le indicazioni per ricevere assistenza, vedere Anteprima pubblica del routing di rete informato di [Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=2151565)

## <a name="overview"></a>Panoramica

Il routing di rete informato fornisce un canale di condivisione dei dati bidirezionale tra Microsoft e la soluzione SD-WAN. Per ogni sede e circuito Internet configurato, Microsoft condivide periodicamente il feedback con la soluzione SD-WAN sulla qualità delle esperienze delle applicazioni di Microsoft 365 selezionate per il traffico di rete associato a ogni circuito Internet specifico. Usando questo feedback, la soluzione SD-WAN può quindi eseguire azioni di ripristino intelligenti instradamento del traffico delle applicazioni di Microsoft 365 tramite collegamenti disponibili alternativi. 

Le degradazioni della qualità del servizio nel percorso di un determinato circuito Internet, ad esempio un aumento della latenza o un'elevata perdita di pacchetti, sono difficili da rilevare in modo continuo. Queste degradazioni possono essere dannose per le esperienze utente per applicazioni come Exchange Online, SharePoint, OneDrive e Microsoft Teams. I sintomi comuni includono la ricerca lenta del contenuto di Exchange, tempi di trasferimento elevati quando si interagisce con le raccolte documenti di SharePoint o OneDrive o una scarsa qualità delle chiamate o delle riunioni in Microsoft Teams.

Il meccanismo di feedback e ripristino all'interno del routing informato sulla rete cerca di rilevare dinamicamente tali problemi in tempo quasi reale e informa la soluzione SD-WAN distribuita di eseguire azioni di ripristino automatico.

Il canale di condivisione dei dati viene inoltre utilizzato per ricevere periodicamente dati ottici a livello di rete dalla soluzione SD-WAN, incluse le informazioni di configurazione e le statistiche di utilizzo associate al dispositivo e ai circuiti collegati. Non vengono raccolte o archiviate informazioni personali. Tutte le informazioni raccolte vengono aggregate alle sedi degli uffici e ai circuiti Internet connessi. Queste informazioni possono aiutare Microsoft a risolvere in modo più efficiente ed efficace i problemi segnalati con l'uso dei servizi e delle applicazioni di Microsoft 365.

>[!NOTE]
>Il routing di rete informato di Microsoft 365 supporta i tenant nel cloud commerciale WW, ma non i cloud GCC Moderate, GCC High, DoD, Germany o China.

## <a name="requirements"></a>Requisiti

### <a name="integrated-sd-wan-solutions"></a>Soluzioni SD-WAN integrate

Microsoft collabora con diversi partner per abilitare l'integrazione con il routing di rete informato di Microsoft 365. Le soluzioni attualmente abilitate includono:

| Device Maker | Nome soluzione | Versione minima |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topologia di rete 

Il routing di rete informato attualmente identifica il traffico associato a una posizione specifica dell'ufficio e a un circuito Internet in base all'indirizzo IP pubblico utilizzato per inviare il traffico di rete a Microsoft. 

Nel caso in cui non vi sia almeno un circuito di rete che fornisce l'accesso diretto a Internet in una posizione di succursale, il routing informato sulla rete potrebbe non fornire un valore significativo.

### <a name="application-usage"></a>Utilizzo dell'applicazione

I dati sull'esperienza delle applicazioni (riflessi tramite metriche di qualità di rete) vengono raccolti tramite l'uso di applicazioni client Microsoft specifiche. Le metriche di Exchange riflettono l'utilizzo del client Outlook e di alcuni utilizzi di Outlook Web App. Le metriche di SharePoint e OneDrive riflettono l'utilizzo degli endpoint di SharePoint specifici del tenant, indipendentemente dall'applicazione client. Le metriche di Teams riflettono l'utilizzo del client desktop di Teams. Quando si valuta l'integrità di un circuito di rete, non viene preso in considerazione altro traffico di applicazioni.

## <a name="enabling-informed-network-routing"></a>Abilitazione del routing di rete informato

L'abilitazione del routing di rete informato richiede più passaggi, alcuni dei quali dovranno essere eseguiti nell'interfaccia di configurazione della soluzione SD-WAN. Consultare il fornitore della soluzione SD-WAN per istruzioni su come avviare il processo di abilitazione del routing informato sulla rete all'interno della soluzione SD-WAN prima di procedere con la configurazione nell'interfaccia di amministrazione di Microsoft 365.

Quando si è pronti per abilitare il routing di rete informato nell'interfaccia di amministrazione di Microsoft 365, assicurarsi di disporre delle autorizzazioni di amministratore globale necessarie.

>[!IMPORTANT]
>Per fornire le autorizzazioni necessarie per le applicazioni a livello di tenant per la soluzione SD-WAN selezionata per accedere al canale di condivisione dei dati di routing di rete informato, è necessario eseguire la procedura seguente come amministratore globale.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Passaggio 1: Aprire le opzioni di configurazione della soluzione SD-WAN

[Nell'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/)selezionare Integrità > **Connettività** di rete nel riquadro di spostamento a sinistra.

Questa sezione dell'interfaccia di amministrazione fornisce metriche aggregate sulla connettività di rete per l'organizzazione e indicazioni su come migliorare la connettività. Vedere Connettività di rete nell'interfaccia di amministrazione di [Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md) per ulteriori informazioni su queste funzionalità disponibili nell'interfaccia di amministrazione.

Selezionare **Impostazioni > soluzione SD-WAN** per aprire il riquadro di configurazione del routing di rete informato. Le altre opzioni  visualizzate in Impostazioni sono applicabili alle indicazioni generali sulla connettività di rete nell'interfaccia di amministrazione e non sono necessarie per abilitare il routing di rete informato.

Nel riquadro di configurazione selezionare Aggiungi la soluzione **SD-WAN (anteprima).**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Passaggio 2: Selezionare la soluzione SD-WAN e il percorso di archiviazione dei dati

Nelle caselle a discesa selezionare la soluzione SD-WAN distribuita e il percorso in cui si desidera archiviare i dati associati al routing informato sulla rete. Per ulteriori [informazioni, vedere](#data-storage) la sezione relativa all'archiviazione dei dati.

Selezionare **Avanti**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Passaggio 3: Accettare i termini per la condivisione dei dati

Leggere attentamente e confermare i termini forniti associati alla condivisione dei dati tra Microsoft e la soluzione SD-WAN selezionata, quindi selezionare la casella di controllo indicata.

Selezionare **Avanti**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Passaggio 4: Concedere le autorizzazioni per la soluzione SD-WAN

Questo passaggio avvierà una richiesta di concessione delle autorizzazioni con Azure Active Directory (Azure AD). Ti verrà richiesto di concedere autorizzazioni a livello di tenant che consentono alla soluzione SD-WAN selezionata di accedere all'archiviazione dei dati di routing di rete informata e alle informazioni sull'integrità del servizio associate al tenant. Questa azione richiede autorizzazioni di ruolo di amministratore globale.

Selezionare il **collegamento Concedere l'autorizzazione a questa applicazione** e seguire le richieste di Azure AD.

Dopo aver completato la concessione delle autorizzazioni, selezionare **Avanti.**

### <a name="step-5-confirm-your-configuration-settings"></a>Passaggio 5: Confermare le impostazioni di configurazione

Il passaggio finale per abilitare il routing informato sulla rete per il tenant è una pagina di conferma che mostra le impostazioni fornite. 

Il routing di rete informato è ora abilitato per il tenant.

Selezionare **Fine** e quindi chiudere il riquadro di configurazione della soluzione SD-WAN.

## <a name="configuring-network-informed-routing"></a>Configurazione del routing informato sulla rete

Gran parte della configurazione verrà eseguita per il routing di rete informato all'interno della soluzione SD-WAN, ad esempio la configurazione della modalità di instradamento del traffico in circostanze normali e i percorsi alternativi da utilizzare se vengono rilevati problemi. Per informazioni dettagliate su questi passaggi di configurazione, consultare il provider di soluzioni SD-WAN.

Ogni posizione dell'ufficio deve essere configurata nell'interfaccia di amministrazione di Microsoft 365 in modo che il routing di rete informato possa identificare correttamente il traffico associato ai circuiti di rete che forniscono la connettività a queste posizioni.

Le posizioni di Office possono essere rilevate automaticamente come parte della raccolta continua di telemetria di rete di Microsoft. Di conseguenza, alcune posizioni potrebbero essere pre-popolate nell'interfaccia di amministrazione per il tenant. 

Se queste posizioni sono accurate, sarà sufficiente abilitare la funzionalità di routing di rete informata per ogni posizione desiderata e configurare i circuiti Internet e i relativi indirizzi IP pubblici. 

Se le posizioni rilevate automaticamente non sono accurate o non sono presenti posizioni pre-popolate nel tenant, sarà necessario aggiungere o modificare manualmente le posizioni per riflettere una topologia accurata dell'organizzazione.

### <a name="updating-locations"></a>Aggiornamento delle posizioni

Le posizioni per il tenant sono disponibili nella **scheda** Posizioni. I percorsi possono essere modificati direttamente nell'elenco o aggiornati utilizzando un file CSV.

Verificare che ogni sede in cui si desidera abilitare il routing di rete informato sia presente nell'elenco.

>[!NOTE]
>Le colonne **nell'elenco Percorsi** per i campioni raccolti e altre informazioni correlate alla valutazione non sono correlate alla funzionalità di routing di rete informata.

### <a name="enabling-a-location-for-informed-network-routing"></a>Abilitazione di una posizione per il routing di rete informato

1. **Nell'elenco Posizioni** scegliere **Modifica dal** menu azioni rapide per aprire il riquadro di configurazione della posizione.

2. Selezionare Usa routing di rete informato di **Microsoft 365 in questa posizione.**

3. Aggiungere tutti i circuiti di rete che forniscono connettività Internet a questa posizione dell'ufficio nella sezione Intervalli di indirizzi IP in uscita **in questa posizione dell'ufficio.** Verificare che ogni circuito sia associato alle subnet di indirizzi IP pubblici univoche che rappresentano il traffico di rete.

4. Selezionare **Salva** per salvare le modifiche.

## <a name="disabling-network-informed-routing"></a>Disabilitazione del routing informato sulla rete

La funzionalità di routing di rete informata può essere disabilitata per l'intero tenant reimpostando le impostazioni della soluzione SD-WAN. Anche se in questo modo verrà interrotta l'elaborazione dei dati all'interno di Microsoft 365, è consigliabile disabilitare anche il routing informato sulla rete all'interno dell'interfaccia di amministrazione.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Passaggio 1: Aprire le opzioni di configurazione della soluzione SD-WAN

Nell'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com/) selezionare **> connettività** di rete nel riquadro di spostamento a sinistra.

Selezionare **Impostazioni > soluzione SD-WAN** per aprire il riquadro di configurazione del routing di rete informato.

Nel riquadro di configurazione viene visualizzato un riepilogo della soluzione SD-WAN attualmente configurata.

### <a name="step-2-reset-your-configuration"></a>Passaggio 2: reimpostare la configurazione

Nel riquadro di configurazione selezionare Ripristina **le impostazioni della soluzione SD-WAN.**

Le impostazioni sono state reimpostate e il routing di rete informato è stato disabilitato. È possibile ri abilitarlo in qualsiasi momento seguendo la procedura descritta in [Abilitazione del routing di rete informato.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Archiviazione dei dati

I dati s scambiati tra Microsoft e il provider di soluzioni SD-WAN vengono archiviati nella posizione di archiviazione dei dati selezionata durante l'abilitazione iniziale del routing informato sulla rete. Le opzioni relative alla posizione di archiviazione dei dati rappresentano aree geografiche contenenti aree geografiche di Microsoft Azure in cui sono archiviati i dati.

>[!NOTE]
>Durante la fase di anteprima, l'unico percorso di archiviazione dei dati disponibile è **il Nord America.** Ulteriori posizioni di archiviazione dei dati saranno disponibili prima della disponibilità generale del routing di rete informato.

I dati vengono conservati in questa posizione per un massimo di 30 giorni. Se disabilitata, tutti i dati rimanenti vengono rimossi entro questa finestra di conservazione di 30 giorni.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Network Connectivity Location Services (anteprima)](office-365-network-mac-location-services.md)
