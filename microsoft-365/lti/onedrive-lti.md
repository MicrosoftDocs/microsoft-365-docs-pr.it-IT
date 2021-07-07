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
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="eea82-103">Integrare Microsoft OneDrive LTI con Canvas</span><span class="sxs-lookup"><span data-stu-id="eea82-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="eea82-104">L'integrazione Microsoft OneDrive LTI con Canvas è un processo in due passaggi.</span><span class="sxs-lookup"><span data-stu-id="eea82-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="eea82-105">Il primo passaggio consente Microsoft OneDrive in Canvas e il secondo passaggio rende disponibile l'Microsoft OneDrive LTI all'interno dei corsi Canvas.</span><span class="sxs-lookup"><span data-stu-id="eea82-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="eea82-106">Impostazioni consigliate per il browser</span><span class="sxs-lookup"><span data-stu-id="eea82-106">Recommended browser settings</span></span>

- <span data-ttu-id="eea82-107">I cookie devono essere abilitati per Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="eea82-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="eea82-108">I popup non devono essere bloccati per Microsoft OneDrive.</span><span class="sxs-lookup"><span data-stu-id="eea82-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="eea82-109">I cookie non sono abilitati per impostazione predefinita nella modalità in incognito del browser Chrome e dovranno essere abilitati.</span><span class="sxs-lookup"><span data-stu-id="eea82-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="eea82-110">Microsoft OneDrive LTI funziona in modalità privata in Microsoft Edge browser.</span><span class="sxs-lookup"><span data-stu-id="eea82-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="eea82-111">Assicurati di non aver bloccato i cookie (abilitati per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="eea82-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="eea82-112">Abilitare Microsoft OneDrive LTI in Canvas</span><span class="sxs-lookup"><span data-stu-id="eea82-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eea82-113">La persona che esegue questa integrazione deve essere un amministratore di Canvas e un amministratore del tenant Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="eea82-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="eea82-114">Accedere al portale <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive registrazione LTI</a></span><span class="sxs-lookup"><span data-stu-id="eea82-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="eea82-115">Seleziona il **pulsante Consenso** amministratore e accetta le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="eea82-115">Select the **Admin Consent** button and accept the permissions.</span></span>

> [!CAUTION]
> <span data-ttu-id="eea82-116">Se questo passaggio non viene eseguito, il passaggio seguente restituirà un errore e non sarà possibile eseguire questo passaggio per un'ora dopo aver ricevuto l'errore.</span><span class="sxs-lookup"><span data-stu-id="eea82-116">If this step isn't performed, the following step will give you an error, and you won't be able to take this step for an hour once you've gotten the error.</span></span>

3. <span data-ttu-id="eea82-117">Selezionare il **pulsante Crea nuovo tenant LTI.**</span><span class="sxs-lookup"><span data-stu-id="eea82-117">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="eea82-118">Nella pagina Registrazione LTI seleziona **Canvas nell'elenco** a discesa e immetti l'URL di base dell'istanza canvas.</span><span class="sxs-lookup"><span data-stu-id="eea82-118">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="eea82-119">Se l'istanza canvas è, ad esempio, ]( , deve essere https://contoso.test.instructure.com https://contoso.test.instructure.com) immesso l'URL completo.</span><span class="sxs-lookup"><span data-stu-id="eea82-119">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="Pagina amministrazione tenant LTI, con un campo a discesa per scegliere la piattaforma consumer LTI e un campo di testo URL.":::

4. <span data-ttu-id="eea82-121">Copia json selezionando il **pulsante Copia** (un'icona a destra che mostra due pagine una sopra l'altra).</span><span class="sxs-lookup"><span data-stu-id="eea82-121">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="eea82-122">Verrà usato per generare la chiave in Canvas.</span><span class="sxs-lookup"><span data-stu-id="eea82-122">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Immagine che mostra il pulsante copia che copierà il testo JSON visualizzato e lo rende disponibile per la generazione delle chiavi in Canvas.":::

5. <span data-ttu-id="eea82-124">Accedi all'istanza di Canvas come amministratore e seleziona **Chiavi** sviluppatore dal menu a sinistra della pagina.</span><span class="sxs-lookup"><span data-stu-id="eea82-124">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="eea82-125">Nell'elenco a discesa crea una chiave per sviluppatore scegliendo **LTI Key** nell'elenco a discesa in alto a destra della pagina.</span><span class="sxs-lookup"><span data-stu-id="eea82-125">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Screenshot che mostra la barra di spostamento sinistra con i tasti sviluppatore selezionati e la voce del tasto LTI selezionata da un elenco a discesa a destra della pagina.":::

6. <span data-ttu-id="eea82-127">Nell'elenco a discesa  Metodo della pagina Configura selezionare Incolla **JSON** come metodo e incollare il testo JSON copiato nel passaggio 5 nel campo di testo visualizzato.</span><span class="sxs-lookup"><span data-stu-id="eea82-127">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="eea82-128">Salva la chiave e diventa disponibile in Canvas in **stato Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="eea82-128">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="eea82-129">Attivare la chiave **e** copiare la chiave specificata nella colonna **Dettagli** da utilizzare nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="eea82-129">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Pagina Canvas con il tasto impostato in uno stato disattivato. Sarà necessario attivarla e la chiave dovrà essere copiata dalla colonna dei dettagli di questa pagina.":::

8. <span data-ttu-id="eea82-131">Torna al portale Microsoft OneDrive registrazione LTI e incolla la chiave nel campo **ID client Canvas.**</span><span class="sxs-lookup"><span data-stu-id="eea82-131">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="eea82-132">Selezionare **Avanti** quando si è pronti.</span><span class="sxs-lookup"><span data-stu-id="eea82-132">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="La pagina di registrazione del tenant LTI, che mostra il testo JSON e la casella di testo in cui deve essere copiata la chiave.":::

9. <span data-ttu-id="eea82-134">Rivedere e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="eea82-134">Review and save your changes.</span></span> <span data-ttu-id="eea82-135">Al completamento della registrazione verrà visualizzato un messaggio.</span><span class="sxs-lookup"><span data-stu-id="eea82-135">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="eea82-136">I dettagli della registrazione possono essere esaminati anche selezionando il **pulsante Visualizza tenant LTI** nella home page.</span><span class="sxs-lookup"><span data-stu-id="eea82-136">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="eea82-137">Abilitare Microsoft OneDrive LTI nei corsi Canvas</span><span class="sxs-lookup"><span data-stu-id="eea82-137">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="eea82-138">Un amministratore di Canvas può abilitare Microsoft OneDrive LTI per tutti i corsi.</span><span class="sxs-lookup"><span data-stu-id="eea82-138">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="eea82-139">Se Microsoft OneDrive LTI è necessario in un corso specifico (e non in tutti i corsi), il docente deve seguire gli stessi passaggi all'interno delle impostazioni del corso.</span><span class="sxs-lookup"><span data-stu-id="eea82-139">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="eea82-140">Accedi come amministratore e passa alla **sezione Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="eea82-140">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="eea82-141">Vai alla sezione **App** e seleziona il **pulsante Visualizza configurazioni app.**</span><span class="sxs-lookup"><span data-stu-id="eea82-141">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="eea82-142">Seleziona il **pulsante Aggiungi** app.</span><span class="sxs-lookup"><span data-stu-id="eea82-142">Select the **Add App** button.</span></span>
4. <span data-ttu-id="eea82-143">**Nell'elenco a discesa Tipo di** configurazione scegliere l'opzione Per **ID** client.</span><span class="sxs-lookup"><span data-stu-id="eea82-143">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="eea82-144">Incolla il valore della chiave per sviluppatore generata in precedenza nel **campo ID client** e seleziona il **pulsante** Invia.</span><span class="sxs-lookup"><span data-stu-id="eea82-144">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Pagina aggiungi app, che mostra l'opzione Per ID client nel menu a discesa Tipo di configurazione.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="eea82-146">Collaboration Impostazioni for Microsoft OneDrive LTI in Canvas Courses</span><span class="sxs-lookup"><span data-stu-id="eea82-146">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="eea82-147">Perché la collaborazione funzioni per docenti e studenti, non è consigliabile abilitare l'impostazione di collaborazione.</span><span class="sxs-lookup"><span data-stu-id="eea82-147">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="eea82-148">Per assicurarti che l'impostazione non sia abilitata, segui i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="eea82-148">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="eea82-149">Accedi come amministratore e passa alla **sezione Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="eea82-149">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="eea82-150">Passare alla **sezione Opzioni** funzionalità e quindi passare alla **sezione** Corso.</span><span class="sxs-lookup"><span data-stu-id="eea82-150">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="eea82-151">Impostare la **funzionalità Strumento di collaborazione esterna** in modo che non sia abilitata.</span><span class="sxs-lookup"><span data-stu-id="eea82-151">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="eea82-152">La collaborazione può essere assegnata a singoli studenti e a gruppi di studenti.</span><span class="sxs-lookup"><span data-stu-id="eea82-152">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="eea82-153">L'assegnazione a singoli studenti funziona per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eea82-153">Assigning to individual students works by default.</span></span> <span data-ttu-id="eea82-154">Per poter assegnare la collaborazione a un gruppo di studenti, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="eea82-154">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="eea82-155">Accedi come amministratore e passa alla sezione **Developer Keys.**</span><span class="sxs-lookup"><span data-stu-id="eea82-155">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="eea82-156">Trovare la chiave con valore 17000000000710 e impostarla su **On**.</span><span class="sxs-lookup"><span data-stu-id="eea82-156">Find the key with value 170000000000710 and set it to **On**.</span></span>
