---
title: Sicurezza della posta elettronica con Threat Explorer in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Visualizzare e analizzare i tentativi di phishing di malware.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 917ad3caf96a982df8b88058ff1c394b3d21dd75
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028545"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>Sicurezza della posta elettronica con Threat Explorer in Microsoft Defender per Office 365

Contenuto dell'articolo:

- [Visualizzare il malware rilevato nella posta elettronica](#view-malware-detected-in-email)
- [Visualizzare l'URL di phishing e fare clic su Dati verdetto](#view-phishing-url-and-click-verdict-data)
- [Avviare un'indagine e una risposta automatizzate](#start-automated-investigation-and-response)

> [!NOTE]
> Questo articolo fa parte di una serie di **3** articoli su **Threat Explorer (Explorer),** sicurezza della posta elettronica e informazioni di base su **Explorer** e sui rilevamenti in tempo reale (ad esempio le differenze tra gli strumenti e le autorizzazioni necessarie per operare).  Gli altri due articoli di questa serie sono la ricerca delle minacce [in Threat Explorer](threat-hunting-in-threat-explorer.md) e Threat Explorer e le nozioni di base sui [rilevamenti in tempo reale.](real-time-detections.md) 

In questo articolo viene illustrato come visualizzare e analizzare i tentativi di malware e phishing rilevati nella posta elettronica Microsoft 365 funzionalità di sicurezza. 

**Si applica a**

- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>Visualizzare il malware rilevato nella posta elettronica

Per visualizzare il malware rilevato nei messaggi di posta [](threat-explorer-views.md#email--malware) elettronica ordinati Microsoft 365 tecnologia, usare la visualizzazione Malware > posta elettronica di Esplora risorse (o rilevamenti in tempo reale). Il malware è la visualizzazione predefinita, quindi potrebbe essere selezionato non appena apri Esplora risorse.

1. Nel portale Microsoft 365 Defender ( ), scegliere Posta <https://security.microsoft.com> **elettronica &** \> **collaborazione Explorer** (o **Rilevamenti in tempo reale**). In questo esempio viene utilizzato Explorer. Se si è nel portale Microsoft 365 Defender convergente ( scorrere fino a https://security.microsoft.com/) **Email & collaboration**  >  **Explorer**.

   Da qui, inizia da View, scegli un determinato intervallo di tempo per analizzare (se necessario) e concentrare i filtri, come da [Explorer walk-through.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)

2. Nel menu **Visualizza** scegliere **Malware in Posta** **elettronica**.

3. Fare **clic su Mittente** e quindi scegliere **Tecnologia di** rilevamento di \> **base.**

   
   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="tecnologia di rilevamento malware":::

   Le tecnologie di rilevamento sono ora disponibili come filtri per il report.

4. Scegliere un'opzione. Selezionare quindi il **pulsante** Aggiorna per applicare il filtro.

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="tecnologia di rilevamento selezionata"::: 

   Il report viene aggiornato per visualizzare i risultati rilevati dal malware nella posta elettronica, utilizzando l'opzione tecnologia selezionata. Da qui è possibile eseguire ulteriori analisi. 

## <a name="view-phishing-url-and-click-verdict-data"></a>Visualizzare l'URL di phishing e fare clic su Dati verdetto

È possibile visualizzare i tentativi di phishing tramite URL nella posta elettronica, incluso un elenco di URL consentiti, bloccati e ignorati. Per identificare gli URL su cui è stato fatto clic, [Safe i collegamenti](safe-links.md) devono essere configurati. Assicurati di configurare i [criteri](set-up-safe-links-policies.md) di Safe per la protezione basata sul clic e la registrazione dei verdetti clic Safe collegamenti.

Per esaminare gli URL dei phish nei messaggi e fare clic sugli URL nei messaggi [   >  **phish,**](threat-explorer-views.md#email--phish) usa la visualizzazione Phish e-mail di Esplora risorse o rilevamenti in tempo reale.

1. Nel portale Microsoft 365 Defender ( ), scegliere Posta <https://security.microsoft.com> **elettronica &** \> **collaborazione Explorer** (o **Rilevamenti in tempo reale**). In questo esempio viene utilizzato Explorer.

2. Scegliere **E-mail**  \> **phish dal** menu Visualizza.

   > [!div class="mx-imgBorder"]
   > ![Menu Visualizza per Esplora risorse nel contesto di phishing](../../media/ExplorerViewEmailPhishMenu.png)

3. Fare **clic su Mittente** e quindi scegliere **URL Fare** clic su \> **verdetto.**

4. Selezionare una o più opzioni, ad esempio **Blocca** e  Blocca ignorate, e quindi selezionare il pulsante Aggiorna sulla stessa riga delle opzioni per applicare il filtro. Non aggiornare la finestra del browser.

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL e clic su verdetti":::

   Il report viene aggiornato per visualizzare due diverse tabelle URL nella scheda URL del report:

   - **Gli URL principali sono** gli URL nei messaggi filtrati e l'azione di recapito della posta elettronica conta per ogni URL. Nella visualizzazione Posta elettronica phish, questo elenco contiene in genere URL legittimi. Gli utenti malintenzionati includono una combinazione di URL buoni e non recapitati nei messaggi per tentare di ottenerli, ma rendono i collegamenti dannosi più interessanti. La tabella degli URL è ordinata in base al numero totale di messaggi di posta elettronica, ma questa colonna è nascosta per semplificare la visualizzazione.

   - **I clic principali** sono Safe URL con ritorno a capo dei collegamenti su cui è stato fatto clic, ordinati in base al numero totale di clic. Anche questa colonna non viene visualizzata per semplificare la visualizzazione. I conteggi totali per colonna indicano il numero Safe clic sul numero di verdetti per ogni URL su cui si fa clic. Nella visualizzazione Posta elettronica phish, questi url sono in genere sospetti o dannosi. Ma la visualizzazione potrebbe includere URL che non sono minacce ma sono in messaggi di phish. I clic url sui collegamenti senza ritorno a capo non vengono visualizzati qui.

   Le due tabelle URL mostrano gli URL principali nei messaggi di posta elettronica di phishing in base all'azione di recapito e alla posizione. Le tabelle mostrano i clic url bloccati o visitati nonostante un avviso, in modo da poter vedere quali potenziali collegamenti non riusciti sono stati presentati agli utenti e che gli utenti hanno fatto clic. Da qui è possibile eseguire ulteriori analisi. Ad esempio, sotto il grafico è possibile visualizzare gli URL principali nei messaggi di posta elettronica bloccati nell'ambiente dell'organizzazione.

   > [!div class="mx-imgBorder"]
   > ![URL di Explorer bloccati](../../media/ExplorerPhishClickVerdictURLs.png)

   Selezionare un URL per visualizzare informazioni più dettagliate.

   > [!NOTE]
   > Nella finestra di dialogo riquadro a comparsa URL, il filtro sui messaggi di posta elettronica viene rimosso per mostrare la visualizzazione completa dell'esposizione dell'URL nell'ambiente. In questo modo è possibile filtrare i messaggi di posta elettronica di cui si è preoccupati in Esplora risorse, trovare URL specifici che sono potenziali minacce e quindi espandere la comprensione dell'esposizione degli URL nell'ambiente (tramite la finestra di dialogo Dettagli URL) senza dover aggiungere filtri URL alla visualizzazione Esplora risorse stessa.

### <a name="interpretation-of-click-verdicts"></a>Interpretazione dei verdetti dei clic

Nei riquadri a comparsa E-mail o URL, Clic principali e nelle esperienze di filtro, vedrai diversi valori di verdetto clic:

- **Nessuno:** Impossibile acquisire il verdetto per l'URL. L'utente potrebbe aver fatto clic tramite l'URL.
- **Consentito:** All'utente è stato consentito passare all'URL.
- **Bloccato:** All'utente è stato impedito di passare all'URL.
- **Verdetto in sospeso:** All'utente è stata presentata la pagina detonazione in sospeso.
- **Bloccato ignorato:** All'utente è stato impedito di passare direttamente all'URL. Ma l'utente ha sovrascritto il blocco per passare all'URL.
- **Verdetto in sospeso ignorato:** All'utente è stata presentata la pagina di detonazione. Tuttavia, l'utente ha sovrascritto il messaggio per accedere all'URL.
- **Errore:** All'utente è stata presentata la pagina di errore oppure si è verificato un errore durante l'acquisizione del verdetto.
- **Errore:** Eccezione sconosciuta durante l'acquisizione del verdetto. L'utente potrebbe aver fatto clic tramite l'URL.

## <a name="start-automated-investigation-and-response"></a>Avviare un'indagine e una risposta automatizzate

> [!NOTE]
> Le funzionalità di analisi e risposta automatizzate sono disponibili in *Microsoft Defender per Office 365 Piano 2* e *Office 365 E5*.

[L'indagine e la risposta automatizzate](automated-investigation-response-office.md) possono risparmiare tempo e impegno per le operazioni di sicurezza dedicato all'analisi e alla mitigazione dei cyberattacchi. Oltre a configurare avvisi che possono attivare un playbook di sicurezza, puoi avviare un processo di indagine e risposta automatizzato da una visualizzazione in Esplora risorse. Per informazioni dettagliate, vedi Esempio: un amministratore [della sicurezza attiva un'indagine da Explorer.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="other-articles"></a>Altri articoli

[Analizzare i messaggi di posta elettronica con la pagina Entità di posta elettronica](mdo-email-entity-page.md)
