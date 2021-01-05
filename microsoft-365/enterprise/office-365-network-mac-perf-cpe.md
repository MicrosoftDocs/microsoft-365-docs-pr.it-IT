---
title: Microsoft 365 informed Network routing
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 informed Network routing
ms.openlocfilehash: 367f83684a4a200e3ddd630e1412c756d7093da1
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749552"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365 informed Network routing (anteprima)

Informed Network routing è una funzionalità che integra diverse applicazioni Microsoft 365 con soluzioni di rete (SD-WAN) di terze parti per ottimizzare e migliorare la connettività di rete per gli endpoint dei servizi Microsoft. La connettività SD-WAN ottimizzata può comportare una migliore esperienza utente e prestazioni.

>[!IMPORTANT]
>Microsoft 365 ha informato che il routing di rete è attualmente in stato di anteprima. Per ulteriori informazioni su questa anteprima, incluse le istruzioni per la ricezione dell'assistenza, vedere [Microsoft 365 informed Network informations Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Panoramica

Il routing di rete informato fornisce un canale di condivisione dei dati bi-direzionale tra Microsoft e la soluzione SD-WAN. Per ogni percorso di Office e circuito Internet configurato, Microsoft condivide periodicamente i commenti e suggerimenti con la soluzione SD-WAN sulla qualità delle esperienze di applicazioni Microsoft 365 per il traffico di rete associato a ogni circuito Internet specifico. Usando questo feedback, la soluzione SD-WAN può quindi intraprendere azioni di ripristino Smart eseguendo il routing del traffico di applicazioni Microsoft 365 tramite collegamenti disponibili alternativi. 

La qualità del servizio degradazioni nel percorso di un determinato circuito Internet, ad esempio una maggiore latenza o una perdita di pacchetti elevata, sono difficili da rilevare su base continuativa. Tali degradi possono essere pregiudizievoli per le esperienze degli utenti per applicazioni quali Exchange Online, SharePoint, OneDrive e Microsoft teams. I sintomi più comuni includono una ricerca lenta del contenuto di Exchange, tempi di trasferimento elevati quando interagiscono con le raccolte documenti di SharePoint o OneDrive o la qualità di chiamata o riunione scadente in Microsoft teams.

Il meccanismo di feedback e ripristino all'interno del routing informativo della rete cerca di rilevare dinamicamente tali problemi in tempo quasi reale e di informare la soluzione SD-WAN distribuita per eseguire azioni di ripristino automatico.

Il canale di condivisione dei dati viene utilizzato anche per ricevere periodicamente dati ottici a livello di rete dalla soluzione SD-WAN, incluse le informazioni di configurazione e le statistiche di utilizzo associate al dispositivo e ai circuiti associati. Nessuna informazione personale è raccolta o memorizzata. Tutte le informazioni raccolte vengono aggregate ai percorsi di Office e ai circuiti Internet connessi. Queste informazioni consentono a Microsoft di risolvere in modo più efficiente ed efficace i problemi segnalati con l'utilizzo di servizi e applicazioni Microsoft 365.

>[!NOTE]
>Microsoft 365 informed Network routing supporta i tenant in WW Commercial cloud, ma non le cloud GCC moderate, GCC High, DoD, Germany o China.

## <a name="requirements"></a>Requisiti

### <a name="integrated-sd-wan-solutions"></a>Soluzioni SD-WAN integrate

Microsoft sta lavorando con vari partner per consentire l'integrazione con Microsoft 365 informata del routing della rete. Le soluzioni attualmente abilitate sono le seguenti:

