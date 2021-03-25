---
title: Configurare i criteri allegati sicuri in Microsoft Defender per Office 365
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
description: Informazioni su come definire i criteri allegati sicuri per proteggere l'organizzazione da file dannosi nella posta elettronica.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206503"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="80e82-103">Configurare i criteri allegati sicuri in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="80e82-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="80e82-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="80e82-104">**Applies to**</span></span>
- [<span data-ttu-id="80e82-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="80e82-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="80e82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80e82-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="80e82-107">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](whats-new-in-defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="80e82-107">This article is intended for business customers who have [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md).</span></span> <span data-ttu-id="80e82-108">Per informazioni sull'analisi degli allegati in Outlook, [vedere Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="80e82-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="80e82-109">Allegati sicuri è una funzionalità di [Microsoft Defender per Office 365](whats-new-in-defender-for-office-365.md) che utilizza un ambiente virtuale per archiviare gli allegati nei messaggi di posta elettronica in ingresso dopo essere stati analizzati dalla protezione [antimalware in Exchange Online Protection (EOP),](anti-malware-protection.md)ma prima del recapito ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="80e82-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="80e82-110">Per ulteriori informazioni, vedere [Allegati sicuri in Microsoft Defender per Office 365.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="80e82-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](safe-attachments.md).</span></span>

