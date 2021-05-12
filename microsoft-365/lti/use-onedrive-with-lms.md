---
title: Usare l OneDrive a interoperabilità degli strumenti di apprendimento
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Crea e classifica le assegnazioni, crea e cura il contenuto del corso e collabora ai file in tempo reale con la nuova app OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: 97baf3e524e483e879d00f5e0c8495b450e13c92
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327740"
---
# <a name="use-microsoft-onedrive-with-your-learning-management-system"></a>Usare Microsoft OneDrive con il sistema di gestione dell'apprendimento

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

Scopri i vantaggi dell'uso Microsoft OneDrive con il sistema LMS (Learning Management System).

**Consente Microsoft Office 365 direttamente nei flussi di lavoro**

L'app Microsoft OneDrive Learning Tools Interoperability (LTI) si integra con il sistema LMS per portare Microsoft OneDrive e Microsoft Office 365 direttamente nei flussi di lavoro più importanti che includono:

- Allegare risorse e organizzare il contenuto.
- Avvio di documenti di collaborazione.
- Creazione e classificazione delle assegnazioni.

**Sicuro e completamente conforme agli standard LTI più recenti**

L Microsoft OneDrive app LTI è compatibile con LTI 1.3 e LTI Advantage. Questo vantaggio consente un'esperienza utente altamente sicura e strettamente integrata.

**Esperienza utente moderna e ricca**

L Microsoft OneDrive app LTI offre il meglio di Microsoft direttamente nell'esperienza LMS. Stiamo migliorando l'integrazione di Office 365 esistente nel sistema LMS offrendo un'esperienza utente più moderna, completa di una selezione file Microsoft OneDrive nuova ed estesa e di esperienze di modifica più complete per i file Office. Microsoft sarà anche completamente proprietaria dell'Microsoft OneDrive LTI App in futuro, il che significa che potrai sempre ottenere automaticamente le versioni più recenti e più recenti di Microsoft.

L Microsoft OneDrive app LTI consente di:

- Allegare Office 365 file di Word, inclusi documenti di Word, PowerPoint presentazioni e Excel dall'Editor contenuto rtf.

- Distribuire Office 365 assegnazioni cloud.

- Visualizzare e organizzare i file personali e Microsoft OneDrive corso.

- Creare collaborazioni in cui i membri del corso possono collaborare a documenti condivisi in tempo reale.

- Accedere a più Microsoft OneDrive, inclusi gli account personali e dell'istituto di istruzione.

- Integrare Office 365 file con i moduli del corso.

- Usa il tuo account Microsoft per l'accesso Single #A0 con il sistema LMS.

## <a name="integrate-with-canvas"></a>Integrazione con Canvas

La persona che esegue questa integrazione deve essere un amministratore di Canvas e un amministratore del tenant Microsoft 365 tenant.

1. Accedi al portale di Microsoft Azure con l'account di amministratore tenant. Anche l'amministratore tenant di Azure deve avere il ruolo di amministratore del gruppo.

    ![amministratore di gruppo evidenziato](../media/lti-media/lti-group-admin.png)

2. Accedere al portale di Microsoft [OneDrive LTI](https://odltiappnl.azurewebsites.net/admin).

3. Accettare le autorizzazioni per completare l'accesso.

    ![accettare autorizzazioni](../media/lti-media/lti-permissions.png)

4. Selezionare **Aggiungi tenant LTI**.

     ![aggiungere tenant LTI](../media/lti-media/lti-add-tenant.png)

5. Seleziona **Piattaforma consumer LTI** come **canvas nell'elenco** a discesa.

6. Seleziona **URL di base** canvas e quindi seleziona **Avanti.**

    ![selezionare Canvas e aggiungere l'URL di base](../media/lti-media/lti-canvas-base-url.png)

   Nella schermata successiva vengono mostrati i campi riservati all'utente.

7. Selezionare **Avanti** da ?? pagina. I REVISORI POSSONO COMPILARE LO SPAZIO VUOTO QUI?

8. Seleziona **Avanti** nella schermata che mostra informazioni riservate all'utente.

   La schermata finale del portale di Azure mostra i passaggi successivi per aggiungere l'istanza canvas.

9. Copia le chiavi per sviluppatori da questa schermata. Userai quando crei l'istanza Canvas.

## <a name="add-the-canvas-instance"></a>Aggiungere l'istanza canvas

1. Nell'istanza canvas deseleziona **Admin**  >  **Developer Keys.**

2. Scegli **LTI Key** nell'elenco a discesa in **Developer Key.**

   ![Ottenere le chiavi per sviluppatori LTI](../media/lti-media/lti-developer-keys.png)

3. Incolla qui le chiavi per sviluppatori.

     ![Incollare le chiavi dello sviluppatore](../media/lti-media/lti-developer-keys.png)

   Il tasto viene creato in **modalità OFF**

   ![Chiavi per sviluppatori create in modalità disattivata](../media/lti-media/lti-copy-developer-keys.png)

4. Copiare il testo evidenziato.
    Questo viene utilizzato come ID client Microsoft OneDrive portale LTI.

5. Incollare il testo nel **campo ID client** Microsoft OneDrive portale LTI e quindi selezionare **Avanti.**

6. Selezionare **Salva**.

7. Visualizzare le impostazioni selezionando **Visualizza tenant LTI**.
