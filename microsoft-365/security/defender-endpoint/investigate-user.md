---
title: Analizzare un account utente in Microsoft Defender for Endpoint
description: Analizzare un account utente per individuare potenziali credenziali compromesse o eseguire il pivot sull'account utente associato durante un'indagine.
keywords: analizzare, account, utente, entità utente, avviso, microsoft defender atp
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 672867d107d005004201caab7d6497ceb048ac97
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587708"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Analizzare un account utente in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>Analizzare le entità account utente

Identificare gli account utente con gli avvisi più attivi (visualizzati nel dashboard come "Utenti a rischio") e analizzare i casi di potenziali credenziali compromesse o eseguire il pivot sull'account utente associato durante l'analisi di un avviso o di un dispositivo per identificare possibili spostamenti laterali tra dispositivi con tale account utente.

Le informazioni sull'account utente sono disponibili nelle visualizzazioni seguenti:

- Dashboard
- Coda avvisi
- Pagina dettagli dispositivo

In queste visualizzazioni è disponibile un collegamento all'account utente selezionabile che consente di accedere alla pagina dei dettagli dell'account utente in cui vengono visualizzati ulteriori dettagli sull'account utente.

Quando si analizza un'entità account utente, viene visualizzato:

- Dettagli dell'account utente, avvisi di Azure Advanced Threat Protection (Azure ATP) e dispositivi connessi, ruolo, tipo di accesso e altri dettagli
- Panoramica degli eventi imprevisti e dei dispositivi dell'utente
- Avvisi correlati a questo utente
- Osservato nell'organizzazione (dispositivi connessi a)

![Immagine della pagina dei dettagli dell'entità account utente](images/atp-user-details-view.png)

### <a name="user-details"></a>Dettagli utente

Il  riquadro Dettagli utente a sinistra fornisce informazioni sull'utente, ad esempio eventi imprevisti aperti correlati, avvisi attivi, nome SAM, SID, avvisi di Azure ATP, numero di dispositivi a cui l'utente è connesso, quando l'utente è stato visto per primo e per ultimo, ruolo e tipi di accesso. A seconda delle funzionalità di integrazione abilitate, verranno visualizzati altri dettagli. Ad esempio, se abiliti l'integrazione di Skype for business, potrai contattare l'utente dal portale. La sezione Avvisi di **Azure ATP** contiene un collegamento che consente di accedere alla pagina di Azure ATP, se è stata abilitata la funzionalità Azure ATP e sono presenti avvisi correlati all'utente. La pagina di Azure ATP fornirà ulteriori informazioni sugli avvisi.

>[!NOTE]
>Dovrai abilitare l'integrazione sia in Azure ATP che in Defender for Endpoint per usare questa funzionalità. In Defender for Endpoint puoi abilitare questa funzionalità nelle funzionalità avanzate. Per ulteriori informazioni su come abilitare le funzionalità avanzate, vedere [Attivare le funzionalità avanzate.](advanced-features.md)

Le schede Panoramica, Avvisi e Osservati nell'organizzazione sono schede diverse che visualizzano vari attributi relativi all'account utente.

### <a name="overview"></a>Panoramica

La **scheda Panoramica** mostra i dettagli degli eventi imprevisti e un elenco dei dispositivi a cui l'utente ha eseguito l'accesso. Puoi espandere questi elementi per visualizzare i dettagli degli eventi di accesso per ogni dispositivo.

### <a name="alerts"></a>Avvisi

Nella **scheda Avvisi** è disponibile un elenco di avvisi associati all'account utente. Questo elenco è una visualizzazione [](alerts-queue.md)filtrata della coda degli avvisi e mostra gli avvisi in cui il contesto utente è l'account utente selezionato, la data in cui è stata rilevata l'ultima attività, una breve descrizione dell'avviso, il dispositivo associato all'avviso, la gravità dell'avviso, lo stato dell'avviso nella coda e a chi è assegnato l'avviso.

### <a name="observed-in-organization"></a>Osservato nell'organizzazione

La scheda Osservati **nell'organizzazione** consente di specificare un intervallo di date per visualizzare un elenco dei dispositivi a cui l'utente è stato osservato connesso, l'account utente connesso più frequente e meno frequente per ognuno di questi dispositivi e il totale degli utenti osservati in ogni dispositivo.

Selezionando un elemento nella tabella Osservati nell'organizzazione, l'elemento verrà espanso, rivelando altri dettagli sul dispositivo. Selezionando direttamente un collegamento all'interno di un elemento, si invierà alla pagina corrispondente.

## <a name="search-for-specific-user-accounts"></a>Cercare account utente specifici

1. Seleziona **Utente** dal menu **a** discesa della barra di ricerca.
2. Immettere l'account utente nel **campo Cerca.**
3. Fare clic sull'icona di ricerca o premere **INVIO.**

Viene visualizzato un elenco di utenti che corrispondono al testo della query. Vedrai il dominio e il nome dell'account utente, l'ultima volta che l'account utente è stato visualizzato e il numero totale di dispositivi a cui è stato eseguito l'accesso negli ultimi 30 giorni.

È possibile filtrare i risultati in base ai periodi di tempo seguenti:

- 1 giorno
- 3 giorni
- 7 giorni
- 30 giorni
- 6 mesi

## <a name="related-topics"></a>Argomenti correlati

- [Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts](alerts-queue.md)
- [Gestire gli avvisi di Microsoft Defender for Endpoint](manage-alerts.md)
- [Analizzare gli avvisi di Microsoft Defender for Endpoint](investigate-alerts.md)
- [Analizzare un file associato a un avviso di Defender for Endpoint](investigate-files.md)
- [Analizzare i dispositivi nell'elenco Defender for Endpoint Devices](investigate-machines.md)
- [Analizzare un indirizzo IP associato a un avviso Defender for Endpoint](investigate-ip.md)
- [Analizzare un dominio associato a un avviso Defender for Endpoint](investigate-domain.md)
