---
title: Responsabilità nella continuità aziendale dei partner di cloud e clienti
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sulle attività di Microsoft nel corso di un incidente di servizio in modo da poter preparare meglio i piani di continuità aziendale.
ms.openlocfilehash: c74bb83352f87faf0bb7f50e8aec4ac813516d3c
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031081"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>Responsabilità del partner di cloud e dei clienti nella gestione della continuità aziendale

Offrire i servizi cloud di Microsoft 365 agli utenti rappresenta una partnership tra l'organizzazione e Microsoft. Microsoft include i servizi di e si è responsabili della connessione degli endpoint client, della gestione dell'identità e dell'accesso e della modalità di utilizzo dei servizi. Ci sono responsabilità condivise, come l’identità e l’infrastruttura della directory. Questo articolo illustra alcuni degli elementi essenziali che è necessario tenere presenti per mantenere il funzionamento dell’azienda nel caso di un incidente di servizio e che consenta di impostare le aspettative relative a ciò che Microsoft potrà eseguire durante un incidente di servizio.

## <a name="transparency-during-service-incidents"></a>Trasparenza durante gli incidenti di servizio

In qualità di partner affidabile, Microsoft crea servizi cloud altamente resilienti e segue procedure strutturate per risolvere gli incidenti di servizio quando si verificano. Quando si verifica un incidente di servizio, Microsoft sa che per i clienti sono essenziali comunicazioni **tempestive**, **mirate** e **ampiamente disponibili**.

## <a name="timely"></a>Tempestive
Microsoft informa gli amministratori di Microsoft 365 aggiornando il Dashboard sull'integrità del servizio (SHD) specifico del tenant nel portale di amministrazione di Microsoft 365. Gli aggiornamenti per gli incidenti di servizio sono in genere forniti con cadenza oraria. Se è necessaria una frequenza diversa, verranno fornite informazioni sulle modifiche apportate alle registrazioni comunicazione di SHD.

## <a name="targeted"></a>Mirate
Nella maggior parte dei casi, quando i sistemi di monitoraggio rilevano un problema, è possibile identificare la base di clienti interessata, da un singolo cliente fino all'area geografica o oltre e indirizzare le comunicazioni necessarie a tali clienti. Questo consente di individuare le informazioni necessarie per la propria azienda e di non essere distratti dalle notifiche non rilevanti. Ad esempio, se è interessato un determinato database di cassette postali, è possibile identificare esattamente i clienti che hanno utenti nell'infrastruttura interessata e assisterli con le comunicazioni. Se l'ambito dell'impatto dell'incidente non è chiaro, le comunicazioni verranno ampliate al più ampio gruppo di clienti potenzialmente interessato.

## <a name="highly-avaliable"></a>Altamente disponibili
Microsoft gestisce più canali per le comunicazioni sullo stato dei servizi utilizzabili dai clienti.

