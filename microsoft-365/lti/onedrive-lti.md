---
title: Usare l Microsoft OneDrive Learning intervarietà degli strumenti di distribuzione
ms.author: heidip
author: MicrosoftHeidi
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
description: Crea e classifica le assegnazioni, crea e cura il contenuto del corso e collabora ai file in tempo reale con la nuova app Microsoft OneDrive Learning Tools Interoperability App.
ms.openlocfilehash: bcb374ed1666f23fa5f3d4692f43a4369670e891
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322222"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Integrare Microsoft OneDrive LTI con Canvas

L'integrazione Microsoft OneDrive LTI con Canvas è un processo in due passaggi. Il primo passaggio consente Microsoft OneDrive in Canvas e il secondo passaggio rende disponibile l'Microsoft OneDrive LTI all'interno dei corsi Canvas.

## <a name="recommended-browser-settings"></a>Impostazioni consigliate per il browser

- I cookie devono essere abilitati per Microsoft OneDrive.
- I popup non devono essere bloccati per Microsoft OneDrive.

> [!NOTE]
> - I cookie non sono abilitati per impostazione predefinita nella modalità in incognito del browser Chrome e dovranno essere abilitati.
> - Microsoft OneDrive LTI funziona in modalità privata in Microsoft Edge browser. Assicurati di non aver bloccato i cookie (abilitati per impostazione predefinita).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Abilitare Microsoft OneDrive LTI in Canvas

> [!IMPORTANT]
> La persona che esegue questa integrazione deve essere un amministratore di Canvas e un amministratore del tenant Microsoft 365 tenant.

1. Accedere al portale <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive registrazione LTI</a>
1. Seleziona il **pulsante Consenso** amministratore e accetta le autorizzazioni.

> [!CAUTION]
> Se questo passaggio non viene eseguito, il passaggio seguente restituirà un errore e non sarà possibile eseguire questo passaggio per un'ora dopo aver ricevuto l'errore.

3. Selezionare il **pulsante Crea nuovo tenant LTI.** Nella pagina Registrazione LTI seleziona **Canvas nell'elenco** a discesa e immetti l'URL di base dell'istanza canvas.

> [!NOTE]
> Se l'istanza canvas è, ad esempio, ]( , deve essere https://contoso.test.instructure.com https://contoso.test.instructure.com) immesso l'URL completo.

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Pagina amministrazione tenant LTI, con un campo a discesa per scegliere la piattaforma consumer LTI e un campo di testo URL.":::

4. Copia json selezionando il **pulsante Copia** (un'icona a destra che mostra due pagine una sopra l'altra). Verrà usato per generare la chiave in Canvas.

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Immagine che mostra il pulsante copia che copierà il testo JSON visualizzato e lo rende disponibile per la generazione delle chiavi in Canvas.":::

5. Accedi all'istanza di Canvas come amministratore e seleziona **Chiavi** sviluppatore dal menu a sinistra della pagina. Nell'elenco a discesa crea una chiave per sviluppatore scegliendo **LTI Key** nell'elenco a discesa in alto a destra della pagina.

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Screenshot che mostra la barra di spostamento sinistra con i tasti sviluppatore selezionati e la voce del tasto LTI selezionata da un elenco a discesa a destra della pagina.":::

6. Nell'elenco a discesa  Metodo della pagina Configura selezionare Incolla **JSON** come metodo e incollare il testo JSON copiato nel passaggio 5 nel campo di testo visualizzato.
7. Salva la chiave e diventa disponibile in Canvas in **stato Disattivato.** Attivare la chiave **e** copiare la chiave specificata nella colonna **Dettagli** da utilizzare nel passaggio successivo.

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Pagina Canvas con il tasto impostato in uno stato disattivato. Sarà necessario attivarla e la chiave dovrà essere copiata dalla colonna dei dettagli di questa pagina.":::

8. Torna al portale Microsoft OneDrive registrazione LTI e incolla la chiave nel campo **ID client Canvas.** Selezionare **Avanti** quando si è pronti.

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="La pagina di registrazione del tenant LTI, che mostra il testo JSON e la casella di testo in cui deve essere copiata la chiave.":::

9. Rivedere e salvare le modifiche. Al completamento della registrazione verrà visualizzato un messaggio.
10. I dettagli della registrazione possono essere esaminati anche selezionando il **pulsante Visualizza tenant LTI** nella home page.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Abilitare Microsoft OneDrive LTI nei corsi Canvas

Un amministratore di Canvas può abilitare Microsoft OneDrive LTI per tutti i corsi. Se Microsoft OneDrive LTI è necessario in un corso specifico (e non in tutti i corsi), il docente deve seguire gli stessi passaggi all'interno delle impostazioni del corso.

1. Accedi come amministratore e passa alla **sezione Impostazioni.**
2. Vai alla sezione **App** e seleziona il **pulsante Visualizza configurazioni app.**
3. Seleziona il **pulsante Aggiungi** app.
4. **Nell'elenco a discesa Tipo di** configurazione scegliere l'opzione Per **ID** client.
5. Incolla il valore della chiave per sviluppatore generata in precedenza nel **campo ID client** e seleziona il **pulsante** Invia.

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Pagina aggiungi app, che mostra l'opzione Per ID client nel menu a discesa Tipo di configurazione.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Collaboration Impostazioni for Microsoft OneDrive LTI in Canvas Courses

> [!NOTE]
> Perché la collaborazione funzioni per docenti e studenti, non è consigliabile abilitare l'impostazione di collaborazione. Per assicurarti che l'impostazione non sia abilitata, segui i passaggi seguenti.

1. Accedi come amministratore e passa alla **sezione Impostazioni.**
1. Passare alla **sezione Opzioni** funzionalità e quindi passare alla **sezione** Corso.
1. Impostare la **funzionalità Strumento di collaborazione esterna** in modo che non sia abilitata.

> [!NOTE]
> La collaborazione può essere assegnata a singoli studenti e a gruppi di studenti. L'assegnazione a singoli studenti funziona per impostazione predefinita. Per poter assegnare la collaborazione a un gruppo di studenti, attenersi alla seguente procedura:

1. Accedi come amministratore e passa alla sezione **Developer Keys.**
1. Trovare la chiave con valore 17000000000710 e impostarla su **On**.
