---
title: Configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita di dati
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
description: Informazioni su come definire e gestire gli avvisi per i criteri di prevenzione della perdita di dati.
ms.openlocfilehash: ee04f6080edcde86dc39c7f4aa43130223fee8bf
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750038"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>Configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita di dati

I criteri di prevenzione della perdita dei dati (DLP) possono intraprendere azioni di protezione per impedire la condivisione involontaria di elementi sensibili. Quando viene eseguita un'azione su un elemento sensibile, è possibile ricevere una notifica configurando gli avvisi per DLP. In questo articolo viene illustrato come definire criteri di avviso rtf collegati ai criteri di prevenzione della perdita dei dati (DLP). Vedrai come usare il nuovo dashboard di [](https://compliance.microsoft.com/) gestione degli avvisi DLP nel Centro conformità Microsoft 365 per visualizzare gli avvisi, gli eventi e i metadati associati per le violazioni dei criteri DLP.

<!-- LEFT OFF HERE-->

## <a name="features"></a>Funzionalità

Di seguito sono riportate le funzionalità seguenti:

-   **Dashboard di gestione degli** avvisi DLP : nel Centro conformità Microsoft 365 [,](https://compliance.microsoft.com/)questo dashboard mostra gli avvisi per i criteri DLP applicati ai carichi di lavoro seguenti:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivi
-   **Opzioni di configurazione avanzata degli** avvisi: queste opzioni fanno parte del flusso di creazione dei criteri DLP. Usarli per creare configurazioni avanzate degli avvisi. È possibile creare un avviso a evento singolo o aggregato, in base al numero di eventi o alle dimensioni dei dati persi.

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare, verificare di disporre dei prerequisiti necessari:

-   Gestione delle licenze per il dashboard di gestione degli avvisi DLP
-   Licenze per le opzioni di configurazione degli avvisi
-   Ruoli

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Gestione delle licenze per il dashboard di gestione degli avvisi DLP

Tutti i tenant idonei per Office 365 DLP possono accedere al nuovo dashboard di gestione degli avvisi DLP. To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business. Per ulteriori informazioni sui requisiti di licenza per Office 365 DLP, vedere Quali licenze forniscono a un utente i diritti a [beneficiare del servizio?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

I clienti che usano [Endpoint DLP](endpoint-dlp-learn-about.md) idonei per [Teams DLP](dlp-microsoft-teams.md) visualizzano gli avvisi dei criteri DLP degli endpoint e Teams gli avvisi dei criteri DLP nel dashboard di gestione degli avvisi DLP.

### <a name="licensing-for-alert-configuration-options"></a>Licenze per le opzioni di configurazione degli avvisi

-   Configurazione degli avvisi a evento **singolo**: le organizzazioni con una sottoscrizione E1, F1 o G1 o una sottoscrizione E3 o G3 possono creare criteri di avviso solo quando viene attivato un avviso ogni volta che si verifica un'attività.
-   **Configurazione degli avvisi aggregati**: per configurare i criteri di avviso aggregati in base a una soglia, è necessario disporre di una delle configurazioni seguenti:
    -   Un abbonamento E5 o G5
    -   Una sottoscrizione E1, F1 o G1 o una sottoscrizione E3 o G3 che include una delle funzionalità seguenti:
        -   Office 365 Advanced Threat Protection (Piano 2)
        -   Conformità Microsoft 365 E5
        -   Microsoft 365 licenza del componente aggiuntivo eDiscovery e controllo

### <a name="roles"></a>Ruoli

Se si desidera visualizzare il dashboard di gestione degli avvisi DLP o modificare le opzioni di configurazione degli avvisi in un criterio DLP, è necessario essere membri di uno di questi gruppi di ruoli:

-   Amministratore di conformità
-   Amministratore dei dati di conformità
-   Amministratore della sicurezza
-   Operatore della sicurezza
-   Ruolo con autorizzazioni di lettura per la sicurezza

Per accedere al dashboard di gestione degli avvisi DLP, è necessario il ruolo Gestisci avvisi e uno dei ruoli seguenti:

-   Gestione della conformità DLP
-   View-Only conformità DLP

## <a name="alert-configuration-experience"></a>Esperienza di configurazione degli avvisi

Se si è idonei per [le opzioni di configurazione](#licensing-for-alert-configuration-options)degli avvisi aggregati, nell'esperienza di creazione dei criteri DLP sono disponibili le opzioni seguenti in linea.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot che mostra le opzioni per i rapporti operazioni non consentite per gli utenti idonei per le opzioni di configurazione degli avvisi aggregati." border="false":::

È possibile utilizzare queste opzioni di configurazione degli avvisi per configurare un'impostazione che definisce la frequenza di corrispondenza di una regola DLP prima dell'attivazione di un avviso. Questa configurazione consente di configurare un criterio per generare un avviso ogni volta che un'attività soddisfa le condizioni dei criteri o quando viene superata una determinata soglia, in base al numero di attività o in base al volume di dati esfiltrati.

Se si è idonei per le [opzioni](#licensing-for-alert-configuration-options)di configurazione degli avvisi a evento singolo, nell'esperienza di creazione dei criteri DLP viene visualizzata l'opzione di configurazione degli avvisi seguente. Utilizzare questa opzione per creare un avviso generato ogni volta che si verifica una corrispondenza di una regola DLP a causa di un'attività dell'utente.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot che mostra le opzioni per i rapporti operazioni non consentite per gli utenti idonei per le opzioni di configurazione degli avvisi a evento singolo." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Dashboard di gestione degli avvisi DLP

Per utilizzare il dashboard di gestione degli avvisi DLP:

1.  Nel Centro [Microsoft 365 conformità](https://www.compliance.microsoft.com)passare a Prevenzione della perdita **di dati**.

2.  Selezionare la **scheda Avvisi** per visualizzare il dashboard degli avvisi DLP.

    -   Scegliere i filtri per affinare l'elenco degli avvisi. Scegliere **Personalizza colonne** per elencare le proprietà che si desidera visualizzare. È inoltre possibile scegliere di ordinare gli avvisi in ordine crescente o decrescente in qualsiasi colonna.
    -   Selezionare un avviso per visualizzare i dettagli:

        :::image type="content" source="../media/alert-details.png" alt-text="Screenshot che mostra i dettagli dell'avviso nel dashboard di gestione degli avvisi DLP." border="false":::

1.  Selezionare la **scheda** Eventi per visualizzare tutti gli eventi associati all'avviso. Puoi scegliere un evento specifico per visualizzarne i dettagli.
    La tabella seguente mostra alcuni dei dettagli dell'evento.
    
    | Categoria          | Nome della proprietà                 | Descrizione                                                                | Tipi di evento applicabili                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Dettagli evento*||
    |      | Id                            | ID univoco associato all'evento                                        | Tutti gli eventi                               |
    |                   | Posizione                      | Carico di lavoro in cui è stato rilevato l'evento                                      | Tutti gli eventi                               |
    |                   | Ora dell'attività              | Ora dell'attività utente che ha causato la violazione DLP                    | Tutti gli eventi                               |
    |*Entità influenzate*||
    |  | Utente                          | Utente che ha causato la violazione DLP                                          | Tutti gli eventi                               |
    |                   | Nome host                      | Nome host del computer in cui è stata rilevata la violazione DLP              | Eventi dei dispositivi                           |
    |                   | Indirizzo IP                    | Indirizzo IP del computer                                                  | Eventi dei dispositivi                           |
    |                   | Percorso file                     | Percorso assoluto del file coinvolto nella violazione                        | SharePoint, OneDrive e Dispositivi |
    |                   | Destinatari di posta elettronica              | Destinatari del messaggio di posta elettronica che ha violato il criterio DLP                       | Exchange eventi                          |
    |                   | Oggetto e-mail                 | Oggetto del messaggio di posta elettronica che ha violato il criterio DLP                          | Exchange eventi                          |
    |                   | Allegati posta elettronica             | Nomi degli allegati nel messaggio di posta elettronica che hanno violato il criterio DLP         | Exchange eventi                          |
    |                   | Proprietario del sito                    | Nome del proprietario del sito                                                     | SharePoint e OneDrive eventi           |
    |                   | URL del sito                      | URL completo del SharePoint o OneDrive sito                                | SharePoint e OneDrive eventi           |
    |                   | File creato                  | Ora di creazione del file                                                      | SharePoint e OneDrive eventi           |
    |                   | File modificato per ultima            | Ora dell'ultima modifica del file                                  | SharePoint e OneDrive eventi           |
    |                   | Dimensioni dei file                     | Dimensioni del file                                                           | SharePoint e OneDrive eventi           |
    |                   | Proprietario del file                    | Proprietario del file                                                          | SharePoint e OneDrive eventi           |
    |*Dettagli criteri*||
    |     | Criteri DLP corrispondenti            | Nome del criterio DLP corrispondente                                    | Tutti gli eventi                               |
    |                   | Regola corrispondente                  | Nome della regola DLP nel criterio DLP corrispondente                    | Tutti gli eventi                               |
    |                   | Tipi di informazioni sensibili rilevati | Tipi di informazioni riservate rilevati come parte del criterio DLP | Tutti gli eventi                               |
    |                   | Azioni intraprese                 | Azioni eseguite come parte del criterio DLP corrispondente                          | Tutti gli eventi                               |
    |                   | Criterio sovrascritto utente          | Indica se l'utente ha sovrascritto il criterio tramite il suggerimento per i criteri                | Tutti gli eventi                               |
    |                   | Sostituzione del testo di giustificazione   | Giustificazione fornita per ignorare il suggerimento per i criteri                          | Tutti gli eventi                               |
    
1.  Selezionare la **scheda Tipi di informazioni riservate** per visualizzare i dettagli sui tipi di informazioni riservate rilevati nel contenuto. I dettagli includono confidenza e conteggio.

2.  Dopo aver indagato sull'avviso, scegliere **Gestisci avviso** per modificare lo stato (**Attivo,** **In** corso, **Ignorato** o **Risolto**). È inoltre possibile aggiungere commenti e assegnare l'avviso a un utente dell'organizzazione.

    -   Per visualizzare la cronologia della gestione del flusso di lavoro, scegliere **Registro di gestione**.
    -   Dopo aver evaso l'azione necessaria per l'avviso, impostare lo stato dell'avviso su **Risolto**.