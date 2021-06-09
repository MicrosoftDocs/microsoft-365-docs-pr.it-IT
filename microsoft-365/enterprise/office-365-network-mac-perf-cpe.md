---
title: Microsoft 365 instradamento di rete informato
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
description: Microsoft 365 instradamento di rete informato
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717588"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 routing di rete informato (anteprima)

Il routing di rete informato è una funzionalità che integra varie applicazioni di Microsoft 365 con soluzioni SD-WAN (Software Defined Network) di terze parti per ottimizzare e migliorare la connettività di rete agli endpoint del servizio Microsoft. La connettività SD-WAN ottimizzata può comportare prestazioni e esperienze utente migliorate.

>[!IMPORTANT]
>Microsoft 365 routing di rete informato è attualmente in stato di anteprima. Per ulteriori informazioni su questa anteprima, incluse le indicazioni per la ricezione di assistenza, vedere Microsoft 365 [instradamento di rete informato Anteprima pubblica.](https://go.microsoft.com/fwlink/?linkid=2151565)

## <a name="overview"></a>Panoramica

Il routing di rete informato fornisce un canale di condivisione dati bidirezionale tra Microsoft e la soluzione SD-WAN. Per ogni sede e circuito Internet configurato, Microsoft condivide periodicamente il feedback con la soluzione SD-WAN sulla qualità delle esperienze delle applicazioni Microsoft 365 selezionate per il traffico di rete associato a ogni circuito Internet specifico. Usando questo feedback, la soluzione SD-WAN può quindi eseguire azioni di ripristino intelligente instradamento Microsoft 365 traffico delle applicazioni attraverso collegamenti disponibili alternativi. 

Le degradazioni della qualità del servizio nel percorso di un particolare circuito Internet, ad esempio un aumento della latenza o un'elevata perdita di pacchetti, sono difficili da rilevare in modo continuo. Queste degradazioni possono essere dannose per le esperienze utente per applicazioni quali Exchange Online, SharePoint, OneDrive e Microsoft Teams. I sintomi comuni includono una ricerca lenta del contenuto Exchange, tempi di trasferimento elevati quando si interagisce con raccolte documenti di SharePoint o OneDrive o qualità scarsa delle chiamate o delle riunioni in Microsoft Teams.

Il meccanismo di feedback e ripristino all'interno del routing informato sulla rete cerca di rilevare dinamicamente tali problemi in tempo quasi reale e informa la soluzione SD-WAN distribuita di eseguire azioni di ripristino automatico.

Il canale di condivisione dei dati viene utilizzato anche per ricevere periodicamente dati di ottica a livello di rete dalla soluzione SD-WAN, incluse le informazioni di configurazione e le statistiche di utilizzo associate al dispositivo e ai circuiti collegati. Non vengono raccolte o archiviate informazioni personali. Tutte le informazioni raccolte vengono aggregate alle posizioni dell'ufficio e ai circuiti Internet connessi. Queste informazioni possono aiutare Microsoft a risolvere in modo più efficiente ed efficace i problemi segnalati con l'uso di Microsoft 365 e applicazioni.

>[!NOTE]
>Microsoft 365 routing di rete informato supporta i tenant nel cloud commerciale WW, ma non nei cloud GCC Moderate, GCC High, DoD, Germany o China.

## <a name="requirements"></a>Requisiti

### <a name="integrated-sd-wan-solutions"></a>Soluzioni SD-WAN integrate

Microsoft sta collaborando con diversi partner per abilitare l'integrazione con Microsoft 365 di rete informato. Le soluzioni attualmente abilitate includono:

| Device Maker | Nome soluzione | Versione minima |
| --- | --- | --- |
| Cisco | [IOS XE SD-WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Topologia di rete 

Il routing di rete informato identifica attualmente il traffico associato a una posizione specifica dell'ufficio e a un circuito Internet in base all'indirizzo IP pubblico utilizzato per inviare il traffico di rete a Microsoft. 

Nel caso in cui non vi sia almeno un circuito di rete che fornisce l'accesso diretto a Internet in una sede di succursale, il routing informato sulla rete potrebbe non fornire un valore significativo.

### <a name="application-usage"></a>Utilizzo dell'applicazione

I dati sull'esperienza dell'applicazione (riflessi tramite metriche di qualità di rete) vengono raccolti tramite l'utilizzo di specifiche applicazioni client Microsoft. Exchange metriche riflettono l'utilizzo del client Outlook e alcuni Outlook Web App di utilizzo. SharePoint e OneDrive metriche riflettono l'utilizzo degli endpoint di SharePoint specifici del tenant, indipendentemente dall'applicazione client. Teams metriche riflettono l'utilizzo del client Teams desktop. Quando si valuta l'integrità di un circuito di rete, non viene preso in considerazione altro traffico di applicazioni.

## <a name="enabling-informed-network-routing"></a>Abilitazione del routing di rete informato

L'abilitazione del routing di rete informato richiede più passaggi, alcuni dei quali dovranno essere eseguiti nell'interfaccia di configurazione della soluzione SD-WAN. Consultare il fornitore della soluzione SD-WAN per istruzioni su come avviare il processo di abilitazione del routing informato sulla rete all'interno della soluzione SD-WAN prima di procedere con la configurazione nell'interfaccia di amministrazione di Microsoft 365.

Quando si è pronti per abilitare il routing di rete informato nell Microsoft 365 di amministrazione, assicurarsi di disporre delle autorizzazioni di amministratore globale necessarie.

>[!IMPORTANT]
>Per fornire le autorizzazioni necessarie per le applicazioni a livello di tenant per la soluzione SD-WAN selezionata per accedere al canale di condivisione dei dati di routing di rete informato, è necessario eseguire la procedura seguente come amministratore globale.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Passaggio 1: Aprire le opzioni di configurazione della soluzione SD-WAN

[Nell'Microsoft 365 di amministrazione](https://admin.microsoft.com/)selezionare Integrità > **Connettività** di rete nel riquadro di spostamento sinistro.

Questa sezione dell'interfaccia di amministrazione fornisce metriche aggregate sulla connettività di rete per l'organizzazione e indicazioni su come migliorare la connettività. Per ulteriori informazioni su queste funzionalità disponibili nell'interfaccia Microsoft 365 di amministrazione, vedere Network [connectivity in the Microsoft 365 Admin Center (preview).](office-365-network-mac-perf-overview.md)

Selezionare **Impostazioni > soluzione SD-WAN per** aprire il riquadro di configurazione del routing di rete informato. Le altre opzioni  visualizzate in Impostazioni sono applicabili alle indicazioni generali sulla connettività di rete nell'interfaccia di amministrazione e non sono necessarie per abilitare il routing di rete informato.

Nel riquadro di configurazione selezionare **Aggiungi la soluzione SD-WAN (anteprima).**

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Passaggio 2: Selezionare la soluzione SD-WAN e il percorso di archiviazione dei dati

Nelle caselle a discesa selezionare la soluzione SD-WAN distribuita e il percorso in cui si desidera archiviare i dati associati al routing informato sulla rete. Per ulteriori [informazioni, vedere](#data-storage) la sezione relativa all'archiviazione dei dati.

Selezionare **Avanti**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Passaggio 3: Accettare i termini per la condivisione dei dati

Leggere attentamente e confermare i termini forniti associati alla condivisione dei dati tra Microsoft e la soluzione SD-WAN selezionata, quindi selezionare la casella di controllo indicata.

Selezionare **Avanti**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Passaggio 4: Concedere le autorizzazioni per la soluzione SD-WAN

Questo passaggio avvierà una richiesta di concessione delle autorizzazioni con Azure Active Directory (Azure AD). Verrà richiesto di concedere autorizzazioni a livello di tenant che consentono alla soluzione SD-WAN selezionata di accedere all'archivio dei dati di routing di rete informato e alle informazioni sull'integrità del servizio associate al tenant. Questa azione richiede autorizzazioni di ruolo amministratore globale.

Selezionare il **collegamento Concedere l'autorizzazione a questa applicazione** e seguire le richieste di Azure AD.

Dopo aver completato la concessione delle autorizzazioni, selezionare **Avanti**.

### <a name="step-5-confirm-your-configuration-settings"></a>Passaggio 5: Confermare le impostazioni di configurazione

Il passaggio finale per abilitare il routing informato sulla rete per il tenant è una pagina di conferma che visualizza le impostazioni fornite. 

Il routing di rete informato è ora abilitato per il tenant.

Selezionare **Fatto** e quindi chiudere il riquadro di configurazione della soluzione SD-WAN.

## <a name="configuring-network-informed-routing"></a>Configurazione del routing informato sulla rete

Si eseguirà gran parte della configurazione per il routing di rete informato all'interno della soluzione SD-WAN, ad esempio configurando la modalità di instradamento del traffico in circostanze normali e i percorsi alternativi da utilizzare in caso di problemi rilevati. Per informazioni dettagliate su questi passaggi di configurazione, consultare il provider di soluzioni SD-WAN.

Ogni posizione dell'ufficio deve essere configurata nell'interfaccia di amministrazione di Microsoft 365 in modo che il routing di rete informato possa identificare correttamente il traffico associato ai circuiti di rete che forniscono connettività a tali posizioni.

Office posizioni potrebbero essere rilevate automaticamente come parte della raccolta continua di telemetria di rete di Microsoft. Di conseguenza, alcune posizioni potrebbero essere pre-popolate nell'interfaccia di amministrazione per il tenant. 

Se queste posizioni sono accurate, sarà sufficiente abilitare la funzionalità di routing di rete informata per ogni posizione desiderata e configurare i circuiti Internet e i relativi indirizzi IP pubblici. 

Se le posizioni rilevate automaticamente non sono accurate o non sono presenti posizioni precompilato nel tenant, sarà necessario aggiungere o modificare manualmente le posizioni per riflettere una topologia accurata dell'organizzazione.

### <a name="updating-locations"></a>Aggiornamento delle posizioni

Le posizioni per il tenant sono disponibili nella **scheda** Posizioni. I percorsi possono essere modificati direttamente nell'elenco o aggiornati utilizzando un file CSV.

Verificare che ogni posizione dell'ufficio in cui si desidera abilitare il routing di rete informato sia presente in questo elenco.

>[!NOTE]
>Le colonne **nell'elenco Percorsi** per i campioni raccolti e altre informazioni correlate alla valutazione non sono correlate alla funzionalità di routing di rete informata.

### <a name="enabling-a-location-for-informed-network-routing"></a>Abilitazione di un percorso per il routing di rete informato

1. **Nell'elenco Posizioni** selezionare **Modifica dal** menu azioni rapide per aprire il riquadro di configurazione della posizione.

2. Selezionare **Usa Microsoft 365 routing di rete informato in questa posizione.**

3. Aggiungere tutti i circuiti di rete che forniscono connettività Internet a questa posizione dell'ufficio nella Egress intervalli di indirizzi **IP in questa posizione dell'ufficio.** Verificare che ogni circuito sia associato alle subnet di indirizzi IP pubblici univoci che rappresentano il traffico di rete.

4. Selezionare **Salva** per salvare le modifiche.

## <a name="disabling-network-informed-routing"></a>Disabilitazione del routing informato sulla rete

La funzionalità di routing di rete informata può essere disabilitata per l'intero tenant reimpostando le impostazioni della soluzione SD-WAN. Anche se in questo modo verrà interrotta l'elaborazione dei dati Microsoft 365, è consigliabile disabilitare anche il routing informato sulla rete all'interno dell'interfaccia di amministrazione.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Passaggio 1: Aprire le opzioni di configurazione della soluzione SD-WAN

[Nell'Microsoft 365 di amministrazione selezionare](https://admin.microsoft.com/) Integrità > **Connettività** di rete nel riquadro di spostamento sinistro.

Selezionare **Impostazioni > soluzione SD-WAN per** aprire il riquadro di configurazione del routing di rete informato.

Nel riquadro di configurazione viene visualizzato un riepilogo della soluzione SD-WAN attualmente configurata.

### <a name="step-2-reset-your-configuration"></a>Passaggio 2: Reimpostare la configurazione

Nel riquadro di configurazione seleziona **Reimposta le impostazioni della soluzione SD-WAN.**

Le impostazioni sono state reimpostate e il routing di rete informato è stato disabilitato. È possibile ri abilitarlo in qualsiasi momento seguendo la procedura descritta in [Abilitazione del routing di rete informato.](#enabling-informed-network-routing)

## <a name="data-storage"></a>Archiviazione dei dati

I dati s scambiati tra Microsoft e il provider di soluzioni SD-WAN vengono archiviati nella posizione di archiviazione dei dati selezionata durante l'abilitazione iniziale del routing informato sulla rete. Le opzioni relative alla posizione di archiviazione dei dati rappresentano le aree geografiche Microsoft Azure aree geografiche in cui sono archiviati i dati.

>[!NOTE]
>Durante la fase di anteprima, l'unico percorso di archiviazione dati disponibile è **Nord America.** Ulteriori posizioni di archiviazione dei dati saranno disponibili prima della disponibilità generale del routing di rete informato.

I dati vengono conservati in questa posizione per un massimo di 30 giorni. Se disabilitata, tutti i dati rimanenti vengono rimossi entro questa finestra di conservazione di 30 giorni.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'Microsoft 365 di amministrazione (anteprima)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Servizi percorso di connettività di rete (anteprima)](office-365-network-mac-location-services.md)
