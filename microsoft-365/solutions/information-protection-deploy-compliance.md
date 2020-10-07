---
title: Utilizzo di Compliance Manager per gestire le azioni di miglioramento
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Informazioni su come utilizzare Score compliance e Compliance Manager per migliorare il livello di protezione dei dati personali.
ms.openlocfilehash: 5b41fa9fc52253d415a22aaa3422a87c4f1bda7c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377100"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Utilizzo di Compliance Manager per gestire le azioni di miglioramento

Microsoft Compliance Manager può aiutare a gestire i miglioramenti relativi alle normative sulla privacy dei dati, come il [regolamento generale sulla protezione dei dati (GDPR)](../compliance/gdpr.md), la [California Consumer Protection Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (US Health Care Privacy Act) e il Brasile Data Protection Act (LGPD).

In questo articolo vengono fornite indicazioni sull'utilizzo di questo strumento per la privacy dei dati.

>[!Note]
>I consigli di Compliance Manager non devono essere interpretati come una garanzia di conformità. Spetta a te valutare e convalidare l'efficacia dei controlli del cliente per il tuo ambiente normativo. Questi servizi sono soggetti ai termini e alle condizioni nelle condizioni dei [servizi online](https://go.microsoft.com/fwlink/?linkid=2108910). Vedere anche [Microsoft 365 Licensing guidance per la sicurezza e la conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Guida introduttiva a Compliance Manager

#### <a name="what-is-compliance-manager"></a>Che cos'è Compliance Manager

[Compliance Manager](../compliance/compliance-manager.md) è uno strumento di valutazione dei rischi basato sul flusso di lavoro nel centro conformità Microsoft 365 per la gestione delle attività di conformità alle normative relative ai servizi cloud Microsoft. Come parte dell'abbonamento a Microsoft 365 o Azure Active Directory (Azure AD), Compliance Manager consente di gestire la conformità normativa all'interno del modello di responsabilità condivisa per i servizi cloud Microsoft.

**Valutazioni pronte per l'uso**

Compliance Manager fornisce modelli predefiniti per la [creazione di valutazioni](../compliance/compliance-manager-assessments.md) allineate ai regolamenti relativi alla privacy dei dati, ad esempio GDPR e HIPAA/HITECH. I modelli dispongono di un mapping di controllo incorporato che consente di eseguire azioni di miglioramento per soddisfare i requisiti del regolamento. Ogni valutazione fornisce informazioni sui controlli che ogni regolamento richiede specifiche per il servizio di destinazione, suddivisi per i controlli gestiti e controllati da Microsoft Manage. 

L'utilizzo di un modello predefinito consente di iniziare rapidamente a valutare i rischi. Man mano che si diventa più abili nell'utilizzo di gestione conformità, è possibile personalizzare un modello precompilato aggiungendo i propri controlli e le azioni di miglioramento oppure è possibile creare valutazioni personalizzate in base alle esigenze dell'organizzazione.

Visualizzare l' [elenco completo dei modelli di valutazione](../compliance/compliance-manager-templates-list.md) forniti da Compliance Manager.

**Punteggio di conformità in tempo reale**

Compliance Manager fornisce anche un punteggio di conformità che misura lo stato di avanzamento del completamento delle azioni di miglioramento consigliate all'interno dei controlli. È possibile utilizzare questo punteggio per monitorare lo stato di avanzamento e assegnare priorità alle azioni in base alle proprie potenzialità di riduzione dei rischi.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Utilizzare la Guida introduttiva di Compliance Manager

La Guida [introduttiva di Compliance Manager](../compliance/compliance-manager-quickstart.md) fornisce i passaggi e i collegamenti graduali alle risorse chiave utili per l'utilizzo di Compliance Manager:

- [Prima visita: familiarizzare con Compliance Manager](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Utilizzo del dashboard di Compliance Manager
    - Informazioni sul punteggio di conformità
    - Informazioni sulle azioni di miglioramento
    - Informazioni su valutazioni e modelli
- [Ramping up: configurare Compliance Manager per gestire le attività di conformità](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Creazione e gestione della prima valutazione
    - Esecuzione di operazioni di implementazione e testing sulle azioni di miglioramento per completare i controlli nelle valutazioni
    - Informazioni sul modo in cui le diverse azioni incidono sul punteggio di conformità
- [Scalabilità verticale: utilizzare funzionalità avanzate per soddisfare le proprie esigenze personalizzate](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Creazione di valutazioni personalizzate per la registrazione di prodotti non Microsoft 365
    - Modifica dei modelli esistenti per l'aggiunta o la rimozione di controlli
    - Configurazione del testing automatizzato delle azioni di miglioramento

## <a name="how-your-compliance-score-is-calculated"></a>Come viene calcolato il punteggio di conformità

Il Punteggio di conformità è calcolato in base a una combinazione di implementazioni di controlli Microsoft e di controllo gestito dal cliente. Per una spiegazione dettagliata, vedere [calcolo del Punteggio di conformità](../compliance/compliance-score-calculation.md) .

Ai controlli viene assegnato un valore di punteggio in base al fatto che siano obbligatori o discrezionali e siano essi preventivo, investigativo o correttivo. Tali collettivamente rappresentano il rischio di non implementarlo in relazione ad altri controlli.

Come illustrato nell'articolo di calcolo del Punteggio di conformità, i controlli preventivi ottengono un punteggio più alto rispetto a quelli di detective e correttivi e i controlli obbligatori ottengono un punteggio più alto rispetto a quelli discrezionali.

L'interfaccia utente di amministrazione del Punteggio di conformità non elenca questi parametri, né fornisce la possibilità di filtrarli. Tuttavia, se si Scarica il modello associato da Compliance Manager, il set di dati risultante elenca questi parametri per la maggior parte delle normative.

Per i controlli tecnici, Compliance Manager aggiorna automaticamente il Punteggio di azione di miglioramento dopo che l'azione è stata implementata e testata correttamente. Altre azioni di controllo non tecnico, come &mdash; quelle che sono operative o correlate alla documentazione &mdash; , devono essere registrate manualmente come implementate prima del conteggio dei punti verso la partitura.

È inoltre possibile implementare alcune azioni di miglioramento per altri scopi &mdash; , ad esempio l'utilizzo di etichette di conservazione per motivi diversi dalla conformità alla normativa sulla privacy dei dati in &mdash; modo da ottenere credito per l'utilizzo di tale caratteristica anche se viene utilizzato per altri scopi e non parte di un'azione di conformità deliberata.

Il Punteggio di conformità deve essere considerato una misura relativa per tenere conto del miglioramento su vasta scala. Non è necessario perseguire un punteggio perfetto.

## <a name="additional-guidance"></a>Indicazioni aggiuntive

Di seguito sono riportate alcune importanti informazioni utili per l'utilizzo di Compliance Manager per ottenere la conformità alla normativa sulla privacy dei dati:

- Ogni normativa sulla privacy dei dati contiene una combinazione di controlli tecnici, specifiche della documentazione e requisiti operativi, di processo e di creazione di report. Tutte queste operazioni vengono visualizzate nelle azioni di miglioramento.

- Per concentrare la visualizzazione delle azioni di miglioramento nell'area di interesse, è possibile filtrare in base al tipo di azione nella scheda **soluzioni** dell'amministratore di Compliance Manager. Per ulteriori informazioni, [vedere filtrare la visualizzazione dashboard di Compliance Manager](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- L'importanza relativa e la priorità delle azioni di miglioramento identificate in Compliance Manager devono essere considerate come parte di una più ampia revisione dei rischi insieme al rischio di privacy dei dati che è stato determinato dall'organizzazione.

- Anche con l'aggregazione delle azioni di miglioramento tra più requisiti normativi, se vengono selezionati i modelli di valutazione della regolamentazione per GDPR, LGPD, CCPA e HIPAA-HITECH, ad esempio, quasi 400 azioni di miglioramento saranno elencate in Compliance Manager. Per gestire meglio questo lungo elenco, utilizzare il filtro azione miglioramento per ridurre il set di risultati a un elenco più gestibile.

- Il filtro categorie fornisce un mezzo per filtrare le azioni di miglioramento tramite raggruppamento logico, in cui la pista, prevenire, proteggere, conservare ed esaminare gli articoli in questa soluzione complessiva è allineata a.

- Alcuni dei controlli elencati nelle azioni di miglioramento possono essere considerati più direttamente associati a un determinato articolo normativo, mentre altri controlli possono essere connessi più indirettamente allo spirito di un regolamento e molte volte sono semplicemente attività consigliate o procedure consigliate.