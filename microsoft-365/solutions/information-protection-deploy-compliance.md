---
title: Utilizzare Compliance Manager per gestire le azioni di miglioramento
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
description: Informazioni su come usare Compliance Score e Compliance Manager per migliorare il livello di protezione dei dati personali.
ms.openlocfilehash: 26e9f54ce77869f4f6ef07c18147483628ddc223
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229300"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Utilizzare Compliance Manager per gestire le azioni di miglioramento

Microsoft Compliance Manager consente di gestire i miglioramenti correlati alle normative sulla privacy dei dati, come il Regolamento generale sulla protezione dei dati [(GDPR)](/compliance/regulatory/gdpr)dell'Unione Europea, [il California Consumer Protection Act CCPA,](/compliance/regulatory/ccpa-faq)HIPAA-HITECH (US Health Care Privacy Act) e il Brazil Data Protection Act (LGPD).

In questo articolo vengono fornite indicazioni sull'utilizzo di questo strumento per scopi di privacy dei dati.

> [!NOTE]
> I consigli di Compliance Manager non devono essere interpretati come una garanzia di conformità. L'utente deve valutare e convalidare l'efficacia dei controlli dei clienti in base all'ambiente normativo. Questi servizi sono soggetti ai termini e alle condizioni delle Condizioni [dei Servizi online.](https://go.microsoft.com/fwlink/?linkid=2108910) Vedi anche indicazioni [Microsoft 365 licenze per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>Introduzione a Compliance Manager

#### <a name="what-is-compliance-manager"></a>Che cos'è Compliance Manager

[Compliance Manager è](../compliance/compliance-manager.md) uno strumento di valutazione dei rischi basato sul flusso di lavoro nel Centro conformità Microsoft 365 per la gestione delle attività di conformità normative correlate ai servizi cloud Microsoft. Nell'ambito della sottoscrizione Microsoft 365 o Azure Active Directory (Azure AD), Compliance Manager consente di gestire la conformità normativa all'interno del modello di responsabilità condivisa per i servizi cloud Microsoft.

**Valutazioni pronte per l'uso**

Compliance Manager fornisce modelli [](../compliance/compliance-manager-assessments.md) predefiniti per la creazione di valutazioni allineate alle normative relative alla privacy dei dati, ad esempio GDPR e HIPAA/HITECH. I modelli dispongono di un mapping di controllo incorporato che consente di eseguire azioni di miglioramento per soddisfare i requisiti del regolamento. Ogni valutazione fornisce informazioni sui controlli che ogni regolamento richiede per il servizio di destinazione, suddiviso dai controlli gestiti e gestiti da Microsoft.

L'utilizzo di un modello predefinito consente di iniziare rapidamente a valutare i rischi. Quando si diventa più esperti nell'utilizzo di Compliance Manager, è possibile personalizzare un modello predefinito aggiungendo controlli e azioni di miglioramento personalizzati oppure creare valutazioni personalizzate in base alle esigenze dell'organizzazione.

