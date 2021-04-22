---
title: Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts
description: Informazioni sul funzionamento delle code degli avvisi di Microsoft Defender for Endpoint e su come ordinare e filtrare gli elenchi di avvisi.
keywords: avvisi, code, coda degli avvisi, ordinare, ordinare, filtrare, gestire gli avvisi, nuovi, in corso, risolti, più recenti, tempo in coda, gravità, periodo di tempo, avvisi esperti di minacce Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934334"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

La **coda Avvisi** mostra un elenco di avvisi contrassegnati dai dispositivi della rete. Per impostazione predefinita, la coda visualizza gli avvisi visualizzati negli ultimi 30 giorni in una visualizzazione raggruppata. Gli avvisi più recenti vengono visualizzati all'inizio dell'elenco per visualizzare prima gli avvisi più recenti.

> [!NOTE]
> La coda degli avvisi è notevolmente ridotta con l'analisi e la correzione automatizzate, consentendo agli esperti delle operazioni di sicurezza di concentrarsi su minacce più sofisticate e altre iniziative di alto valore. Quando un avviso contiene un'entità supportata per l'indagine automatizzata (ad esempio, un file) in un dispositivo con un sistema operativo supportato, è possibile avviare un'indagine e una correzione automatizzate. Per ulteriori informazioni sulle indagini automatizzate, vedere [Overview of Automated investigations](automated-investigations.md).

Sono disponibili diverse opzioni tra cui è possibile scegliere per personalizzare la visualizzazione della coda degli avvisi. 

Nella barra di spostamento superiore è possibile:

- Selezionare la visualizzazione raggruppata o la visualizzazione elenco
- Personalizzare le colonne per aggiungere o rimuovere colonne 
- Selezionare gli elementi da visualizzare per pagina
- Spostarsi tra le pagine
- Applicazione di filtri

