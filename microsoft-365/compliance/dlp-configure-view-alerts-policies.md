---
title: Configurare e visualizzare gli avvisi per i criteri DLP (anteprima)
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

In questo articolo viene illustrato come definire criteri di avviso intensi che sono collegati ai criteri di prevenzione della perdita di dati (DLP). Vedrai come usare il nuovo dashboard di gestione degli avvisi DLP nel [centro conformità di Microsoft 365](https://compliance.microsoft.com/) per visualizzare avvisi, eventi e metadati associati per violazioni dei criteri DLP.

## <a name="features"></a>Funzionalità

Le caratteristiche seguenti fanno parte di questa anteprima:

-   **Dashboard per la gestione degli avvisi DLP**: nel [centro conformità di Microsoft 365](https://compliance.microsoft.com/), questo dashboard Visualizza gli avvisi per i criteri DLP applicati ai carichi di lavoro seguenti:

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   Dispositivi
-   **Opzioni avanzate di configurazione degli avvisi**: queste opzioni fanno parte del flusso di creazione dei criteri DLP. Utilizzarli per creare configurazioni di avviso avanzate. È possibile creare un avviso a evento singolo o un avviso aggregato, in base al numero di eventi o alle dimensioni dei dati persi.

## <a name="before-you-begin"></a>Informazioni preliminari

Prima di iniziare, verificare di disporre dei prerequisiti necessari:

-   Licenze per il dashboard di gestione degli avvisi DLP
-   Gestione delle licenze per le opzioni di configurazione degli avvisi
-   Ruoli

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>Licenze per il dashboard di gestione degli avvisi DLP

Tutti i tenant idonei per Office 365 DLP possono accedere al nuovo dashboard di gestione degli avvisi DLP. Per iniziare, è necessario essere idonei per Office 365 DLP per Exchange Online, SharePoint Online e OneDrive for business. Per ulteriori informazioni sui requisiti di licenza per Office 365 DLP, vedere [quali licenze offrono i diritti per un utente di usufruire del servizio?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).

I clienti che partecipano all'anteprima pubblica di [Endpoint DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) o che sono idonei per i [Team DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) vedranno gli avvisi relativi ai criteri DLP di endpoint e gli avvisi relativi ai criteri DLP del team nel dashboard di gestione degli avvisi DLP.

### <a name="licensing-for-alert-configuration-options"></a>Gestione delle licenze per le opzioni di configurazione degli avvisi

-   **Configurazione degli avvisi a evento singolo**: le organizzazioni con un abbonamento E1, F1 o G1 o un abbonamento E3 o G3 possono creare criteri di avviso solo in caso di attivazione di un avviso ogni volta che si verifica un'attività.
-   **Configurazione degli avvisi aggregati**: per configurare i criteri di avviso aggregati in base a una soglia, è necessario disporre di una delle configurazioni seguenti:
    -   Un abbonamento E5 o G5
    -   Un abbonamento E1, F1 o G1 o un abbonamento E3 o G3 che include una delle caratteristiche seguenti:
        -   Office 365 Advanced Threat Protection (Piano 2)
        -   Conformità Microsoft 365 E5
        -   Microsoft 365 eDiscovery e la licenza di controllo del componente aggiuntivo

### <a name="roles"></a>Ruoli

Se si desidera visualizzare il dashboard per la gestione degli avvisi DLP o per modificare le opzioni di configurazione degli avvisi in un criterio DLP, è necessario essere membri di uno di questi gruppi di ruoli:

-   Amministratore di conformità
-   Amministratore dei dati di conformità
-   Amministratore della sicurezza
-   Operatore della sicurezza
-   Ruolo con autorizzazioni di lettura per la sicurezza

Per accedere al dashboard di gestione degli avvisi DLP, è necessario il ruolo Gestisci notifiche e uno dei seguenti ruoli:

-   Gestione della conformità DLP
-   View-Only la gestione della conformità DLP

## <a name="alert-configuration-experience"></a>Esperienza di configurazione degli avvisi

Se si è idonei per le [Opzioni di configurazione degli avvisi aggregati](#licensing-for-alert-configuration-options), è possibile visualizzare le opzioni seguenti in linea con l'esperienza di creazione di criteri DLP.

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="Schermata che mostra le opzioni per i rapporti sugli incidenti per gli utenti idonei per le opzioni di configurazione degli avvisi aggregati." border="false":::

È possibile utilizzare queste opzioni di configurazione degli avvisi per configurare un'impostazione che definisce la frequenza con cui può verificarsi una corrispondenza della regola DLP prima che venga attivato un avviso. Questa configurazione consente di configurare un criterio per la generazione di un avviso ogni volta che un'attività corrisponde alle condizioni dei criteri o quando si supera una determinata soglia, in base al numero di attività o in base al volume dei dati di exfiltrated.

Se si è idonei per le [Opzioni di configurazione degli avvisi a evento singolo](#licensing-for-alert-configuration-options), vedere la seguente opzione di configurazione degli avvisi nell'esperienza di creazione dei criteri DLP. Utilizzare questa opzione per creare un avviso che viene generato ogni volta che si verifica una corrispondenza della regola DLP a causa di un'attività dell'utente.

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="Schermata che mostra le opzioni per i rapporti sugli incidenti per gli utenti idonei per le opzioni di configurazione degli avvisi aggregati." border="false":::

## <a name="dlp-alert-management-dashboard"></a>Dashboard di gestione degli avvisi DLP

Per utilizzare il dashboard di gestione degli avvisi DLP:

1.  Nel [centro conformità di Microsoft 365](https://www.compliance.microsoft.com), passare a **prevenzione della perdita di dati**.

2.  Selezionare la scheda **avvisi** per visualizzare il dashboard avvisi DLP.

    -   Scegliere filtri per affinare l'elenco degli avvisi. Scegliere **Personalizza colonne** per elencare le proprietà che si desidera visualizzare. È inoltre possibile scegliere di ordinare gli avvisi in ordine crescente o decrescente in qualsiasi colonna.
    -   Selezionare un avviso per visualizzare i dettagli:

        :::image type="content" source="../media/alert-details.png" alt-text="Schermata che mostra le opzioni per i rapporti sugli incidenti per gli utenti idonei per le opzioni di configurazione degli avvisi aggregati." border="false":::

1.  Selezionare la scheda **eventi** per visualizzare tutti gli eventi associati all'avviso. È possibile scegliere un evento specifico per visualizzarne i dettagli.
    Nella tabella seguente vengono illustrati alcuni dettagli dell'evento.
    
    | Categoria          | Nome della proprietà                 | Descrizione                                                                | Tipi di evento applicabili                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*Dettagli evento*||
    |      | Id                            | ID univoco associato all'evento                                        | Tutti gli eventi                               |
    |                   | Posizione                      | Carico di lavoro in cui è stato rilevato l'evento                                      | Tutti gli eventi                               |
    |                   | Data e ora di attività              | Data e ora dell'attività dell'utente che ha causato la violazione DLP                    | Tutti gli eventi                               |
    |*Entità interessate*||
    |  | Utente                          | Utente che ha causato la violazione DLP                                          | Tutti gli eventi                               |
    |                   | Nome host                      | Nome host del computer in cui è stata rilevata la violazione DLP              | Eventi per i dispositivi                           |
    |                   | Indirizzo IP                    | Indirizzo IP del computer                                                  | Eventi per i dispositivi                           |
    |                   | Percorso file                     | Percorso assoluto del file coinvolto nella violazione                        | Eventi di SharePoint, OneDrive e Devices |
    |                   | Destinatari della posta elettronica              | Destinatari del messaggio di posta elettronica che ha violato il criterio DLP                       | Eventi di Exchange                          |
    |                   | Oggetto del messaggio di posta elettronica                 | Oggetto del messaggio di posta elettronica che ha violato il criterio DLP                          | Eventi di Exchange                          |
    |                   | Allegati di posta elettronica             | Nomi degli allegati nel messaggio di posta elettronica che ha violato il criterio DLP         | Eventi di Exchange                          |
    |                   | Proprietario del sito                    | Nome del proprietario del sito                                                     | Eventi di SharePoint e OneDrive           |
    |                   | URL del sito                      | URL completo del sito di SharePoint o OneDrive                                | Eventi di SharePoint e OneDrive           |
    |                   | File creato                  | Data e ora di creazione dei file                                                      | Eventi di SharePoint e OneDrive           |
    |                   | Ultimo file modificato            | Data e ora dell'Ultima modifica del file                                  | Eventi di SharePoint e OneDrive           |
    |                   | Dimensioni dei file                     | Dimensione del file                                                           | Eventi di SharePoint e OneDrive           |
    |                   | Proprietario del file                    | Proprietario del file                                                          | Eventi di SharePoint e OneDrive           |
    |*Dettagli dei criteri*||
    |     | Criteri DLP corrispondenti            | Nome del criterio DLP corrispondente                                    | Tutti gli eventi                               |
    |                   | Regola corrispondente                  | Nome della regola DLP del criterio DLP corrispondente                    | Tutti gli eventi                               |
    |                   | Tipi di informazioni riservate rilevati | Tipi di informazioni riservate rilevate come parte del criterio DLP | Tutti gli eventi                               |
    |                   | Azioni intraprese                 | Azioni intraprese come parte del criterio DLP corrispondente                          | Tutti gli eventi                               |
    |                   | Criteri di overrode degli utenti          | Se l'utente ha superato il criterio tramite il suggerimento per i criteri                | Tutti gli eventi                               |
    |                   | Sostituisci testo giustificazione   | Giustificazione fornita per ignorare il suggerimento per i criteri                          | Tutti gli eventi                               |
    
1.  Selezionare la scheda tipi di informazioni **riservate** per visualizzare i dettagli relativi ai tipi di informazioni riservate rilevati nel contenuto. I dettagli includono confidenza e conteggio.

2.  Dopo aver esaminato l'avviso, scegliere **Manage alert** per modificare lo stato (**attivo**, **indagatore**, **respinto**o **risolto**). È inoltre possibile aggiungere commenti e assegnare l'avviso a un utente dell'organizzazione.

    -   Per visualizzare la cronologia della gestione dei flussi di lavoro, scegliere **log di gestione**.
    -   Dopo aver apportato l'azione necessaria per l'avviso, impostare lo stato dell'avviso su **risolto**.
