---
title: Panoramica di Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
search.appverid:
- MOE150
- MET150
description: Informazioni su Microsoft Compliance Manager, uno strumento di valutazione dei rischi basato sul flusso di lavoro gratuito in Microsoft Service Trust Portal.
ms.openlocfilehash: 84f076a45a3944d1d711a8e04199b357aa52791d
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224643"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft Compliance Manager (anteprima)

> [!IMPORTANT]
> Compliance Manager non è disponibile in Office 365 gestito da 21Vianet, Office 365 Germany, Office 365 U.S. Government Community High (GCC High) o Office 365 Dipartimento della Difesa.

**In questo articolo**leggere questo articolo per informazioni su quali Compliance Manager è e comprendere i componenti principali.

Informazioni **sugli aggiornamenti**: sono stati pubblicati diversi aggiornamenti nella versione di anteprima pubblica di aprile 2020. Visitare le [Note sulla versione di Compliance Manager](compliance-manager-release-notes.md) per visualizzare i problemi nuovi e noti.

## <a name="what-is-compliance-manager"></a>Che cos'è Compliance Manager

[Microsoft Compliance Manager (Preview)](https://servicetrust.microsoft.com/ComplianceManager) è uno strumento gratuito di valutazione dei rischi basato sul flusso di lavoro in Microsoft Service Trust Portal per la gestione delle attività di conformità alle normative relative ai servizi cloud di Microsoft. Parte dell'abbonamento a Microsoft 365, Office 365 o Azure Active Directory, Compliance Manager consente di gestire la conformità normativa all'interno del modello di responsabilità condivisa per i servizi cloud Microsoft.

Con Compliance Manager, l'organizzazione può:
  
- Combinare informazioni dettagliate sulla conformità fornite ai revisori e ai regolatori dei servizi cloud con l'autovalutazione di conformità per gli standard e le normative applicabili alla propria organizzazione. Sono inclusi gli standard e i regolamenti delineati dall'organizzazione internazionale per la standardizzazione (ISO), dall'Istituto nazionale per gli standard e dalla tecnologia (NIST), dalla portabilità di assicurazione malattia e dalla legge sulla responsabilità (HIPAA), dal regolamento generale sulla protezione dei dati (GDPR) e da molti altri.
- Consentono di assegnare, monitorare e registrare le attività relative alla conformità e alla valutazione, che consentono all'organizzazione di superare le barriere del team per raggiungere gli obiettivi di conformità.
- Fornire un punteggio di conformità che consenta di monitorare lo stato di avanzamento e la priorità dei controlli di controllo che consentono di ridurre l'esposizione ai rischi dell'organizzazione.
- Fornire un repository sicuro per l'upload e la gestione di evidenze e altri elementi correlati alle attività di conformità.
- Produrre rapporti di Microsoft Excel riccamente dettagliati che documentano le attività di conformità eseguite da Microsoft e dalla propria organizzazione per i revisori, i regolatori e altri revisori di conformità.

  
> [!IMPORTANT]
> I consigli di Compliance Manager e Punteggio di conformità non devono essere interpretati come una garanzia di conformità. Spetta a te valutare e convalidare l'efficacia dei controlli del cliente per il tuo ambiente normativo. Questi servizi sono attualmente in anteprima e sono soggetti ai termini e alle condizioni nelle condizioni dei [servizi online](https://go.microsoft.com/fwlink/?linkid=2108910). Vedere anche [linee guida per la gestione delle licenze di Microsoft 365 per sicurezza e conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="relationship-to-compliance-score"></a>Relazione con punteggio di conformità

[Microsoft Compliance Score (Preview)](compliance-score.md) è una funzionalità del centro conformità di Microsoft 365 che fornisce una visualizzazione di primo livello nella posizione di conformità dell'organizzazione. Calcola un punteggio basato sui rischi misurando lo stato di avanzamento del processo di completamento delle azioni che consentono di ridurre i rischi per la protezione dei dati e gli standard normativi. La conoscenza del Punteggio di conformità globale aiuta l'organizzazione a comprendere e gestire la conformità. Capire in [che modo viene calcolato il Punteggio di conformità](compliance-score-methodology.md).

Compliance Manager condivide lo stesso backend con punteggio di conformità. Durante la fase di anteprima pubblica per entrambi gli strumenti, Compliance Manager è la posizione in cui verranno gestite le valutazioni e le implementazioni dei controlli personalizzati. Per ulteriori informazioni [, vedere relazione tra conformità score e Compliance Manager](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="compliance-manager-components"></a>Componenti di Compliance Manager

Compliance Manager utilizza diversi componenti che consentono di eseguire le attività di gestione della conformità. Questi componenti interagiscono per fornire un flusso di lavoro di gestione completo e rapporti di conformità senza problemi per i revisori.

Nel diagramma vengono illustrate le relazioni tra i componenti principali di Compliance Manager:

![Relazioni in Compliance Manager versione 3](../media/compliance-manager-relationships.png)

## <a name="groups"></a>Gruppi

I [gruppi](working-with-compliance-manager.md#groups) sono contenitori che consentono di organizzare valutazioni e condividere le informazioni comuni e le attività del flusso di lavoro tra le valutazioni che dispongono dello stesso o dei controlli gestiti dal cliente. Quando due diverse valutazioni nello stesso gruppo condividono il controllo gestito dal cliente, il completamento dei dettagli dell'implementazione, il testing e lo stato del controllo vengono sincronizzati automaticamente allo stesso controllo in qualsiasi altra valutazione del gruppo. Questo unifica gli elementi di azione assegnati per ogni controllo nel gruppo e riduce il lavoro di duplicazione. È inoltre possibile scegliere di utilizzare i gruppi da organizzare. Valutazioni per anno, area, standard di conformità o altri raggruppamenti per facilitare l'organizzazione del lavoro di conformità.

## <a name="assessments"></a>Valutazioni

Le [valutazioni](working-with-compliance-manager.md#assessments) sono contenitori che consentono di organizzare i controlli in base alle responsabilità condivise tra Microsoft e l'organizzazione per valutare i rischi per la sicurezza e la conformità dei servizi cloud. Le valutazioni consentono di implementare le misure di salvaguardia della protezione dei dati specificate da standard di conformità e standard di protezione dei dati applicabili, regolamenti o leggi. Consentono di discernere la protezione dei dati e la posizione di conformità rispetto allo standard del settore selezionato per il servizio cloud Microsoft selezionato. Le valutazioni sono state completate dall'implementazione dei controlli inclusi nella valutazione che corrispondono a uno standard di certificazione.

Per impostazione predefinita, Compliance Manager crea le seguenti valutazioni per l'organizzazione:

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 GDPR

Le valutazioni hanno diversi componenti:
  
- **Servizi nell'ambito**: ogni valutazione si applica a un set specifico di servizi Microsoft.
- **Controlli gestiti Microsoft**: per ogni servizio cloud, Microsoft implementa e gestisce un insieme di controlli di conformità per gli standard e le normative applicabili.
- **Controlli gestiti dal cliente**: questi controlli vengono implementati dall'organizzazione quando si eseguono azioni per ogni controllo.
- **Punteggio di valutazione**: la percentuale del punteggio totale possibile per i controlli gestiti dal cliente nella valutazione. In questo modo è possibile monitorare l'implementazione delle azioni assegnate a ogni controllo.

## <a name="controls"></a>Controlli

I [controlli](working-with-compliance-manager.md#controls-and-actions) sono contenitori dei processi di conformità in Compliance Manager che definiscono la modalità di gestione delle attività di conformità. Questi controlli sono organizzati in famiglie di controllo che si allineano con la struttura di valutazione per le certificazioni o le normative corrispondenti.

- **ID di controllo**: il nome del controllo selezionato dalla certificazione o dal regolamento corrispondente.
- **Titolo di controllo**: il titolo dell'ID di controllo della certificazione o del regolamento corrispondente.
- **ID articolo**: questo campo è solo per le valutazioni di GDPR e specifica il numero dell'articolo GDPR corrispondente.
- **Descrizione**: testo del controllo dalla certificazione o dalla regolamentazione corrispondente. A causa di limitazioni del copyright, un collegamento alle informazioni rilevanti è elencato per gli standard ISO.

![Controlli in Compliance Manager versione 3](../media/compliance-manager-controls.png)

Sono disponibili tre tipi di controlli in Compliance Manager, **controlli gestiti da Microsoft**, **controlli gestiti dal cliente**e **controlli di gestione condivisi**.

### <a name="microsoft-managed-controls"></a>Controlli gestiti da Microsoft

Per ogni servizio cloud, Microsoft implementa e gestisce un insieme di controlli come parte della conformità di Microsoft con vari standard e normative. Ogni controllo fornisce informazioni dettagliate sul modo in cui Microsoft ha implementato il controllo e su come e quando tale implementazione è stata testata e convalidata da Microsoft e/o da un revisore di terze parti indipendente.

### <a name="customer-managed-controls"></a>Controlli gestiti dal cliente

I controlli gestiti dal cliente sono gestiti dall'organizzazione. L'organizzazione è responsabile dell'implementazione del controllo gestito dal cliente nell'ambito del processo di conformità per un determinato standard o regolamentazione. I controlli gestiti dal cliente sono organizzati in famiglie di controllo per la certificazione o regolamentazione corrispondente. Utilizzare i controlli gestiti dal cliente per implementare le azioni consigliate suggerite da Microsoft come parte delle attività di conformità. L'organizzazione può utilizzare le istruzioni e le azioni dei clienti consigliate in ogni controllo gestito dal cliente per gestire il processo di implementazione e valutazione per tale controllo.

I controlli gestiti dal cliente nelle valutazioni dispongono anche di funzionalità di gestione dei flussi di lavoro incorporate che è possibile utilizzare per gestire e monitorare i progressi compiuti verso il completamento della valutazione. Con questa funzionalità del flusso di lavoro, è possibile:

- Assegnare elementi azione per ogni controllo
- Registrare gli elementi di azione assegnati
- Caricare la prova dell'implementazione del controllo
- Documentare il testing e la convalida del controllo
- Contrassegnare gli elementi di azione come implementato e testato

Ad esempio, un responsabile della conformità nell'organizzazione assegna un elemento di azione a un amministratore IT con la responsabilità e le autorizzazioni necessarie per eseguire l'azione consigliata. L'amministratore IT carica la prova delle attività di implementazione (schermate delle impostazioni di configurazione o dei criteri) e assegna la voce di azione al responsabile della conformità al termine dell'operazione. Il responsabile della conformità valuta l'evidenza raccolta, verifica l'implementazione del controllo e registra la data di implementazione e i risultati dei test in Compliance Manager.

### <a name="shared-management-controls"></a>Controlli di gestione condivisi

Un controllo condiviso si riferisce a qualsiasi controllo in cui Microsoft e i clienti condividono le responsabilità per l'implementazione. Ad esempio, i controlli relativi alla selezione del personale, alla gestione degli account e delle password e alla crittografia richiedono azioni sia di Microsoft che dei clienti.

## <a name="action-items"></a>Attività

[Gli elementi Actions](working-with-compliance-manager.md#controls-and-actions) sono inclusi nei controlli gestiti dal cliente come parte della funzionalità di gestione dei flussi di lavoro incorporata che è possibile utilizzare per gestire e monitorare i progressi compiuti verso il completamento della valutazione.

Gli utenti dell'organizzazione possono utilizzare Compliance Manager per esaminare i controlli gestiti dal cliente da tutte le valutazioni per cui sono stati assegnati. Quando un utente accede a Responsabile Conformità e apre la dashboard **Azioni**, viene visualizzato un elenco delle attività assegnate all'utente stesso. In base al ruolo di Compliance Manager assegnatogli, l'utente può fornire dettagli relativi all'implementazione o al test, aggiornare lo stato o assegnare attività.

I controlli di certificazione vengono in genere implementati da una persona e testati da un altro. Ad esempio, dopo aver completato gli elementi dell'azione inizialmente assegnati a una persona per l'implementazione, gli elementi di azione vengono assegnati alla persona successiva per testare e caricare la prova. Gli utenti che dispongono di autorizzazioni sufficienti per le assegnazioni di controllo possono assegnare e riassegnare gli elementi di azione. In questo modo è possibile gestire in modo centralizzato le assegnazioni dei controlli e il routing decentralizzato degli elementi di azione tra gli implementatori e i tester.

Si noti che le **azioni di miglioramento** nel punteggio di conformità sono equivalenti agli **elementi azione** in Compliance Manager.

## <a name="permissions"></a>Autorizzazioni

Compliance Manager usa un modello di autorizzazione di controllo dell'accesso basato sui ruoli. Solo agli utenti a cui è stato assegnato il ruolo utente è consentito di accedere a Compliance Manager e le azioni consentite da ogni utente sono limitate in base al tipo di ruolo. [Visualizzare una tabella](working-with-compliance-manager.md#permissions) in cui sono riportate le azioni consentite per ogni autorizzazione.

L'amministratore del portale per Compliance Manager può impostare le autorizzazioni per gli altri utenti all'interno di Compliance Manager attenendosi alla procedura seguente:

1. Dal menu a discesa **in alto,** selezionare **amministratore**, quindi **Impostazioni**.
2. Selezionare il ruolo che si desidera assegnare e quindi aggiungere il dipendente che si desidera assegnare a quel ruolo. Gli utenti saranno quindi in grado di eseguire determinate azioni.

Gli utenti a cui è assegnato il [ruolo di lettore globale in Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader) dispongono dell'autorizzazione di sola lettura per accedere a Compliance Manager. Tuttavia, non sono in grado di modificare i dati o di eseguire azioni all'interno di Compliance Manager.

Non esiste più un ruolo di **accesso Guest** predefinito. A ogni utente deve essere assegnato un ruolo per poter accedere e lavorare in Compliance Manager.
  
## <a name="manage-evidence"></a>Gestione delle evidenze

Compliance Manager è in grado di archiviare la prova delle attività di implementazione relative al testing e alla convalida dei controlli gestiti dal cliente. Evidence include documenti, fogli di calcolo, schermate, immagini, script, file di output dello script e altri file. Compliance Manager riceve automaticamente anche la telemetria e crea un record di prova per gli elementi azione integrati con il Punteggio sicuro. Tutti i dati caricati come elementi di prova in Compliance Manager sono archiviati negli Stati Uniti nei siti di archiviazione cloud Microsoft. Questi dati vengono replicati tra le aree di Azure situate nel sudest asiatico e nell'Europa occidentale.

## <a name="templates"></a>Modelli

Compliance Manager fornisce [modelli](working-with-compliance-manager.md#templates) preconfigurati per le valutazioni e consente di creare modelli personalizzati per i controlli gestiti dal cliente per soddisfare i requisiti di conformità. I nuovi modelli vengono creati importando le informazioni sui controlli da un file di Excel oppure è possibile creare un modello da una copia di un modello esistente.

I modelli preconfigurati sono i seguenti:

1. [Legge generale sulla protezione dei dati (LGPD) in Brasile](https://go.microsoft.com/fwlink/?linkid=2115387)
2. [California Consumer Privacy Act (CCPA)](https://go.microsoft.com/fwlink/?linkid=2108871) (anteprima)
3. [Matrice dei controlli cloud di Cloud Security Alliance (CSA) (CCM) 3.0.1](https://go.microsoft.com/fwlink/?linkid=2109076)
4. [GDPR Unione europea](https://go.microsoft.com/fwlink/?linkid=2108870)
5. [Opuscolo sulla sicurezza delle istituzioni finanziarie federali (FFIEC)](https://go.microsoft.com/fwlink/?linkid=2109077)
6. [FedRAMP moderato](https://go.microsoft.com/fwlink/?linkid=2108869)
7. [HIPAA](https://go.microsoft.com/fwlink/?linkid=2109078)  /  [Hitech](https://go.microsoft.com/fwlink/?linkid=2109079)
8. [IRAP](https://go.microsoft.com/fwlink/?linkid=2113709)  /  ISM (anteprima) del [governo australiano](https://go.microsoft.com/fwlink/?linkid=2113024)
9. [ISO 27001:2013](https://go.microsoft.com/fwlink/?linkid=2109073)
10. [ISO 27018:2014](https://go.microsoft.com/fwlink/?linkid=2109074)
11. [ISO 27701:2019](https://go.microsoft.com/fwlink/?linkid=2113025)
12. [Linea di base per la protezione dei dati di Microsoft 365](compliance-score-methodology.md#initial-score-based-on-microsoft-365-data-protection-baseline)
13. [NIST 800-53 Rev. 4](https://go.microsoft.com/fwlink/?linkid=2109075)
14. [NIST 800-171](https://go.microsoft.com/fwlink/?linkid=2108867)
15. [NIST Cybersecurity Framework (CSF)](https://go.microsoft.com/fwlink/?linkid=2108868)
16. [SOC 1](https://go.microsoft.com/fwlink/?linkid=2115184)
17. [SOC 2](https://go.microsoft.com/fwlink/?linkid=2115184)

## <a name="secure-score-integration"></a>Integrazione del Punteggio sicuro

Compliance Manager è integrato con [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) per applicare automaticamente il credito al Punteggio sicuro al Punteggio di conformità per gli elementi di azione sincronizzati. Questa operazione è configurabile per singoli elementi azione o tutte le azioni a livello globale e fornisce gli aggiornamenti da un punteggio sicuro.

Ad esempio, si dispone di un requisito relativo alla sicurezza per l'attivazione di Azure Rights Management nell'organizzazione che si applica anche a un elemento di azione correlato alla conformità. Quando Azure Rights Management viene attivato ed elaborato dal punteggio sicuro, Compliance Manager riceve la notifica dell'aggiornamento e il punteggio dell'azione viene aggiornato automaticamente con il credito di completamento.

## <a name="ready-to-get-started"></a>Pronti per iniziare?

Iniziare a [lavorare con Compliance Manager](working-with-compliance-manager.md) per gestire le attività di conformità alle normative per l'organizzazione.

## <a name="resources"></a>Risorse

- [Guida interattiva: valutare e migliorare i controlli di protezione dei dati con Compliance Manager](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft sicurezza, privacy e conformità Tech community](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)