![Immagine della coda degli avvisi](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>Ordinare, filtrare e raggruppare la coda degli avvisi

È possibile applicare i filtri seguenti per limitare l'elenco degli avvisi e ottenere una visualizzazione più mirata degli avvisi.

### <a name="severity"></a>Gravità

Gravità avviso | Descrizione
:---|:---
Alto </br>(Rosso) | Avvisi comunemente visualizzati associati a minacce persistenti avanzate (APT). Questi avvisi indicano un rischio elevato a causa della gravità dei danni che possono infliggere ai dispositivi. Alcuni esempi sono: attività degli strumenti di furto di credenziali, attività ransomware non associate ad alcun gruppo, manomissione di sensori di sicurezza o attività dannose indicative di un avversario umano.
Medio </br>(Arancione) | Avvisi relativi al rilevamento degli endpoint e ai comportamenti di risposta post-violazione che potrebbero far parte di una minaccia persistente avanzata (APT). Ciò include comportamenti osservati tipici delle fasi di attacco, modifiche anomali del Registro di sistema, esecuzione di file sospetti e così via. Anche se alcuni potrebbero essere parte dei test di sicurezza interni, richiede un'indagine perché potrebbe anche essere parte di un attacco avanzato.
Basso </br>(Giallo) | Avvisi sulle minacce associate al malware prevalente. Ad esempio, strumenti di hacking, strumenti di hacking non malware, come l'esecuzione di comandi di esplorazione, la cancellazione dei registri e così via, che spesso non indicano una minaccia avanzata per l'organizzazione. Potrebbe anche derivare da un test isolato degli strumenti di sicurezza da parte di un utente dell'organizzazione.
Informativa </br>(Grigio) | Avvisi che potrebbero non essere considerati dannosi per la rete, ma che possono aumentare la consapevolezza della sicurezza dell'organizzazione su potenziali problemi di sicurezza.

#### <a name="understanding-alert-severity"></a>Informazioni sulla gravità degli avvisi

Le gravità degli avvisi di Microsoft Defender Antivirus (Microsoft Defender AV) e Defender for Endpoint sono diverse perché rappresentano ambiti diversi.

La gravità della minaccia di Microsoft Defender AV rappresenta la gravità assoluta della minaccia rilevata (malware) e viene assegnata in base al potenziale rischio per il singolo dispositivo, se infetto.

La gravità dell'avviso Defender for Endpoint rappresenta la gravità del comportamento rilevato, il rischio effettivo per il dispositivo, ma soprattutto il potenziale rischio per l'organizzazione.

Quindi, ad esempio:

- La gravità di un avviso defender per endpoint su una minaccia rilevata da Microsoft Defender AV che è stata completamente impedita e che non ha infettato il dispositivo è classificata come "informativo" perché non si è verificata alcuna minaccia effettiva.
- Un avviso su un malware commerciale è stato rilevato durante l'esecuzione, ma è stato bloccato e corretti da Microsoft Defender AV, è classificato come "Basso" perché potrebbe aver causato alcuni danni al singolo dispositivo, ma non rappresenta alcuna minaccia dell'organizzazione.
- Un avviso sul malware rilevato durante l'esecuzione che può rappresentare una minaccia non solo per il singolo dispositivo ma per l'organizzazione, indipendentemente dal fatto che sia stato bloccato alla fine, può essere classificato come "Medio" o "Alto".
- Gli avvisi comportamentali sospetti, che non sono stati bloccati o corretti, verranno classificati come "Low", "Medium" o "High" seguendo le stesse considerazioni sulle minacce organizzative.

#### <a name="understanding-alert-categories"></a>Informazioni sulle categorie di avviso

Abbiamo ridefinito le categorie di avviso per allinearsi alle [tattiche](https://attack.mitre.org/tactics/enterprise/) di attacco aziendale nella matrice [MITRE ATT&CK](https://attack.mitre.org/). I nuovi nomi di categoria si applicano a tutti i nuovi avvisi. Gli avvisi esistenti manderanno i nomi delle categorie precedenti.

Nella tabella seguente sono elencate le categorie correnti e il modo in cui vengono in genere mappate alle categorie precedenti. 

| Nuova categoria       | Nome categoria API   | Attività o componente delle minacce rilevate                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Raccolta           | Raccolta          | Individuazione e raccolta di dati per l'esfiltrazione                                                                                         |
| Comando e controllo  | CommandAndControl   | Connessione all'infrastruttura di rete controllata da un utente malintenzionato per inoltrare dati o ricevere comandi                                          |
| Accesso alle credenziali    | CredentialAccess    | Ottenere credenziali valide per estendere il controllo su dispositivi e altre risorse nella rete                                       |
| Evasione della difesa      | DefenseEvasion      | Evitare i controlli di sicurezza, ad esempio disattivando le app di sicurezza, eliminando gli impianto e eseguendo rootkit                        |
| Individuazione            | Individuazione           | Raccolta di informazioni su dispositivi e risorse importanti, ad esempio computer di amministratore, controller di dominio e file server  |
| Esecuzione            | Esecuzione           | Avvio di strumenti di attacco e codice dannoso, tra cui RATI e backdoor                                                             |
| Exfiltration         | Exfiltration        | Estrazione dei dati dalla rete in una posizione esterna controllata da un utente malintenzionato                                                         |
| Exploit              | Exploit             | Codice di exploit e possibile attività di sfruttamento                                                                                       |
| Accesso iniziale       | InitialAccess       | Ottenere l'immissione iniziale nella rete di destinazione, in genere con tentativi di indovinare password, exploit o messaggi di posta elettronica di phishing                      |
| Movimento laterale     | LateralMovement     | Spostamento tra dispositivi nella rete di destinazione per raggiungere risorse critiche o ottenere la persistenza della rete                                |
| Malware              | Malware             | Backdoor, trojan e altri tipi di codice dannoso                                                                                 |
| Persistenza          | Persistenza         | Creazione di punti di estendibilità dell'avvio automatico (ASEP) per rimanere attivi e superare i riavvii del sistema                                        |
| Escalation dei privilegi | PrivilegeEscalation | Ottenere livelli di autorizzazione superiori per il codice eseguendolo nel contesto di un processo o di un account con privilegi                         |
| Ransomware           | Ransomware          | Malware che crittografa i file ed estorce il pagamento per ripristinare l'accesso                                                                     |
| Attività sospette  | SuspiciousActivity  | Attività atipiche che potrebbero essere attività di malware o parte di un attacco                                                                 |
| Software indesiderato    | UnwantedSoftware    | App e app di bassa reputazione che influiscono sulla produttività e sull'esperienza utente; rilevato come applicazioni potenzialmente indesiderate (PUA) |

### <a name="status"></a>Stato

È possibile scegliere di limitare l'elenco di avvisi in base al relativo stato.

### <a name="investigation-state"></a>Stato dell'indagine

Corrisponde allo stato di analisi automatica.

### <a name="category"></a>Categoria

È possibile scegliere di filtrare la coda per visualizzare tipi specifici di attività dannose.

### <a name="assigned-to"></a>Assegnata a

Puoi scegliere tra la visualizzazione degli avvisi assegnati all'utente o l'automazione.

### <a name="detection-source"></a>Origine di rilevamento

Selezionare l'origine che ha attivato il rilevamento degli avvisi. I partecipanti all'anteprima di Microsoft Threat Experts possono ora filtrare e visualizzare i rilevamenti del nuovo servizio di ricerca gestito da esperti di minacce.

>[!NOTE]
>Il filtro Antivirus verrà visualizzato solo se i dispositivi usano Microsoft Defender Antivirus come prodotto antimalware di protezione in tempo reale predefinito.

| Origine di rilevamento                  | Valore API                  |
|-----------------------------------|----------------------------|
| Sensori di terze parti                 | ThirdPartySensors          |
| Antivirus                         | WindowsDefenderAv          |
| Indagine automatizzata           | AutomatedInvestigation     |
| Rilevamento personalizzato                  | CustomDetection            |
| Ti personalizzato                         | CustomerTI                 |
| EDR                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | MTP                        |
| Microsoft Defender per Office 365 | OfficeATP                  |
| Microsoft Threat Experts          | ThreatExperts              |
| SmartScreen                       | WindowsDefenderSmartScreen |

### <a name="os-platform"></a>Piattaforma del sistema operativo

Limita la visualizzazione della coda degli avvisi selezionando la piattaforma del sistema operativo che vuoi analizzare.

### <a name="device-group"></a>Gruppo di dispositivi

Se hai gruppi di dispositivi specifici che vuoi controllare, puoi selezionare i gruppi per limitare la visualizzazione della coda degli avvisi. 

### <a name="associated-threat"></a>Minaccia associata

Utilizzare questo filtro per concentrarsi sugli avvisi correlati alle minacce di alto profilo. È possibile visualizzare l'elenco completo delle minacce di alto profilo in [Analisi delle minacce](threat-analytics.md).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire gli avvisi di Microsoft Defender for Endpoint](manage-alerts.md)
- [Analizzare gli avvisi di Microsoft Defender for Endpoint](investigate-alerts.md)
- [Analizzare un file associato a un avviso di Microsoft Defender for Endpoint](investigate-files.md)
- [Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint](investigate-machines.md)
- [Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint](investigate-ip.md)
- [Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint](investigate-domain.md)
- [Analizzare un account utente in Microsoft Defender for Endpoint](investigate-user.md)
