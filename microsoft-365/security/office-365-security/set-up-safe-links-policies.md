---
title: Configurare i Cassaforte dei collegamenti in Microsoft Defender per Office 365
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
description: Gli amministratori possono imparare a visualizzare, creare, modificare ed eliminare i criteri dei collegamenti Cassaforte e le impostazioni dei collegamenti Cassaforte globali in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1e0257fd124a53b2191ad8025ce42dc13a2e23e
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096769"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="5ed34-103">Configurare i Cassaforte dei collegamenti in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="5ed34-103">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ed34-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5ed34-104">**Applies to**</span></span>
- [<span data-ttu-id="5ed34-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5ed34-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ed34-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ed34-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="5ed34-107">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="5ed34-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="5ed34-108">Se si è un utente principale che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="5ed34-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="5ed34-109">Cassaforte I collegamenti in [Microsoft Defender per Office 365](defender-for-office-365.md) forniscono l'analisi DEGLI URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica dei clic degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni.</span><span class="sxs-lookup"><span data-stu-id="5ed34-109">Safe Links in [Microsoft Defender for Office 365](defender-for-office-365.md) provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="5ed34-110">Per ulteriori informazioni, vedere [Cassaforte collegamenti in Microsoft Defender per Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="5ed34-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="5ed34-111">Non esiste un criterio predefinito o predefinito per Cassaforte collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-111">There's no built-in or default Safe Links policy.</span></span> <span data-ttu-id="5ed34-112">Per ottenere Cassaforte l'analisi dei collegamenti degli URL, è necessario creare uno o più criteri Cassaforte collegamenti, come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5ed34-112">To get Safe Links scanning of URLs, you need to create one or more Safe Links policies as described in this article.</span></span>

> [!NOTE]
>
> <span data-ttu-id="5ed34-113">È possibile configurare le impostazioni globali per la Cassaforte dei collegamenti **esterni** ai criteri Cassaforte collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-113">You configure the global settings for Safe Links protection **outside** of Safe Links policies.</span></span> <span data-ttu-id="5ed34-114">Per istruzioni, vedere [Configure global settings for Cassaforte Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="5ed34-114">For instructions, see [Configure global settings for Safe Links in Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md).</span></span>
>
> <span data-ttu-id="5ed34-115">Gli amministratori devono considerare le diverse impostazioni di configurazione per Cassaforte collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-115">Admins should consider the different configuration settings for Safe Links.</span></span> <span data-ttu-id="5ed34-116">Una delle opzioni disponibili è includere informazioni identificabili dall'utente Cassaforte collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-116">One of the available options is to include user identifiable information in Safe Links.</span></span> <span data-ttu-id="5ed34-117">Questa funzionalità consente *ai team di Security Ops di* analizzare potenziali compromissione degli utenti, intraprendere azioni correttive e limitare costose violazioni.</span><span class="sxs-lookup"><span data-stu-id="5ed34-117">This feature enables *Security Ops teams* to investigate potential user compromise, take corrective action, and limit costly breaches.</span></span>

<span data-ttu-id="5ed34-118">È possibile configurare i criteri collegamenti Cassaforte nel portale di Microsoft 365 Defender o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi di Microsoft Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="5ed34-118">You can configure Safe Links policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="5ed34-119">Gli elementi di base di un criterio Cassaforte collegamenti sono:</span><span class="sxs-lookup"><span data-stu-id="5ed34-119">The basic elements of a Safe Links policy are:</span></span>

- <span data-ttu-id="5ed34-120">Il criterio collegamenti **sicuri:** attivare la protezione dei collegamenti di Cassaforte, attivare l'analisi degli URL in tempo reale, specificare se attendere il completamento dell'analisi in tempo reale prima di recapitare il messaggio, attivare l'analisi dei messaggi interni, specificare se tenere traccia dei clic degli utenti sugli URL e specificare se consentire agli utenti di fare clic sull'URL originale.</span><span class="sxs-lookup"><span data-stu-id="5ed34-120">**The safe links policy**: Turn on Safe Links protection, turn on real-time URL scanning, specify whether to wait for real-time scanning to complete before delivering the message, turn on scanning for internal messages, specify whether to track user clicks on URLs, and specify whether to allow users to click trough to the original URL.</span></span>
- <span data-ttu-id="5ed34-121">**La regola dei collegamenti sicuri**: Specifica la priorità e i filtri destinatari (a cui si applica il criterio).</span><span class="sxs-lookup"><span data-stu-id="5ed34-121">**The safe links rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="5ed34-122">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri Cassaforte collegamenti nel portale Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="5ed34-122">The difference between these two elements isn't obvious when you manage Safe Links policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="5ed34-123">Quando si crea un criterio Cassaforte collegamenti sicuri, si crea contemporaneamente una regola per i collegamenti sicuri e il criterio collegamenti sicuri associati utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="5ed34-123">When you create a Safe Links policy, you're actually creating a safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="5ed34-124">Quando si modifica un criterio Cassaforte collegamenti sicuri, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola dei collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-124">When you modify a Safe Links policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe links rule.</span></span> <span data-ttu-id="5ed34-125">Tutte le altre impostazioni modificano il criterio dei collegamenti sicuri associati.</span><span class="sxs-lookup"><span data-stu-id="5ed34-125">All other settings modify the associated safe links policy.</span></span>
- <span data-ttu-id="5ed34-126">Quando si rimuove un criterio Cassaforte collegamenti sicuri, la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="5ed34-126">When you remove a Safe Links policy, the safe links rule and the associated safe links policy are removed.</span></span>

<span data-ttu-id="5ed34-127">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="5ed34-127">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="5ed34-128">Per ulteriori informazioni, vedere la sezione Use [Exchange Online PowerShell or standalone EOP PowerShell to configure Cassaforte Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5ed34-128">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) section later in this article.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ed34-129">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="5ed34-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5ed34-130">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="5ed34-130">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5ed34-131">Per passare direttamente alla pagina **Cassaforte collegamenti,** utilizzare <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="5ed34-131">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="5ed34-132">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ed34-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5ed34-133">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ed34-133">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5ed34-134">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-134">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5ed34-135">Per creare, modificare ed eliminare i criteri collegamenti Cassaforte, è  necessario essere  membri dei gruppi di ruoli  Gestione organizzazione  o Amministratore sicurezza nel portale di Microsoft 365 Defender e membri del gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ed34-135">To create, modify, and delete Safe Links policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="5ed34-136">Per l'accesso in sola lettura ai Cassaforte dei collegamenti, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5ed34-136">For read-only access to Safe Links policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="5ed34-137">Per ulteriori informazioni, vedere [Autorizzazioni nel portale Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Autorizzazioni in [Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="5ed34-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="5ed34-138">L'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ed34-138">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5ed34-139">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5ed34-139">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  <span data-ttu-id="5ed34-140">.</span><span class="sxs-lookup"><span data-stu-id="5ed34-140">.</span></span> <span data-ttu-id="5ed34-141">- Il **gruppo di ruoli Gestione** organizzazione di sola [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5ed34-141">- The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="5ed34-142">Per le impostazioni consigliate per i criteri Cassaforte collegamenti, vedere Cassaforte [impostazioni dei criteri collegamenti.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="5ed34-142">For our recommended settings for Safe Links policies, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

- <span data-ttu-id="5ed34-143">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="5ed34-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="5ed34-144">[Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="5ed34-144">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="5ed34-145">Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri dei collegamenti Cassaforte esistenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-145">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a><span data-ttu-id="5ed34-146">Utilizzare il portale Microsoft 365 Defender per creare criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-146">Use the Microsoft 365 Defender portal to create Safe Links policies</span></span>

<span data-ttu-id="5ed34-147">La creazione di un criterio personalizzato Cassaforte collegamenti sicuri nel portale di Microsoft 365 Defender crea contemporaneamente la regola dei collegamenti sicuri e il criterio collegamenti sicuri associati utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="5ed34-147">Creating a custom Safe Links policy in the Microsoft 365 Defender portal creates the safe links rule and the associated safe links policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="5ed34-148">Nel portale Microsoft 365 Defender, passare alla sezione **Criteri & criteri** di minaccia Cassaforte \>  \>  \> **collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-148">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="5ed34-149">Nella pagina **Cassaforte collegamenti** fare clic su Crea ![ icona ](../../media/m365-cc-sc-create-icon.png) **Crea**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-149">On the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="5ed34-150">Verrà **visualizzata la procedura guidata Cassaforte nuovi** collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-150">The **New Safe Links policy** wizard opens.</span></span> <span data-ttu-id="5ed34-151">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-151">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="5ed34-152">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="5ed34-153">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="5ed34-154">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5ed34-155">Nella pagina **Utenti e domini** visualizzata identificare i destinatari interni a cui si applica il criterio (condizioni del destinatario):</span><span class="sxs-lookup"><span data-stu-id="5ed34-155">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="5ed34-156">**Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ed34-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="5ed34-157">**Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ed34-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="5ed34-158">**Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5ed34-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="5ed34-159">Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="5ed34-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="5ed34-160">Ripetere questa procedura tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="5ed34-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="5ed34-161">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="5ed34-161">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="5ed34-163">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="5ed34-163">next to the value.</span></span>

   <span data-ttu-id="5ed34-164">Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="5ed34-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="5ed34-165">Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.</span><span class="sxs-lookup"><span data-stu-id="5ed34-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="5ed34-166">Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="5ed34-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="5ed34-167">Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="5ed34-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="5ed34-168">**Escludere questi utenti, gruppi** e domini: per aggiungere eccezioni per i destinatari interni a cui si applica il criterio (eccezioni dei destinatari), selezionare questa opzione e configurare le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="5ed34-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recipient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="5ed34-169">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="5ed34-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="5ed34-170">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5ed34-171">Nella pagina **Impostazioni di** protezione visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-171">On the **Protection settings** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5ed34-172">**Selezionare l'azione per URL** sconosciuti potenzialmente  dannosi nei messaggi: selezionare Attivato per abilitare la protezione Cassaforte collegamenti per i collegamenti nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5ed34-172">**Select the action for unknown potentially malicious URLs in messages**: Select **On** to enable Safe Links protection for links in email messages.</span></span> <span data-ttu-id="5ed34-173">Se si attiva questa impostazione, sono disponibili le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-173">If you turn this setting on, the following settings are available:</span></span>
     - <span data-ttu-id="5ed34-174">**Applica l'analisi degli URL** in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file: selezionare questa opzione per abilitare l'analisi in tempo reale dei collegamenti nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5ed34-174">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this option to enable real-time scanning of links in email messages.</span></span> <span data-ttu-id="5ed34-175">Se si attiva questa impostazione, è disponibile l'impostazione seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-175">If you turn this setting on the following setting is available:</span></span>
       - <span data-ttu-id="5ed34-176">**Attendere il completamento dell'analisi** degli URL prima di recapitare il messaggio: selezionare questa opzione per attendere il completamento dell'analisi degli URL in tempo reale prima di recapitare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-176">**Wait for URL scanning to complete before delivering the message**: Select this option to wait for real-time URL scanning to complete before delivering the message.</span></span>
     - <span data-ttu-id="5ed34-177">**Applica Cassaforte** collegamenti ai messaggi di posta elettronica inviati all'interno dell'organizzazione : selezionare questa opzione per applicare il criterio Collegamenti Cassaforte ai messaggi tra mittenti interni e destinatari interni.</span><span class="sxs-lookup"><span data-stu-id="5ed34-177">**Apply Safe Links to email messages sent within the organization**: Select this option to apply the Safe Links policy to messages between internal senders and internal recipients.</span></span>
   - <span data-ttu-id="5ed34-178">**Selezionare l'azione per** URL sconosciuti o potenzialmente dannosi all'interno di Microsoft Teams : selezionare Attivato per abilitare la protezione dei collegamenti Cassaforte per i collegamenti in Teams. </span><span class="sxs-lookup"><span data-stu-id="5ed34-178">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Select **On** to enable Safe Links protection for links in Teams.</span></span>
   - <span data-ttu-id="5ed34-179">**Non tenere traccia dei clic degli utenti:** lasciare deselezionata questa impostazione per abilitare la verifica dei clic degli utenti sugli URL nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5ed34-179">**Do not track user clicks**: Leave this setting unselected to enable the tracking user clicks on URLs in email messages.</span></span>
   - <span data-ttu-id="5ed34-180">**Non consentire agli utenti di passare all'URL** originale: selezionare questa opzione per impedire agli utenti di passare all'URL originale nelle pagine [di avviso.](safe-links.md#warning-pages-from-safe-links)</span><span class="sxs-lookup"><span data-stu-id="5ed34-180">**Do not allow users to click through to original URL**: Select this option to block users from clicking through to the original URL in [warning pages](safe-links.md#warning-pages-from-safe-links).</span></span>
   - <span data-ttu-id="5ed34-181">**Non riscrivere gli URL** seguenti: consente di accedere agli URL specificati che altrimenti verrebbero bloccati Cassaforte collegamenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-181">**Do not rewrite the following URLs**: Allows access the specified URLs that would otherwise be blocked by Safe Links.</span></span>

     <span data-ttu-id="5ed34-182">Nella casella digitare l'URL o il valore desiderato e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-182">In the box, type the URL or value that you want, and then click **Add**.</span></span> <span data-ttu-id="5ed34-183">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="5ed34-183">Repeat this step as many times as necessary.</span></span>

     <span data-ttu-id="5ed34-184">Per rimuovere una voce esistente, fare clic su</span><span class="sxs-lookup"><span data-stu-id="5ed34-184">To remove an existing entry, click</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="5ed34-186">accanto alla voce.</span><span class="sxs-lookup"><span data-stu-id="5ed34-186">next to the entry.</span></span>

     <span data-ttu-id="5ed34-187">Per la sintassi delle voci, vedere Sintassi delle voci per [l'elenco "Non riscrivere gli URL seguenti".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="5ed34-187">For entry syntax, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>

   <span data-ttu-id="5ed34-188">Per informazioni dettagliate su queste impostazioni, vedere Cassaforte [impostazioni](safe-links.md#safe-links-settings-for-email-messages) dei collegamenti per i messaggi di posta elettronica e Cassaforte collegamenti per [Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="5ed34-188">For detailed information about these settings, see [Safe Links settings for email messages](safe-links.md#safe-links-settings-for-email-messages) and [Safe Links settings for Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).</span></span>

   <span data-ttu-id="5ed34-189">Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri Standard e Strict, vedere Cassaforte [links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="5ed34-189">For more the recommended values for Standard and Strict policy settings, see [Safe Links policy settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).</span></span>

   <span data-ttu-id="5ed34-190">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-190">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="5ed34-191">Nella pagina **Notifica** visualizzata selezionare uno dei seguenti valori per Come **si desidera inviare una** notifica agli utenti? :</span><span class="sxs-lookup"><span data-stu-id="5ed34-191">On the **Notification** page that appears, select one of the following values for **How would you like to notify your users?**:</span></span>
   - <span data-ttu-id="5ed34-192">**Usare il testo di notifica predefinito**</span><span class="sxs-lookup"><span data-stu-id="5ed34-192">**Use the default notification text**</span></span>
   - <span data-ttu-id="5ed34-193">**Usa testo di notifica personalizzato**: Se si seleziona questo valore (la lunghezza non può superare i 200 caratteri), vengono visualizzate le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-193">**Use custom notification text**: If you select this value (the length cannot exceed 200 characters), the following settings appear:</span></span>
     - <span data-ttu-id="5ed34-194">**Usare Microsoft Translator per la localizzazione automatica**</span><span class="sxs-lookup"><span data-stu-id="5ed34-194">**Use Microsoft Translator for automatic localization**</span></span>
     - <span data-ttu-id="5ed34-195">**Testo di notifica personalizzato:** immettere il testo della notifica personalizzata in questa casella.</span><span class="sxs-lookup"><span data-stu-id="5ed34-195">**Custom notification text**: Enter the custom notification text in this box.</span></span>

   <span data-ttu-id="5ed34-196">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-196">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="5ed34-197">Nella pagina **Controllo** visualizzata controllare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5ed34-197">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="5ed34-198">È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="5ed34-198">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="5ed34-199">Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="5ed34-199">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="5ed34-200">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-200">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="5ed34-201">Nel messaggio di conferma visualizzato fare clic su **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-201">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a><span data-ttu-id="5ed34-202">Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-202">Use the Microsoft 365 Defender portal to view Safe Links policies</span></span>

1. <span data-ttu-id="5ed34-203">Nel portale Microsoft 365 Defender, passare alla sezione **Criteri & criteri** di minaccia Cassaforte \>  \>  \> **collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-203">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="5ed34-204">Nella pagina **Cassaforte collegamenti** vengono visualizzate le proprietà seguenti nell'elenco dei criteri Cassaforte collegamenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-204">On the **Safe Links** page, the following properties are displayed in the list of Safe Links policies:</span></span>
   - <span data-ttu-id="5ed34-205">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5ed34-205">**Name**</span></span>
   - <span data-ttu-id="5ed34-206">**Stato**</span><span class="sxs-lookup"><span data-stu-id="5ed34-206">**Status**</span></span>
   - <span data-ttu-id="5ed34-207">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="5ed34-207">**Priority**</span></span>

3. <span data-ttu-id="5ed34-208">Quando si seleziona un criterio facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="5ed34-208">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a><span data-ttu-id="5ed34-209">Utilizzare il portale Microsoft 365 Defender per modificare i criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-209">Use the Microsoft 365 Defender portal to modify Safe Links policies</span></span>

1. <span data-ttu-id="5ed34-210">Nel portale Microsoft 365 Defender, passare alla sezione **Criteri & criteri** di minaccia Cassaforte \>  \>  \> **collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-210">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="5ed34-211">Nella pagina **Cassaforte collegamenti** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="5ed34-211">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5ed34-212">Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="5ed34-212">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="5ed34-213">Per ulteriori informazioni sulle impostazioni, vedere la sezione precedente Utilizzare il portale di Microsoft 365 Defender [per](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) creare criteri Cassaforte collegamenti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5ed34-213">For more information about the settings, see the previous [Use the Microsoft 365 Defender portal to create Safe Links policies](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) section in this article.</span></span>  

<span data-ttu-id="5ed34-214">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5ed34-214">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-links-policies"></a><span data-ttu-id="5ed34-215">Abilitare o disabilitare i criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-215">Enable or disable Safe Links policies</span></span>

1. <span data-ttu-id="5ed34-216">Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \> **sezione** \> **Cassaforte Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-216">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="5ed34-217">Nella pagina **Cassaforte collegamenti** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="5ed34-217">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5ed34-218">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-218">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="5ed34-219">**Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .</span><span class="sxs-lookup"><span data-stu-id="5ed34-219">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="5ed34-220">**Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-220">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="5ed34-221">Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-221">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="5ed34-222">Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-222">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="5ed34-223">Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-223">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-links-policies"></a><span data-ttu-id="5ed34-224">Impostare la priorità dei criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-224">Set the priority of Safe Links policies</span></span>

<span data-ttu-id="5ed34-225">Per impostazione predefinita, Cassaforte collegamenti hanno una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="5ed34-225">By default, Safe Links are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="5ed34-226">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="5ed34-226">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="5ed34-227">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-227">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="5ed34-228">Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5ed34-228">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="5ed34-229">La modifica di priorità di un criterio è utile solo se si hanno più criteri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-229">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

<span data-ttu-id="5ed34-230">**Nota**:</span><span class="sxs-lookup"><span data-stu-id="5ed34-230">**Note**:</span></span>

- <span data-ttu-id="5ed34-231">Nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio collegamenti Cassaforte solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-231">In the Microsoft 365 Defender portal, you can only change the priority of the Safe Links policy after you create it.</span></span> <span data-ttu-id="5ed34-232">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola dei collegamenti sicuri (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="5ed34-232">In PowerShell, you can override the default priority when you create the safe links rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="5ed34-233">Cassaforte I criteri dei collegamenti vengono elaborati nell'ordine in cui vengono visualizzati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="5ed34-233">Safe Links policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="5ed34-234">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="5ed34-234">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

1. <span data-ttu-id="5ed34-235">Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \> **sezione** \> **Cassaforte Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-235">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="5ed34-236">Nella pagina **Cassaforte collegamenti** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="5ed34-236">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5ed34-237">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato viene visualizzato **Aumenta priorità** o **Riduci priorità** in base al valore di priorità corrente e al numero di criteri personalizzati:</span><span class="sxs-lookup"><span data-stu-id="5ed34-237">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="5ed34-238">Per il criterio con **valore Priority** **0 è** disponibile solo **l'opzione Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="5ed34-238">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="5ed34-239">Il criterio con il valore **Di priorità** più basso (ad esempio, **3)** ha solo l'opzione **Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="5ed34-239">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="5ed34-240">Se si dispone di tre o più criteri, per i  criteri tra i valori di priorità più alta e più bassa sono disponibili le opzioni Aumenta priorità e **Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="5ed34-240">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="5ed34-241">Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-241">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="5ed34-242">Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-242">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a><span data-ttu-id="5ed34-243">Utilizzare il portale Microsoft 365 Defender per rimuovere i criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-243">Use the Microsoft 365 Defender portal to remove Safe Links policies</span></span>

1. <span data-ttu-id="5ed34-244">Nel portale Microsoft 365 Defender, passare a Criteri di **collaborazione** & e-mail & regole Criteri di minaccia \>  \>  \> **sezione** \> **Cassaforte Collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="5ed34-245">Nella pagina **Cassaforte collegamenti** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="5ed34-245">On the **Safe Links** page, select a policy from the list by clicking on the name.</span></span> <span data-ttu-id="5ed34-246">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="5ed34-247">Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a><span data-ttu-id="5ed34-248">Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare i criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-248">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Links policies</span></span>

<span data-ttu-id="5ed34-249">Come descritto in precedenza, un criterio Cassaforte collegamenti sicuri è costituito da un criterio collegamenti sicuri e da una regola per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-249">As previously described, a Safe Links policy consists of a safe links policy and a safe links rule.</span></span>

<span data-ttu-id="5ed34-250">In PowerShell, la differenza tra i criteri dei collegamenti sicuri e le regole dei collegamenti sicuri è evidente.</span><span class="sxs-lookup"><span data-stu-id="5ed34-250">In PowerShell, the difference between safe links policies and safe links rules is apparent.</span></span> <span data-ttu-id="5ed34-251">È possibile gestire i criteri dei collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksPolicy** e gestire le regole dei collegamenti sicuri utilizzando i cmdlet **\* -SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="5ed34-251">You manage safe links policies by using the **\*-SafeLinksPolicy** cmdlets, and you manage safe links rules by using the **\*-SafeLinksRule** cmdlets.</span></span>

- <span data-ttu-id="5ed34-252">In PowerShell, si crea prima il criterio collegamenti sicuri, quindi si crea la regola dei collegamenti sicuri che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="5ed34-252">In PowerShell, you create the safe links policy first, then you create the safe links rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="5ed34-253">In PowerShell, le impostazioni nel criterio collegamenti sicuri e nella regola dei collegamenti sicuri vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="5ed34-253">In PowerShell, you modify the settings in the safe links policy and the safe links rule separately.</span></span>
- <span data-ttu-id="5ed34-254">Quando si rimuove un criterio collegamenti sicuri da PowerShell, la regola dei collegamenti sicuri corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="5ed34-254">When you remove a safe links policy from PowerShell, the corresponding safe links rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-links-policies"></a><span data-ttu-id="5ed34-255">Usare PowerShell per creare criteri Cassaforte collegamenti</span><span class="sxs-lookup"><span data-stu-id="5ed34-255">Use PowerShell to create Safe Links policies</span></span>

<span data-ttu-id="5ed34-256">La creazione di Cassaforte dei collegamenti in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="5ed34-256">Creating a Safe Links policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="5ed34-257">Creare il criterio collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-257">Create the safe links policy.</span></span>
2. <span data-ttu-id="5ed34-258">Creare la regola dei collegamenti sicuri che specifica il criterio dei collegamenti sicuri a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="5ed34-258">Create the safe links rule that specifies the safe links policy that the rule applies to.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="5ed34-259">È possibile creare una nuova regola per i collegamenti sicuri e assegnarle un criterio di collegamenti sicuri non associazione esistente.</span><span class="sxs-lookup"><span data-stu-id="5ed34-259">You can create a new safe links rule and assign an existing, unassociated safe links policy to it.</span></span> <span data-ttu-id="5ed34-260">Una regola dei collegamenti sicuri non può essere associata a più di un criterio collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-260">A safe links rule can't be associated with more than one safe links policy.</span></span>
>
> - <span data-ttu-id="5ed34-261">È possibile configurare le impostazioni seguenti nei nuovi criteri dei collegamenti sicuri in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="5ed34-261">You can configure the following settings on new safe links policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
>   - <span data-ttu-id="5ed34-262">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-SafeLinksRule).**</span><span class="sxs-lookup"><span data-stu-id="5ed34-262">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeLinksRule** cmdlet).</span></span>
>   - <span data-ttu-id="5ed34-263">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="5ed34-263">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeLinksRule** cmdlet).</span></span>
>
> - <span data-ttu-id="5ed34-264">Un nuovo criterio di collegamenti sicuri creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola per i collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-264">A new safe links policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe links rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a><span data-ttu-id="5ed34-265">Passaggio 1: Usare PowerShell per creare un criterio collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-265">Step 1: Use PowerShell to create a safe links policy</span></span>

<span data-ttu-id="5ed34-266">Per creare un criterio collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-266">To create a safe links policy, use this syntax:</span></span>

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - <span data-ttu-id="5ed34-267">Per informazioni dettagliate sulla sintassi delle voci da utilizzare per il parametro _DoNotRewriteUrls,_ vedere [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="5ed34-267">For details about the entry syntax to use for the _DoNotRewriteUrls_ parameter, see [Entry syntax for the "Do not rewrite the following URLs" list](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).</span></span>
>
> - <span data-ttu-id="5ed34-268">Per ulteriori sintassi che è possibile utilizzare per il parametro _DoNotRewriteUrls_ quando si modificano i criteri dei collegamenti sicuri esistenti utilizzando il cmdlet **Set-SafeLinksPolicy,** vedere la sezione Utilizzare [PowerShell](#use-powershell-to-modify-safe-links-policies) per modificare i criteri dei collegamenti sicuri più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5ed34-268">For additional syntax that you can use for the _DoNotRewriteUrls_ parameter when you modify existing safe links policies by using the **Set-SafeLinksPolicy** cmdlet, see the [Use PowerShell to modify safe links policies](#use-powershell-to-modify-safe-links-policies) section later in this article.</span></span>

<span data-ttu-id="5ed34-269">In questo esempio viene creato un criterio collegamenti sicuri denominato Contoso All con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-269">This example creates a safe links policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="5ed34-270">Attivare l'analisi e la riscrittura degli URL nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5ed34-270">Turn on URL scanning and rewriting in email messages.</span></span>
- <span data-ttu-id="5ed34-271">Attivare l'analisi degli URL in Teams (solo anteprima TAP).</span><span class="sxs-lookup"><span data-stu-id="5ed34-271">Turn on URL scanning in Teams (TAP Preview only).</span></span>
- <span data-ttu-id="5ed34-272">Attiva l'analisi in tempo reale degli URL selezionati, inclusi i collegamenti selezionati che puntano ai file.</span><span class="sxs-lookup"><span data-stu-id="5ed34-272">Turn on real-time scanning of clicked URLs, including clicked links that point to files.</span></span>
- <span data-ttu-id="5ed34-273">Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-273">Wait for URL scanning to complete before delivering the message.</span></span>
- <span data-ttu-id="5ed34-274">Attivare l'analisi e la riscrittura degli URL per i messaggi interni.</span><span class="sxs-lookup"><span data-stu-id="5ed34-274">Turn on URL scanning and rewriting for internal messages.</span></span>
- <span data-ttu-id="5ed34-275">Tenere traccia dei clic degli utenti correlati alla protezione dei collegamenti di Cassaforte (non viene utilizzato il parametro _DoNotTrackUserClicks_ e il valore predefinito è $false, che significa che i clic degli utenti vengono monitorati).</span><span class="sxs-lookup"><span data-stu-id="5ed34-275">Track user clicks related to Safe Links protection (we aren't using the _DoNotTrackUserClicks_ parameter, and the default value is $false, which means user clicks are tracked).</span></span>
- <span data-ttu-id="5ed34-276">Non consentire agli utenti di passare all'URL originale.</span><span class="sxs-lookup"><span data-stu-id="5ed34-276">Do not allow users to click through to the original URL.</span></span>

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

<span data-ttu-id="5ed34-277">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="5ed34-277">For detailed syntax and parameter information, see [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a><span data-ttu-id="5ed34-278">Passaggio 2: Utilizzare PowerShell per creare una regola di collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-278">Step 2: Use PowerShell to create a safe links rule</span></span>

<span data-ttu-id="5ed34-279">Per creare una regola di collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-279">To create a safe links rule, use this syntax:</span></span>

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="5ed34-280">In questo esempio viene creata una regola di collegamenti sicuri denominata Contoso All con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-280">This example creates a safe links rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="5ed34-281">La regola è associata al criterio collegamenti sicuri denominato Contoso All.</span><span class="sxs-lookup"><span data-stu-id="5ed34-281">The rule is associated with the safe links policy named Contoso All.</span></span>
- <span data-ttu-id="5ed34-282">La regola si applica a tutti i destinatari del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="5ed34-282">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="5ed34-283">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="5ed34-283">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="5ed34-284">La regola è abilitata (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="5ed34-284">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="5ed34-285">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5ed34-285">For detailed syntax and parameter information, see [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).</span></span>

### <a name="use-powershell-to-view-safe-links-policies"></a><span data-ttu-id="5ed34-286">Usare PowerShell per visualizzare i criteri dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-286">Use PowerShell to view safe links policies</span></span>

<span data-ttu-id="5ed34-287">Per visualizzare i criteri dei collegamenti sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-287">To view existing safe links policies, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="5ed34-288">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri dei collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-288">This example returns a summary list of all safe links policies.</span></span>

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

<span data-ttu-id="5ed34-289">In questo esempio vengono restituite informazioni dettagliate per il criterio collegamenti sicuri denominato Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="5ed34-289">This example returns detailed information for the safe links policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

<span data-ttu-id="5ed34-290">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="5ed34-290">For detailed syntax and parameter information, see [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy).</span></span>

### <a name="use-powershell-to-view-safe-links-rules"></a><span data-ttu-id="5ed34-291">Usare PowerShell per visualizzare le regole dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-291">Use PowerShell to view safe links rules</span></span>

<span data-ttu-id="5ed34-292">Per visualizzare le regole dei collegamenti sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-292">To view existing safe links rules, use the following syntax:</span></span>

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="5ed34-293">In questo esempio viene restituito un elenco riepilogativo di tutte le regole dei collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="5ed34-293">This example returns a summary list of all safe links rules.</span></span>

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

<span data-ttu-id="5ed34-294">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-294">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

<span data-ttu-id="5ed34-295">In questo esempio vengono restituite informazioni dettagliate per la regola dei collegamenti sicuri denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="5ed34-295">This example returns detailed information for the safe links rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

<span data-ttu-id="5ed34-296">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5ed34-296">For detailed syntax and parameter information, see [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule).</span></span>

### <a name="use-powershell-to-modify-safe-links-policies"></a><span data-ttu-id="5ed34-297">Utilizzare PowerShell per modificare i criteri dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-297">Use PowerShell to modify safe links policies</span></span>

<span data-ttu-id="5ed34-298">Non è possibile rinominare un criterio collegamenti sicuri in PowerShell (il cmdlet **Set-SafeLinksPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="5ed34-298">You can't rename a safe links policy in PowerShell (the **Set-SafeLinksPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="5ed34-299">Quando si rinomina un criterio Cassaforte collegamenti sicuri nel portale Microsoft 365 Defender, si rinomina solo la regola dei collegamenti _sicuri._</span><span class="sxs-lookup"><span data-stu-id="5ed34-299">When you rename a Safe Links policy in the Microsoft 365 Defender portal, you're only renaming the safe links _rule_.</span></span>

<span data-ttu-id="5ed34-300">L'unica considerazione aggiuntiva per la modifica dei criteri dei collegamenti sicuri in PowerShell è la sintassi disponibile per il parametro _DoNotRewriteUrls_ (l'elenco "Non riscrivere gli [URL seguenti"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)</span><span class="sxs-lookup"><span data-stu-id="5ed34-300">The only additional consideration for modifying safe links policies in PowerShell is the available syntax for the _DoNotRewriteUrls_ parameter (the ["Do not rewrite the following URLs" list](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):</span></span>

- <span data-ttu-id="5ed34-301">Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la sintassi seguente: `"Entry1","Entry2,..."EntryN"` .</span><span class="sxs-lookup"><span data-stu-id="5ed34-301">To add values that will replace any existing entries, use the following syntax: `"Entry1","Entry2,..."EntryN"`.</span></span>
- <span data-ttu-id="5ed34-302">Per aggiungere o rimuovere valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span><span class="sxs-lookup"><span data-stu-id="5ed34-302">To add or remove values without affecting other existing entries, use the following syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`</span></span>

<span data-ttu-id="5ed34-303">In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio collegamenti sicuri come descritto nella sezione Passaggio [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Utilizzare PowerShell per creare un criterio collegamenti sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5ed34-303">Otherwise, the same settings are available when you create a safe links policy as described in the [Step 1: Use PowerShell to create a safe links policy](#step-1-use-powershell-to-create-a-safe-links-policy) section earlier in this article.</span></span>

<span data-ttu-id="5ed34-304">Per modificare un criterio collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-304">To modify a safe links policy, use this syntax:</span></span>

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="5ed34-305">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)</span><span class="sxs-lookup"><span data-stu-id="5ed34-305">For detailed syntax and parameter information, see [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy).</span></span>

### <a name="use-powershell-to-modify-safe-links-rules"></a><span data-ttu-id="5ed34-306">Utilizzare PowerShell per modificare le regole dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-306">Use PowerShell to modify safe links rules</span></span>

<span data-ttu-id="5ed34-307">L'unica impostazione non disponibile quando si modifica una regola di collegamenti sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5ed34-307">The only setting that's not available when you modify a safe links rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="5ed34-308">Per abilitare o disabilitare le regole dei collegamenti sicuri esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="5ed34-308">To enable or disable existing safe links rules, see the next section.</span></span>

<span data-ttu-id="5ed34-309">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Utilizzare PowerShell per creare una regola di collegamenti sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5ed34-309">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe links rule](#step-2-use-powershell-to-create-a-safe-links-rule) section earlier in this article.</span></span>

<span data-ttu-id="5ed34-310">Per modificare una regola dei collegamenti sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-310">To modify a safe links rule, use this syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="5ed34-311">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="5ed34-311">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a><span data-ttu-id="5ed34-312">Abilitazione o disabilitazione delle regole dei collegamenti sicuri tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ed34-312">Use PowerShell to enable or disable safe links rules</span></span>

<span data-ttu-id="5ed34-313">L'abilitazione o la disabilitazione di una regola di collegamenti sicuri in PowerShell abilita o disabilita l'intero criterio collegamenti Cassaforte (la regola dei collegamenti sicuri e il criterio collegamenti sicuri assegnati).</span><span class="sxs-lookup"><span data-stu-id="5ed34-313">Enabling or disabling a safe links rule in PowerShell enables or disables the whole Safe Links policy (the safe links rule and the assigned safe links policy).</span></span>

<span data-ttu-id="5ed34-314">Per abilitare o disabilitare una regola di collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-314">To enable or disable a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

<span data-ttu-id="5ed34-315">In questo esempio viene disabilitata la regola dei collegamenti sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="5ed34-315">This example disables the safe links rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="5ed34-316">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="5ed34-316">This example enables same rule.</span></span>

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="5ed34-317">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) [e Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="5ed34-317">For detailed syntax and parameter information, see [Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule) and [Disable-SafeLinksRule](/powershell/module/exchange/disable-safelinksrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a><span data-ttu-id="5ed34-318">Utilizzare PowerShell per impostare la priorità delle regole dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-318">Use PowerShell to set the priority of safe links rules</span></span>

<span data-ttu-id="5ed34-p131">Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="5ed34-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="5ed34-324">Per impostare la priorità di una regola di collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-324">To set the priority of a safe links rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="5ed34-p132">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="5ed34-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> <span data-ttu-id="5ed34-327">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeLinksRule.**</span><span class="sxs-lookup"><span data-stu-id="5ed34-327">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeLinksRule** cmdlet instead.</span></span>

<span data-ttu-id="5ed34-328">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)</span><span class="sxs-lookup"><span data-stu-id="5ed34-328">For detailed syntax and parameter information, see [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule).</span></span>

### <a name="use-powershell-to-remove-safe-links-policies"></a><span data-ttu-id="5ed34-329">Usare PowerShell per rimuovere i criteri dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-329">Use PowerShell to remove safe links policies</span></span>

<span data-ttu-id="5ed34-330">Quando si utilizza PowerShell per rimuovere un criterio collegamenti sicuri, la regola dei collegamenti sicuri corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="5ed34-330">When you use PowerShell to remove a safe links policy, the corresponding safe links rule isn't removed.</span></span>

<span data-ttu-id="5ed34-331">Per rimuovere un criterio collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-331">To remove a safe links policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="5ed34-332">In questo esempio viene rimosso il criterio collegamenti sicuri denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="5ed34-332">This example removes the safe links policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

<span data-ttu-id="5ed34-333">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span><span class="sxs-lookup"><span data-stu-id="5ed34-333">For detailed syntax and parameter information, see [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).</span></span>

### <a name="use-powershell-to-remove-safe-links-rules"></a><span data-ttu-id="5ed34-334">Usare PowerShell per rimuovere le regole dei collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="5ed34-334">Use PowerShell to remove safe links rules</span></span>

<span data-ttu-id="5ed34-335">Quando si utilizza PowerShell per rimuovere una regola dei collegamenti sicuri, il criterio collegamenti sicuri corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="5ed34-335">When you use PowerShell to remove a safe links rule, the corresponding safe links policy isn't removed.</span></span>

<span data-ttu-id="5ed34-336">Per rimuovere una regola di collegamenti sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5ed34-336">To remove a safe links rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

<span data-ttu-id="5ed34-337">In questo esempio viene rimossa la regola dei collegamenti sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="5ed34-337">This example removes the safe links rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

<span data-ttu-id="5ed34-338">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span><span class="sxs-lookup"><span data-stu-id="5ed34-338">For detailed syntax and parameter information, see [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).</span></span>

<span data-ttu-id="5ed34-339">Per verificare che Cassaforte link esempa l'analisi dei messaggi, controlla microsoft Defender disponibile per Office 365 report.</span><span class="sxs-lookup"><span data-stu-id="5ed34-339">To verify that Safe Links is scanning messages, check the available Microsoft Defender for Office 365 reports.</span></span> <span data-ttu-id="5ed34-340">Per altre informazioni, vedi [Visualizzare i report per Defender per Office 365](view-reports-for-mdo.md) e Usare Esplora risorse nel portale [Microsoft 365 Defender.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="5ed34-340">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5ed34-341">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="5ed34-341">How do you know these procedures worked?</span></span>

<span data-ttu-id="5ed34-342">Per verificare di aver creato, modificato o rimosso correttamente i criteri Cassaforte collegamenti, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5ed34-342">To verify that you've successfully created, modified, or removed Safe Links policies, do any of the following steps:</span></span>

- <span data-ttu-id="5ed34-343">Nel portale Microsoft 365 Defender, passare **a Criteri & criteri di** minaccia \>  \> **Cassaforte collegamenti**.</span><span class="sxs-lookup"><span data-stu-id="5ed34-343">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Safe Links**.</span></span> <span data-ttu-id="5ed34-344">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="5ed34-344">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="5ed34-345">Per visualizzare altri dettagli, selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="5ed34-345">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="5ed34-346">In Exchange Online PowerShell o Exchange Online Protection PowerShell, sostituire con il nome del criterio o della regola, eseguire il comando seguente e \<Name\> verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="5ed34-346">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
