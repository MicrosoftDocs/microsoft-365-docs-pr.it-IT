---
title: Configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 10/15/2020
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
description: Informazioni su come definire e gestire gli avvisi per i criteri DLP.
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651461"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>Configurare e visualizzare gli avvisi per i criteri DLP (anteprima)

In questo articolo viene illustrato come definire criteri di avviso rtf collegati ai criteri di prevenzione della perdita dei dati (DLP). Verrà illustrato come usare il nuovo dashboard di gestione degli avvisi DLP nel Centro conformità [Microsoft 365](https://compliance.microsoft.com/) per visualizzare avvisi, eventi e metadati associati per violazioni dei criteri DLP.

## <a name="features"></a>Funzionalità

Le funzionalità seguenti fanno parte di questa anteprima:

-   **Dashboard di gestione degli** avvisi DLP: nel Centro conformità [Microsoft 365,](https://compliance.microsoft.com/)questo dashboard mostra gli avvisi per i criteri DLP applicati ai carichi di lavoro seguenti:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivi
-   **Opzioni di configurazione degli avvisi avanzate:** queste opzioni fanno parte del flusso di creazione dei criteri DLP. Usarli per creare configurazioni di avvisi avanzate. È possibile creare un avviso a evento singolo o un avviso aggregato, in base al numero di eventi o alle dimensioni dei dati persi.

## <a name="before-you-begin"></a>Prima di iniziare

Prima di iniziare, verificare di disporre dei prerequisiti necessari:

-   Gestione delle licenze per il dashboard di gestione degli avvisi DLP
-   Licenze per le opzioni di configurazione degli avvisi
-   Ruoli

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Gestione delle licenze per il dashboard di gestione degli avvisi DLP

Tutti i tenant idonei per la prevenzione della perdita dei dati di Office 365 possono accedere al nuovo dashboard di gestione degli avvisi DLP. To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business. Per ulteriori informazioni sui requisiti di licenza per la prevenzione della perdita dei dati di Office 365, vedere Quali licenze forniscono a un utente i diritti per trarre [vantaggio dal servizio?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

I clienti che partecipano all'anteprima pubblica di [Endpoint DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) o che sono idonei per DLP di [Teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) visualizzano gli avvisi dei criteri DLP degli endpoint e gli avvisi dei criteri DLP di Teams nel dashboard di gestione degli avvisi DLP.

### <a name="licensing-for-alert-configuration-options"></a>Licenze per le opzioni di configurazione degli avvisi

-   Configurazione degli avvisi a evento **singolo:** le organizzazioni che dispongono di una sottoscrizione E1, F1 o G1 o di una sottoscrizione E3 o G3 possono creare criteri di avviso solo quando viene attivato un avviso ogni volta che si verifica un'attività.
-   **Configurazione degli avvisi aggregati:** per configurare criteri di avviso aggregati in base a una soglia, è necessario disporre di una delle configurazioni seguenti:
    -   Una sottoscrizione E5 o G5
    -   Una sottoscrizione E1, F1 o G1 oppure una sottoscrizione E3 o G3 che include una delle funzionalità seguenti:
        -   Office 365 Advanced Threat Protection (Piano 2)
        -   Conformità Microsoft 365 E5
        -   Licenza del componente aggiuntivo eDiscovery e controllo di Microsoft 365

### <a name="roles"></a>Ruoli

Se si desidera visualizzare il dashboard di gestione degli avvisi DLP o modificare le opzioni di configurazione degli avvisi in un criterio DLP, è necessario essere membri di uno di questi gruppi di ruoli:

-   Amministratore di conformità
-   Amministratore dei dati di conformità
-   Amministratore della sicurezza
-   Operatore della sicurezza
-   Ruolo con autorizzazioni di lettura per la sicurezza

Per accedere al dashboard di gestione degli avvisi DLP, è necessario il ruolo Gestisci avvisi e uno dei ruoli seguenti:

-   Gestione conformità DLP
-   View-Only conformità DLP

## <a name="alert-configuration-experience"></a>Esperienza di configurazione degli avvisi

Se si è idonei per [le opzioni di](#licensing-for-alert-configuration-options)configurazione degli avvisi aggregati, nell'esperienza di creazione dei criteri DLP vengono in linea con le opzioni seguenti.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for aggregated alert configuration options." border="false":::

È possibile utilizzare queste opzioni di configurazione degli avvisi per configurare un'impostazione che definisce la frequenza con cui può verificarsi una corrispondenza alla regola DLP prima dell'attivazione di un avviso. Questa configurazione consente di configurare un criterio per generare un avviso ogni volta che un'attività soddisfa le condizioni dei criteri o quando viene superata una determinata soglia, in base al numero di attività o in base al volume di dati esfiltrati.

If you're eligible for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you see the following alert configuration option in the DLP policy authoring experience. Utilizzare questa opzione per creare un avviso generato ogni volta che si verifica una corrispondenza alla regola DLP a causa di un'attività dell'utente.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Screenshot showing options for incident reports for users who are eligible for single-event alert configuration options." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Dashboard di gestione degli avvisi DLP

Per utilizzare il dashboard di gestione degli avvisi DLP:

1.  Nel Centro [conformità Microsoft 365](https://www.compliance.microsoft.com)passare a **Prevenzione della perdita dei dati.**

2.  Selezionare la **scheda Avvisi** per visualizzare il dashboard degli avvisi DLP.

    -   Scegliere i filtri per perfezionare l'elenco degli avvisi. Scegliere **Personalizza colonne** per elencare le proprietà che si desidera visualizzare. Puoi anche scegliere di ordinare gli avvisi in ordine crescente o decrescente in qualsiasi colonna.
    -   Selezionare un avviso per visualizzare i dettagli:

        :::image type="content" source="../media/alert-details.png" alt-text="Screenshot showing alert details on the DLP alert management dashboard." border="false":::

1.  Selezionare la **scheda Eventi** per visualizzare tutti gli eventi associati all'avviso. È possibile scegliere un evento specifico per visualizzarne i dettagli.
    Nella tabella seguente sono riportati alcuni dettagli dell'evento.
    
    | Categoria          | Nome della proprietà                 | Descrizione                                                                | Tipi di evento applicabili                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Dettagli evento*||
    |      | Id                            | ID univoco associato all'evento                                        | Tutti gli eventi                               |
    |                   | Posizione                      | Carico di lavoro in cui è stato rilevato l'evento                                      | Tutti gli eventi                               |
    |                   | Ora dell'attività              | Ora dell'attività dell'utente che ha causato la violazione DLP                    | Tutti gli eventi                               |
    |*Entità influenzate*||
    |  | Utente                          | Utente che ha causato la violazione DLP                                          | Tutti gli eventi                               |
    |                   | Nome host                      | Nome host del computer in cui è stata rilevata la violazione DLP              | Eventi dei dispositivi                           |
    |                   | Indirizzo IP                    | Indirizzo IP del computer                                                  | Eventi dei dispositivi                           |
    |                   | Percorso file                     | Percorso assoluto del file coinvolto nella violazione                        | Eventi di SharePoint, OneDrive e Dispositivi |
    |                   | Destinatari di posta elettronica              | Destinatari del messaggio di posta elettronica che ha violato il criterio DLP                       | Eventi di Exchange                          |
    |                   | Oggetto del messaggio di posta elettronica                 | Oggetto del messaggio di posta elettronica che ha violato il criterio DLP                          | Eventi di Exchange                          |
    |                   | Allegati di posta elettronica             | Nomi degli allegati nel messaggio di posta elettronica che hanno violato il criterio DLP         | Eventi di Exchange                          |
    |                   | Proprietario del sito                    | Nome del proprietario del sito                                                     | Eventi di SharePoint e OneDrive           |
    |                   | URL del sito                      | URL completo del sito di SharePoint o OneDrive                                | Eventi di SharePoint e OneDrive           |
    |                   | File creato                  | Ora di creazione dei file                                                      | Eventi di SharePoint e OneDrive           |
    |                   | Ultima modifica al file            | Ora dell'ultima modifica del file                                  | Eventi di SharePoint e OneDrive           |
    |                   | Dimensioni dei file                     | Dimensioni del file                                                           | Eventi di SharePoint e OneDrive           |
    |                   | Proprietario del file                    | Proprietario del file                                                          | Eventi di SharePoint e OneDrive           |
    |*Dettagli dei criteri*||
    |     | Criteri DLP corrispondenti            | Nome del criterio DLP corrispondente                                    | Tutti gli eventi                               |
    |                   | Regola corrispondente                  | Nome della regola DLP nel criterio DLP corrispondente                    | Tutti gli eventi                               |
    |                   | Tipi di informazioni sensibili rilevati | Tipi di informazioni riservate rilevati come parte del criterio DLP | Tutti gli eventi                               |
    |                   | Azioni intraprese                 | Azioni eseguite come parte del criterio DLP corrispondente                          | Tutti gli eventi                               |
    |                   | Criterio sovrascritto dall'utente          | Indica se l'utente ha sovrascritto il criterio tramite il suggerimento per i criteri                | Tutti gli eventi                               |
    |                   | Sostituzione del testo di giustificazione   | Giustificazione fornita per ignorare il suggerimento per i criteri                          | Tutti gli eventi                               |
    
1.  Selezionare la **scheda Tipi di informazioni** riservate per visualizzare i dettagli sui tipi di informazioni sensibili rilevati nel contenuto. I dettagli includono confidenza e conteggio.

2.  Dopo aver indagato sull'avviso, **scegliere** Gestisci avviso per modificare lo stato (**Attivo,** **In** **corso,** Ignorato o **Risolto).** È inoltre possibile aggiungere commenti e assegnare l'avviso a un utente dell'organizzazione.

    -   Per visualizzare la cronologia della gestione dei flussi di lavoro, scegliere **Registro di gestione.**
    -   Dopo aver eseguita l'azione necessaria per l'avviso, impostare lo stato dell'avviso su **Risolto.**
