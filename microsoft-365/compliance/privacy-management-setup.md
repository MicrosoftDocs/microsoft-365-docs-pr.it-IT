---
title: Introduzione alla gestione della privacy di Microsoft (anteprima)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Informazioni su come configurare la gestione della privacy per l'organizzazione, impostare ruoli e autorizzazioni e configurare impostazioni importanti.
ms.openlocfilehash: 5199cf96e9ede3287dc9ac33e26388c065189748
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378553"
---
# <a name="get-started-with-privacy-management-preview"></a>Introduzione alla gestione della privacy (anteprima)

In questo articolo: informazioni su come configurare l'accesso  alla gestione della **privacy** per l'organizzazione, come iniziare a valutare i dati e come gestire le impostazioni **importanti.**

## <a name="sign-up"></a>Effettuare la registrazione

La gestione della privacy sarà disponibile all'interno del Centro conformità Microsoft 365. L'anteprima pubblica della gestione della privacy è disponibile per le organizzazioni con licenze enterprise E1, E3 ed E5 Office 365 e Microsoft 365 enterprise. Dopo la disponibilità generale della gestione della privacy, le organizzazioni dovranno ottenere una nuova licenza.

Tieni presente che l'anteprima pubblica della gestione della privacy non sarà disponibile per i clienti di US Government Community (GCC) Moderate, GCC High o Department of Defense (DoD).

Per iniziare a usare l'anteprima pubblica, ottieni la sottoscrizione di anteprima dall'interfaccia di amministrazione. Se non si ha ancora la licenza quando si seleziona per la prima volta la gestione della privacy nel Centro conformità, si verrà indirizzati all'interfaccia di amministrazione per iniziare. Si consiglia all'amministratore globale di accedere e impostare le autorizzazioni utente come descritto di seguito quando visita la gestione della privacy per la prima volta. Se non si è in possesso del ruolo necessario per ottenere la sottoscrizione o il consenso alle condizioni per l'utilizzo della gestione della privacy, verrà richiesto di contattare l'amministratore globale per assistenza.

Confermando che si desidera iniziare a usare i segnali di gestione della privacy che si accettano le condizioni e il processo di valutazione dei dati personali. È possibile esaminare i collegamenti forniti per intero prima di procedere.

## <a name="set-user-permissions-and-assign-roles"></a>Impostare le autorizzazioni utente e assegnare ruoli

La gestione della privacy utilizza un modello di autorizzazione RBAC (Role-Based Access Control). Solo gli utenti assegnati a un ruolo possono accedere alla gestione della privacy e le azioni consentite da ogni utente sono limitate per tipo di ruolo.

Le autorizzazioni e le assegnazioni di ruolo per la gestione della privacy possono essere gestite all'interno del Centro conformità Microsoft 365, come indicato di seguito. Tieni presente che i ruoli specifici per la gestione della privacy non verranno visualizzati Azure Active Directory.

### <a name="in-the-microsoft-365-compliance-center"></a>Nella finestra Centro conformità Microsoft 365

- Selezionare Autorizzazioni nel riquadro di spostamento sinistro.
- Espandere Centro conformità e selezionare Ruoli. Verrà visualizzato l'elenco completo dei gruppi di ruoli. 
- Scorrere per trovare i gruppi di gestione della privacy o cercare per parola chiave, ad esempio "privacy".
- Selezionare il gruppo di ruoli pertinente per visualizzare una descrizione, i ruoli assegnati e un elenco di membri.
- Usa il collegamento Modifica accanto a queste sezioni per aggiungere o modificare gli utenti o modificare le impostazioni.

### <a name="learn-about-role-groups-and-roles"></a>Informazioni sui gruppi di ruoli e sui ruoli

In questa sezione vengono descritti i gruppi di ruoli e i ruoli rilevanti per la gestione della privacy. I membri devono essere assegnati ai gruppi di ruoli dall'amministratore di primo livello a seconda delle attività che devono eseguire e del livello di accesso ai file appropriato. Ogni gruppo di ruoli include uno o più ruoli. Questi ruoli possono riguardare attività specifiche di gestione della privacy o possono corrispondere a funzioni chiave abilitate o limitate per i membri del gruppo.

I gruppi di ruoli possono essere personalizzati, se necessario. Per evitare la perdita accidentale dell'accesso, è consigliabile creare una copia del gruppo di ruoli esistente che si desidera personalizzare, assegnare alla copia un nome identificabile, apportare e verificare le modifiche al nuovo gruppo e assegnare le persone a tale gruppo nel modo appropriato.

