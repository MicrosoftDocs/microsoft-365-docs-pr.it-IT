---
title: Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a visualizzare, creare, modificare ed eliminare i criteri collegamenti sicuri e le impostazioni globali dei collegamenti sicuri in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 29d777a7f351b9ab33232cb0136703ce3fa29842
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290154"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b6363-103">Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="b6363-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b6363-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="b6363-104">**Applies to**</span></span>
- [<span data-ttu-id="b6363-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="b6363-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b6363-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6363-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="b6363-107">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b6363-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="b6363-108">Per informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="b6363-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="b6363-109">Collegamenti sicuri è una funzionalità di [Microsoft Defender per Office 365](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="b6363-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="b6363-110">Per altre informazioni, vedere [Collegamenti sicuri in Microsoft Defender per Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="b6363-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="b6363-111">Non esiste un criterio collegamenti sicuri predefinito o predefinito.</span><span class="sxs-lookup"><span data-stu-id="b6363-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="b6363-112">Per ottenere l'analisi dei collegamenti sicuri degli URL, è necessario creare uno o più criteri collegamenti sicuri come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6363-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="b6363-113">Le impostazioni globali per la protezione dei collegamenti sicuri vengono configurate **al di fuori** dei criteri collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="b6363-114">Per istruzioni, vedere [Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365.](configure-global-settings-for-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="b6363-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>

<span data-ttu-id="b6363-115">È possibile configurare i criteri collegamenti sicuri nel Centro sicurezza & e conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni ai componenti aggiuntivi di Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="b6363-115">You can configure Safe Links policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="b6363-116">Gli elementi di base di un criterio collegamenti sicuri sono:</span><span class="sxs-lookup"><span data-stu-id="b6363-116">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="b6363-117">Il criterio collegamenti sicuri **:** attivare la protezione dei collegamenti sicuri, attivare l'analisi degli URL in tempo reale, specificare se attendere il completamento dell'analisi in tempo reale prima di recapitare il messaggio, attivare l'analisi dei messaggi interni, specificare se tenere traccia dei clic degli utenti sugli URL e specificare se consentire agli utenti di fare clic sull'URL originale.</span><span class="sxs-lookup"><span data-stu-id="b6363-117">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="b6363-118">**La regola per i collegamenti sicuri**: specifica la priorità e i filtri destinatario (a chi si applica il criterio).</span><span class="sxs-lookup"><span data-stu-id="b6363-118">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="b6363-119">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri collegamenti sicuri nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="b6363-119">The difference between these two elements isn't obvious when you manage Safe Links polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b6363-120">Quando si crea un criterio collegamenti sicuri, si crea contemporaneamente una regola per i collegamenti sicuri e il criterio collegamenti sicuri associati utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="b6363-120">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b6363-121">Quando si modifica un criterio collegamenti sicuri, le impostazioni relative al nome, alla priorità, abilitata o disabilitata e ai filtri destinatari modificano la regola per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-121">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="b6363-122">Tutte le altre impostazioni modificano il criterio collegamenti sicuri associato.</span><span class="sxs-lookup"><span data-stu-id="b6363-122">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="b6363-123">Quando si rimuove un criterio collegamenti sicuri, vengono rimossi la regola dei collegamenti sicuri e il criterio collegamenti sicuri associato.</span><span class="sxs-lookup"><span data-stu-id="b6363-123">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="b6363-124">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="b6363-124">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b6363-125">Per ulteriori informazioni, vedere la sezione Utilizzare Exchange Online PowerShell o [PowerShell EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) autonomo per configurare i criteri collegamenti sicuri più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6363-125">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b6363-126">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="b6363-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b6363-127">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b6363-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b6363-128">Per passare direttamente alla **pagina Collegamenti sicuri,** utilizzare <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="b6363-128">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="b6363-129">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b6363-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b6363-130">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b6363-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b6363-131">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6363-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="b6363-132">Per creare, modificare ed eliminare i criteri collegamenti sicuri,  è necessario essere membri dei gruppi di ruoli Gestione organizzazione  o Amministratore sicurezza nel Centro sicurezza & **conformità** e membri del gruppo di ruoli Gestione organizzazione in Exchange Online. </span><span class="sxs-lookup"><span data-stu-id="b6363-132">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="b6363-133">Per l'accesso in sola lettura ai criteri collegamenti  sicuri, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore **di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b6363-133">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="b6363-134">Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md) e Autorizzazioni in Exchange [Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="b6363-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="b6363-135">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6363-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b6363-136">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b6363-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="b6363-137">.</span><span class="sxs-lookup"><span data-stu-id="b6363-137">.</span></span> <span data-ttu-id="b6363-138">- Il **gruppo di ruoli Gestione** organizzazione di sola visualizzazione in Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b6363-138">- The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="b6363-139">Per le impostazioni consigliate per i criteri collegamenti sicuri, vedere [Impostazioni dei criteri collegamenti sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b6363-139">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="b6363-140">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="b6363-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b6363-141">[Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="b6363-141">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="b6363-142">Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri collegamenti sicuri esistenti.</span><span class="sxs-lookup"><span data-stu-id="b6363-142">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a><span data-ttu-id="b6363-143">Usare il Centro sicurezza & conformità per creare criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-143">Use the Security & Compliance Center to create Safe Links policies</span></span>

<span data-ttu-id="b6363-144">La creazione di un criterio collegamenti sicuri personalizzato nel Centro sicurezza & conformità crea la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="b6363-144">Creating a custom Safe Links policy in the Security & Compliance Center creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="b6363-145">Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6363-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b6363-146">Nella pagina **Collegamenti sicuri** fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="b6363-146">On the **Safe Links** page, click **Create**.</span></span>

3. <span data-ttu-id="b6363-147">Verrà **visualizzata la procedura guidata Nuovo criterio collegamenti** sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-147">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="b6363-148">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6363-148">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b6363-149">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="b6363-149">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b6363-150">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="b6363-150">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b6363-151">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6363-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b6363-152">Nella pagina **Impostazioni** visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6363-152">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="b6363-153">**Selezionare l'azione per URL sconosciuti** potenzialmente dannosi nei messaggi: selezionare **Attivato** per abilitare la protezione collegamenti sicuri per i collegamenti nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b6363-153">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span>

   - <span data-ttu-id="b6363-154">**Selezionare l'azione per URL sconosciuti** o potenzialmente  dannosi in Microsoft Teams: selezionare Attiva per abilitare la protezione dei collegamenti sicuri per i collegamenti in Teams.</span><span class="sxs-lookup"><span data-stu-id="b6363-154">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>

   - <span data-ttu-id="b6363-155">**Applicare l'analisi degli URL** in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file: selezionare questa impostazione per abilitare l'analisi in tempo reale dei collegamenti nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b6363-155">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting to enable real-time scanning of links in email messages.</span></span>

   - <span data-ttu-id="b6363-156">**Attendere il completamento dell'analisi degli URL prima** di recapitare il messaggio: selezionare questa impostazione per attendere il completamento dell'analisi degli URL in tempo reale prima di recapitare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6363-156">**Wait for URL scanning to complete before delivering the message**: Select this setting to wait for real-time URL scanning to complete before delivering the message.</span></span>

   - <span data-ttu-id="b6363-157">**Applica collegamenti sicuri ai messaggi di posta elettronica** inviati all'interno dell'organizzazione: selezionare questa impostazione per applicare il criterio Collegamenti sicuri ai messaggi tra mittenti interni e destinatari interni.</span><span class="sxs-lookup"><span data-stu-id="b6363-157">**Apply Safe Links to email messages sent within the organization**: Select this setting to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>

   - <span data-ttu-id="b6363-158">**Non tenere traccia dei clic degli utenti:** lasciare deselezionata questa impostazione per abilitare la verifica dei clic degli utenti sugli URL nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b6363-158">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>

   - <span data-ttu-id="b6363-159">**Non consentire agli utenti di passare all'URL** originale: selezionare questa impostazione per impedire agli utenti di fare clic sull'URL originale nelle pagine [di avviso.](atp-safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="b6363-159">**Do not allow users to click through to original URL**: Select this setting to block users from clicking through to the original URL in [warning pages](atp-safe-links.md#warning-pages-from-safe-links).</span></span>

   - <span data-ttu-id="b6363-160">**Non riscrivere gli URL** seguenti: consente l'accesso agli URL specificati che altrimenti verrebbero bloccati dai collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-160">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="b6363-161">Nella casella digitare l'URL o il valore desiderato e quindi fare clic su</span><span class="sxs-lookup"><span data-stu-id="b6363-161">In the box, type the URL or value that you want, and then click</span></span> ![Icona del pulsante Aggiungi](../../media/ITPro-EAC-AddIcon.png)<span data-ttu-id="b6363-163">.</span><span class="sxs-lookup"><span data-stu-id="b6363-163">.</span></span>

     <span data-ttu-id="b6363-164">Per rimuovere una voce esistente, selezionarla e quindi fare clic su</span><span class="sxs-lookup"><span data-stu-id="b6363-164">To remove an existing entry, select it and then click</span></span> ![Icona del pulsante Elimina](../../media/ITPro-EAC-DeleteIcon.png)<span data-ttu-id="b6363-166">.</span><span class="sxs-lookup"><span data-stu-id="b6363-166">.</span></span>

     <span data-ttu-id="b6363-167">Per la sintassi delle voci, vedere la sintassi delle voci per [l'elenco "Non riscrivere gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="b6363-167">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="b6363-168">Per informazioni dettagliate su queste impostazioni, vedere [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and Safe Links settings for Microsoft [Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="b6363-168">For detailed information about these settings, see [Safe Links settings for email messages](atp-safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="b6363-169">Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri Standard e Strict, vedere Impostazioni dei criteri [collegamenti sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="b6363-169">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="b6363-170">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6363-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b6363-171">Nella pagina **Applicato a** visualizzata, identificare i destinatari interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="b6363-171">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="b6363-172">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b6363-172">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b6363-173">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="b6363-173">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b6363-174">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b6363-174">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="b6363-175">Fare **clic su Aggiungi condizione.**</span><span class="sxs-lookup"><span data-stu-id="b6363-175">Click **Add a condition**.</span></span> <span data-ttu-id="b6363-176">Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se:**</span><span class="sxs-lookup"><span data-stu-id="b6363-176">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="b6363-177">**Il destinatario è**: specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6363-177">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b6363-178">**Il destinatario è membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6363-178">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="b6363-179">**Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6363-179">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="b6363-180">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una qualsiasi di queste** caselle.</span><span class="sxs-lookup"><span data-stu-id="b6363-180">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="b6363-181">Fare clic nella casella e scorrere l'elenco dei valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="b6363-181">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="b6363-182">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b6363-182">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="b6363-183">Per aggiungere ulteriori valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="b6363-183">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="b6363-184">Per rimuovere singole voci, fare **clic sull'icona** ![ Rimuovi sul ](../../media/scc-remove-icon.png) valore.</span><span class="sxs-lookup"><span data-stu-id="b6363-184">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="b6363-185">Per rimuovere l'intera condizione, fare **clic sull'icona** ![ Rimuovi nella ](../../media/scc-remove-icon.png) condizione.</span><span class="sxs-lookup"><span data-stu-id="b6363-185">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="b6363-186">Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se.**</span><span class="sxs-lookup"><span data-stu-id="b6363-186">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="b6363-187">Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**.</span><span class="sxs-lookup"><span data-stu-id="b6363-187">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="b6363-188">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="b6363-188">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b6363-189">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b6363-189">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b6363-190">Nella pagina **Verifica le impostazioni** visualizzata, rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b6363-190">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="b6363-191">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="b6363-191">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b6363-192">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b6363-192">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a><span data-ttu-id="b6363-193">Usare il Centro sicurezza & conformità per visualizzare i criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-193">Use the Security & Compliance Center to view Safe Links policies</span></span>

1. <span data-ttu-id="b6363-194">Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6363-194">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b6363-195">Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="b6363-195">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="b6363-196">I dettagli dei criteri vengono visualizzati in un riquadro a comparsa</span><span class="sxs-lookup"><span data-stu-id="b6363-196">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a><span data-ttu-id="b6363-197">Utilizzare il Centro sicurezza & conformità per modificare i criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-197">Use the Security & Compliance Center to modify Safe Links policies</span></span>

1. <span data-ttu-id="b6363-198">Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6363-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b6363-199">Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="b6363-199">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b6363-200">Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic **su Modifica criterio.**</span><span class="sxs-lookup"><span data-stu-id="b6363-200">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="b6363-201">Le impostazioni disponibili nel riquadro a comparsa visualizzate sono identiche a quelle descritte nella sezione Usare il Centro sicurezza [& conformità](#use-the-security--compliance-center-to-create-safe-links-policies) per creare criteri collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-201">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Links policies](#use-the-security--compliance-center-to-create-safe-links-policies) section.</span></span>

<span data-ttu-id="b6363-202">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b6363-202">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="b6363-203">Abilitare o disabilitare i criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-203">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="b6363-204">Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6363-204">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b6363-205">Si noti il valore nella **colonna** Stato:</span><span class="sxs-lookup"><span data-stu-id="b6363-205">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="b6363-206">Spostare l'interruttore a sinistra per disabilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="b6363-206">Move the toggle to the left to disable the policy:</span></span> ![Disattivare i criteri](../../media/scc-toggle-off.png)<span data-ttu-id="b6363-208">.</span><span class="sxs-lookup"><span data-stu-id="b6363-208">.</span></span>

   - <span data-ttu-id="b6363-209">Spostare l'interruttore a destra per abilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="b6363-209">Move the toggle to the right to enable the policy:</span></span> ![Attivare i criteri](../../media/scc-toggle-on.png)<span data-ttu-id="b6363-211">.</span><span class="sxs-lookup"><span data-stu-id="b6363-211">.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="b6363-212">Impostare la priorità dei criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-212">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="b6363-213">Per impostazione predefinita, ai criteri collegamenti sicuri viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="b6363-213">By default, Safe Links policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="b6363-214">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="b6363-214">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b6363-215">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="b6363-215">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b6363-216">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="b6363-216">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="b6363-217">I criteri collegamenti sicuri vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore priority** 0).</span><span class="sxs-lookup"><span data-stu-id="b6363-217">Safe Links policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

> [!NOTE]
> <span data-ttu-id="b6363-218">Nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio Collegamenti sicuri solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="b6363-218">In the Security & Compliance Center, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="b6363-219">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola dei collegamenti sicuri (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="b6363-219">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="b6363-220">Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="b6363-220">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="b6363-221">Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6363-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b6363-222">Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="b6363-222">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b6363-223">Nel riquadro a comparsa dei dettagli del criterio visualizzato, fai clic sul pulsante di priorità disponibile:</span><span class="sxs-lookup"><span data-stu-id="b6363-223">In the policy details fly out that appears, click the available priority button:</span></span>

   - <span data-ttu-id="b6363-224">Il criterio Collegamenti sicuri con **valore Priorità** **0** ha solo il **pulsante Diminuisci** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="b6363-224">The Safe Links policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="b6363-225">Per il criterio Collegamenti sicuri con il valore **di priorità** più basso (ad esempio, **3)** è disponibile solo il pulsante **Aumenta** priorità.</span><span class="sxs-lookup"><span data-stu-id="b6363-225">The Safe Links policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="b6363-226">Se si dispone di tre o più criteri collegamenti sicuri,  i criteri tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità **e Diminuisci** priorità disponibili.</span><span class="sxs-lookup"><span data-stu-id="b6363-226">If you have three or more Safe Links policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="b6363-227">Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **di** Priorità.</span><span class="sxs-lookup"><span data-stu-id="b6363-227">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="b6363-228">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b6363-228">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a><span data-ttu-id="b6363-229">Usare il Centro sicurezza & conformità per rimuovere i criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-229">Use the Security & Compliance Center to remove Safe Links policies</span></span>

1. <span data-ttu-id="b6363-230">Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6363-230">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span>

2. <span data-ttu-id="b6363-231">Nella pagina **Collegamenti sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="b6363-231">On the **Safe Links** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="b6363-232">Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic su **Elimina** criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="b6363-232">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="b6363-233">Utilizzare PowerShell di Exchange Online o PowerShell di EOP autonomo per configurare i criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-233">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="b6363-234">Come descritto in precedenza, un criterio collegamenti sicuri è costituito da un criterio collegamenti sicuri e da una regola per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-234">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="b6363-235">In PowerShell, la differenza tra i criteri dei collegamenti sicuri e le regole dei collegamenti sicuri è evidente.</span><span class="sxs-lookup"><span data-stu-id="b6363-235">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="b6363-236">È possibile gestire i criteri collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksPolicy** e gestire le regole dei collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="b6363-236">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="b6363-237">In PowerShell, si crea prima il criterio collegamenti sicuri, quindi si crea la regola dei collegamenti sicuri che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="b6363-237">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b6363-238">In PowerShell, è possibile modificare le impostazioni nei criteri collegamenti sicuri e nella regola dei collegamenti sicuri separatamente.</span><span class="sxs-lookup"><span data-stu-id="b6363-238">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="b6363-239">Quando si rimuove un criterio collegamenti sicuri da PowerShell, la regola dei collegamenti sicuri corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="b6363-239">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="b6363-240">Utilizzare PowerShell per creare criteri collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-240">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="b6363-241">La creazione di un criterio collegamenti sicuri in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="b6363-241">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b6363-242">Creare il criterio collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-242">Create the safe links policy.</span></span>
2. <span data-ttu-id="b6363-243">Creare la regola per i collegamenti sicuri che specifica il criterio per i collegamenti sicuri a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="b6363-243">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="b6363-244">È possibile creare una nuova regola per i collegamenti sicuri e assegnare un criterio collegamenti sicuri esistente e non ad essa.</span><span class="sxs-lookup"><span data-stu-id="b6363-244">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="b6363-245">Una regola per i collegamenti sicuri non può essere associata a più criteri collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-245">A safe links rule can't be associated with more than one safe links policy.</span></span>
> 
> - <span data-ttu-id="b6363-246">È possibile configurare le impostazioni seguenti nei nuovi criteri per i collegamenti sicuri in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="b6363-246">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
> 
>   - <span data-ttu-id="b6363-247">Creare il nuovo criterio come disabilitato (_abilitato_ `$false` nel cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="b6363-247">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="b6363-248">Impostare la priorità del criterio durante la creazione (_Priority_ ) nel _\<Number\>_ cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="b6363-248">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
> 
> - <span data-ttu-id="b6363-249">Un nuovo criterio collegamenti sicuri creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-249">A new safe links policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="b6363-250">Passaggio 1: Utilizzare PowerShell per creare un criterio collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-250">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="b6363-251">Per creare un criterio collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-251">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - <span data-ttu-id="b6363-252">Per informazioni dettagliate sulla sintassi delle voci da utilizzare per il parametro _DoNotRewriteUrls,_ vedere La sintassi delle voci per l'elenco ["Non riscrivere gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="b6363-252">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
> 
> - <span data-ttu-id="b6363-253">Per ulteriori informazioni sulla sintassi che è possibile utilizzare per il parametro _DoNotRewriteUrls_ quando si modificano i criteri dei collegamenti sicuri esistenti utilizzando il cmdlet **Set-SafeLinksPolicy,** vedere la sezione Utilizzare [PowerShell](#use-powershell-to-modify-safe-links-policies) per modificare i criteri dei collegamenti sicuri più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6363-253">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="b6363-254">In questo esempio viene creato un criterio collegamenti sicuri denominato Contoso All con i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b6363-254">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="b6363-255">Attivare l'analisi e la riscrittura degli URL nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b6363-255">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="b6363-256">Attivare l'analisi degli URL in Teams (solo anteprima TAP).</span><span class="sxs-lookup"><span data-stu-id="b6363-256">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="b6363-257">Attivare l'analisi in tempo reale degli URL selezionati, inclusi i collegamenti selezionati che puntano ai file.</span><span class="sxs-lookup"><span data-stu-id="b6363-257">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="b6363-258">Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b6363-258">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="b6363-259">Attivare l'analisi e la riscrittura degli URL per i messaggi interni.</span><span class="sxs-lookup"><span data-stu-id="b6363-259">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="b6363-260">Tenere traccia dei clic degli utenti correlati alla protezione dei collegamenti sicuri (non viene utilizzato il parametro _DoNotTrackUserClicks_ e il valore predefinito è $false, ovvero i clic degli utenti vengono monitorati).</span><span class="sxs-lookup"><span data-stu-id="b6363-260">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="b6363-261">Non consentire agli utenti di passare all'URL originale.</span><span class="sxs-lookup"><span data-stu-id="b6363-261">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="b6363-262">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="b6363-262">For detailed syntax and parameter information, see [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="b6363-263">Passaggio 2: Utilizzare PowerShell per creare una regola per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-263">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="b6363-264">Per creare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-264">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="b6363-265">In questo esempio viene creata una regola per i collegamenti sicuri denominata Contoso All con le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="b6363-265">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="b6363-266">La regola è associata al criterio collegamenti sicuri denominato Contoso All.</span><span class="sxs-lookup"><span data-stu-id="b6363-266">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="b6363-267">La regola si applica a tutti i destinatari nel contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="b6363-267">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="b6363-268">Poiché non viene utilizzato il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="b6363-268">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="b6363-269">La regola è abilitata (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="b6363-269">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="b6363-270">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="b6363-270">For detailed syntax and parameter information, see [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="b6363-271">Usare PowerShell per visualizzare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-271">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="b6363-272">Per visualizzare i criteri collegamenti sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-272">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b6363-273">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-273">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="b6363-274">In questo esempio vengono restituite informazioni dettagliate per il criterio collegamenti sicuri denominato Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b6363-274">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="b6363-275">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="b6363-275">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="b6363-276">Utilizzare PowerShell per visualizzare le regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-276">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="b6363-277">Per visualizzare le regole dei collegamenti sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-277">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b6363-278">In questo esempio viene restituito un elenco riepilogativo di tutte le regole per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="b6363-278">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="b6363-279">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6363-279">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="b6363-280">In questo esempio vengono restituite informazioni dettagliate per la regola dei collegamenti sicuri denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b6363-280">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="b6363-281">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="b6363-281">For detailed syntax and parameter information, see [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="b6363-282">Utilizzare PowerShell per modificare i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-282">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="b6363-283">Non è possibile rinominare un criterio collegamenti sicuri in PowerShell (il cmdlet **Set-SafeLinksPolicy** non dispone di alcun _parametro_ Name).</span><span class="sxs-lookup"><span data-stu-id="b6363-283">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b6363-284">Quando si rinomina un criterio collegamenti sicuri nel Centro sicurezza & conformità, si rinomina solo la regola dei collegamenti _sicuri._</span><span class="sxs-lookup"><span data-stu-id="b6363-284">When you rename a Safe Links policy in the Security & Compliance Center, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="b6363-285">L'unica considerazione aggiuntiva per la modifica dei criteri per i collegamenti sicuri in PowerShell è la sintassi disponibile per il parametro _DoNotRewriteUrls_ (l'elenco "Non riscrivere gli [URL seguenti"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span><span class="sxs-lookup"><span data-stu-id="b6363-285">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="b6363-286">Per aggiungere valori che sostituiranno eventuali voci esistenti, utilizzare la sintassi seguente: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="b6363-286">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="b6363-287">Per aggiungere o rimuovere valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="b6363-287">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="b6363-288">In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio collegamenti sicuri come descritto nel passaggio [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Utilizzare PowerShell per creare una sezione dei criteri collegamenti sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6363-288">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="b6363-289">Per modificare un criterio collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-289">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b6363-290">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="b6363-290">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="b6363-291">Utilizzare PowerShell per modificare le regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-291">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="b6363-292">L'unica impostazione non disponibile quando si modifica una regola per i collegamenti sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="b6363-292">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b6363-293">Per abilitare o disabilitare le regole dei collegamenti sicuri esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="b6363-293">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="b6363-294">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel passaggio [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Utilizzare PowerShell per creare una regola per i collegamenti sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b6363-294">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="b6363-295">Per modificare una regola per i collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-295">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b6363-296">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="b6363-296">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="b6363-297">Abilitazione o disabilitazione delle regole per i collegamenti sicuri tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6363-297">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="b6363-298">L'abilitazione o la disabilitazione di una regola per i collegamenti sicuri in PowerShell abilita o disabilita l'intero criterio Collegamenti sicuri (la regola per i collegamenti sicuri e il criterio collegamenti sicuri assegnati).</span><span class="sxs-lookup"><span data-stu-id="b6363-298">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="b6363-299">Per abilitare o disabilitare una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-299">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="b6363-300">In questo esempio viene disabilitata la regola per i collegamenti sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b6363-300">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b6363-301">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="b6363-301">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b6363-302">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) [e Disable-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="b6363-302">For detailed syntax and parameter information, see [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="b6363-303">Utilizzare PowerShell per impostare la priorità delle regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-303">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="b6363-304">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="b6363-304">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b6363-305">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="b6363-305">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b6363-306">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="b6363-306">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b6363-307">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="b6363-307">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b6363-308">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="b6363-308">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b6363-309">Per impostare la priorità di una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-309">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b6363-p123">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="b6363-p123">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="b6363-312">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="b6363-312">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="b6363-313">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="b6363-313">For detailed syntax and parameter information, see [Set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="b6363-314">Utilizzare PowerShell per rimuovere i criteri per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-314">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="b6363-315">Quando si utilizza PowerShell per rimuovere un criterio collegamenti sicuri, la regola dei collegamenti sicuri corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="b6363-315">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="b6363-316">Per rimuovere un criterio collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-316">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b6363-317">In questo esempio viene rimosso il criterio collegamenti sicuri denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b6363-317">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b6363-318">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="b6363-318">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="b6363-319">Utilizzare PowerShell per rimuovere le regole per i collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="b6363-319">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="b6363-320">Quando si utilizza PowerShell per rimuovere una regola per i collegamenti sicuri, il criterio collegamenti sicuri corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="b6363-320">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="b6363-321">Per rimuovere una regola per i collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b6363-321">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="b6363-322">In questo esempio viene rimossa la regola per i collegamenti sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b6363-322">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="b6363-323">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="b6363-323">For detailed syntax and parameter information, see [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="b6363-324">Per verificare che Collegamenti sicuri eseere in corso l'analisi dei messaggi, controllare i report di Microsoft Defender per Office 365 disponibili.</span><span class="sxs-lookup"><span data-stu-id="b6363-324">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="b6363-325">Per altre informazioni, vedere [Visualizzare i report per Defender per Office 365](view-reports-for-atp.md) e Usare Esplora risorse nel Centro sicurezza & [conformità.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="b6363-325">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b6363-326">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="b6363-326">How do you know these procedures worked?</span></span>

<span data-ttu-id="b6363-327">Per verificare la corretta creazione, modifica o rimozione dei criteri collegamenti sicuri, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b6363-327">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="b6363-328">Nel Centro sicurezza & conformità passare a Collegamenti sicuri dei criteri di **gestione** delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="b6363-328">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**.</span></span> <span data-ttu-id="b6363-329">Verificare l'elenco dei criteri, i relativi **valori di** stato e i relativi **valori di** priorità.</span><span class="sxs-lookup"><span data-stu-id="b6363-329">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b6363-330">Per visualizzare altri dettagli, selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b6363-330">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="b6363-331">In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, sostituire con il nome del criterio o della regola, eseguire il comando seguente \<Name\> e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b6363-331">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