- Se l'interfaccia di amministrazione o il dashboard sull’integrità dei servizi nell'interfaccia di amministrazione non sono disponibili, è possibile monitorare lo stato del servizio tramite il [sito di backup](https://status.office365.com/).
- È disponibile un account Twitter [@MSFT365Status](https://twitter.com/msft365status?lang=en) in cui verranno fornite risposte ai report sull’impatto e forniti aggiornamenti per gli eventi interessati di SHD.
- L'app Amministrazione per gli amministratori del tenant di Microsoft 365 offre la possibilità di connettersi allo stato del servizio di Microsoft 365 dell'organizzazione ovunque ci si trovi. Gli amministratori del tenant avranno la possibilità di visualizzare le informazioni sull'integrità del servizio e gli aggiornamenti di stato della manutenzione dal proprio dispositivo mobile. Per altre informazioni consultare le [Domande frequenti dell’app Amministrazione](https://docs.microsoft.com/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide).
- L'[API per le comunicazioni dei servizi di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api) consente di accedere alle comunicazioni del servizio in modo da poter monitorare più facilmente l'ambiente. È possibile connettersi all'API, ricevere i dati di integrità dei servizi in tempo reale e pubblicare le informazioni in un dashboard interno per fornire agli utenti dell'organizzazione informazioni sugli incidenti. La distribuzione interna delle informazioni può ridurre il lavoro del supporto tecnico durante un incidente.
- Per gli incidenti principali, Microsoft pubblica delle Revisioni post evento (PIR) in SHD nell'interfaccia di amministrazione. Le PIR contengono informazioni chiave sull'incidente per comprendere la natura dell'interruzione. In genere contiene le sezioni seguenti:
    - impatto sugli utenti
    - ambito dell'impatto
    - data e ora di inizio dell'incidente
    - causa principale
    - azioni intraprese
    - passaggi successivi
- Le comunicazioni accessorie sono disponibili nel centro messaggi di Microsoft 365, come le comunicazioni sulle modifiche imminenti, sulle nuove funzionalità o sulla manutenzione pianificata.
- Per altre informazioni, vedere la [Guida sull'integrità e sulla continuità dei servizi](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) per scoprire diversi canali di comunicazione e come monitorare l'integrità dei servizi.
 
Offrire l’accesso ai servizi online di Microsoft 365 rappresenta una partnership tra l'organizzazione e Microsoft. Nel grafico seguente viene riepilogato l'equilibrio di responsabilità per Microsoft e il cliente durante un incidente di servizio e durante normali operazioni.

![equilibrio del cliente e responsabilità di Microsoft](media/ebcm/responsibilities.png)

## <a name="your-environment---service-continuity"></a>Ambiente - continuità del servizio
Pensando al piano di continuità, tenere presente gli eventi che possono avere un impatto sull'organizzazione e la capacità complessiva di comunicare. A un livello elevato, ci sono tre fattori che possono influire sull’azienda.

### <a name="people"></a>Persone
Considerare gli eventi che possono avere un impatto sulla forza lavoro come una calamità naturale o una pandemia. Questo aspetto viene spesso trascurato a causa dell’improbabile natura di un impatto su vasta scala, se la forza lavoro è distribuita in più sedi. Tuttavia, se una gran parte della forza lavoro fosse offline, l'azienda continuerebbe a essere operativa? Come ovviare a questo problema?

### <a name="location"></a>Posizione
Molte organizzazioni richiedono che i dipendenti si trovino in posizioni fisiche o di rete specifiche per connettersi ai sistemi aziendali e ai servizi cloud.  
Microsoft pubblica i [principi di connettività di rete](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) che guidano le imprese attraverso le procedure consigliate per configurare la connettività di rete alle risorse cloud. Esempi di ottimizzazione includono l'implementazione di VPN tunnel split per consentire le connessioni direttamente dalla rete di un utente invece che su un tunnel VPN.  Anche se questi principi di connettività sono importanti per mantenere connessioni con una latenza bassa, la resilienza dei servizi richiede metodi alternativi per la connessione a risorse aziendali per la collaborazione generale.

### <a name="systems"></a>Sistemi
Molte soluzioni per la collaborazione dipendono dai sistemi, come la rete WAN (Wide Area Network) aziendale. Se questi sistemi non fossero disponibili, quali sarebbero le ripercussioni per l’organizzazione?
Questo elemento grafico rappresenta i problemi che possono avere un impatto su più aree. La tabella seguente include esempi da tenere in considerazione

![diagramma di Venn](media/ebcm/venn-diagram.png)

I piani di continuità devono considerare ognuna di queste aree. Ad esempio: se si desidera che gli utenti si trovino nella rete aziendale e al contempo ci fosse una tormenta di neve, in che modo questi utenti avrebbero accesso alle risorse chiave? Se la neve impedisse di raggiungere l’ufficio e gli ingegneri del servizio avessero bisogno di connettersi alla rete aziendale, esiste un criterio che impone di avere dei laptop aziendali a casa?