Visualizzare [l'elenco completo dei modelli di valutazione](../compliance/compliance-manager-templates-list.md) forniti da Compliance Manager.

**Punteggio di conformità in tempo reale**

Compliance Manager fornisce anche un punteggio di conformità che misura i progressi nel completamento delle azioni di miglioramento consigliate all'interno dei controlli. Puoi usare questo punteggio per monitorare lo stato di avanzamento e definire le priorità delle azioni in base al loro potenziale per ridurre i rischi.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Usare la guida introduttiva di Compliance Manager

Nella [guida introduttiva di Compliance Manager](../compliance/compliance-manager-quickstart.md) sono disponibili passaggi e collegamenti a risorse chiave per l'utilizzo di Compliance Manager:

- [Prima visita: acquisire familiarità con Compliance Manager](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Utilizzo del dashboard di Compliance Manager
    - Informazioni sul punteggio di conformità
    - Learning sulle azioni di miglioramento
    - Informazioni su valutazioni e modelli
- [Ramping up: configure Compliance Manager to manage your compliance activities](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Creazione e gestione della prima valutazione
    - Esecuzione del lavoro di implementazione e test sulle azioni di miglioramento per completare i controlli nelle valutazioni
    - Informazioni sull'impatto delle diverse azioni sul punteggio di conformità
- [Scalabilità verticale: usare funzionalità avanzate per soddisfare le esigenze personalizzate](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Creazione di valutazioni personalizzate per tenere traccia dei prodotti non Microsoft 365 personalizzati
    - Modifica dei modelli esistenti per aggiungere o rimuovere controlli
    - Configurazione di test automatizzati delle azioni di miglioramento

## <a name="how-your-compliance-score-is-calculated"></a>Come viene calcolato il punteggio di conformità

Il punteggio di conformità viene calcolato in base a una combinazione di implementazioni di controlli microsoft e gestite dal cliente. Per [una spiegazione dettagliata, vedere calcolo](../compliance/compliance-score-calculation.md) del punteggio di conformità.

Ai controlli viene assegnato un valore di punteggio in base al fatto che siano obbligatori o discrezionali e che siano preventivi, detective o correttivi. Questi rappresentano collettivamente il rischio di non implementarlo rispetto ad altri controlli.

Come illustrato nell'articolo di calcolo del punteggio di conformità, i controlli preventivi ottengono un punteggio più alto rispetto a quelli detective e correttivi, mentre i controlli obbligatori ottengono un punteggio più alto rispetto a quelli discrezionali.

L'interfaccia utente dell'amministratore del punteggio di conformità non elenca questi parametri, né offre la possibilità di filtrarli in base a essi. Tuttavia, se si scarica il modello associato da Compliance Manager, il set di dati risultante elenca questi parametri per la maggior parte delle normative.

Per i controlli tecnici, Compliance Manager aggiorna automaticamente il punteggio dell'azione di miglioramento dopo che l'azione è stata implementata e testata correttamente. Altre azioni di controllo non tecniche, come quelle operative o correlate alla documentazione, devono essere registrate manualmente come implementate prima che i punti contino verso &mdash; &mdash; il punteggio.

Molti utenti stanno anche implementando determinate azioni di miglioramento per altri scopi, ad esempio utilizzando le etichette di conservazione per motivi diversi dalla conformità alle normative sulla privacy dei dati, in modo da ottenere credito per l'utilizzo di tale funzionalità anche se viene utilizzata per altri scopi e non fa parte di un'azione intenzionale di &mdash; &mdash; conformità.

Il punteggio di conformità deve essere considerato una misura relativa per tenere traccia del miglioramento su larga scala. Non è consigliabile ottenere un punteggio perfetto.

## <a name="additional-guidance"></a>Indicazioni aggiuntive

Ecco alcuni suggerimenti importanti per l'uso di Compliance Manager per aiutarti a raggiungere la conformità alle normative sulla privacy dei dati:

- Ogni normativa sulla privacy dei dati include una combinazione di controlli tecnici, specifiche della documentazione e requisiti operativi, di processo e di segnalazione. Tutte queste informazioni vengono mostrate nelle azioni di miglioramento.

- Per focalizzare la visualizzazione delle azioni di miglioramento sull'area di interesse, è possibile filtrare in base al tipo di azione nella **scheda Soluzioni** dell'amministratore di Compliance Manager. Ulteriori informazioni sul [filtro della visualizzazione del dashboard di Compliance Manager.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- L'importanza relativa e la priorità delle azioni di miglioramento identificate in Compliance Manager devono essere considerate come parte di una revisione dei rischi più ampia insieme al rischio per la privacy dei dati che hai determinato che l'organizzazione deve gestire.

- Anche con l'aggregazione delle azioni di miglioramento in più requisiti normativi, se i modelli di valutazione delle normative per GDPR, LGPD, CCPA e HIPAA-HITECH sono selezionati, ad esempio, quasi 400 azioni di miglioramento saranno elencate in Compliance Manager. Per affrontare meglio questo lungo elenco, utilizzare il filtro delle azioni di miglioramento per ridurre il set di risultati a un elenco più gestibile.

- Il filtro Categorie consente di filtrare le azioni di miglioramento in base al raggruppamento logico, a cui si allineano gli articoli Track, Prevent, Protect, Retain e Investigate di questa soluzione complessiva.

- Alcuni dei controlli elencati nelle azioni di miglioramento possono essere considerati più direttamente legati a uno specifico articolo normativo, mentre altri controlli possono essere più indirettamente associati allo spirito di una normativa e molte volte sono semplicemente attività consigliate o procedure consigliate.