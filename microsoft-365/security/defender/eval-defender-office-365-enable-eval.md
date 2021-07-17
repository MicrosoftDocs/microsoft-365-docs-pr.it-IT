---
title: Abilitare l'ambiente di valutazione per Microsoft Defender per Office 365 nell'ambiente di produzione, attivare la valutazione, l'attivazione
description: Passaggi per attivare la valutazione di Microsoft Defender per Office365, con licenze di valutazione, gestione dei record MX, & controllo dei domini accettati e delle connessioni in ingresso.
keywords: Microsoft 365 Defender prova, provare Microsoft 365 Defender, valutare Microsoft 365 Defender, laboratorio di valutazione Microsoft 365 Defender, pilota di Microsoft 365 Defender, sicurezza informatica, minaccia persistente avanzata, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458367"
---
# <a name="enable-the-evaluation-environment"></a><span data-ttu-id="ca06a-104">Abilitare l'ambiente di valutazione</span><span class="sxs-lookup"><span data-stu-id="ca06a-104">Enable the evaluation environment</span></span>

<span data-ttu-id="ca06a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ca06a-105">**Applies to:**</span></span>
- <span data-ttu-id="ca06a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca06a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ca06a-107">Questo articolo è [il passaggio 2 di 3 nel](eval-defender-office-365-overview.md) processo di configurazione dell'ambiente di valutazione per Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca06a-107">This article is [Step 2 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ca06a-108">Per ulteriori informazioni su questo processo, vedere [l'articolo di panoramica](eval-defender-office-365-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ca06a-108">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="ca06a-109">Usa la procedura seguente per abilitare la valutazione per Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ca06a-109">Use the following steps to enable the evaluation for Microsoft Defender for Office 365.</span></span>


![Passaggi per abilitare Microsoft Defender per Office 365 nell'ambiente di valutazione di Microsoft Defender](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [<span data-ttu-id="ca06a-111">Passaggio 1: Attivare le licenze di valutazione</span><span class="sxs-lookup"><span data-stu-id="ca06a-111">Step 1: Activate trial licenses</span></span>](#step-1-activate-trial-licenses)
- [<span data-ttu-id="ca06a-112">Passaggio 2: Controllare e verificare il record MX pubblico</span><span class="sxs-lookup"><span data-stu-id="ca06a-112">Step 2: Audit and verify the public MX record</span></span>](#step-2-audit-and-verify-the-public-mx-record)
- [<span data-ttu-id="ca06a-113">Passaggio 3: Controllare i domini accettati</span><span class="sxs-lookup"><span data-stu-id="ca06a-113">Step 3: Audit accepted domains</span></span>](#step-3-audit-accepted-domains)
- [<span data-ttu-id="ca06a-114">Passaggio 4: controllare i connettori in ingresso</span><span class="sxs-lookup"><span data-stu-id="ca06a-114">Step 4: Audit inbound connectors</span></span>](#step-4-audit-inbound-connectors)
- [<span data-ttu-id="ca06a-115">Passaggio 5: attivare la valutazione</span><span class="sxs-lookup"><span data-stu-id="ca06a-115">Step 5: Activate the evaluation</span></span>](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a><span data-ttu-id="ca06a-116">Passaggio 1: Attivare le licenze di valutazione</span><span class="sxs-lookup"><span data-stu-id="ca06a-116">Step 1: Activate trial licenses</span></span>

<span data-ttu-id="ca06a-117">Accedere a Microsoft Defender per l'ambiente Office 365 o al portale di amministrazione tenant esistente.</span><span class="sxs-lookup"><span data-stu-id="ca06a-117">Log on to your existing Microsoft Defender for Office 365 environment or tenant administration portal.</span></span>

1. <span data-ttu-id="ca06a-118">Passare al portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="ca06a-118">Navigate to the administration portal.</span></span>
2. <span data-ttu-id="ca06a-119">Seleziona Acquista servizi dalla barra di avvio veloce.</span><span class="sxs-lookup"><span data-stu-id="ca06a-119">Select Purchase Services from the quick launch.</span></span>

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Fare clic su Acquista servizi nel riquadro di spostamento di Office 365.":::

3.  <span data-ttu-id="ca06a-121">Scorri verso il basso fino alla Add-On (o cerca "Defender") per individuare Microsoft Defender per Office 365 piani.</span><span class="sxs-lookup"><span data-stu-id="ca06a-121">Scroll down to the Add-On section (or search for "Defender") to locate the Microsoft Defender for Office 365 plans.</span></span>
4.  <span data-ttu-id="ca06a-122">Fare clic su Dettagli accanto al piano che si desidera valutare.</span><span class="sxs-lookup"><span data-stu-id="ca06a-122">Click Details next the plan you want to evaluate.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Fare clic sul pulsante Dettagli.":::

5. <span data-ttu-id="ca06a-124">Fai clic sul *collegamento Avvia versione di valutazione* gratuita.</span><span class="sxs-lookup"><span data-stu-id="ca06a-124">Click the *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Fai clic su Avvia versione di valutazione gratuita *collegamento ipertestuale* in questo pannello.":::

6. <span data-ttu-id="ca06a-126">Conferma la richiesta e fai clic *sul pulsante Prova* ora.</span><span class="sxs-lookup"><span data-stu-id="ca06a-126">Confirm your request and click the *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Ora fai clic sul pulsante Prova ora *.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a><span data-ttu-id="ca06a-128">Passaggio 2: Controllare e verificare il record MX pubblico</span><span class="sxs-lookup"><span data-stu-id="ca06a-128">Step 2: Audit and verify the public MX record</span></span>

<span data-ttu-id="ca06a-129">Per valutare in modo efficace Microsoft Defender per Office 365, è importante che la posta elettronica esterna in ingresso sia inoltrata tramite l'istanza di Exchange Online Protection (EOP) associata al tenant.</span><span class="sxs-lookup"><span data-stu-id="ca06a-129">To effectively evaluate Microsoft Defender for Office 365, it's important that inbound external email be relayed through the Exchange Online Protection (EOP) instance associated with your tenant.</span></span>

1. <span data-ttu-id="ca06a-130">Accedere al portale di amministrazione di M365, espandere Impostazioni e selezionare Domini.</span><span class="sxs-lookup"><span data-stu-id="ca06a-130">Log on to the M365 Admin Portal, expand Settings, and select Domains.</span></span>
2. <span data-ttu-id="ca06a-131">Selezionare il dominio di posta elettronica verificato e fare clic su Gestisci DNS.</span><span class="sxs-lookup"><span data-stu-id="ca06a-131">Select your verified email domain and click Manage DNS.</span></span>
3. <span data-ttu-id="ca06a-132">Prendere nota del record MX generato e assegnato al tenant EOP.</span><span class="sxs-lookup"><span data-stu-id="ca06a-132">Make note of the MX record generated and assigned to your EOP tenant.</span></span>
4. <span data-ttu-id="ca06a-133">Accedere alla zona DNS esterna (pubblica) e controllare il record MX primario associato al dominio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ca06a-133">Access your external (public) DNS zone and check the primary MX record associated with your email domain.</span></span>
    - <span data-ttu-id="ca06a-134">*Se il record MX pubblico corrisponde attualmente all'indirizzo EOP assegnato (ad esempio, tenant-com.mail.protection.outlook.com),* non è necessario apportare ulteriori modifiche al routing.</span><span class="sxs-lookup"><span data-stu-id="ca06a-134">*If your public MX record currently matches the assigned EOP address (e.g. tenant-com.mail.protection.outlook.com) then no further routing changes should be required*.</span></span>
    - <span data-ttu-id="ca06a-135">Se il record MX pubblico attualmente si risolve in un gateway SMTP di terze parti o locale, potrebbero essere necessarie configurazioni di routing aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="ca06a-135">If your public MX record currently resolves to a third-party or on-premises SMTP gateway then additional routing configurations may be required.</span></span>
    - <span data-ttu-id="ca06a-136">Se il record MX pubblico attualmente si risolve in un Exchange locale, è possibile che si sia ancora in un modello ibrido in cui alcune cassette postali del destinatario non sono ancora state migrate in EXO.</span><span class="sxs-lookup"><span data-stu-id="ca06a-136">If your public MX record currently resolves to on-premises Exchange then you may still be in a hybrid model where some recipient mailbox have not yet been migrated to EXO.</span></span>

## <a name="step-3-audit-accepted-domains"></a><span data-ttu-id="ca06a-137">Passaggio 3: Controllare i domini accettati</span><span class="sxs-lookup"><span data-stu-id="ca06a-137">Step 3: Audit accepted domains</span></span>

1. <span data-ttu-id="ca06a-138">Accedere al portale di Exchange Online, selezionare Posta Flow e quindi fare clic su Domini accettati.</span><span class="sxs-lookup"><span data-stu-id="ca06a-138">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Accepted Domains.</span></span>
2. <span data-ttu-id="ca06a-139">Dall'elenco dei domini accettati che sono stati aggiunti e verificati nel tenant, prendere nota del tipo **di** dominio per il dominio di posta elettronica principale.</span><span class="sxs-lookup"><span data-stu-id="ca06a-139">From the list of accepted domains that have been added and verified in your tenant, make note of the **domain type** for your primary email domain.</span></span>
    - <span data-ttu-id="ca06a-140">Se il tipo di dominio è impostato su ***Autorevole,*** si presuppone che tutte le cassette postali dei destinatari per l'organizzazione risiedano attualmente in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ca06a-140">If the domain type is set to ***Authoritative*** then it is assumed all recipient mailboxes for your organization currently reside in Exchange Online.</span></span>
    - <span data-ttu-id="ca06a-141">Se il tipo di dominio è impostato su ***Inoltro*** interno, è possibile che si sia ancora in un modello ibrido in cui alcune cassette postali dei destinatari risiedono ancora in locale.</span><span class="sxs-lookup"><span data-stu-id="ca06a-141">If the domain type is set to ***Internal Relay*** then you may still be in a hybrid model where some recipient mailboxes still reside on-premises.</span></span>

## <a name="step-4-audit-inbound-connectors"></a><span data-ttu-id="ca06a-142">Passaggio 4: controllare i connettori in ingresso</span><span class="sxs-lookup"><span data-stu-id="ca06a-142">Step 4: Audit inbound connectors</span></span>

1. <span data-ttu-id="ca06a-143">Accedere al portale di Exchange Online, selezionare Mail Flow e quindi fare clic su Connettori.</span><span class="sxs-lookup"><span data-stu-id="ca06a-143">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Connectors.</span></span>
2. <span data-ttu-id="ca06a-144">Nell'elenco dei connettori configurati prendere nota di tutte le voci provenienti dall'organizzazione **partner** e che possono essere correlate a un gateway SMTP di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ca06a-144">From the list of configured connectors, make note of any entries which are from **Partner Organization** and may correlate to a third-party SMTP gateway.</span></span>
3. <span data-ttu-id="ca06a-145">Nell'elenco dei connettori configurati prendere nota delle voci etichettate Dal server di posta elettronica **dell'organizzazione,** che potrebbero indicare che si è ancora in uno scenario ibrido.</span><span class="sxs-lookup"><span data-stu-id="ca06a-145">From the list of configured connectors, make note of any entries labeled **From your organization's email server** which may indicate that you are still in hybrid scenario.</span></span>

## <a name="step-5-activate-the-evaluation"></a><span data-ttu-id="ca06a-146">Passaggio 5: attivare la valutazione</span><span class="sxs-lookup"><span data-stu-id="ca06a-146">Step 5: Activate the evaluation</span></span>

<span data-ttu-id="ca06a-147">Usa le istruzioni qui per attivare Microsoft Defender per Office 365 valutazione dal portale Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ca06a-147">Use the instructions here to activate your Microsoft Defender for Office 365 evaluation from the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="ca06a-148">Accedere al tenant con un account che abbia accesso al Microsoft 365 Defender portale.</span><span class="sxs-lookup"><span data-stu-id="ca06a-148">Log on to your tenant with an account that has access to the Microsoft 365 Defender portal.</span></span>
2. <span data-ttu-id="ca06a-149">Scegli se vuoi impostare il portale **Microsoft 365 Defender come** interfaccia predefinita per Microsoft Defender per Office 365 amministrazione (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="ca06a-149">Choose whether you want to make the **Microsoft 365 Defender portal** your default interface for Microsoft Defender for Office 365 administration (recommended).</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Fare clic sul pulsante Attiva impostazioni per usare il portale Microsoft 365 Defender centralizzato e migliorato per l'amministrazione.":::

3. <span data-ttu-id="ca06a-151">Nel menu di spostamento seleziona **Criteri & regole** in Collaborazione & posta *elettronica*.</span><span class="sxs-lookup"><span data-stu-id="ca06a-151">From the navigation menu, select **Policies & Rules** under *Email & Collaboration*.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Ecco un'immagine del menu Collaborazione & posta elettronica che punta a Criteri & regole. Fai clic qui.":::

4. <span data-ttu-id="ca06a-153">Nel dashboard *Regole &* criteri fare clic su Criteri **di minaccia.**</span><span class="sxs-lookup"><span data-stu-id="ca06a-153">On the *Policy & Rules* dashboard, click **Threat Policies**.</span></span>

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Immagine del dashboard Regole & criteri e una freccia che punta ai criteri di minaccia. Fare clic su avanti.":::

5. <span data-ttu-id="ca06a-155">Scorri verso il *basso fino a Criteri* aggiuntivi e seleziona il riquadro Valuta Defender **Office 365** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ca06a-155">Scroll down to *Additional Policies* and select the **Evaluate Defender for Office 365** tile.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Il riquadro Eval Defender per Office 365 che indica che si tratta di una versione di valutazione di 30 giorni tra i vettori di & di collaborazione. Fare clic su.":::

6. <span data-ttu-id="ca06a-157">Ora scegliere se la posta elettronica esterna Exchange Online direttamente o a un gateway o a un servizio di terze parti e fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="ca06a-157">Now choose whether external email routes to Exchange Online directly, or to a third-party gateway or service, and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 valuterà l'invio di posta alle cassette postali Exchange Online utenti. Fornire i dettagli su come viene instradata la posta elettronica ora, incluso il nome del connettore in uscita che instrada la posta. Se si utilizza solo Exchange Online Protection (EOP) non si dispone di un connettore. Scegliere uno dei provider di terze parti o locali oppure utilizzare solo EOP.":::

7. <span data-ttu-id="ca06a-159">Se si utilizza un gateway di terze parti, selezionare il nome del fornitore nell'elenco a discesa insieme al connettore in ingresso associato alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="ca06a-159">If you use a third-party gateway, select the vendor name from the drop-down along with the inbound connector associated with that solution.</span></span> <span data-ttu-id="ca06a-160">Dopo aver elencato le risposte, fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="ca06a-160">When you've listed your answers, click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="In questa finestra di dialogo scegli il servizio fornitore di terze parti utilizzato dall'organizzazione oppure seleziona *Altro*. Nella finestra di dialogo successiva, selezionare il connettore in ingresso. Quindi fare clic su Avanti.":::

8. <span data-ttu-id="ca06a-162">Rivedere le impostazioni e fare clic sul **pulsante Crea** valutazione.</span><span class="sxs-lookup"><span data-stu-id="ca06a-162">Review your settings and click the **Create Evaluation** button.</span></span>

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="In questo riquadro è presente un elenco a discesa per esaminare le impostazioni. È inoltre disponibile un collegamento selezionabile per modificare il tipo di instradamento, se necessario. Quando sei pronto, fai clic sul pulsante grande blu Crea valutazione.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="E ora la configurazione è stata completata. Il pulsante blu in questa pagina indica &quot;Vai a valutazione&quot;.":::      |

## <a name="next-steps"></a><span data-ttu-id="ca06a-165">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ca06a-165">Next steps</span></span>

<span data-ttu-id="ca06a-166">Passaggio 3 di 3: Configurare il progetto pilota per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="ca06a-166">Step 3 of 3: Set up the pilot for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="ca06a-167">Torna alla panoramica di [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ca06a-167">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="ca06a-168">Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ca06a-168">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>