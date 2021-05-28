---
title: Informazioni dettagliate sulla rappresentazione
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come funzionano le informazioni dettagliate sulla rappresentazione. Possono determinare rapidamente quali mittenti inviano legittimamente messaggi di posta elettronica nelle proprie organizzazioni da domini che non superano i controlli di autenticazione della posta elettronica (SPF, DKIM o DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a11dd30030ccce886abd50ff72b5a09b10938ece
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535769"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a><span data-ttu-id="8b1f7-104">Informazioni dettagliate sulla rappresentazione in Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="8b1f7-104">Impersonation insight in Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8b1f7-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-105">**Applies to**</span></span>
- [<span data-ttu-id="8b1f7-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8b1f7-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8b1f7-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="8b1f7-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8b1f7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b1f7-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="8b1f7-109">Le funzionalità descritte in questo articolo sono disponibili in Anteprima, sono soggette a modifiche e non sono disponibili in tutte le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-109">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="8b1f7-110">La rappresentazione è il punto in cui il mittente di un messaggio di posta elettronica è molto simile a un indirizzo di posta elettronica mittente reale o previsto.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-110">Impersonation is where the sender of an email message looks very similar to a real or expected sender email address.</span></span> <span data-ttu-id="8b1f7-111">Gli utenti malintenzionati spesso imitavano gli indirizzi di posta elettronica dei mittenti nel phishing o in altri tipi di attacchi nel tentativo di ottenere l'attendibilità del destinatario.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-111">Attackers often user impersonated sender email addresses in phishing or other types of attacks in an effort to gain the trust of the recipient.</span></span> <span data-ttu-id="8b1f7-112">Esistono fondamentalmente due tipi di rappresentazione:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-112">There are basically two types of impersonation:</span></span>

- <span data-ttu-id="8b1f7-113">**Rappresentazione di dominio**: anziché lila@contoso.com, l'indirizzo di posta elettronica del mittente rappresentato è lila@ćóntoso.com.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-113">**Domain impersonation**: Instead of lila@contoso.com, the impersonated sender's email address is lila@ćóntoso.com.</span></span>
- <span data-ttu-id="8b1f7-114">**Rappresentazione utente**: anziché michelle@contoso.com, l'indirizzo di posta elettronica del mittente rappresentato è rnichell@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-114">**User impersonation**: Instead of michelle@contoso.com, the impersonated sender's email address is rnichell@contoso.com.</span></span>

<span data-ttu-id="8b1f7-115">La rappresentazione del dominio è diversa [dallo spoofing del](anti-spoofing-protection.md)dominio, perché il dominio rappresentato è in genere un dominio reale registrato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-115">Domain impersonation is different from [domain spoofing](anti-spoofing-protection.md), because the impersonated domain is typically a real, registered domain.</span></span> <span data-ttu-id="8b1f7-116">I messaggi provenienti dai mittenti nel dominio rappresentato possono e spesso superare controlli regolari di autenticazione della posta elettronica che altrimenti identificherebbero i tentativi di spoofing (SPF, DKIM e DMARC).</span><span class="sxs-lookup"><span data-stu-id="8b1f7-116">Messages from senders in the impersonated domain can and often do pass regular email authentication checks that would otherwise identify spoofing attempts (SPF, DKIM, and DMARC).</span></span>

<span data-ttu-id="8b1f7-117">La protezione della rappresentazione fa parte delle impostazioni dei criteri anti-phishing) che sono esclusive di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-117">Impersonation protection is part of the anti-phishing policy settings) that are exclusive to Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8b1f7-118">Per ulteriori informazioni su queste impostazioni, vedere Impostazioni di rappresentazione nei criteri [anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="8b1f7-118">For more information about these settings, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="8b1f7-119">È possibile utilizzare le informazioni dettagliate sulla rappresentazione per identificare rapidamente i messaggi provenienti da mittenti o domini mittenti impersonati configurati per la protezione della rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-119">You can use the impersonation insight to quickly identify messages from impersonated senders or sender domains that you've configured for impersonation protection.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8b1f7-120">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8b1f7-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8b1f7-121">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8b1f7-122">Per passare direttamente alle informazioni dettagliate sulla rappresentazione nella **pagina Anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="8b1f7-122">To go directly to the impersonation insight on the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="8b1f7-123">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-123">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8b1f7-124">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-124">**Organization Management**</span></span>
  - <span data-ttu-id="8b1f7-125">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-125">**Security Administrator**</span></span>
  - <span data-ttu-id="8b1f7-126">**Ruolo con autorizzazioni di lettura per la sicurezza**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-126">**Security Reader**</span></span>
  - <span data-ttu-id="8b1f7-127">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-127">**Global Reader**</span></span>

  <span data-ttu-id="8b1f7-128">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8b1f7-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="8b1f7-129">**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre  agli utenti le autorizzazioni necessarie nel Centro sicurezza e conformità di & e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-129">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8b1f7-130">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8b1f7-130">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="8b1f7-131">Abiliti e configura la protezione dalla rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-131">You enable and configure impersonation protection in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="8b1f7-132">La protezione della rappresentazione non è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-132">Impersonation protection is not enabled by default.</span></span> <span data-ttu-id="8b1f7-133">Per ulteriori informazioni, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8b1f7-133">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="open-the-impersonation-insight-in-the-security--compliance-center"></a><span data-ttu-id="8b1f7-134">Aprire le informazioni dettagliate sulla rappresentazione nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="8b1f7-134">Open the impersonation insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="8b1f7-135">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="8b1f7-136">Nella pagina principale **Anti-phishing,** l'analisi della rappresentazione è simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-136">On the main **Anti-phishing page**, the impersonation insight looks like this:</span></span>

   <span data-ttu-id="8b1f7-137">Questa panoramica ha due modalità:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-137">This insight has two modes:</span></span>

    - <span data-ttu-id="8b1f7-138">**Modalità insight:** se la protezione della rappresentazione è abilitata e configurata in qualsiasi criterio anti-phishing, l'analisi mostra il numero di messaggi rilevati dai mittenti impersonati negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-138">**Insight mode**: If impersonation protection is enabled and configured in any anti-phishing policies, the insight shows the number of detected messages from impersonated senders over the past seven days.</span></span> <span data-ttu-id="8b1f7-139">Questo è il totale di tutti i mittenti impersonati rilevati da tutti i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-139">This is the total of all detected impersonated senders from all anti-phishing policies.</span></span>
    - <span data-ttu-id="8b1f7-140">What **if mode**: Se la protezione della rappresentazione non è abilitata e  configurata in qualsiasi criterio anti-phishing attivo, le informazioni dettagliate mostrano quanti messaggi sarebbero stati rilevati dalle funzionalità di protezione della rappresentazione negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-140">**What if mode**: If impersonation protection is not enabled and configured in any active anti-phishing policies, the insight shows you how many messages *would* have been detected by our impersonation protection capabilities over the past seven days.</span></span>

   <span data-ttu-id="8b1f7-141">In entrambi i modi, **Domains impersonated** mostra il numero di messaggi provenienti da mittenti in domini protetti, mentre **Users impersonated** mostra il numero di messaggi provenienti da utenti protetti.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-141">Either way, **Domains impersonated** shows the number of messages from senders in protected domains, while **Users impersonated** shows the number of messages from protected users.</span></span>

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a><span data-ttu-id="8b1f7-142">Visualizzare informazioni sui messaggi provenienti da mittenti in domini impersonati</span><span class="sxs-lookup"><span data-stu-id="8b1f7-142">View information about messages from senders in impersonated domains</span></span>

<span data-ttu-id="8b1f7-143">Nella pagina Informazioni dettagliate sulla rappresentazione fare clic **su Domini impersonati.**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-143">On the impersonation insight, click **Domains impersonated**.</span></span> <span data-ttu-id="8b1f7-144">La **pagina Informazioni dettagliate** sulla rappresentazione visualizzata contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-144">The **Impersonation insight** page that opens contains the following information:</span></span>

- <span data-ttu-id="8b1f7-145">**Dominio mittente**: Dominio di rappresentazione, ovvero il dominio utilizzato per inviare il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-145">**Sender Domain**: The impersonating domain, which is the domain that was used to send the email message.</span></span> 
- <span data-ttu-id="8b1f7-146">**Numero messaggi**: numero di messaggi provenienti dal dominio del mittente che rappresenta il dominio negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-146">**Message count**: The number of messages from impersonating sender domain over the last 7 days.</span></span>
- <span data-ttu-id="8b1f7-147">**Tipo di rappresentazione:** questo valore indica la posizione rilevata della rappresentazione , ad esempio **Dominio nell'indirizzo**.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-147">**Impersonation type**: This value shows the detected location of the impersonation (for example, **Domain in address**).</span></span>
- <span data-ttu-id="8b1f7-148">**Dominio rappresentato:** il dominio rappresentato, che dovrebbe essere simile al dominio configurato per la protezione della rappresentazione nel criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-148">**Impersonated domain(s)**: The impersonated domain, which should closely resemble the domain that's configured for impersonation protection in the anti-phishing policy.</span></span>
- <span data-ttu-id="8b1f7-149">**Tipo di dominio:** questo valore è **Dominio aziendale** per i domini interni o **Dominio personalizzato** per i domini personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-149">**Domain type**: This value is **Company domain** for internal domains or **Custom domain** for custom domains.</span></span>
- <span data-ttu-id="8b1f7-150">**Criterio**: Criterio anti-phishing che ha rilevato il dominio rappresentato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-150">**Policy**: The anti-phishing policy that detected the impersonated domain.</span></span>
- <span data-ttu-id="8b1f7-151">**Allowed to impersonate**: Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-151">**Allowed to impersonate**: One of the following values:</span></span>
  - <span data-ttu-id="8b1f7-152">**Sì:** il dominio è stato configurato come dominio trusted (eccezione per la protezione della rappresentazione) nel criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-152">**Yes**: The domain was configured as trusted domain (an exception for impersonation protection) in the anti-spam policy.</span></span> <span data-ttu-id="8b1f7-153">I messaggi provenienti dai mittenti nel dominio rappresentato sono stati rilevati, ma sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-153">Messages from senders in the impersonated domain were detected, but allowed.</span></span>
  - <span data-ttu-id="8b1f7-154">**No**: il dominio è stato configurato per la protezione della rappresentazione nel criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-154">**No**: The domain was configured for impersonation protection in the anti-spam policy.</span></span> <span data-ttu-id="8b1f7-155">I messaggi provenienti da mittenti nel dominio rappresentato sono stati rilevati e agiti in base all'azione per i domini impersonati nel criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-155">Messages from senders in the impersonated domain were detected and acted upon based on the action for impersonated domains in the anti-spam policy.</span></span>

<span data-ttu-id="8b1f7-156">È possibile fare clic su intestazioni di colonna selezionate per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-156">You can click selected column headings to sort the results.</span></span>

<span data-ttu-id="8b1f7-157">Per filtrare i risultati, è possibile utilizzare la casella **Dominio** filtro per immettere un elenco di valori delimitati da virgole per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-157">To filter the results, you can use the **Filter domain** box to enter a comma-separated list of values to filter the results.</span></span>

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a><span data-ttu-id="8b1f7-158">Visualizzare i dettagli sui messaggi provenienti dai mittenti nei domini impersonati</span><span class="sxs-lookup"><span data-stu-id="8b1f7-158">View details about messages from senders in impersonated domains</span></span>

<span data-ttu-id="8b1f7-159">Nella pagina **Informazioni dettagliate sulla rappresentazione** selezionare una delle righe disponibili.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-159">On the **Impersonation insight** page, select one of the available rows.</span></span> <span data-ttu-id="8b1f7-160">Il riquadro a comparsa dei dettagli visualizzato contiene le informazioni e le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-160">The details flyout that appears contains the following information and features:</span></span>

- <span data-ttu-id="8b1f7-161">**Criteri di rappresentazione della selezione da modificare:** selezionare il criterio anti-phishing interessato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-161">**Selection impersonation policy to modify**: Select the affected anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="8b1f7-162">Sono disponibili solo i criteri in cui il dominio rappresentato è definito nel criterio.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-162">Only polices where the impersonated domain is defined in the policy are available.</span></span> <span data-ttu-id="8b1f7-163">Fare riferimento alla pagina precedente per vedere quale criterio era effettivamente responsabile del rilevamento del dominio rappresentato (probabilmente in base al destinatario e alla priorità del criterio).</span><span class="sxs-lookup"><span data-stu-id="8b1f7-163">Refer to the previous page to see which policy was actually responsible for detecting the impersonated domain (likely based on the recipient and the priority of the policy).</span></span>

- <span data-ttu-id="8b1f7-164">**Aggiungi all'elenco** di rappresentazione consentiti : utilizzare questo  interruttore per aggiungere o rimuovere il mittente dai mittenti e dai domini attendibili (eccezioni di rappresentazione) per il criterio anti-phishing selezionato:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-164">**Add to the allowed to impersonation list**: Use this toggle to add or remove the sender from the **Trusted senders and domains** (impersonation exceptions) for the anti-phishing policy that you selected:</span></span>
  - <span data-ttu-id="8b1f7-165">Se il **valore di Allowed to impersonate** per questa voce è **No,** l'interruttore è disattivato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-165">If the **Allowed to impersonate** value for this entry was **No**, the toggle is off.</span></span> <span data-ttu-id="8b1f7-166">Per escludere tutti i mittenti in questo dominio dalla valutazione per protezione dalla rappresentazione, fai scorrere l'interruttore su Attiva: ![ Attiva/ ](../../media/scc-toggle-on.png) attiva.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-166">To exempt all senders in this domain from evaluation by impersonation protection, slide the toggle to on: ![Toggle on](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="8b1f7-167">Il dominio viene aggiunto **all'elenco Domini attendibili** nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-167">The domain is added to the **Trusted domains** list in the impersonation protection settings of the anti-phishing policy.</span></span>
  - <span data-ttu-id="8b1f7-168">Se il **valore consentito per rappresentare questa** voce è **Sì,** l'interruttore è attivato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-168">If the **Allowed to impersonate** value for this entry was **Yes**, the toggle is on.</span></span> <span data-ttu-id="8b1f7-169">Per restituire tutti i mittenti in questo dominio alla valutazione tramite protezione della rappresentazione, fai scorrere l'interruttore su Off: ![ Toggle off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="8b1f7-169">To return all senders in this domain to evaluation by impersonation protection, slide the toggle to off: ![Toggle off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="8b1f7-170">Il dominio viene rimosso **dall'elenco Domini attendibili** nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-170">The domain is removed from the **Trusted domains** list in the impersonation protection settings of the anti-phishing policy.</span></span>

- <span data-ttu-id="8b1f7-171">Perché l'abbiamo preso.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-171">Why we caught this.</span></span>
- <span data-ttu-id="8b1f7-172">Cosa è necessario fare.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-172">What you need to do.</span></span>
- <span data-ttu-id="8b1f7-173">Riepilogo del dominio che elenca il dominio rappresentato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-173">A domain summary that list the impersonated domain.</span></span>
- <span data-ttu-id="8b1f7-174">WhoIs i dati sul mittente.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-174">WhoIs data about the sender.</span></span>
- <span data-ttu-id="8b1f7-175">Collegamento per aprire [Esplora minacce](threat-explorer.md) per visualizzare ulteriori dettagli sul mittente.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-175">A link to open [Threat Explorer](threat-explorer.md) to see additional details about the sender.</span></span>
- <span data-ttu-id="8b1f7-176">Messaggi simili provenienti dallo stesso mittente recapitati all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-176">Similar messages from the same sender that were delivered to your organization.</span></span>

## <a name="view-information-about-messages-from-impersonated-senders"></a><span data-ttu-id="8b1f7-177">Visualizzare informazioni sui messaggi provenienti da mittenti impersonati</span><span class="sxs-lookup"><span data-stu-id="8b1f7-177">View information about messages from impersonated senders</span></span>

<span data-ttu-id="8b1f7-178">In Informazioni dettagliate sulla rappresentazione fare clic **su Utenti impersonati**.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-178">On the impersonation insight, click **Users impersonated**.</span></span> <span data-ttu-id="8b1f7-179">La **pagina Informazioni dettagliate** sulla rappresentazione visualizzata contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-179">The **Impersonation insight** page that opens contains the following information:</span></span>

- <span data-ttu-id="8b1f7-180">**Sender**: Indirizzo di posta elettronica del mittente che ha inviato il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-180">**Sender**: The email address of the impersonating sender that sent the email message.</span></span>
- <span data-ttu-id="8b1f7-181">**Conteggio messaggi**: numero di messaggi provenienti dal mittente che rappresenta il mittente negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-181">**Message count**: The number of messages from the impersonating sender over the last 7 days.</span></span>
- <span data-ttu-id="8b1f7-182">**Tipo di rappresentazione:** questo valore è **User in display name**.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-182">**Impersonation type**: This value is **User in display name**.</span></span>
- <span data-ttu-id="8b1f7-183">**Utenti impersonati:** l'indirizzo di posta elettronica del mittente rappresentato, che dovrebbe essere simile all'utente configurato per la protezione della rappresentazione nel criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-183">**Impersonated user(s)**: The email address of the impersonated sender, which should closely resemble the user that's configured for impersonation protection in the anti-phishing policy.</span></span>
- <span data-ttu-id="8b1f7-184">**Tipo di utente**: Questo valore indica il tipo di protezione applicato (ad esempio, **Utente** protetto o Intelligence **cassetta postale).**</span><span class="sxs-lookup"><span data-stu-id="8b1f7-184">**User type**: This value shows the type of protection applied (for example, **Protected user** or **Mailbox Intelligence**).</span></span>
- <span data-ttu-id="8b1f7-185">**Criterio**: Criterio anti-phishing che ha rilevato il mittente rappresentato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-185">**Policy**: The anti-phishing policy that detected the impersonated sender.</span></span>
- <span data-ttu-id="8b1f7-186">**Allowed to impersonate**: Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-186">**Allowed to impersonate**: One of the following values:</span></span>
  - <span data-ttu-id="8b1f7-187">**Sì**: il mittente è stato configurato come utente attendibile (un'eccezione per la protezione dalla rappresentazione) nel criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-187">**Yes**: The sender was configured as trusted user (an exception for impersonation protection) in the anti-spam policy.</span></span> <span data-ttu-id="8b1f7-188">I messaggi provenienti dal mittente rappresentato sono stati rilevati, ma sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-188">Messages from the impersonated sender were detected, but allowed.</span></span>
  - <span data-ttu-id="8b1f7-189">**No**: il mittente è stato configurato per la protezione della rappresentazione nel criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-189">**No**: The sender was configured for impersonation protection in the anti-spam policy.</span></span> <span data-ttu-id="8b1f7-190">I messaggi provenienti dal mittente rappresentato sono stati rilevati e agiti in base all'azione per gli utenti impersonati nel criterio di protezione da posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-190">Messages from the impersonated sender were detected and acted upon based on the action for impersonated users in the anti-spam policy.</span></span>

<span data-ttu-id="8b1f7-191">È possibile fare clic su intestazioni di colonna selezionate per ordinare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-191">You can click selected column headings to sort the results.</span></span>

<span data-ttu-id="8b1f7-192">Per filtrare i risultati, è possibile utilizzare **la** casella Filtro mittente per immettere un elenco di valori delimitati da virgole per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-192">To filter the results, you can use the **Filter sender** box to enter a comma-separated list of values to filter the results.</span></span>

### <a name="view-details-about-messages-from-impersonated-senders"></a><span data-ttu-id="8b1f7-193">Visualizzare i dettagli sui messaggi provenienti da mittenti impersonati</span><span class="sxs-lookup"><span data-stu-id="8b1f7-193">View details about messages from impersonated senders</span></span>

<span data-ttu-id="8b1f7-194">Nella pagina **Informazioni dettagliate sulla rappresentazione** selezionare una delle righe disponibili.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-194">On the **Impersonation insight** page, select one of the available rows.</span></span> <span data-ttu-id="8b1f7-195">Il riquadro a comparsa dei dettagli visualizzato contiene le informazioni e le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-195">The details flyout that appears contains the following information and features:</span></span>

- <span data-ttu-id="8b1f7-196">**Criteri di rappresentazione della selezione da modificare:** selezionare il criterio anti-phishing interessato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-196">**Selection impersonation policy to modify**: Select the affected anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="8b1f7-197">Sono disponibili solo i criteri in cui il mittente rappresentato è definito nel criterio.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-197">Only polices where the impersonated sender is defined in the policy are available.</span></span> <span data-ttu-id="8b1f7-198">Fare riferimento alla pagina precedente per vedere quale criterio è stato effettivamente responsabile del rilevamento del mittente rappresentato (probabilmente in base al destinatario e alla priorità del criterio).</span><span class="sxs-lookup"><span data-stu-id="8b1f7-198">Refer to the previous page to see which policy was actually responsible for detecting the impersonated sender (likely based on the recipient and the priority of the policy).</span></span>

- <span data-ttu-id="8b1f7-199">**Aggiungi all'elenco** di rappresentazione consentiti : utilizzare questo  interruttore per aggiungere o rimuovere il mittente dai mittenti e dai domini attendibili (eccezioni di rappresentazione) per il criterio anti-phishing selezionato:</span><span class="sxs-lookup"><span data-stu-id="8b1f7-199">**Add to the allowed to impersonation list**: Use this toggle to add or remove the sender from the **Trusted senders and domains** (impersonation exceptions) for the anti-phishing policy that you selected:</span></span>
  - <span data-ttu-id="8b1f7-200">Se il **valore di Allowed to impersonate** per questa voce è **No,** l'interruttore è disattivato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-200">If the **Allowed to impersonate** value for this entry was **No**, the toggle is off.</span></span> <span data-ttu-id="8b1f7-201">Per escludere il mittente dalla valutazione per protezione dalla rappresentazione, fai scorrere l'interruttore su Attiva: ![ Attiva/ ](../../media/scc-toggle-on.png) attiva.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-201">To exempt the sender from evaluation by impersonation protection, slide the toggle to on: ![Toggle on](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="8b1f7-202">Il mittente viene aggiunto **all'elenco Utenti** attendibili nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-202">The sender is added to the **Trusted users** list in the impersonation protection settings of the anti-phishing policy.</span></span>
  - <span data-ttu-id="8b1f7-203">Se il **valore consentito per rappresentare questa** voce è **Sì,** l'interruttore è attivato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-203">If the **Allowed to impersonate** value for this entry was **Yes**, the toggle is on.</span></span> <span data-ttu-id="8b1f7-204">Per restituire il mittente alla valutazione tramite la protezione della rappresentazione, fai scorrere l'interruttore su off: ![ Toggle off ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="8b1f7-204">To return the sender to evaluation by impersonation protection, slide the toggle to off: ![Toggle off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="8b1f7-205">Il mittente viene rimosso **dall'elenco Utenti** attendibili nelle impostazioni di protezione della rappresentazione del criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-205">The sender is removed from the **Trusted users** list in the impersonation protection settings of the anti-phishing policy.</span></span>

- <span data-ttu-id="8b1f7-206">Perché l'abbiamo preso.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-206">Why we caught this.</span></span>
- <span data-ttu-id="8b1f7-207">Cosa è necessario fare.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-207">What you need to do.</span></span>
- <span data-ttu-id="8b1f7-208">Riepilogo del mittente che elenca il mittente rappresentato.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-208">A sender summary that list the impersonated sender.</span></span>
- <span data-ttu-id="8b1f7-209">WhoIs i dati sul mittente.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-209">WhoIs data about the sender.</span></span>
- <span data-ttu-id="8b1f7-210">Collegamento per aprire [Esplora minacce](threat-explorer.md) per visualizzare ulteriori dettagli sul mittente.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-210">A link to open [Threat Explorer](threat-explorer.md) to see additional details about the sender.</span></span>
- <span data-ttu-id="8b1f7-211">Messaggi simili provenienti dallo stesso mittente recapitati all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b1f7-211">Similar messages from the same sender that were delivered to your organization.</span></span>