---
title: Configurare i Cassaforte allegati in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Informazioni su come definire i criteri Cassaforte allegati per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7220140c25ecf457b42514356e41aabdf5481bb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054329"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="51838-103">Configurare i Cassaforte allegati in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="51838-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="51838-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="51838-104">**Applies to**</span></span>
- [<span data-ttu-id="51838-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="51838-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="51838-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51838-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="51838-107">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="51838-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="51838-108">Se si è un utente principale che desidera informazioni sull'analisi degli allegati in Outlook, vedere [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="51838-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="51838-109">Cassaforte Allegati è una funzionalità di [Microsoft Defender per Office 365 che](whats-new-in-defender-for-office-365.md) usa un ambiente virtuale per archiviare gli allegati nei messaggi di posta elettronica in ingresso dopo essere stati analizzati dalla protezione [antimalware in Exchange Online Protection (EOP),](anti-malware-protection.md)ma prima del recapito ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="51838-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="51838-110">Per ulteriori informazioni, vedere [Cassaforte allegati in Microsoft Defender per Office 365](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="51838-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="51838-111">Non esiste un criterio predefinito o predefinito Cassaforte allegati.</span><span class="sxs-lookup"><span data-stu-id="51838-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="51838-112">Per ottenere Cassaforte allegati degli allegati dei messaggi di posta elettronica, è necessario creare uno o più criteri Cassaforte allegati come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="51838-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="51838-113">È possibile configurare i criteri allegati Cassaforte nel portale di Microsoft 365 Defender o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="51838-113">You can configure Safe Attachments policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="51838-114">Gli elementi di base di un criterio Cassaforte allegati sono:</span><span class="sxs-lookup"><span data-stu-id="51838-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="51838-115">Criterio allegati sicuri **:** Specifica le azioni per i rilevamenti di malware sconosciuti, se inviare messaggi con allegati di malware a un indirizzo di posta elettronica specificato e se recapitare i messaggi se l'analisi degli allegati Cassaforte non può essere completata.</span><span class="sxs-lookup"><span data-stu-id="51838-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="51838-116">**La regola degli allegati sicuri**: Specifica la priorità e i filtri destinatari (a cui si applica il criterio).</span><span class="sxs-lookup"><span data-stu-id="51838-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="51838-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri Cassaforte allegati nel portale Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="51838-117">The difference between these two elements isn't obvious when you manage Safe Attachments policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="51838-118">Quando si crea un criterio Cassaforte allegati, si sta creando contemporaneamente una regola degli allegati sicuri e il criterio di allegato sicuro associato utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="51838-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="51838-119">Quando si modifica un criterio Cassaforte allegati, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="51838-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="51838-120">Tutte le altre impostazioni modificano i criteri allegati sicuri associati.</span><span class="sxs-lookup"><span data-stu-id="51838-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="51838-121">Quando si rimuove un criterio Cassaforte allegati sicuri, vengono rimossi la regola degli allegati sicuri e i criteri allegati sicuri associati.</span><span class="sxs-lookup"><span data-stu-id="51838-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="51838-122">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="51838-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="51838-123">Per ulteriori informazioni, vedere la sezione Use [Exchange Online PowerShell or standalone EOP PowerShell to configure Cassaforte Attachments più](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="51838-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="51838-124">Nell'area impostazioni globali delle impostazioni Cassaforte allegati è possibile configurare funzionalità che non dipendono dai criteri Cassaforte allegati.</span><span class="sxs-lookup"><span data-stu-id="51838-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="51838-125">Per istruzioni, vedere Attivare Cassaforte allegati per [SharePoint, OneDrive e](turn-on-mdo-for-spo-odb-and-teams.md) Microsoft Teams e [Cassaforte documenti in Microsoft 365 E5](safe-docs.md).</span><span class="sxs-lookup"><span data-stu-id="51838-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51838-126">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="51838-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51838-127">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="51838-127">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="51838-128">Per passare direttamente alla pagina **Cassaforte allegati,** utilizzare <https://security.microsoft.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="51838-128">To go directly to the **Safe Attachments** page, use <https://security.microsoft.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="51838-129">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51838-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="51838-130">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="51838-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="51838-131">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-131">You need permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="51838-132">Per creare, modificare ed eliminare i criteri allegati Cassaforte, è  necessario  essere membri dei gruppi di  ruoli Gestione organizzazione  o Amministratore sicurezza nel portale di Microsoft 365 Defender e membri del gruppo di ruoli Gestione organizzazione in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="51838-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Microsoft 365 Defender portal **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="51838-133">Per l'accesso in sola lettura ai criteri Cassaforte allegati,  è necessario  essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza nel portale Microsoft 365 Defender sicurezza.</span><span class="sxs-lookup"><span data-stu-id="51838-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Microsoft 365 Defender portal.</span></span>

  <span data-ttu-id="51838-134">Per ulteriori informazioni, vedere [Autorizzazioni nel portale Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Autorizzazioni in [Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="51838-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="51838-135">**Note**:</span><span class="sxs-lookup"><span data-stu-id="51838-135">**Notes**:</span></span>

  - <span data-ttu-id="51838-136">L'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51838-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="51838-137">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="51838-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="51838-138">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="51838-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="51838-139">Per le impostazioni consigliate per i criteri Cassaforte allegati, vedere impostazioni [Cassaforte allegati](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="51838-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="51838-140">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="51838-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a><span data-ttu-id="51838-141">Usare il portale Microsoft 365 Defender per creare criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-141">Use the Microsoft 365 Defender portal to create Safe Attachments policies</span></span>

<span data-ttu-id="51838-142">La creazione di un criterio Cassaforte allegati personalizzati nel portale di Microsoft 365 Defender crea la regola degli allegati sicuri e i criteri allegati sicuri associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="51838-142">Creating a custom Safe Attachments policy in the Microsoft 365 Defender portal creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="51838-143">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.</span><span class="sxs-lookup"><span data-stu-id="51838-143">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="51838-144">Nella pagina **Cassaforte allegati** fare clic su Crea ![ icona ](../../media/m365-cc-sc-create-icon.png) **Crea**.</span><span class="sxs-lookup"><span data-stu-id="51838-144">On the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="51838-145">Viene aperta la creazione guidata criteri.</span><span class="sxs-lookup"><span data-stu-id="51838-145">The policy wizard opens.</span></span> <span data-ttu-id="51838-146">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-146">On the **Name your policy** page, configure the following settings:</span></span>
   - <span data-ttu-id="51838-147">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="51838-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="51838-148">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="51838-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="51838-149">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="51838-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="51838-150">Nella pagina **Utenti e domini** visualizzata identificare i destinatari interni a cui si applica il criterio (condizioni del destinatario):</span><span class="sxs-lookup"><span data-stu-id="51838-150">On the **Users and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="51838-151">**Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51838-151">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="51838-152">**Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51838-152">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="51838-153">**Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51838-153">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="51838-154">Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="51838-154">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="51838-155">Ripetere questa procedura tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="51838-155">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="51838-156">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="51838-156">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="51838-158">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="51838-158">next to the value.</span></span>

   <span data-ttu-id="51838-159">Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="51838-159">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="51838-160">Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.</span><span class="sxs-lookup"><span data-stu-id="51838-160">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="51838-161">Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="51838-161">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="51838-162">Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="51838-162">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="51838-163">**Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni per i destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="51838-163">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="51838-164">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="51838-164">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="51838-165">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="51838-165">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="51838-166">Nella pagina **Impostazioni** configurazione delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-166">On the **Settings** page, configure the following settings:</span></span>

   - <span data-ttu-id="51838-167">**Cassaforte Allegati risposta malware sconosciuta**: selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="51838-167">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>
     - <span data-ttu-id="51838-168">**Disattivato:** in genere, non è consigliabile questo valore.</span><span class="sxs-lookup"><span data-stu-id="51838-168">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="51838-169">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="51838-169">**Monitor**</span></span>
     - <span data-ttu-id="51838-170">**Block**: questo è il valore predefinito e il valore consigliato in Standard e Strict [preset security policies](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="51838-170">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="51838-171">**Sostituisce**</span><span class="sxs-lookup"><span data-stu-id="51838-171">**Replace**</span></span>
     - <span data-ttu-id="51838-172">**Recapito dinamico (funzionalità di anteprima)**</span><span class="sxs-lookup"><span data-stu-id="51838-172">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="51838-173">Questi valori sono illustrati nelle impostazioni [Cassaforte dei criteri Allegati.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="51838-173">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="51838-174">Reindirizzare i messaggi con allegati rilevati **:** se si seleziona Abilita reindirizzamento **,** è possibile specificare un indirizzo di posta elettronica nella casella Invia messaggi che contengono allegati **bloccati,** monitorati o sostituiti all'indirizzo di posta elettronica specificato per inviare messaggi contenenti allegati di malware per l'analisi e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="51838-174">**Redirect messages with detected attachments**: If you select **Enable redirect**, you can specify an email address in the **Send messages that contain blocked, monitored, or replaced attachments to the specified email address** box to send messages that contain malware attachments for analysis and investigation.</span></span>

     <span data-ttu-id="51838-175">Per le impostazioni dei criteri Standard e Strict è consigliabile abilitare il reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="51838-175">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="51838-176">Per ulteriori informazioni, vedere [impostazioni Cassaforte allegati](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span><span class="sxs-lookup"><span data-stu-id="51838-176">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="51838-177">Applicare la risposta di rilevamento allegati Cassaforte se l'analisi non può essere completata (timeout o **errori): l'azione** specificata da **Cassaforte Allegati** risposta malware sconosciuta viene eseguita sui messaggi anche quando non è possibile completare l'analisi degli allegati di Cassaforte.</span><span class="sxs-lookup"><span data-stu-id="51838-177">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="51838-178">Se è stata selezionata questa opzione, selezionare sempre **Abilita reindirizzamento** e specificare un indirizzo di posta elettronica per inviare messaggi contenenti allegati di malware.</span><span class="sxs-lookup"><span data-stu-id="51838-178">If you selected this option, always select **Enable redirect** and specify an email address to send messages that contain malware attachments.</span></span> <span data-ttu-id="51838-179">In caso contrario, i messaggi potrebbero essere persi.</span><span class="sxs-lookup"><span data-stu-id="51838-179">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="51838-180">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="51838-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="51838-181">Nella pagina **Controllo** visualizzata controllare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="51838-181">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="51838-182">È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="51838-182">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="51838-183">Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="51838-183">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="51838-184">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="51838-184">When you're finished, click **Submit**.</span></span>

7. <span data-ttu-id="51838-185">Nel messaggio di conferma visualizzato fare clic su **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="51838-185">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a><span data-ttu-id="51838-186">Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-186">Use the Microsoft 365 Defender portal to view Safe Attachments policies</span></span>

1. <span data-ttu-id="51838-187">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.</span><span class="sxs-lookup"><span data-stu-id="51838-187">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="51838-188">Nella pagina **Cassaforte allegati** vengono visualizzate le proprietà seguenti nell'elenco dei criteri:</span><span class="sxs-lookup"><span data-stu-id="51838-188">On the **Safe Attachments** page, the following properties are displayed in the list of policies:</span></span>
   - <span data-ttu-id="51838-189">**Nome**</span><span class="sxs-lookup"><span data-stu-id="51838-189">**Name**</span></span>
   - <span data-ttu-id="51838-190">**Stato**</span><span class="sxs-lookup"><span data-stu-id="51838-190">**Status**</span></span>
   - <span data-ttu-id="51838-191">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="51838-191">**Priority**</span></span>

3. <span data-ttu-id="51838-192">Quando si seleziona un criterio facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="51838-192">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a><span data-ttu-id="51838-193">Utilizzare il portale Microsoft 365 Defender per modificare i criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-193">Use the Microsoft 365 Defender portal to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="51838-194">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.</span><span class="sxs-lookup"><span data-stu-id="51838-194">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="51838-195">Nella pagina **Cassaforte allegati** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="51838-195">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="51838-196">Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="51838-196">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="51838-197">Per ulteriori informazioni sulle impostazioni, vedere la sezione Usare il portale di Microsoft 365 Defender per creare criteri Cassaforte [allegati](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="51838-197">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create Safe Attachments policies](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) section earlier in this article.</span></span>  

<span data-ttu-id="51838-198">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="51838-198">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="51838-199">Abilitare o disabilitare i criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-199">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="51838-200">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.</span><span class="sxs-lookup"><span data-stu-id="51838-200">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="51838-201">Nella pagina **Cassaforte allegati** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="51838-201">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="51838-202">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-202">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="51838-203">**Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .</span><span class="sxs-lookup"><span data-stu-id="51838-203">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="51838-204">**Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="51838-204">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="51838-205">Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="51838-205">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="51838-206">Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="51838-206">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="51838-207">Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="51838-207">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="51838-208">Impostare la priorità dei criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-208">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="51838-209">Per impostazione predefinita, Cassaforte criteri allegati hanno una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="51838-209">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="51838-210">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="51838-210">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="51838-211">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="51838-211">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="51838-212">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="51838-212">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="51838-213">Cassaforte I criteri allegati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="51838-213">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="51838-214">**Nota:** nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio allegati Cassaforte solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="51838-214">**Note**: In the Microsoft 365 Defender portal, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="51838-215">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola degli allegati sicuri (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="51838-215">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="51838-216">Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="51838-216">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="51838-217">La modifica di priorità di un criterio è utile solo se si hanno più criteri.</span><span class="sxs-lookup"><span data-stu-id="51838-217">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="51838-218">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.</span><span class="sxs-lookup"><span data-stu-id="51838-218">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="51838-219">Nella pagina **Cassaforte allegati** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="51838-219">On the **Safe Attachments** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="51838-220">Nella parte superiore del riquadro a comparsa dei  dettagli del  criterio visualizzato, vedrai Aumentare la priorità o Diminuire la priorità in base al valore di priorità corrente e al numero di criteri:</span><span class="sxs-lookup"><span data-stu-id="51838-220">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of policies:</span></span>
   - <span data-ttu-id="51838-221">Per il criterio con **valore Priority** **0 è** disponibile solo **l'opzione Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="51838-221">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="51838-222">Il criterio con il valore **Di priorità** più basso (ad esempio, **3)** ha solo l'opzione **Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="51838-222">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="51838-223">Se si dispone di tre o più criteri, per i  criteri tra i valori di priorità più alta e più bassa sono disponibili le opzioni Aumenta priorità e **Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="51838-223">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="51838-224">Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.</span><span class="sxs-lookup"><span data-stu-id="51838-224">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="51838-225">Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="51838-225">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a><span data-ttu-id="51838-226">Utilizzare il portale Microsoft 365 Defender per rimuovere i criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-226">Use the Microsoft 365 Defender portal to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="51838-227">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.</span><span class="sxs-lookup"><span data-stu-id="51838-227">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span>

2. <span data-ttu-id="51838-228">Nella pagina **Cassaforte allegati** selezionare un criterio personalizzato nell'elenco facendo clic sul nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="51838-228">On the **Safe Attachments** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="51838-229">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.</span><span class="sxs-lookup"><span data-stu-id="51838-229">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="51838-230">Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="51838-230">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="51838-231">Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare i criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-231">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="51838-232">Come descritto in precedenza, un criterio Cassaforte allegati è costituito da un criterio di allegato sicuro e da una regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="51838-232">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="51838-233">In PowerShell, la differenza tra i criteri degli allegati sicuri e le regole degli allegati sicuri è evidente.</span><span class="sxs-lookup"><span data-stu-id="51838-233">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="51838-234">È possibile gestire i criteri degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentPolicy** e le regole degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="51838-234">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="51838-235">In PowerShell, si crea prima il criterio degli allegati sicuri, quindi si crea la regola degli allegati sicuri che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="51838-235">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="51838-236">In PowerShell, le impostazioni nel criterio degli allegati sicuri e nella regola degli allegati sicuri vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="51838-236">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="51838-237">Quando si rimuove un criterio di allegato sicuro da PowerShell, la regola degli allegati sicuri corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="51838-237">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="51838-238">Utilizzare PowerShell per creare criteri Cassaforte allegati</span><span class="sxs-lookup"><span data-stu-id="51838-238">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="51838-239">La creazione Cassaforte criteri allegati in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="51838-239">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="51838-240">Creare il criterio degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="51838-240">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="51838-241">Creare la regola degli allegati sicuri che specifica il criterio degli allegati sicuri a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="51838-241">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="51838-242">**Note**:</span><span class="sxs-lookup"><span data-stu-id="51838-242">**Notes**:</span></span>

- <span data-ttu-id="51838-243">È possibile creare una nuova regola degli allegati sicuri e assegnarle un criterio di allegato sicuro non associato esistente.</span><span class="sxs-lookup"><span data-stu-id="51838-243">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="51838-244">Una regola degli allegati sicuri non può essere associata a più criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="51838-244">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="51838-245">È possibile configurare le impostazioni seguenti nei nuovi criteri allegati sicuri in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="51838-245">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="51838-246">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="51838-246">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="51838-247">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="51838-247">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="51838-248">Un nuovo criterio di allegato sicuro creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="51838-248">A new safe attachment policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="51838-249">Passaggio 1: Usare PowerShell per creare criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-249">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="51838-250">Per creare criteri allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-250">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="51838-251">In questo esempio viene creato un criterio di allegato sicuro denominato Contoso All con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-251">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="51838-252">Blocca i messaggi che vengono trovati come contenenti malware Cassaforte'analisi dei documenti (non viene utilizzato il parametro _Action_ e il valore predefinito è `Block` ).</span><span class="sxs-lookup"><span data-stu-id="51838-252">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="51838-253">Il reindirizzamento è abilitato e i messaggi che contengono malware vengono inviati a sec-ops@contoso.com per l'analisi e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="51838-253">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="51838-254">Se Cassaforte'analisi degli allegati non è disponibile o si verificano errori, non recapitare il messaggio (non viene utilizzato il parametro _ActionOnError_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="51838-254">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="51838-255">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentPolicy.](/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="51838-255">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="51838-256">Passaggio 2: Usare PowerShell per creare una regola degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-256">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="51838-257">Per creare una regola degli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-257">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="51838-258">In questo esempio viene creata una regola di allegato sicura denominata Contoso All con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-258">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="51838-259">La regola è associata al criterio degli allegati sicuri denominato Contoso All.</span><span class="sxs-lookup"><span data-stu-id="51838-259">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="51838-260">La regola si applica a tutti i destinatari del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="51838-260">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="51838-261">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="51838-261">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="51838-262">La regola è abilitata (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="51838-262">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="51838-263">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="51838-263">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="51838-264">Usare PowerShell per visualizzare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-264">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="51838-265">Per visualizzare i criteri allegati sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-265">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="51838-266">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="51838-266">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="51838-267">In questo esempio vengono restituite informazioni dettagliate per il criterio degli allegati sicuri denominato Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="51838-267">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="51838-268">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="51838-268">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="51838-269">Usare PowerShell per visualizzare le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-269">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="51838-270">Per visualizzare le regole degli allegati sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-270">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="51838-271">In questo esempio viene restituito un elenco riepilogativo di tutte le regole degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="51838-271">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="51838-272">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-272">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="51838-273">In questo esempio vengono restituite informazioni dettagliate per la regola degli allegati sicuri denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="51838-273">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="51838-274">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="51838-274">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="51838-275">Utilizzare PowerShell per modificare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-275">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="51838-276">Non è possibile rinominare un criterio degli allegati sicuri in PowerShell (il cmdlet **Set-SafeAttachmentPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="51838-276">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="51838-277">Quando si rinomina un criterio Cassaforte allegati nel portale Microsoft 365 Defender, si rinomina solo la regola degli allegati _sicuri._</span><span class="sxs-lookup"><span data-stu-id="51838-277">When you rename a Safe Attachments policy in the Microsoft 365 Defender portal, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="51838-278">In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio degli allegati sicuri come descritto nella sezione Passaggio [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) utilizzare PowerShell per creare un criterio di allegati sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="51838-278">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="51838-279">Per modificare un criterio degli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-279">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="51838-280">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="51838-280">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="51838-281">Utilizzare PowerShell per modificare le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-281">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="51838-282">L'unica impostazione non disponibile quando si modifica una regola degli allegati sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="51838-282">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="51838-283">Per abilitare o disabilitare le regole degli allegati sicuri esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="51838-283">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="51838-284">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Utilizzare PowerShell per creare una regola degli allegati sicuri in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="51838-284">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="51838-285">Per modificare una regola degli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-285">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="51838-286">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="51838-286">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="51838-287">Abilitazione o disabilitazione delle regole degli allegati sicuri tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="51838-287">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="51838-288">L'abilitazione o la disabilitazione di una regola degli allegati sicuri in PowerShell abilita o disabilita l'intero criterio allegati Cassaforte (la regola degli allegati sicuri e il criterio degli allegati sicuri assegnati).</span><span class="sxs-lookup"><span data-stu-id="51838-288">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="51838-289">Per abilitare o disabilitare una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-289">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="51838-290">In questo esempio viene disabilitata la regola degli allegati sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="51838-290">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="51838-291">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="51838-291">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="51838-292">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) [e Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="51838-292">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="51838-293">Utilizzare PowerShell per impostare la priorità delle regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-293">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="51838-p126">Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="51838-p126">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="51838-299">Per impostare la priorità di una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-299">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="51838-p127">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="51838-p127">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="51838-302">**Nota:** per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="51838-302">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="51838-303">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="51838-303">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="51838-304">Usare PowerShell per rimuovere i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-304">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="51838-305">Quando si utilizza PowerShell per rimuovere un criterio di allegato sicuro, la regola degli allegati sicuri corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="51838-305">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="51838-306">Per rimuovere un criterio di allegato sicuro in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-306">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="51838-307">In questo esempio viene rimosso il criterio degli allegati sicuri denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="51838-307">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="51838-308">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="51838-308">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="51838-309">Usare PowerShell per rimuovere le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="51838-309">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="51838-310">Quando si utilizza PowerShell per rimuovere una regola degli allegati sicuri, il criterio di allegato sicuro corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="51838-310">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="51838-311">Per rimuovere una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51838-311">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="51838-312">In questo esempio viene rimossa la regola degli allegati sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="51838-312">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="51838-313">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="51838-313">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="51838-314">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="51838-314">How do you know these procedures worked?</span></span>

<span data-ttu-id="51838-315">Per verificare che i criteri allegati siano stati creati, modificati o rimossi correttamente, Cassaforte eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51838-315">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="51838-316">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & posta elettronica & criteri di minaccia sezione Criteri \>  \>  \>  di \> **Cassaforte Allegati**.</span><span class="sxs-lookup"><span data-stu-id="51838-316">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Policies** section \> **Safe Attachments**.</span></span> <span data-ttu-id="51838-317">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="51838-317">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="51838-318">Per visualizzare altri dettagli, selezionare il criterio dall'elenco facendo clic sul nome e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="51838-318">To view more details, select the policy from the list by clicking on the name, and view the details in the fly out.</span></span>

- <span data-ttu-id="51838-319">In Exchange Online PowerShell o Exchange Online Protection PowerShell, sostituire con il nome del criterio o della regola, eseguire il comando seguente e \<Name\> verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="51838-319">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="51838-320">Per verificare che Cassaforte allegati esempa l'analisi dei messaggi, controlla il Defender disponibile per Office 365 report.</span><span class="sxs-lookup"><span data-stu-id="51838-320">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="51838-321">Per altre informazioni, vedi [Visualizzare i report per Defender per Office 365](view-reports-for-mdo.md) e Usare Esplora risorse nel portale [Microsoft 365 Defender.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="51838-321">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Microsoft 365 Defender portal](threat-explorer.md).</span></span>