**Gestione della privacy**: questo gruppo contiene tutti i ruoli di autorizzazione per la gestione della privacy in un singolo gruppo. Questo è il modo più semplice per iniziare rapidamente a gestire la gestione della privacy e a gestire il controllo degli accessi per altri gruppi che utilizzeranno la gestione della privacy. È inoltre adatta per le organizzazioni che non necessitano di autorizzazioni separate definite per gruppi di utenti distinti.

**Amministratori** gestione privacy : i membri di questo gruppo di ruoli si concentrano sulle attività di configurazione e amministrazione e hanno un ampio accesso alle funzioni di gestione della privacy, tra cui la creazione, la lettura, l'aggiornamento e l'eliminazione dei criteri di gestione della privacy, le richieste di diritti dell'oggetto, le autorizzazioni di gestione della privacy e le impostazioni di gestione della privacy.

**Analisti della gestione della privacy:** i membri di questo gruppo di ruoli agiscono come analisti dei casi di gestione della privacy. Possono analizzare le corrispondenze dei criteri, visualizzare i metadati dei file ed eseguire azioni correttive. Questo gruppo non può accedere ai file completi tramite Esplora contenuto.

**Investigatori sulla gestione della privacy:** i membri di questo gruppo agiscono come investigatori dei dati di gestione della privacy. Possono analizzare le corrispondenze dei criteri, visualizzare il contenuto del file associato ed eseguire azioni correttive. Questo gruppo può accedere ai file tramite Esplora contenuto.

**Visualizzatore gestione privacy**: i membri di questo gruppo possono visualizzare informazioni analitiche nella gestione della privacy, ad esempio la panoramica, il profilo dati e i report delle richieste dell'oggetto.

**Subject Rights Request Administrators**: I membri di questo gruppo hanno accesso completo per amministrare e creare richieste di diritti dell'oggetto.

**Collaboratori per la gestione della privacy:** i membri di questo gruppo hanno accesso ai collaboratori alle richieste di diritti dell'oggetto.

Per visualizzare i ruoli specifici inclusi in ogni gruppo di ruoli, vedere la tabella seguente.

| **Gruppo di ruoli**      | **Ruoli inclusi**                        |
|:-- |:--|
| Gestione della privacy  | Gestione dei casi                           |
|                     | Visualizzatore contenuto classificazione dati        |
|                     | Visualizzatore elenco classificazione dati           |
|                     | Amministratore gestione privacy                  |
|                     | Analisi della gestione della privacy               |
|                     | Indagine sulla gestione della privacy          |
|                     | Contributo permanente per la gestione della privacy |
|                     | Contributo temporaneo sulla gestione della privacy |
|                     | Visualizzatore gestione privacy                 |
|                     | Amministratore richiesta diritti soggetto              |
|                     | View-Only case                            |
| Amministratore gestione privacy | Gestione dei casi                      |
|                          | Amministratore gestione privacy             |
|                          | View-Only case                       |
| Analisti della gestione della privacy | Gestione dei casi                   |
|                             | Visualizzatore elenco classificazione dati   |
|                             | Analisi della gestione della privacy       |
|                             | View-Only case                    |
| Investigatori per la gestione della privacy | Gestione dei casi              |
|                                  | Visualizzatore contenuto classificazione dati |
|                                  | Visualizzatore elenco classificazione dati    |
|                                  | Indagine sulla gestione della privacy   |
|                                  | View-Only case                     |
| Visualizzatore gestione privacy        | Visualizzatore gestione privacy          |
| Amministratore richiesta diritti soggetto | Amministratore richiesta diritti soggetto   |
|Collaboratori per la gestione della privacy       | Contributo temporaneo sulla gestione della privacy |
|                                      | Contributo permanente per la gestione della privacy |

## <a name="configure-settings"></a>Configurare le impostazioni

La Impostazioni è accessibile tramite il volante nell'angolo in alto a destra delle pagine principali della gestione della privacy. Consente agli amministratori di gestione della privacy di configurare le proprietà essenziali nella gestione della privacy. Le opzioni disponibili sono le seguenti.

### <a name="anonymization"></a>Anonimizzazione

Questa funzionalità consente di mostrare le versioni anonime dei nomi utente all'interno delle funzionalità di gestione della privacy agli utenti in determinati ruoli. Questo sostituirà i nomi visualizzati identificabili come "Grace Taylor" con un'etichetta generica come "AnonyIS8-988" per mascherare le identità degli utenti durante la revisione dei dati sensibili. Questa opzione non si applica al modulo di richiesta dei diritti dell'oggetto.