| Creatore di dispositivi | Nome della soluzione | Versione minima |
| --- | --- | --- |
| Cisco | [SD-WAN PER IOS](https://go.microsoft.com/fwlink/?linkid=2151460) | 20,4/17,4 |

### <a name="network-topology"></a>Topologia di rete 

Il routing di rete informato attualmente identifica il traffico associato a una specifica posizione di Office e a un circuito Internet in base all'indirizzo IP pubblico utilizzato per inviare il traffico di rete a Microsoft. 

Nel caso in cui non sia presente almeno un circuito di rete che fornisca l'accesso diretto a Internet in una sede di succursale, il routing informato dalla rete potrebbe non fornire un valore significativo.

### <a name="application-usage"></a>Utilizzo dell'applicazione

I dati relativi alle applicazioni (riflesse dalle metriche sulla qualità della rete) vengono raccolti tramite l'utilizzo di Microsoft Outlook nei dispositivi che eseguono Windows, teams, SharePoint e OneDrive. Quando si valuta l'integrità di un circuito di rete, non viene considerato altro traffico di applicazioni.

## <a name="enabling-informed-network-routing"></a>Abilitazione del routing di rete informato

L'abilitazione del routing di rete informato richiede più passaggi, alcuni dei quali dovranno essere eseguiti all'interno dell'interfaccia di configurazione della soluzione SD-WAN. Consultare il fornitore della soluzione SD-WAN per istruzioni su come avviare il processo di abilitazione del routing informato della rete all'interno della soluzione SD-WAN prima di procedere con la configurazione nell'interfaccia di amministrazione di Microsoft 365.

Quando si è pronti per abilitare il routing di rete informato nell'interfaccia di amministrazione di Microsoft 365, verificare di disporre delle autorizzazioni di amministratore globale necessarie.

>[!IMPORTANT]
>Per fornire le autorizzazioni necessarie per le applicazioni a livello di tenant per la soluzione SD-WAN selezionata per accedere al canale di condivisione dei dati di routing di rete informato, è necessario eseguire la procedura seguente come amministratore globale.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Passaggio 1: aprire le opzioni di configurazione della soluzione SD-WAN

Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/)selezionare **integrità > connettività di rete** nel riquadro di spostamento sinistro.

In questa sezione dell'interfaccia di amministrazione sono disponibili metriche di connettività di rete aggregate per l'organizzazione e vengono fornite indicazioni su come migliorare la connettività. Per ulteriori informazioni su queste funzionalità disponibili all'interno dell'interfaccia di amministrazione, vedere [connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md) .

Selezionare **impostazioni > soluzione SD-WAN** per aprire il riquadro di configurazione del routing di rete informato. Le altre opzioni visualizzate in **Impostazioni** sono applicabili alle indicazioni generali sulla connettività di rete nell'interfaccia di amministrazione e non sono necessarie per abilitare il routing di rete informato.

Nel riquadro di configurazione, selezionare **Aggiungi la soluzione SD-WAN (Preview)**.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Passaggio 2: selezionare la soluzione SD-WAN e il percorso di archiviazione dei dati

