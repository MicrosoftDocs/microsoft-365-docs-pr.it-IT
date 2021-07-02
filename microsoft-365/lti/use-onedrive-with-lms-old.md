---
title: Usare l'interoperabilità degli strumenti di OneDrive Learning di distribuzione
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
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256985"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>Usare Microsoft OneDrive LTI con Canvas

> [!IMPORTANT]
> Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico. Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.

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