<span data-ttu-id="80e82-111">Non esiste un criterio predefinito per gli allegati sicuri o predefinito.</span><span class="sxs-lookup"><span data-stu-id="80e82-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="80e82-112">Per ottenere l'analisi degli allegati sicuri degli allegati dei messaggi di posta elettronica, è necessario creare uno o più criteri allegati sicuri come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="80e82-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="80e82-113">È possibile configurare i criteri allegati sicuri nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="80e82-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="80e82-114">Gli elementi di base di un criterio Allegati sicuri sono:</span><span class="sxs-lookup"><span data-stu-id="80e82-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="80e82-115">**Il** criterio allegati sicuri : Specifica le azioni per i rilevamenti di malware sconosciuti, se inviare messaggi con allegati di malware a un indirizzo di posta elettronica specificato e se recapitare i messaggi se l'analisi degli allegati sicuri non può essere completata.</span><span class="sxs-lookup"><span data-stu-id="80e82-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="80e82-116">**La regola degli allegati sicuri**: Specifica la priorità e i filtri destinatari (a cui si applica il criterio).</span><span class="sxs-lookup"><span data-stu-id="80e82-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="80e82-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri allegati sicuri nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="80e82-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="80e82-118">Quando si crea un criterio Allegati sicuri, si crea contemporaneamente una regola degli allegati sicuri e il criterio di allegato sicuro associato utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="80e82-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="80e82-119">Quando si modifica un criterio Allegati sicuri, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="80e82-120">Tutte le altre impostazioni modificano i criteri allegati sicuri associati.</span><span class="sxs-lookup"><span data-stu-id="80e82-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="80e82-121">Quando si rimuove un criterio Allegati sicuri, vengono rimossi la regola degli allegati sicuri e il criterio di allegato sicuro associato.</span><span class="sxs-lookup"><span data-stu-id="80e82-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="80e82-122">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="80e82-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="80e82-123">Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online o [PowerShell EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autonomo per configurare i criteri allegati sicuri più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="80e82-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="80e82-124">Nell'area impostazioni globali delle impostazioni allegati sicuri è possibile configurare funzionalità che non dipendono dai criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="80e82-125">Per istruzioni, vedere Attivare allegati sicuri [per SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) e Documenti sicuri in Microsoft [365 E5.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="80e82-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="80e82-126">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="80e82-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="80e82-127">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="80e82-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="80e82-128">Per passare direttamente alla **pagina Allegati sicuri,** utilizzare <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="80e82-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="80e82-129">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="80e82-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="80e82-130">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="80e82-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="80e82-131">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e82-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="80e82-132">Per creare, modificare ed eliminare i criteri allegati sicuri,  è necessario essere membri dei gruppi di ruoli Gestione organizzazione  o Amministratore sicurezza nel Centro sicurezza & conformità e membri del gruppo di ruoli Gestione organizzazione in Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="80e82-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="80e82-133">Per l'accesso in sola lettura ai criteri allegati  sicuri,  è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="80e82-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="80e82-134">Per ulteriori informazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Permissions in Exchange [Online.](/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="80e82-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="80e82-135">**Note**:</span><span class="sxs-lookup"><span data-stu-id="80e82-135">**Notes**:</span></span>

  - <span data-ttu-id="80e82-136">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="80e82-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="80e82-137">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="80e82-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="80e82-138">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="80e82-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="80e82-139">Per le impostazioni consigliate per i criteri allegati sicuri, vedere [Impostazioni degli allegati sicuri.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="80e82-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="80e82-140">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="80e82-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="80e82-141">Usare il Centro sicurezza & conformità per creare criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="80e82-142">La creazione di un criterio allegati sicuri personalizzato nel Centro sicurezza & conformità crea contemporaneamente la regola degli allegati sicuri e i criteri allegati sicuri associati utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="80e82-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="80e82-143">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **Allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="80e82-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="80e82-144">Nella pagina **Allegati sicuri** fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="80e82-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="80e82-145">Verrà **visualizzata la procedura guidata Nuovo criterio Allegati** sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="80e82-146">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e82-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="80e82-147">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="80e82-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="80e82-148">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="80e82-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="80e82-149">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80e82-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="80e82-150">Nella pagina **Impostazioni** visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e82-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="80e82-151">**Allegati sicuri Risposta malware sconosciuta**: selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="80e82-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="80e82-152">**Disattivato:** in genere, non è consigliabile questo valore.</span><span class="sxs-lookup"><span data-stu-id="80e82-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="80e82-153">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="80e82-153">**Monitor**</span></span>
     - <span data-ttu-id="80e82-154">**Block**: questo è il valore predefinito e il valore consigliato in Standard e Strict [preset security policies](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="80e82-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="80e82-155">**Sostituisce**</span><span class="sxs-lookup"><span data-stu-id="80e82-155">**Replace**</span></span>
     - <span data-ttu-id="80e82-156">**Recapito dinamico (funzionalità di anteprima)**</span><span class="sxs-lookup"><span data-stu-id="80e82-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="80e82-157">Questi valori sono illustrati nelle [impostazioni dei criteri Allegati sicuri.](safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="80e82-157">These values are explained in [Safe Attachments policy settings](safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="80e82-158">Inviare l'allegato al seguente indirizzo di posta elettronica **:** Per  i valori di azione **Blocca,** Monitor o **Sostituisci,** è possibile selezionare Abilita reindirizzamento per inviare messaggi contenenti allegati di malware all'indirizzo di posta elettronica interno o esterno specificato per l'analisi e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="80e82-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="80e82-159">Per le impostazioni dei criteri Standard e Strict è consigliabile abilitare il reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="80e82-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="80e82-160">Per ulteriori informazioni, vedere [Impostazioni degli allegati sicuri.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="80e82-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="80e82-161">**Applicare la selezione** precedente se si verifica il timeout o l'errore dell'analisi antimalware per gli allegati: l'azione specificata da Allegati sicuri risposta **malware** sconosciuta viene eseguita sui messaggi anche quando l'analisi degli allegati sicuri non può essere completata.</span><span class="sxs-lookup"><span data-stu-id="80e82-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="80e82-162">Se è stata selezionata questa opzione, selezionare sempre **Reindirizzamento abilitato.**</span><span class="sxs-lookup"><span data-stu-id="80e82-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="80e82-163">In caso contrario, i messaggi potrebbero essere persi.</span><span class="sxs-lookup"><span data-stu-id="80e82-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="80e82-164">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80e82-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="80e82-165">Nella pagina **Applicato a** visualizzata identificare i destinatari interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="80e82-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="80e82-166">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="80e82-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="80e82-167">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="80e82-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="80e82-168">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="80e82-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="80e82-169">Fare **clic su Aggiungi condizione.**</span><span class="sxs-lookup"><span data-stu-id="80e82-169">Click **Add a condition**.</span></span> <span data-ttu-id="80e82-170">Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se**:</span><span class="sxs-lookup"><span data-stu-id="80e82-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="80e82-171">**Il destinatario è**: Specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80e82-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="80e82-172">**Il destinatario è un membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80e82-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="80e82-173">**Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80e82-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="80e82-174">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una casella** Qualsiasi di queste.</span><span class="sxs-lookup"><span data-stu-id="80e82-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="80e82-175">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="80e82-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="80e82-176">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="80e82-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="80e82-177">Per aggiungere altri valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="80e82-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="80e82-178">Per rimuovere singole voci, fare clic **su Rimuovi** ![ Icona Rimuovi sul ](../../media/scc-remove-icon.png) valore.</span><span class="sxs-lookup"><span data-stu-id="80e82-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="80e82-179">Per rimuovere l'intera condizione, fare **clic su Rimuovi** Icona Rimuovi nella ![ ](../../media/scc-remove-icon.png) condizione.</span><span class="sxs-lookup"><span data-stu-id="80e82-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="80e82-180">Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se**.</span><span class="sxs-lookup"><span data-stu-id="80e82-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="80e82-181">Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**.</span><span class="sxs-lookup"><span data-stu-id="80e82-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="80e82-182">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="80e82-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="80e82-183">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="80e82-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="80e82-184">Nella pagina **Rivedere le impostazioni** visualizzata esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="80e82-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="80e82-185">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="80e82-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="80e82-186">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="80e82-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="80e82-187">Usare il Centro sicurezza & conformità per visualizzare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="80e82-188">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **Allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="80e82-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="80e82-189">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="80e82-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="80e82-190">I dettagli dei criteri vengono visualizzati in un riquadro a comparsa</span><span class="sxs-lookup"><span data-stu-id="80e82-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="80e82-191">Utilizzare il Centro sicurezza & conformità per modificare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="80e82-192">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **Allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="80e82-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="80e82-193">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="80e82-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="80e82-194">Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic **su Modifica criterio.**</span><span class="sxs-lookup"><span data-stu-id="80e82-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="80e82-195">Le impostazioni disponibili nel riquadro a comparsa visualizzato sono identiche a quelle descritte nella sezione Usare il Centro [sicurezza &](#use-the-security--compliance-center-to-create-safe-attachments-policies) conformità per creare criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="80e82-196">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="80e82-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="80e82-197">Abilitare o disabilitare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="80e82-198">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **Allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="80e82-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="80e82-199">Notare il valore nella **colonna** Stato:</span><span class="sxs-lookup"><span data-stu-id="80e82-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="80e82-200">Spostare l'interruttore a sinistra</span><span class="sxs-lookup"><span data-stu-id="80e82-200">Move the toggle to the left</span></span> ![Disattivare i criteri](../../media/scc-toggle-off.png) <span data-ttu-id="80e82-202">per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="80e82-202">to disable the policy.</span></span>

   - <span data-ttu-id="80e82-203">Spostare l'interruttore verso destra</span><span class="sxs-lookup"><span data-stu-id="80e82-203">Move the toggle to the right</span></span> ![Attivare i criteri](../../media/scc-toggle-on.png) <span data-ttu-id="80e82-205">per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="80e82-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="80e82-206">Impostare la priorità dei criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="80e82-207">Per impostazione predefinita, ai criteri allegati sicuri viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="80e82-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="80e82-208">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="80e82-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="80e82-209">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="80e82-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="80e82-210">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="80e82-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="80e82-211">I criteri allegati sicuri vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="80e82-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="80e82-212">**Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio Allegati sicuri solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="80e82-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="80e82-213">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola degli allegati sicuri (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="80e82-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="80e82-214">Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="80e82-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="80e82-215">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **Allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="80e82-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="80e82-216">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="80e82-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="80e82-217">Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic sul pulsante priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="80e82-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="80e82-218">Per il criterio Allegati sicuri con **valore Priorità** **0** è disponibile solo il **pulsante** Riduci priorità.</span><span class="sxs-lookup"><span data-stu-id="80e82-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="80e82-219">Il criterio Allegati sicuri con il valore **di priorità** più basso ( ad **esempio, 3**) ha solo il **pulsante Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="80e82-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="80e82-220">Se si dispone di tre o più criteri allegati sicuri,  i criteri  tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e Riduci priorità disponibili.</span><span class="sxs-lookup"><span data-stu-id="80e82-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="80e82-221">Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **Priorità.**</span><span class="sxs-lookup"><span data-stu-id="80e82-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="80e82-222">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="80e82-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="80e82-223">Usare il Centro sicurezza & conformità per rimuovere i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="80e82-224">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **Allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="80e82-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="80e82-225">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="80e82-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="80e82-226">Nel riquadro a comparsa dei dettagli del criterio visualizzato fare clic su **Elimina** criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="80e82-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="80e82-227">Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per configurare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="80e82-228">Come descritto in precedenza, un criterio Allegati sicuri è costituito da un criterio degli allegati sicuri e da una regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="80e82-229">In PowerShell, la differenza tra i criteri degli allegati sicuri e le regole degli allegati sicuri è evidente.</span><span class="sxs-lookup"><span data-stu-id="80e82-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="80e82-230">È possibile gestire i criteri degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentPolicy** e le regole degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="80e82-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="80e82-231">In PowerShell, si crea prima il criterio degli allegati sicuri, quindi si crea la regola degli allegati sicuri che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="80e82-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="80e82-232">In PowerShell, le impostazioni nel criterio degli allegati sicuri e nella regola degli allegati sicuri vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="80e82-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="80e82-233">Quando si rimuove un criterio di allegato sicuro da PowerShell, la regola degli allegati sicuri corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="80e82-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="80e82-234">Usare PowerShell per creare criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="80e82-235">La creazione di un criterio allegati sicuri in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="80e82-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="80e82-236">Creare il criterio degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="80e82-237">Creare la regola degli allegati sicuri che specifica il criterio degli allegati sicuri a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="80e82-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="80e82-238">**Note**:</span><span class="sxs-lookup"><span data-stu-id="80e82-238">**Notes**:</span></span>

- <span data-ttu-id="80e82-239">È possibile creare una nuova regola degli allegati sicuri e assegnarle un criterio di allegato sicuro non associato esistente.</span><span class="sxs-lookup"><span data-stu-id="80e82-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="80e82-240">Una regola degli allegati sicuri non può essere associata a più criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="80e82-241">È possibile configurare le impostazioni seguenti nei nuovi criteri allegati sicuri in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="80e82-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="80e82-242">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="80e82-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="80e82-243">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="80e82-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="80e82-244">Un nuovo criterio di allegato sicuro creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="80e82-245">Passaggio 1: Usare PowerShell per creare criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="80e82-246">Per creare criteri allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="80e82-247">In questo esempio viene creato un criterio di allegato sicuro denominato Contoso All con i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e82-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="80e82-248">Bloccare i messaggi che vengono trovati come contenenti malware dall'analisi dei documenti sicuri (non viene utilizzato il parametro _Action_ e il valore predefinito è `Block` ).</span><span class="sxs-lookup"><span data-stu-id="80e82-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="80e82-249">Il reindirizzamento è abilitato e i messaggi che contengono malware vengono inviati a sec-ops@contoso.com per l'analisi e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="80e82-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="80e82-250">Se l'analisi degli allegati sicuri non è disponibile o si verificano errori, non recapitare il messaggio (non viene utilizzato il _parametro ActionOnError_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="80e82-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="80e82-251">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentPolicy.](/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="80e82-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="80e82-252">Passaggio 2: Usare PowerShell per creare una regola degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="80e82-253">Per creare una regola degli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="80e82-254">In questo esempio viene creata una regola di allegato sicura denominata Contoso All con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e82-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="80e82-255">La regola è associata al criterio degli allegati sicuri denominato Contoso All.</span><span class="sxs-lookup"><span data-stu-id="80e82-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="80e82-256">La regola si applica a tutti i destinatari del contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="80e82-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="80e82-257">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="80e82-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="80e82-258">La regola è abilitata (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="80e82-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="80e82-259">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="80e82-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="80e82-260">Usare PowerShell per visualizzare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="80e82-261">Per visualizzare i criteri allegati sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="80e82-262">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="80e82-263">In questo esempio vengono restituite informazioni dettagliate per il criterio degli allegati sicuri denominato Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="80e82-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="80e82-264">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="80e82-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="80e82-265">Usare PowerShell per visualizzare le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="80e82-266">Per visualizzare le regole degli allegati sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="80e82-267">In questo esempio viene restituito un elenco riepilogativo di tutte le regole degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="80e82-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="80e82-268">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e82-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="80e82-269">In questo esempio vengono restituite informazioni dettagliate per la regola degli allegati sicuri denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="80e82-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="80e82-270">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="80e82-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="80e82-271">Utilizzare PowerShell per modificare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="80e82-272">Non è possibile rinominare un criterio degli allegati sicuri in PowerShell (il cmdlet **Set-SafeAttachmentPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="80e82-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="80e82-273">Quando si rinomina un criterio Allegati sicuri nel Centro sicurezza & conformità, si rinomina solo la regola degli allegati _sicuri._</span><span class="sxs-lookup"><span data-stu-id="80e82-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="80e82-274">In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio degli allegati sicuri come descritto nella sezione Passaggio [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) utilizzare PowerShell per creare un criterio di allegati sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="80e82-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="80e82-275">Per modificare un criterio degli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="80e82-276">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span><span class="sxs-lookup"><span data-stu-id="80e82-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="80e82-277">Utilizzare PowerShell per modificare le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="80e82-278">L'unica impostazione non disponibile quando si modifica una regola degli allegati sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="80e82-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="80e82-279">Per abilitare o disabilitare le regole degli allegati sicuri esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="80e82-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="80e82-280">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Utilizzare PowerShell per creare una regola degli allegati sicuri in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="80e82-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="80e82-281">Per modificare una regola degli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="80e82-282">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="80e82-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="80e82-283">Abilitazione o disabilitazione delle regole degli allegati sicuri tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="80e82-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="80e82-284">L'abilitazione o la disabilitazione di una regola degli allegati sicuri in PowerShell abilita o disabilita l'intero criterio Allegati sicuri (la regola degli allegati sicuri e il criterio degli allegati sicuri assegnati).</span><span class="sxs-lookup"><span data-stu-id="80e82-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="80e82-285">Per abilitare o disabilitare una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="80e82-286">In questo esempio viene disabilitata la regola degli allegati sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="80e82-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="80e82-287">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="80e82-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="80e82-288">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) [e Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="80e82-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="80e82-289">Utilizzare PowerShell per impostare la priorità delle regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="80e82-290">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="80e82-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="80e82-291">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="80e82-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="80e82-292">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="80e82-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="80e82-293">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="80e82-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="80e82-294">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="80e82-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="80e82-295">Per impostare la priorità di una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="80e82-p124">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="80e82-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="80e82-298">**Nota:** per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="80e82-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="80e82-299">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="80e82-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="80e82-300">Usare PowerShell per rimuovere i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="80e82-301">Quando si utilizza PowerShell per rimuovere un criterio di allegato sicuro, la regola degli allegati sicuri corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="80e82-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="80e82-302">Per rimuovere un criterio di allegato sicuro in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="80e82-303">In questo esempio viene rimosso il criterio degli allegati sicuri denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="80e82-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="80e82-304">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="80e82-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="80e82-305">Usare PowerShell per rimuovere le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="80e82-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="80e82-306">Quando si utilizza PowerShell per rimuovere una regola degli allegati sicuri, il criterio di allegato sicuro corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="80e82-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="80e82-307">Per rimuovere una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="80e82-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="80e82-308">In questo esempio viene rimossa la regola degli allegati sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="80e82-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="80e82-309">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span><span class="sxs-lookup"><span data-stu-id="80e82-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="80e82-310">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="80e82-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="80e82-311">Per verificare che i criteri allegati sicuri siano stati creati, modificati o rimossi correttamente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80e82-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="80e82-312">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **Allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="80e82-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="80e82-313">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="80e82-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="80e82-314">Per visualizzare altri dettagli, selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="80e82-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="80e82-315">In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, sostituire con il nome del criterio o della regola, eseguire il \<Name\> comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="80e82-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="80e82-316">Per verificare che gli allegati sicuri esempeno l'analisi dei messaggi, controllare i report di Defender for Office 365 disponibili.</span><span class="sxs-lookup"><span data-stu-id="80e82-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="80e82-317">Per ulteriori informazioni, vedere [View reports for Defender for Office 365](view-reports-for-mdo.md) e Use Explorer in the Security & Compliance [Center.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="80e82-317">For more information, see [View reports for Defender for Office 365](view-reports-for-mdo.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