Nelle caselle a discesa, selezionare la soluzione SD-WAN che è stata distribuita e il percorso in cui si desidera che i dati associati al routing informato dalla rete siano archiviati. Per ulteriori informazioni, vedere la sezione [archiviazione dei dati](#data-storage) .

Selezionare **Avanti**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Passaggio 3: accettare i termini per la condivisione dei dati

Leggere attentamente e riconoscere i termini forniti associati alla condivisione dei dati tra Microsoft e la soluzione SD-WAN selezionata, quindi selezionare la casella di controllo indicata.

Selezionare **Avanti**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Passaggio 4: concedere le autorizzazioni per la soluzione SD-WAN

Questo passaggio avvierà una richiesta di concessione delle autorizzazioni con Azure Active Directory (Azure AD). Verrà richiesto di concedere le autorizzazioni a livello di tenant che consentono all'utente di accedere alla soluzione SD-WAN selezionata all'archiviazione dei dati del routing della rete informata e alle informazioni di integrità del servizio associate al tenant. Questa azione richiede le autorizzazioni per il ruolo di amministratore globale.

Selezionare il collegamento **concedi a questo applicazione** e seguire le richieste di Azure ad.

Dopo aver completato la concessione delle autorizzazioni, selezionare **Avanti**.

### <a name="step-5-confirm-your-configuration-settings"></a>Passaggio 5: confermare le impostazioni di configurazione

L'ultimo passaggio per abilitare il routing informato della rete per il tenant è una pagina di conferma in cui vengono visualizzate le impostazioni fornite. 

Il routing di rete informato è ora abilitato per il tenant.

Fare clic su **fine** e quindi chiudere il riquadro di configurazione della soluzione SD-WAN.

## <a name="configuring-network-informed-routing"></a>Configurazione del routing informata della rete

Si eseguirà gran parte della configurazione per il routing di rete informato all'interno della soluzione SD-WAN, ad esempio la configurazione del traffico che deve essere instradato in circostanze normali e i percorsi alternativi che devono essere utilizzati se vengono rilevati problemi. Consultare il provider di soluzioni SD-WAN per informazioni dettagliate su questi passaggi di configurazione.

Ogni percorso di Office deve essere configurato nell'interfaccia di amministrazione di Microsoft 365 in modo che il routing di rete informato possa identificare correttamente il traffico associato ai circuiti di rete che forniscono la connettività a tali posizioni.

Le posizioni di Office possono essere rilevate automaticamente come parte della raccolta di telemetria di rete di Microsoft in corso. Di conseguenza, alcuni percorsi potrebbero essere precompilati nell'interfaccia di amministrazione del tenant. 

Se tali posizioni sono accurate, è sufficiente abilitare la funzionalità di routing della rete informata per ogni posizione desiderata e configurare i circuiti Internet e gli indirizzi IP pubblici. 

Se le posizioni rilevate automaticamente non sono accurate oppure non sono presenti posizioni prepopolate nel tenant, sarà necessario aggiungere o modificare manualmente le posizioni per riflettere una topologia accurata dell'organizzazione.

### <a name="updating-locations"></a>Percorsi di aggiornamento

Le posizioni del tenant possono essere trovate nella scheda **percorsi** . È possibile modificare le posizioni direttamente nell'elenco o essere aggiornate utilizzando un file CSV.

Verificare che in questo elenco siano presenti tutte le posizioni di Office in cui si desidera abilitare il routing di rete informato.

>[!NOTE]
>Le colonne dell'elenco **percorsi** per gli esempi raccolti e altre informazioni relative alla valutazione non sono correlate alla funzionalità di routing della rete informata.

### <a name="enabling-a-location-for-informed-network-routing"></a>Abilitazione di un percorso per il routing di rete informato

1. Nell'elenco **percorsi** scegliere **modifica** dal menu azioni rapide per aprire il riquadro Configurazione percorso.

2. Selezionare **use Microsoft 365 informed Network routing in questa posizione**.

3. Aggiungere tutti i circuiti di rete che forniscono la connettività Internet a questa posizione di Office negli **intervalli di indirizzi IP di uscita** nella sezione percorso di Office. Assicurarsi che ogni circuito sia associato alle subnet degli indirizzi IP pubblici univoci che rappresentano il traffico di rete.

4. Selezionare **Salva** per salvare le modifiche.

## <a name="disabling-network-informed-routing"></a>Disabilitazione del routing informata della rete

La funzionalità di routing della rete informata potrebbe essere disattivata per l'intero tenant reimpostando le impostazioni della soluzione SD-WAN. Anche se si interrompe tutto l'elaborazione dei dati all'interno di Microsoft 365, è inoltre necessario disabilitare il routing informato dalla rete all'interno dell'interfaccia di amministrazione.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Passaggio 1: aprire le opzioni di configurazione della soluzione SD-WAN

Nell'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/) selezionare **integrità > connettività di rete** nel riquadro di spostamento sinistro.

Selezionare **impostazioni > soluzione SD-WAN** per aprire il riquadro di configurazione del routing di rete informato.

Nel riquadro di configurazione viene visualizzato un riepilogo della soluzione SD-WAN attualmente configurata.

### <a name="step-2-reset-your-configuration"></a>Passaggio 2: reimpostare la configurazione

Nel riquadro di configurazione, selezionare **Reimposta le impostazioni della soluzione SD-WAN**.

Le impostazioni sono state ripristinate e il routing di rete informato è stato disabilitato. È possibile riattivarlo in qualsiasi momento seguendo i passaggi descritti in [Abilitazione del routing di rete informato](#enabling-informed-network-routing).

## <a name="data-storage"></a>Archiviazione dei dati

I dati scambiati tra Microsoft e il provider di soluzioni SD-WAN sono archiviati nel percorso di archiviazione dei dati selezionato durante l'attivazione iniziale del routing informata dalla rete. Le opzioni percorso di archiviazione dei dati rappresentano aree geografiche con aree di Microsoft Azure in cui sono archiviati i dati.

>[!NOTE]
>Durante la fase di anteprima, l'unica posizione di archiviazione dei dati disponibile è il **Nord America**. Altre posizioni di archiviazione dei dati diventeranno disponibili prima della disponibilità generale del routing di rete informato.

I dati vengono conservati in questa posizione per un massimo di 30 giorni. Quando disabilitato, tutti i dati rimanenti vengono rimossi all'interno di questa finestra di conservazione di 30 giorni.

## <a name="related-topics"></a>Argomenti correlati

[Connettività di rete nell'interfaccia di amministrazione di Microsoft 365 (anteprima)](office-365-network-mac-perf-overview.md)

[Microsoft 365 servizi di localizzazione della connettività di rete (anteprima)](office-365-network-mac-location-services.md)
