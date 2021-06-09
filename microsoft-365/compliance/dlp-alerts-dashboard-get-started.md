---
title: Introduzione alla dashboard degli avvisi per la prevenzione delle perdita dei dati
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Introduzione alla definizione e alla gestione degli avvisi per i criteri di prevenzione della perdita di dati.
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843867"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>Introduzione alla dashboard degli avvisi per la prevenzione delle perdita dei dati

I criteri di prevenzione della perdita dei dati (DLP) possono intraprendere azioni di protezione per impedire la condivisione involontaria di elementi sensibili. Quando viene eseguita un'azione su un elemento sensibile, è possibile ricevere una notifica configurando gli avvisi per DLP. In questo articolo viene illustrato come definire criteri di avviso rtf collegati ai criteri di prevenzione della perdita dei dati (DLP). Vedrai come usare il dashboard di gestione [](https://compliance.microsoft.com/) degli avvisi [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) nel Centro conformità Microsoft 365 per visualizzare avvisi, eventi e metadati associati per le violazioni dei criteri DLP.

Se non si ha la novità degli avvisi DLP, vedere Informazioni sul dashboard degli avvisi di [prevenzione della perdita dei dati](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare, verificare di disporre dei prerequisiti necessari:

-   Gestione delle licenze per il dashboard di gestione degli avvisi DLP
-   Licenze per le opzioni di configurazione degli avvisi
-   Ruoli

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Gestione delle licenze per il dashboard di gestione degli avvisi DLP

Tutti i tenant idonei per Office 365 DLP possono accedere al dashboard di gestione degli avvisi DLP. To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business. Per ulteriori informazioni sui requisiti di licenza per Office 365 DLP, vedere Quali licenze forniscono a un utente i diritti a [beneficiare del servizio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

I clienti che usano [Endpoint DLP](endpoint-dlp-learn-about.md) idonei per [Teams DLP](dlp-microsoft-teams.md) visualizzano gli avvisi dei criteri DLP degli endpoint e Teams gli avvisi dei criteri DLP nel dashboard di gestione degli avvisi DLP.

La **funzionalità di anteprima** del contenuto è disponibile solo per queste licenze:

- Microsoft 365 (E5)
- Office 365 (E5)
- Componente aggiuntivo Conformità avanzata (E5)
- Microsoft 365 E5/A5 Information Protection and Governance
- Conformità Microsft 365 E5/A5

### <a name="licensing-for-alert-configuration-options"></a>Licenze per le opzioni di configurazione degli avvisi

Configurazione degli avvisi a evento **singolo**: le organizzazioni con una sottoscrizione E1, F1 o G1 o una sottoscrizione E3 o G3 possono creare criteri di avviso solo quando viene attivato un avviso ogni volta che si verifica un'attività.

**Configurazione degli avvisi aggregati:** per configurare i criteri di avviso aggregati in base a una soglia, è necessario una delle configurazioni di licenza seguenti:

- Un abbonamento E5 o G5
- Una sottoscrizione E1, F1 o G1 o una sottoscrizione E3 o G3 che include una delle funzionalità seguenti:
    - Office 365 Advanced Threat Protection (Piano 2)
    - Conformità Microsoft 365 E5
    - Microsoft 365 licenza del componente aggiuntivo eDiscovery e controllo

### <a name="roles"></a>Ruoli


Se si desidera visualizzare il dashboard di gestione degli avvisi DLP o modificare le opzioni di configurazione degli avvisi in un criterio DLP, è necessario essere membri di uno di questi gruppi di ruoli:

- Amministratore di conformità
- Amministratore dei dati di conformità
- Amministratore della sicurezza
- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura per la sicurezza

Per accedere al dashboard di gestione degli avvisi DLP, è necessario:

- Gestire gli avvisi

e uno di questi due ruoli:

- Gestione della conformità DLP
- View-Only conformità DLP

Per accedere alla funzionalità Anteprima contenuto e alle funzionalità contenuto sensibile e contesto corrispondenti, è necessario essere membri di:

- Gruppo di ruoli Visualizzatore contenuto di Esplora contenuto

che ha il ruolo visualizzatore contenuto per la classificazione dei dati preassato.

## <a name="dlp-alert-configuration"></a>Configurazione degli avvisi DLP

Per informazioni su come configurare un avviso nel criterio DLP, vedere [Da dove iniziare con la prevenzione della perdita dei dati.](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)

### <a name="aggregate-event-alert-configuration"></a>Configurazione dell'avviso di evento aggregato

Se l'organizzazione ha una licenza per [le opzioni di](#licensing-for-alert-configuration-options)configurazione degli avvisi aggregati, queste opzioni verranno visualizzati quando si crea o si modifica un criterio DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot che mostra le opzioni per i rapporti operazioni non consentite per gli utenti idonei per le opzioni di configurazione degli avvisi aggregati." border="false":::

Questa configurazione consente di configurare un criterio per generare un avviso ogni volta che un'attività soddisfa le condizioni dei criteri o quando viene superata una determinata soglia, in base al numero di attività o in base al volume di dati esfiltrati.

### <a name="single-event-alert-configuration"></a>Configurazione avviso evento singolo

Se l'organizzazione ha una licenza per [le opzioni](#licensing-for-alert-configuration-options)di configurazione degli avvisi a evento singolo, queste opzioni verranno visualizzati quando si crea o si modifica un criterio DLP. Utilizzare questa opzione per creare un avviso generato ogni volta che si verifica una corrispondenza di una regola DLP.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot che mostra le opzioni per i rapporti operazioni non consentite per gli utenti idonei per le opzioni di configurazione degli avvisi a evento singolo." border="false":::

## <a name="investigate-a-dlp-alert"></a>Analizzare un avviso DLP

Per utilizzare il dashboard di gestione degli avvisi DLP:

1. Nel Centro [Microsoft 365 conformità](https://www.compliance.microsoft.com)passare a Prevenzione della perdita **di dati**.
2. Selezionare la **scheda Avvisi** per visualizzare il dashboard degli avvisi DLP.
3. Selezionare un avviso per visualizzare i dettagli:

:::image type="content" source="../media/alert-details.png" alt-text="Screenshot che mostra i dettagli dell'avviso nel dashboard di gestione degli avvisi DLP." border="false":::

4. Selezionare la **scheda** Eventi per visualizzare tutti gli eventi associati all'avviso. Puoi scegliere un evento specifico per visualizzarne i dettagli. Per un elenco di alcuni dei dettagli dell'evento disponibili, vedere Informazioni sul dashboard avvisi di prevenzione della [perdita di dati.](dlp-alerts-dashboard-learn.md)
5. Selezionare **Dettagli** per aprire la **pagina Panoramica** per l'avviso. La pagina di panoramica fornisce un riepilogo:
    1. di ciò che è successo
    1. che ha eseguito le azioni che hanno causato la corrispondenza dei criteri
    1. informazioni sui criteri corrispondenti e altro ancora 

6. Scegliere la **scheda** Eventi per accedere a:
    1. contenuto coinvolto
    1. tipi di informazioni riservate corrispondenti
    1. metadati

7. Selezionare la **scheda Tipi di informazioni riservate** per visualizzare i dettagli sui tipi di informazioni riservate rilevati nel contenuto. I dettagli includono la probabilità, il conteggio e il contenuto corrispondente al tipo di informazioni riservate.

8. Dopo aver indagato sull'avviso, tornare alla scheda **Panoramica** in cui è possibile gestire la triage e gestire l'eliminazione dell'avviso e aggiungere commenti.

- Per visualizzare la cronologia della gestione del flusso di lavoro, scegliere **Registro di gestione**.
- Dopo aver evaso l'azione necessaria per l'avviso, impostare lo stato dell'avviso su **Risolto**.

## <a name="see-also"></a>Vedere anche

- [Informazioni sugli avvisi di prevenzione della perdita di dati e sul dashboard degli avvisi](dlp-alerts-dashboard-learn.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)