### <a name="user-notification-emails"></a>Messaggi di posta elettronica di notifica utente

Quando viene rilevata una corrispondenza per i criteri di gestione dei dati, la gestione della privacy può inviare un messaggio di posta elettronica agli utenti interessati con azioni correttive da intraprendere e un collegamento alla formazione sulla privacy. In Impostazioni, è possibile abilitare o disabilitare la funzionalità di notifica tramite posta elettronica della gestione della privacy nel suo complesso. È possibile attivare singole notifiche, impostare la frequenza di posta elettronica e specificare un URL di formazione quando si crea o si modifica un criterio. Se la funzionalità di notifica è disattivata in Impostazioni, qualsiasi configurazione a livello di criterio per messaggi di notifica specifici verrà disabilitata. Per ulteriori informazioni sui criteri, vedere [Create and manage policies.](privacy-management-policies.md)

### <a name="teams-collaboration"></a>Collaborazione in Teams

Integrare Microsoft Teams con la gestione della privacy per migliorare la collaborazione con gli stakeholder. Ogni volta che viene creata una richiesta di diritti dell'oggetto, verrà creato un team associato. Gli utenti possono essere aggiunti a un team dalla scheda Collaboratori della richiesta. Per ulteriori informazioni sulle richieste di diritti dell'oggetto, vedere [Manage subject rights requests.](privacy-management-subject-rights-requests.md)

### <a name="power-automate-flows"></a>Power Automate flussi

Usa Power Automate flussi di lavoro per gestire automaticamente processi e attività correlati alla privacy. Puoi creare flussi nella sezione Impostazioni usando i modelli di gestione della privacy predefiniti o usare la console Power Automate per creare flussi personalizzati. Per ulteriori informazioni sulle Power Automate, vedere la [documentazione Power Automate.](/power-automate/)

### <a name="data-matching"></a>Corrispondenza dati

Utilizzare questa sezione per caricare schemi di dati che descrivono gli attributi degli interessati, che consentono di identificare l'oggetto dei dati corretto durante la ricerca di dati personali all'interno dell'Microsoft 365 locale. Gli schemi e i pacchetti di regole vengono creati e caricati in formato XML. In Caricamento dati personali è inoltre possibile inviare dati personali che corrispondono a uno schema fornito. Puoi creare e caricare il tuo file o scegliere di caricare i dati personali da Azure. Per ulteriori informazioni sulle richieste di diritti dell'oggetto, vedere [Manage subject rights requests.](privacy-management-subject-rights-requests.md)

### <a name="data-retention-periods"></a>Periodi di conservazione dei dati

Per le richieste di diritti dell'oggetto, scegli per quanto tempo vuoi conservare i dati finali raccolti e segnalare dopo la chiusura di una richiesta. È possibile selezionare tra 30 o 90 giorni. Per ulteriori informazioni sulle richieste di diritti dell'oggetto, vedere [Manage subject rights requests.](privacy-management-subject-rights-requests.md)

### <a name="data-review-tags"></a>Tag di revisione dei dati

Gestisci i tag che userai per contrassegnare i file recuperati in una richiesta di diritti dell'oggetto. In questa sezione è possibile modificare i nomi e le descrizioni dei tag personalizzati. Puoi anche modificare le descrizioni dei tag per i tag predefiniti forniti dal sistema. I nomi dei tag di sistema non possono essere modificati. Per ulteriori informazioni sulle richieste di diritti dell'oggetto, vedere [Manage subject rights requests.](privacy-management-subject-rights-requests.md)

## <a name="get-initial-data-insights"></a>Ottenere informazioni dettagliate sui dati iniziali

Dopo aver effettuato l'accesso alla gestione della privacy, si arriva alla **pagina Panoramica.** Questa pagina fornisce informazioni dettagliate dinamiche sui dati personali archiviati nell'ambiente Microsoft 365 per individuare rapidamente i problemi, identificare gli indicatori di rischio e intervenire per risolvere i problemi. La panoramica dovrebbe essere popolata con informazioni dettagliate iniziali entro le prime 24 ore dalla registrazione. Mentre si continua a usare la gestione della privacy, la pagina di panoramica verrà aggiornata per continuare a fornire informazioni aggiornate.

Per ulteriori approfondimenti sui dati  nel tempo, la pagina del profilo dati fornirà più visualizzazioni e analisi e fornirà una visualizzazione di alto livello dei dati dell'organizzazione in base alla posizione geografica e al servizio Microsoft 365.

Per altre informazioni su queste pagine, vedi [Trovare e visualizzare i dati.](privacy-management-data-profile.md)
