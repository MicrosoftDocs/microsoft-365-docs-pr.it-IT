---
title: Configurare il filtro posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a visualizzare, creare, modificare ed eliminare i criteri di posta indesiderata in uscita in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ceaf0d276aff4504dd34aa3229c28c9cb042742d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065354"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="3c1df-103">Configurare il filtro posta indesiderata in uscita in EOP</span><span class="sxs-lookup"><span data-stu-id="3c1df-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3c1df-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="3c1df-104">**Applies to**</span></span>
- [<span data-ttu-id="3c1df-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3c1df-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3c1df-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="3c1df-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3c1df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c1df-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3c1df-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi di posta elettronica in uscita inviati tramite EOP vengono controllati automaticamente per verificare la presenza di posta indesiderata e attività di invio insolite.</span><span class="sxs-lookup"><span data-stu-id="3c1df-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="3c1df-109">La posta indesiderata in uscita da un utente dell'organizzazione indica in genere un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="3c1df-109">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="3c1df-110">I messaggi in uscita sospetti vengono contrassegnati come posta indesiderata (indipendentemente dal livello di probabilità di posta indesiderata o dal livello di probabilità di posta indesiderata) e vengono instradati attraverso il [pool](high-risk-delivery-pool-for-outbound-messages.md) di recapito ad alto rischio per proteggere la reputazione del servizio (ovvero, mantenere i server di posta elettronica di origine di Microsoft 365 fuori dagli elenchi di indirizzi IP bloccati).</span><span class="sxs-lookup"><span data-stu-id="3c1df-110">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="3c1df-111">Agli amministratori viene automaticamente notificata l'attività di posta elettronica in uscita sospetta e gli utenti bloccati tramite [criteri di avviso.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3c1df-111">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="3c1df-112">EOP utilizza i criteri di posta indesiderata in uscita come parte della difesa generale dell'organizzazione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3c1df-112">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="3c1df-113">Per altre informazioni, vedere [Protezione dalla posta indesiderata](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3c1df-113">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="3c1df-114">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-114">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="3c1df-115">Per una maggiore granularità, è inoltre possibile creare criteri di posta indesiderata in uscita personalizzati che si applicano a utenti, gruppi o domini specifici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c1df-115">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3c1df-116">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="3c1df-116">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3c1df-117">È possibile configurare i criteri di posta indesiderata in uscita nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="3c1df-117">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="3c1df-118">Gli elementi di base di un criterio di posta indesiderata in uscita in EOP sono:</span><span class="sxs-lookup"><span data-stu-id="3c1df-118">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="3c1df-119">**Il criterio di filtro della posta** indesiderata in uscita : Specifica le azioni per i verdetti del filtro posta indesiderata in uscita e le opzioni di notifica.</span><span class="sxs-lookup"><span data-stu-id="3c1df-119">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="3c1df-120">**Regola filtro posta indesiderata in uscita**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-120">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="3c1df-121">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di protezione dalla posta indesiderata in uscita nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="3c1df-121">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="3c1df-122">Quando si crea un criterio, si sta creando contemporaneamente una regola di filtro della posta indesiderata in uscita e il criterio di filtro della posta indesiderata in uscita associato utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="3c1df-122">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="3c1df-123">Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-123">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="3c1df-124">Tutte le altre impostazioni modificano il criterio di filtro della posta indesiderata in uscita associato.</span><span class="sxs-lookup"><span data-stu-id="3c1df-124">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="3c1df-125">Quando si rimuove un criterio, la regola di filtro della posta indesiderata in uscita e il criterio di filtro della posta indesiderata in uscita associato vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="3c1df-125">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="3c1df-126">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="3c1df-126">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="3c1df-127">Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online o [PowerShell EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) autonomo per configurare i criteri di posta indesiderata in uscita più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3c1df-127">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this article.</span></span>

<span data-ttu-id="3c1df-128">Ogni organizzazione dispone di un criterio di protezione da posta indesiderata in uscita predefinito denominato Default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="3c1df-128">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="3c1df-129">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola di filtro della posta indesiderata in uscita (filtri destinatari).</span><span class="sxs-lookup"><span data-stu-id="3c1df-129">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="3c1df-130">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="3c1df-130">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3c1df-131">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta rispetto al criterio denominato Predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-131">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="3c1df-132">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="3c1df-132">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3c1df-133">Per aumentare l'efficacia del filtro posta indesiderata in uscita, è possibile creare criteri di protezione da posta indesiderata in uscita personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3c1df-133">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3c1df-134">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3c1df-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3c1df-135">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3c1df-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3c1df-136">Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="3c1df-136">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="3c1df-137">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3c1df-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3c1df-138">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3c1df-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3c1df-139">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="3c1df-139">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3c1df-140">Per aggiungere, modificare ed eliminare i criteri di posta indesiderata in uscita, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-140">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3c1df-141">Per l'accesso in sola lettura ai criteri di posta indesiderata in uscita, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3c1df-141">For read-only access to outbound spam policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3c1df-142">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="3c1df-142">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="3c1df-143">**Note**:</span><span class="sxs-lookup"><span data-stu-id="3c1df-143">**Notes**:</span></span>

  - <span data-ttu-id="3c1df-144">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3c1df-144">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3c1df-145">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3c1df-145">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="3c1df-146">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3c1df-146">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="3c1df-147">Per le impostazioni consigliate per i criteri di posta indesiderata in uscita, vedere [EOP outbound spam filter settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="3c1df-147">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="3c1df-148">I [](../../compliance/alert-policies.md) criteri di avviso predefiniti denominati Limite di invio  della posta elettronica **superato,** Modelli di invio di posta elettronica sospetti rilevati e Utente con restrizioni per l'invio di messaggi di posta elettronica già inviano notifiche di posta elettronica ai membri del gruppo **TenantAdmins** (**Amministratori** globali ) sull'attività insolita di posta elettronica in uscita e sugli utenti bloccati a causa della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-148">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="3c1df-149">Per ulteriori informazioni, vedere [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="3c1df-149">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="3c1df-150">È consigliabile utilizzare questi criteri di avviso anziché le opzioni di notifica nei criteri di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-150">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="3c1df-151">Usare il Centro sicurezza & conformità per creare criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-151">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="3c1df-152">La creazione di un criterio di posta indesiderata in uscita personalizzato nel Centro sicurezza & conformità crea contemporaneamente la regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata associato utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="3c1df-152">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="3c1df-153">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3c1df-154">Nella pagina **Impostazioni protezione da posta indesiderata** fare clic su Crea un criterio in **uscita.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-154">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="3c1df-155">Nel riquadro **a comparsa Del criterio** filtro posta indesiderata in uscita che si apre, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c1df-155">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3c1df-156">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="3c1df-157">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-157">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="3c1df-158">(Facoltativo) Espandere la **sezione Notifiche** per configurare altri utenti che devono ricevere copie e notifiche di messaggi di posta elettronica in uscita sospetti:</span><span class="sxs-lookup"><span data-stu-id="3c1df-158">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="3c1df-159">**Invia una copia dei messaggi di posta** elettronica in uscita sospetti a persone specifiche: questa impostazione aggiunge gli utenti specificati come destinatari Ccn ai messaggi in uscita sospetti.</span><span class="sxs-lookup"><span data-stu-id="3c1df-159">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="3c1df-160">Questa impostazione funziona solo nel criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-160">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="3c1df-161">Non funziona nei criteri di posta indesiderata in uscita personalizzati creati dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3c1df-161">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="3c1df-162">Per abilitare questa impostazione:</span><span class="sxs-lookup"><span data-stu-id="3c1df-162">To enable this setting:</span></span>

     1. <span data-ttu-id="3c1df-163">Selezionare la casella di controllo per abilitare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="3c1df-163">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="3c1df-164">Fare **clic su Aggiungi utenti.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-164">Click **Add people**.</span></span> <span data-ttu-id="3c1df-165">Nel riquadro **a comparsa Aggiungi o rimuovi** destinatari visualizzato:</span><span class="sxs-lookup"><span data-stu-id="3c1df-165">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="3c1df-166">Immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="3c1df-166">Enter the sender's email address.</span></span> <span data-ttu-id="3c1df-167">È possibile specificare più indirizzi di posta elettronica separati da punto e virgola (;) o un destinatario per riga.</span><span class="sxs-lookup"><span data-stu-id="3c1df-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="3c1df-168">Scegliere</span><span class="sxs-lookup"><span data-stu-id="3c1df-168">Click</span></span> ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="3c1df-170">per aggiungere i destinatari.</span><span class="sxs-lookup"><span data-stu-id="3c1df-170">to add the recipients.</span></span>

        <span data-ttu-id="3c1df-171">Ripetere questi passaggi tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="3c1df-171">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="3c1df-172">I destinatari aggiunti vengono visualizzati nella **sezione Elenco destinatari** nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="3c1df-172">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="3c1df-173">Per eliminare un destinatario, fare clic ![ sul pulsante ](../../media/scc-remove-icon.png) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="3c1df-173">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="3c1df-174">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-174">When you're finished, click **Save**.</span></span>

        <span data-ttu-id="3c1df-175">Per disabilitare questa impostazione, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="3c1df-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="3c1df-176">**Notificare a persone specifiche se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita:**</span><span class="sxs-lookup"><span data-stu-id="3c1df-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="3c1df-177">Questa impostazione è in fase di rimozione dai criteri di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-177">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="3c1df-178">Il criterio di  avviso predefinito denominato Utente a cui è stato impedito di inviare messaggi di posta elettronica invia già  notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** ( [](../../compliance/alert-policies.md) **Amministratori** globali ) quando gli utenti vengono bloccati a causa del superamento dei limiti nella sezione Limiti destinatari.</span><span class="sxs-lookup"><span data-stu-id="3c1df-178">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="3c1df-179">**È consigliabile utilizzare il criterio** di avviso anziché questa impostazione nel criterio di posta indesiderata in uscita per inviare una notifica agli amministratori e ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="3c1df-179">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users**.</span></span> <span data-ttu-id="3c1df-180">Per istruzioni, vedere [Verificare le impostazioni degli avvisi per gli utenti con restrizioni.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)</span><span class="sxs-lookup"><span data-stu-id="3c1df-180">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="3c1df-181">(Facoltativo) Espandere la **sezione Limiti destinatari** per configurare i limiti e le azioni per i messaggi di posta elettronica in uscita sospetti:</span><span class="sxs-lookup"><span data-stu-id="3c1df-181">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="3c1df-182">Queste impostazioni sono applicabili solo alle cassette postali basate su cloud.</span><span class="sxs-lookup"><span data-stu-id="3c1df-182">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="3c1df-183">**Numero massimo di destinatari per utente**</span><span class="sxs-lookup"><span data-stu-id="3c1df-183">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="3c1df-184">Un valore valido è compreso tra 0 e 10000.</span><span class="sxs-lookup"><span data-stu-id="3c1df-184">A valid value is 0 to 10000.</span></span> <span data-ttu-id="3c1df-185">Il valore predefinito è 0, ovvero vengono utilizzati i valori predefiniti del servizio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-185">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="3c1df-186">Per ulteriori informazioni, vedere [Limiti di invio.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)</span><span class="sxs-lookup"><span data-stu-id="3c1df-186">For more information, see [Sending limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="3c1df-187">**Limite orario esterno**: numero massimo di destinatari esterni all'ora.</span><span class="sxs-lookup"><span data-stu-id="3c1df-187">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="3c1df-188">**Limite orario interno**: numero massimo di destinatari interni all'ora.</span><span class="sxs-lookup"><span data-stu-id="3c1df-188">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="3c1df-189">**Limite giornaliero**: numero totale massimo di destinatari al giorno.</span><span class="sxs-lookup"><span data-stu-id="3c1df-189">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="3c1df-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span><span class="sxs-lookup"><span data-stu-id="3c1df-190">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="3c1df-191">Per tutte le azioni,  i destinatari specificati nel criterio Utente con restrizioni per l'invio di avvisi di posta elettronica (e nell'impostazione Ora ridondante Notifica a persone specifiche se un mittente è bloccato **a** causa dell'invio di posta indesiderata in uscita nel criterio di posta indesiderata in uscita ricevono le notifiche di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3c1df-191">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="3c1df-192">**Limitare l'invio di posta elettronica all'utente fino al giorno seguente:** questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-192">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="3c1df-193">Le notifiche di posta elettronica vengono inviate e l'utente non sarà in grado di inviare altri messaggi fino al giorno successivo, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3c1df-193">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="3c1df-194">L'amministratore non può ignorare questo blocco.</span><span class="sxs-lookup"><span data-stu-id="3c1df-194">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="3c1df-195">L'avviso attività denominato **Utente con restrizioni per** l'invio di messaggi di posta elettronica notifica agli amministratori (tramite posta elettronica e nella pagina **Visualizza** avvisi).</span><span class="sxs-lookup"><span data-stu-id="3c1df-195">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="3c1df-196">Vengono inoltre notificati tutti i destinatari specificati nell'impostazione Notifica a persone specifiche se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita nel criterio. </span><span class="sxs-lookup"><span data-stu-id="3c1df-196">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="3c1df-197">L'utente non sarà in grado di inviare altri messaggi fino al giorno successivo, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="3c1df-197">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="3c1df-198">L'amministratore non può ignorare questo blocco.</span><span class="sxs-lookup"><span data-stu-id="3c1df-198">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="3c1df-199">Limitare l'invio di posta elettronica all'utente: le notifiche di posta elettronica vengono inviate, l'utente viene aggiunto al portale [utenti con  **restrizioni] <https://sip.protection.office.com/restrictedusers>** nel Centro sicurezza & conformità e l'utente non può inviare messaggi di posta elettronica finché non viene rimosso dal portale utenti con restrizioni da un amministratore.  Dopo che un amministratore ha rimosso l'utente dall'elenco, l'utente non sarà più limitato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="3c1df-199">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="3c1df-200">Per istruzioni, vedere Rimozione di un utente dal portale utenti con [restrizioni dopo l'invio di posta indesiderata.](removing-user-from-restricted-users-portal-after-spam.md)</span><span class="sxs-lookup"><span data-stu-id="3c1df-200">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="3c1df-201">**Nessuna azione, solo avviso:** vengono inviate notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3c1df-201">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="3c1df-202">(Facoltativo) Espandere **la sezione Inoltro automatico** per controllare l'inoltro automatico della posta elettronica da parte degli utenti a mittenti esterni.</span><span class="sxs-lookup"><span data-stu-id="3c1df-202">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="3c1df-203">Per ulteriori informazioni, vedere [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span><span class="sxs-lookup"><span data-stu-id="3c1df-203">For more information, see [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="3c1df-204">Prima di settembre 2020, queste impostazioni sono disponibili ma non applicate.</span><span class="sxs-lookup"><span data-stu-id="3c1df-204">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="3c1df-205">Queste impostazioni si applicano solo alle cassette postali basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="3c1df-205">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="3c1df-206">Quando l'inoltro automatico è disabilitato, il destinatario riceverà un rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito) se i mittenti esterni inviano messaggi di posta elettronica a una cassetta postale con inoltro sul posto.</span><span class="sxs-lookup"><span data-stu-id="3c1df-206">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="3c1df-207">Se il messaggio viene inviato  da un mittente interno e il metodo di inoltro è l'inoltro delle cassette postali [(noto](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) anche come _inoltro SMTP),_ il mittente interno otterrà il rapporto di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-207">If the message is sent by an internal sender **and** the forwarding method is [mailbox forwarding](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (also known as _SMTP forwarding_), the internal sender will get the NDR.</span></span> <span data-ttu-id="3c1df-208">Il mittente interno non ottiene un rapporto di mancato recapito se l'inoltro è avvenuto a causa di una regola di Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3c1df-208">The internal sender does not get an NDR if the forwarding occurred due to an inbox rule.</span></span>

   <span data-ttu-id="3c1df-209">I valori disponibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c1df-209">The available values are:</span></span>

   - <span data-ttu-id="3c1df-210">**Automatico - Controllato dal sistema:** consente al filtro posta indesiderata in uscita di controllare l'inoltro automatico della posta elettronica esterna.</span><span class="sxs-lookup"><span data-stu-id="3c1df-210">**Automatic - System-controlled**: Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="3c1df-211">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-211">This is the default value.</span></span>
   - <span data-ttu-id="3c1df-212">**On**: L'inoltro automatico della posta elettronica esterna non è disabilitato dal criterio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-212">**On**: Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="3c1df-213">**Disattivato**: l'inoltro automatico della posta elettronica esterna è disabilitato dal criterio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-213">**Off**: All automatic external email forwarding is disabled by the policy.</span></span>

7. <span data-ttu-id="3c1df-214">(Obbligatorio) Espandere la **sezione Applicato a** per identificare i mittenti interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-214">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="3c1df-215">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="3c1df-215">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="3c1df-216">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<sender1\>_ o _\<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="3c1df-216">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="3c1df-217">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<sender1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="3c1df-217">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="3c1df-218">È più facile fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le condizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="3c1df-218">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="3c1df-219">È possibile fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png) per rimuovere le condizioni che non si vogliono configurare.</span><span class="sxs-lookup"><span data-stu-id="3c1df-219">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="3c1df-220">**Il dominio del mittente** è : Specifica i mittenti in uno o più domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c1df-220">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="3c1df-221">Fare clic sulla casella **Aggiungi un tag** per visualizzare e selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-221">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="3c1df-222">Fare nuovamente clic sulla casella **Aggiungi un tag** per selezionare altri domini se è disponibile più di un dominio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-222">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="3c1df-223">**Sender è**: Specifica uno o più utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c1df-223">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="3c1df-224">Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="3c1df-224">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="3c1df-225">Fare di nuovo clic **sulla casella Aggiungi un tag** per selezionare altri mittenti.</span><span class="sxs-lookup"><span data-stu-id="3c1df-225">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="3c1df-226">**Sender è un membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c1df-226">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="3c1df-227">Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="3c1df-227">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="3c1df-228">Fare di nuovo clic **sulla casella Aggiungi un tag** per selezionare altri mittenti.</span><span class="sxs-lookup"><span data-stu-id="3c1df-228">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="3c1df-229">**Tranne quando**: per aggiungere eccezioni alla regola, fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le eccezioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="3c1df-229">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="3c1df-230">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="3c1df-230">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="3c1df-231">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-231">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="3c1df-232">Usare il Centro sicurezza & conformità per visualizzare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-232">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="3c1df-233">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3c1df-234">Nella pagina **Impostazioni protezione da posta indesiderata** fare clic su Espandi icona per espandere un criterio di posta indesiderata in ![ ](../../media/scc-expand-icon.png) uscita:</span><span class="sxs-lookup"><span data-stu-id="3c1df-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="3c1df-235">Il criterio predefinito denominato **Criterio filtro posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-235">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="3c1df-236">Un criterio personalizzato creato in cui il valore nella colonna **Tipo** è Criterio di posta indesiderata **in uscita personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="3c1df-237">Le impostazioni dei criteri vengono visualizzate nei dettagli dei criteri espansi visualizzati oppure è possibile fare clic **su Modifica criterio.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-237">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="3c1df-238">Utilizzare il Centro sicurezza & conformità per modificare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-238">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="3c1df-239">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3c1df-240">Nella pagina **Impostazioni protezione da posta indesiderata** fare clic su Espandi icona per espandere un criterio di posta indesiderata in ![ ](../../media/scc-expand-icon.png) uscita:</span><span class="sxs-lookup"><span data-stu-id="3c1df-240">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="3c1df-241">Il criterio predefinito denominato **Criterio filtro posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-241">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="3c1df-242">Un criterio personalizzato creato in cui il valore nella colonna **Tipo** è Criterio di posta indesiderata **in uscita personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-242">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="3c1df-243">Fare clic su **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-243">Click **Edit policy**.</span></span>

<span data-ttu-id="3c1df-244">Per i criteri di posta indesiderata in uscita personalizzati, le impostazioni disponibili nel riquadro a comparsa visualizzato sono identiche a quelle descritte nella sezione Utilizzare il Centro sicurezza [& conformità](#use-the-security--compliance-center-to-create-outbound-spam-policies) per creare criteri di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-244">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="3c1df-245">Per il criterio di protezione da posta  indesiderata in uscita predefinito denominato Criterio filtro posta indesiderata in **uscita,** la sezione Applicato a non è disponibile (il criterio si applica a tutti gli utenti) e non è possibile rinominare il criterio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-245">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="3c1df-246">Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche di quarantena per gli utenti finali. Vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3c1df-246">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="3c1df-247">Abilitare o disabilitare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-247">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="3c1df-248">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-248">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3c1df-249">Nella pagina **Impostazioni protezione da** posta indesiderata fare clic su Espandi icona per espandere un criterio personalizzato creato (il valore nella colonna Tipo è Criterio di protezione da posta indesiderata in uscita ![ ](../../media/scc-expand-icon.png) **personalizzato).** </span><span class="sxs-lookup"><span data-stu-id="3c1df-249">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="3c1df-250">Nei dettagli dei criteri espansi visualizzati, notare il valore nella colonna **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-250">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="3c1df-251">Spostare l'interruttore a sinistra per disabilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="3c1df-251">Move the toggle to the left to disable the policy:</span></span> ![Disattiva](../../media/scc-toggle-off.png)

   <span data-ttu-id="3c1df-253">Spostare l'interruttore a destra per abilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="3c1df-253">Move the toggle to the right to enable the policy:</span></span> ![Attiva](../../media/scc-toggle-on.png)

<span data-ttu-id="3c1df-255">Non è possibile disabilitare il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-255">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="3c1df-256">Impostare la priorità dei criteri di posta indesiderata in uscita personalizzati</span><span class="sxs-lookup"><span data-stu-id="3c1df-256">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="3c1df-257">Per impostazione predefinita, ai criteri di posta indesiderata in uscita viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="3c1df-257">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="3c1df-258">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="3c1df-258">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3c1df-259">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="3c1df-259">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="3c1df-260">I criteri di posta indesiderata in uscita personalizzati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="3c1df-260">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3c1df-261">Il criterio di protezione da posta indesiderata in uscita predefinito denominato **Criterio** filtro posta indesiderata in uscita ha il valore di priorità **Lowest** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="3c1df-261">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="3c1df-262">Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="3c1df-262">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="3c1df-263">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-263">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3c1df-264">Nella pagina **Impostazioni protezione da posta indesiderata** individuare i criteri in cui il valore nella colonna **Tipo** è Criterio di protezione da posta indesiderata in **uscita personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-264">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="3c1df-265">Notare i valori nella colonna **Priorità**:</span><span class="sxs-lookup"><span data-stu-id="3c1df-265">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="3c1df-266">Il criterio di posta indesiderata in uscita personalizzato con la priorità più alta ha il ![ valore Icona freccia giù ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-266">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="3c1df-267">Il criterio di posta indesiderata in uscita personalizzato con la priorità più bassa ha il valore Icona ![ freccia ](../../media/ITPro-EAC-UpArrowIcon.png) **su n** (ad esempio, Icona freccia su ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **3).**</span><span class="sxs-lookup"><span data-stu-id="3c1df-267">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="3c1df-268">Se si dispone di tre o più criteri di posta indesiderata in uscita personalizzati, i criteri tra la priorità più alta e la priorità più bassa hanno valori Icona freccia su Icona freccia giù ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (ad esempio, Icona freccia su Icona freccia giù ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="3c1df-268">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="3c1df-269">Fare clic su</span><span class="sxs-lookup"><span data-stu-id="3c1df-269">Click</span></span> ![Icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="3c1df-271">oppure</span><span class="sxs-lookup"><span data-stu-id="3c1df-271">or</span></span> ![Icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="3c1df-273">per spostare il criterio di posta indesiderata in uscita personalizzato verso l'alto o verso il basso nell'elenco di priorità.</span><span class="sxs-lookup"><span data-stu-id="3c1df-273">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="3c1df-274">Usare il Centro sicurezza & conformità per rimuovere i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-274">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="3c1df-275">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-275">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="3c1df-276">Nella pagina **Impostazioni protezione da** posta indesiderata fare clic su Espandi icona per espandere il criterio personalizzato che si desidera eliminare (la colonna Tipo è Criterio di protezione da posta indesiderata in uscita ![ ](../../media/scc-expand-icon.png) **personalizzato).** </span><span class="sxs-lookup"><span data-stu-id="3c1df-276">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="3c1df-277">Nei dettagli sui criteri espansi visualizzati, fare clic su **Elimina criterio**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-277">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="3c1df-278">Fare clic su **Sì** quando viene visualizzata la finestra di dialogo di avviso.</span><span class="sxs-lookup"><span data-stu-id="3c1df-278">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="3c1df-279">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c1df-279">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="3c1df-280">Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per configurare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-280">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="3c1df-281">Come descritto in precedenza, un criterio di posta indesiderata in uscita è costituito da un criterio di filtro della posta indesiderata in uscita e da una regola di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-281">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="3c1df-282">In PowerShell di Exchange Online o PowerShell EOP autonomo, la differenza tra i criteri di filtro della posta indesiderata in uscita e le regole di filtro della posta indesiderata in uscita è evidente.</span><span class="sxs-lookup"><span data-stu-id="3c1df-282">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="3c1df-283">È possibile gestire i criteri di filtro della posta indesiderata in uscita utilizzando i cmdlet **\* -HostedOutboundSpamFilterPolicy** e gestire le regole di filtro della posta indesiderata in uscita utilizzando i cmdlet **\* -HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-283">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="3c1df-284">In PowerShell, si crea prima il criterio di filtro della posta indesiderata in uscita, quindi si crea la regola di filtro della posta indesiderata in uscita che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="3c1df-284">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="3c1df-285">In PowerShell le impostazioni vengono modificate separatamente nei criteri di filtro della posta indesiderata in uscita e nella regola di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-285">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="3c1df-286">Quando si rimuove un criterio di filtro della posta indesiderata in uscita da PowerShell, la regola di filtro della posta indesiderata in uscita corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="3c1df-286">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="3c1df-287">Utilizzare PowerShell per creare criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-287">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="3c1df-288">La creazione di un criterio di posta indesiderata in uscita in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="3c1df-288">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3c1df-289">Creare il criterio di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-289">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="3c1df-290">Creare la regola di filtro della posta indesiderata in uscita che specifica il criterio di filtro della posta indesiderata in uscita a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="3c1df-290">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="3c1df-291">**Note**:</span><span class="sxs-lookup"><span data-stu-id="3c1df-291">**Notes**:</span></span>

- <span data-ttu-id="3c1df-292">È possibile creare una nuova regola di filtro della posta indesiderata in uscita e assegnarle un criterio di filtro della posta indesiderata in uscita esistente e non associazione.</span><span class="sxs-lookup"><span data-stu-id="3c1df-292">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="3c1df-293">Una regola di filtro della posta indesiderata in uscita non può essere associata a più di un criterio di filtro della posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="3c1df-293">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="3c1df-294">È possibile configurare le impostazioni seguenti nei nuovi criteri di filtro della posta indesiderata in uscita in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="3c1df-294">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="3c1df-295">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-HostedOutboundSpamFilterRule).**</span><span class="sxs-lookup"><span data-stu-id="3c1df-295">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="3c1df-296">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-296">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="3c1df-297">Un nuovo criterio di filtro della posta indesiderata in uscita creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola di filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3c1df-297">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="3c1df-298">Passaggio 1: Utilizzare PowerShell per creare un criterio di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-298">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="3c1df-299">Per creare un criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-299">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="3c1df-300">In questo esempio viene creato un nuovo criterio di filtro della posta indesiderata in uscita denominato Contoso Executives con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c1df-300">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="3c1df-301">I limiti di frequenza dei destinatari sono limitati ai valori più piccoli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3c1df-301">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="3c1df-302">Per ulteriori informazioni, vedere [Limiti di invio tra le opzioni di Microsoft 365.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="3c1df-302">For more information, see [Sending limits across Microsoft 365 options](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="3c1df-303">Dopo aver raggiunto uno dei limiti, all'utente viene impedito di inviare messaggi.</span><span class="sxs-lookup"><span data-stu-id="3c1df-303">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="3c1df-304">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="3c1df-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="3c1df-305">Passaggio 2: Utilizzare PowerShell per creare una regola di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-305">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="3c1df-306">Per creare una regola di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-306">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3c1df-307">In questo esempio viene creata una nuova regola di filtro della posta indesiderata in uscita denominata Contoso Executives con queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="3c1df-307">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="3c1df-308">Il criterio di filtro della posta indesiderata in uscita denominato Contoso Executives è associato alla regola.</span><span class="sxs-lookup"><span data-stu-id="3c1df-308">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>
- <span data-ttu-id="3c1df-309">La regola viene applicata ai membri del gruppo Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="3c1df-309">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

<span data-ttu-id="3c1df-310">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3c1df-310">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="3c1df-311">Usare PowerShell per visualizzare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-311">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="3c1df-312">Per restituire un elenco riepilogativo di tutti i criteri di filtro della posta indesiderata in uscita, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="3c1df-312">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="3c1df-313">Per restituire informazioni dettagliate su uno specifico criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-313">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="3c1df-314">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio di filtro della posta indesiderata in uscita denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="3c1df-314">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="3c1df-315">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="3c1df-315">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="3c1df-316">Utilizzare PowerShell per visualizzare le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-316">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="3c1df-317">Per visualizzare le regole di filtro della posta indesiderata in uscita esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-317">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="3c1df-318">Per restituire un elenco riepilogativo di tutte le regole di filtro della posta indesiderata in uscita, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="3c1df-318">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="3c1df-319">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c1df-319">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="3c1df-320">Per restituire informazioni dettagliate su una specifica regola di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-320">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="3c1df-321">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola di filtro della posta indesiderata in uscita denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="3c1df-321">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="3c1df-322">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3c1df-322">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="3c1df-323">Utilizzare PowerShell per modificare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-323">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="3c1df-324">Le stesse impostazioni sono disponibili quando si modifica un criterio di filtro antimalware in PowerShell come quando si crea il criterio come descritto nella sezione [Passaggio 1:](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) utilizzare PowerShell per creare un criterio di filtro della posta indesiderata in uscita in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3c1df-324">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="3c1df-325">Non è possibile rinominare un criterio di filtro della posta indesiderata in uscita (il cmdlet **Set-HostedOutboundSpamFilterPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="3c1df-325">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3c1df-326">Quando si rinomina un criterio di posta indesiderata in uscita nel Centro sicurezza & conformità, si rinomina solo la regola di filtro della posta indesiderata in _uscita._</span><span class="sxs-lookup"><span data-stu-id="3c1df-326">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="3c1df-327">Per modificare un criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-327">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3c1df-328">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="3c1df-328">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="3c1df-329">Utilizzare PowerShell per modificare le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-329">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="3c1df-330">L'unica impostazione non disponibile quando si modifica una regola di filtro della posta indesiderata in uscita in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3c1df-330">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3c1df-331">Per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="3c1df-331">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="3c1df-332">In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola di filtro della posta indesiderata in uscita in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3c1df-332">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="3c1df-333">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione [Passaggio 2:](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) Utilizzare PowerShell per creare una regola di filtro della posta indesiderata in uscita più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3c1df-333">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this article.</span></span>

<span data-ttu-id="3c1df-334">Per modificare una regola di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-334">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3c1df-335">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3c1df-335">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="3c1df-336">Utilizzare PowerShell per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-336">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="3c1df-337">L'abilitazione o la disabilitazione di una regola di filtro della posta indesiderata in uscita in PowerShell abilita o disabilita l'intero criterio di posta indesiderata in uscita (la regola di filtro della posta indesiderata in uscita e il criterio di filtro della posta indesiderata in uscita assegnato).</span><span class="sxs-lookup"><span data-stu-id="3c1df-337">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="3c1df-338">Non è possibile abilitare o disabilitare il criterio di posta indesiderata in uscita predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="3c1df-338">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="3c1df-339">Per abilitare o disabilitare una regola di filtro della posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-339">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="3c1df-340">In questo esempio viene disabilitata la regola di filtro della posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3c1df-340">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3c1df-341">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="3c1df-341">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3c1df-342">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) [e Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3c1df-342">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="3c1df-343">Utilizzare PowerShell per impostare la priorità delle regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-343">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="3c1df-344">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="3c1df-344">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="3c1df-345">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="3c1df-345">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="3c1df-346">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="3c1df-346">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="3c1df-347">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="3c1df-347">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="3c1df-348">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="3c1df-348">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3c1df-349">Per impostare la priorità di una regola di filtro della posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-349">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3c1df-p141">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="3c1df-p141">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="3c1df-352">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-HostedOutboundSpamFilterRule.**</span><span class="sxs-lookup"><span data-stu-id="3c1df-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="3c1df-353">Il criterio di filtro della posta indesiderata predefinito in uscita non dispone di una regola di filtro della posta indesiderata corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="3c1df-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="3c1df-354">Utilizzare PowerShell per rimuovere i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="3c1df-355">Quando si utilizza PowerShell per rimuovere un criterio di filtro della posta indesiderata in uscita, la regola di filtro della posta indesiderata in uscita corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="3c1df-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="3c1df-356">Per rimuovere un criterio di filtro della posta indesiderata in uscita in PowerShell, utilizzare questa sintassi:</span><span class="sxs-lookup"><span data-stu-id="3c1df-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3c1df-357">In questo esempio viene rimosso il criterio di filtro della posta indesiderata in uscita denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3c1df-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3c1df-358">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="3c1df-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="3c1df-359">Utilizzare PowerShell per rimuovere le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="3c1df-360">Quando si utilizza PowerShell per rimuovere una regola di filtro della posta indesiderata in uscita, il criterio di filtro della posta indesiderata in uscita corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="3c1df-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="3c1df-361">Per rimuovere una regola di filtro della posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3c1df-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="3c1df-362">In questo esempio viene rimossa la regola di filtro della posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3c1df-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="3c1df-363">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="3c1df-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="3c1df-364">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="3c1df-364">For more information</span></span>

[<span data-ttu-id="3c1df-365">Rimuovere utenti bloccati dal portale Utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="3c1df-365">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="3c1df-366">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="3c1df-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="3c1df-367">Domande frequenti sulla protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="3c1df-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="3c1df-368">Report dei messaggi inoltrati automaticamente</span><span class="sxs-lookup"><span data-stu-id="3c1df-368">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)