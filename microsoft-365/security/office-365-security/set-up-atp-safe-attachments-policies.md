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
ms.openlocfilehash: 9343ce222f1deb84e900f0d6f18e7d55daa73372
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084614"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="99df8-103">Configurare i criteri allegati sicuri in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="99df8-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="99df8-104">Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="99df8-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="99df8-105">Per informazioni sull'analisi degli allegati in Outlook, vedere [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="99df8-105">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="99df8-106">Allegati sicuri è una funzionalità di Microsoft Defender per [Office 365](office-365-atp.md) che utilizza un ambiente virtuale per controllare gli allegati nei messaggi di posta elettronica in ingresso dopo che sono stati analizzati dalla protezione [antimalware in Exchange Online Protection (EOP),](anti-malware-protection.md)ma prima del recapito ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="99df8-106">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="99df8-107">Per altre informazioni, vedere [Allegati sicuri in Microsoft Defender per Office 365.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="99df8-107">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="99df8-108">Non esiste un criterio predefinito per gli allegati sicuri o predefinito.</span><span class="sxs-lookup"><span data-stu-id="99df8-108">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="99df8-109">Per ottenere l'analisi degli allegati dei messaggi di posta elettronica con allegati sicuri, è necessario creare uno o più criteri allegati sicuri come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="99df8-109">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="99df8-110">È possibile configurare i criteri allegati sicuri nel Centro sicurezza & conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi Defender per Office 365).</span><span class="sxs-lookup"><span data-stu-id="99df8-110">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="99df8-111">Gli elementi di base di un criterio Allegati sicuri sono:</span><span class="sxs-lookup"><span data-stu-id="99df8-111">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="99df8-112">**Il** criterio allegati sicuri : specifica le azioni per i rilevamenti di malware sconosciuti, se inviare messaggi con allegati di malware a un indirizzo di posta elettronica specificato e se recapitare i messaggi se l'analisi degli allegati sicuri non può essere completata.</span><span class="sxs-lookup"><span data-stu-id="99df8-112">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="99df8-113">**La regola degli allegati sicuri**: specifica la priorità e i filtri destinatario (a chi si applica il criterio).</span><span class="sxs-lookup"><span data-stu-id="99df8-113">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="99df8-114">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri allegati sicuri nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="99df8-114">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="99df8-115">Quando si crea un criterio Allegati sicuri, si crea contemporaneamente una regola per gli allegati sicuri e il criterio allegati sicuri associato utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="99df8-115">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="99df8-116">Quando si modifica un criterio Allegati sicuri, le impostazioni relative al nome, alla priorità, all'allegato abilitato o disabilitato e ai filtri destinatari modificano la regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-116">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="99df8-117">Tutte le altre impostazioni modificano il criterio degli allegati sicuri associato.</span><span class="sxs-lookup"><span data-stu-id="99df8-117">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="99df8-118">Quando si rimuove un criterio Allegati sicuri, vengono rimossi la regola degli allegati sicuri e il criterio allegato sicuro associato.</span><span class="sxs-lookup"><span data-stu-id="99df8-118">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="99df8-119">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="99df8-119">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="99df8-120">Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online o [PowerShell EOP](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) autonomo per configurare i criteri allegati sicuri più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="99df8-120">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="99df8-121">Nell'area delle impostazioni globali delle impostazioni allegati sicuri è possibile configurare caratteristiche che non dipendono dai criteri Allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-121">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="99df8-122">Per istruzioni, vedere Attivare allegati sicuri [per SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e Documenti sicuri in Microsoft [365 E5.](safe-docs.md)</span><span class="sxs-lookup"><span data-stu-id="99df8-122">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="99df8-123">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="99df8-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="99df8-124">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="99df8-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="99df8-125">Per passare direttamente alla **pagina Allegati sicuri,** utilizzare <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="99df8-125">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="99df8-126">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="99df8-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="99df8-127">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="99df8-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="99df8-128">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99df8-128">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="99df8-129">Per creare, modificare ed eliminare i criteri allegati sicuri,  è necessario essere membri dei gruppi di ruoli Gestione organizzazione  o Amministratore sicurezza nel Centro sicurezza & conformità e membri del gruppo di ruoli Gestione organizzazione in Exchange Online.  </span><span class="sxs-lookup"><span data-stu-id="99df8-129">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="99df8-130">Per l'accesso in sola lettura ai criteri allegati  sicuri,  è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="99df8-130">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="99df8-131">Per ulteriori informazioni, vedere [Autorizzazioni nel Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md) e Autorizzazioni in Exchange [Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="99df8-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="99df8-132">**Note**:</span><span class="sxs-lookup"><span data-stu-id="99df8-132">**Notes**:</span></span>

  - <span data-ttu-id="99df8-133">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="99df8-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="99df8-134">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="99df8-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="99df8-135">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="99df8-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="99df8-136">Per le impostazioni consigliate per i criteri allegati sicuri, vedere [Impostazioni allegati sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="99df8-136">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="99df8-137">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="99df8-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="99df8-138">Usare il Centro sicurezza & conformità per creare criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-138">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="99df8-139">La creazione di un criterio allegati sicuri personalizzato nel Centro sicurezza & conformità crea la regola degli allegati sicuri e il criterio allegati sicuri associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="99df8-139">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="99df8-140">Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="99df8-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="99df8-141">Nella pagina **Allegati sicuri** fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="99df8-141">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="99df8-142">Verrà **visualizzata la procedura guidata nuovo criterio Allegati** sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-142">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="99df8-143">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99df8-143">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="99df8-144">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="99df8-144">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="99df8-145">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="99df8-145">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="99df8-146">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="99df8-146">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="99df8-147">Nella pagina **Impostazioni** visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99df8-147">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="99df8-148">**Risposta malware sconosciuto allegati sicuri**: selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="99df8-148">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="99df8-149">**Disattivato:** in genere, questo valore non è consigliato.</span><span class="sxs-lookup"><span data-stu-id="99df8-149">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="99df8-150">**Monitor**</span><span class="sxs-lookup"><span data-stu-id="99df8-150">**Monitor**</span></span>
     - <span data-ttu-id="99df8-151">**Blocco:** questo è il valore predefinito e il valore consigliato nei criteri di sicurezza standard [e rigidi.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="99df8-151">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="99df8-152">**Sostituisce**</span><span class="sxs-lookup"><span data-stu-id="99df8-152">**Replace**</span></span>
     - <span data-ttu-id="99df8-153">**Recapito dinamico (funzionalità di anteprima)**</span><span class="sxs-lookup"><span data-stu-id="99df8-153">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="99df8-154">Questi valori sono illustrati nelle [impostazioni dei criteri allegati sicuri.](atp-safe-attachments.md#safe-attachments-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="99df8-154">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="99df8-155">Inviare l'allegato al seguente indirizzo di posta **elettronica:** per  i valori di azione **Blocca,** Monitora o **Sostituisci,** è possibile selezionare Abilita reindirizzamento per inviare messaggi contenenti allegati di malware all'indirizzo di posta elettronica interno o esterno specificato per l'analisi e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="99df8-155">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="99df8-156">Per le impostazioni dei criteri Standard e Strict è consigliabile abilitare il reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="99df8-156">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="99df8-157">Per ulteriori informazioni, vedere [Impostazioni allegati sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)</span><span class="sxs-lookup"><span data-stu-id="99df8-157">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="99df8-158">**Applicare la selezione** precedente se si verifica il timeout o  l'errore dell'analisi antimalware per gli allegati: l'azione specificata dalla risposta malware sconosciuto allegati sicuri viene eseguita sui messaggi anche quando l'analisi degli allegati sicuri non può essere completata.</span><span class="sxs-lookup"><span data-stu-id="99df8-158">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="99df8-159">Se è stata selezionata questa opzione, selezionare sempre **Reindirizzamento abilitato.**</span><span class="sxs-lookup"><span data-stu-id="99df8-159">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="99df8-160">In caso contrario, i messaggi potrebbero essere persi.</span><span class="sxs-lookup"><span data-stu-id="99df8-160">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="99df8-161">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="99df8-161">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="99df8-162">Nella pagina **Applicato a** visualizzata, identificare i destinatari interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="99df8-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="99df8-163">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="99df8-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="99df8-164">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="99df8-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="99df8-165">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="99df8-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="99df8-166">Fare **clic su Aggiungi condizione.**</span><span class="sxs-lookup"><span data-stu-id="99df8-166">Click **Add a condition**.</span></span> <span data-ttu-id="99df8-167">Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se:**</span><span class="sxs-lookup"><span data-stu-id="99df8-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="99df8-168">**Il destinatario è**: specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="99df8-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="99df8-169">**Il destinatario è membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="99df8-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="99df8-170">**Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="99df8-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="99df8-171">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una qualsiasi di queste** caselle.</span><span class="sxs-lookup"><span data-stu-id="99df8-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="99df8-172">Fare clic nella casella e scorrere l'elenco dei valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="99df8-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="99df8-173">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="99df8-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="99df8-174">Per aggiungere ulteriori valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="99df8-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="99df8-175">Per rimuovere singole voci, fare **clic sull'icona** ![ Rimuovi sul ](../../media/scc-remove-icon.png) valore.</span><span class="sxs-lookup"><span data-stu-id="99df8-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="99df8-176">Per rimuovere l'intera condizione, fare **clic sull'icona** ![ Rimuovi nella ](../../media/scc-remove-icon.png) condizione.</span><span class="sxs-lookup"><span data-stu-id="99df8-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="99df8-177">Per aggiungere una condizione aggiuntiva, fare **clic su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se.**</span><span class="sxs-lookup"><span data-stu-id="99df8-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="99df8-178">Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**.</span><span class="sxs-lookup"><span data-stu-id="99df8-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="99df8-179">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="99df8-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="99df8-180">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="99df8-180">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="99df8-181">Nella pagina **Controlla le impostazioni** visualizzata, rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="99df8-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="99df8-182">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="99df8-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="99df8-183">Al termine dell'operazione, scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="99df8-183">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="99df8-184">Usare il Centro sicurezza & conformità per visualizzare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-184">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="99df8-185">Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="99df8-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="99df8-186">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="99df8-186">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="99df8-187">I dettagli dei criteri vengono visualizzati in un riquadro a comparsa</span><span class="sxs-lookup"><span data-stu-id="99df8-187">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="99df8-188">Utilizzare il Centro sicurezza & conformità per modificare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-188">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="99df8-189">Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="99df8-189">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="99df8-190">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="99df8-190">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="99df8-191">Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic **su Modifica criterio.**</span><span class="sxs-lookup"><span data-stu-id="99df8-191">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="99df8-192">Le impostazioni disponibili nel riquadro a comparsa visualizzate sono identiche a quelle descritte nella sezione Usare il Centro sicurezza [&](#use-the-security--compliance-center-to-create-safe-attachments-policies) conformità per creare criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-192">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="99df8-193">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="99df8-193">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="99df8-194">Abilitare o disabilitare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-194">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="99df8-195">Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="99df8-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="99df8-196">Si noti il valore nella **colonna** Stato:</span><span class="sxs-lookup"><span data-stu-id="99df8-196">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="99df8-197">Spostare l'interruttore a sinistra</span><span class="sxs-lookup"><span data-stu-id="99df8-197">Move the toggle to the left</span></span> ![Disattivare i criteri](../../media/scc-toggle-off.png) <span data-ttu-id="99df8-199">per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="99df8-199">to disable the policy.</span></span>

   - <span data-ttu-id="99df8-200">Spostare l'interruttore verso destra</span><span class="sxs-lookup"><span data-stu-id="99df8-200">Move the toggle to the right</span></span> ![Attivare i criteri](../../media/scc-toggle-on.png) <span data-ttu-id="99df8-202">per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="99df8-202">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="99df8-203">Impostare la priorità dei criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-203">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="99df8-204">Per impostazione predefinita, ai criteri allegati sicuri viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="99df8-204">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="99df8-205">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="99df8-205">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="99df8-206">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="99df8-206">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="99df8-207">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="99df8-207">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="99df8-208">I criteri allegati sicuri vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore priority** 0).</span><span class="sxs-lookup"><span data-stu-id="99df8-208">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="99df8-209">**Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio Allegati sicuri solo dopo la creazione.</span><span class="sxs-lookup"><span data-stu-id="99df8-209">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="99df8-210">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola degli allegati sicuri (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="99df8-210">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="99df8-211">Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="99df8-211">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="99df8-212">Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="99df8-212">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="99df8-213">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="99df8-213">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="99df8-214">Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic sul pulsante di priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="99df8-214">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="99df8-215">Per il criterio Allegati sicuri con **valore Priorità** **0** è disponibile solo il **pulsante Diminuisci** priorità.</span><span class="sxs-lookup"><span data-stu-id="99df8-215">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="99df8-216">Per il criterio Allegati sicuri con il valore **di priorità** più basso (ad esempio, **3)** è disponibile solo il pulsante **Aumenta** priorità.</span><span class="sxs-lookup"><span data-stu-id="99df8-216">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="99df8-217">Se si dispone di tre o più criteri allegati sicuri,  i criteri tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e **Diminuisci** priorità disponibili.</span><span class="sxs-lookup"><span data-stu-id="99df8-217">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="99df8-218">Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **di** Priorità.</span><span class="sxs-lookup"><span data-stu-id="99df8-218">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="99df8-219">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="99df8-219">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="99df8-220">Usare il Centro sicurezza & conformità per rimuovere i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-220">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="99df8-221">Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="99df8-221">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="99df8-222">Nella pagina **Allegati sicuri** selezionare un criterio dall'elenco e fare clic su di esso (non selezionare la casella di controllo).</span><span class="sxs-lookup"><span data-stu-id="99df8-222">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="99df8-223">Nel riquadro a comparsa dei dettagli del criterio visualizzato, fare clic su Elimina criterio **e** quindi su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="99df8-223">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="99df8-224">Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per configurare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-224">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="99df8-225">Come descritto in precedenza, i criteri allegati sicuri sono costituiti da un criterio allegati sicuri e da una regola per gli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-225">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="99df8-226">In PowerShell, la differenza tra i criteri allegati sicuri e le regole degli allegati sicuri è evidente.</span><span class="sxs-lookup"><span data-stu-id="99df8-226">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="99df8-227">È possibile gestire i criteri allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentPolicy** e gestire le regole degli allegati sicuri utilizzando i cmdlet **\* -SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="99df8-227">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="99df8-228">In PowerShell, si crea prima il criterio degli allegati sicuri, quindi si crea la regola degli allegati sicuri che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="99df8-228">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="99df8-229">In PowerShell, è possibile modificare le impostazioni nei criteri allegati sicuri e nella regola degli allegati sicuri separatamente.</span><span class="sxs-lookup"><span data-stu-id="99df8-229">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="99df8-230">Quando si rimuove un criterio allegati sicuri da PowerShell, la regola degli allegati sicuri corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="99df8-230">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="99df8-231">Utilizzare PowerShell per creare criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-231">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="99df8-232">La creazione di un criterio allegati sicuri in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="99df8-232">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="99df8-233">Creare il criterio allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-233">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="99df8-234">Creare la regola degli allegati sicuri che specifica il criterio allegati sicuri a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="99df8-234">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="99df8-235">**Note**:</span><span class="sxs-lookup"><span data-stu-id="99df8-235">**Notes**:</span></span>

- <span data-ttu-id="99df8-236">È possibile creare una nuova regola per gli allegati sicuri e assegnarle un criterio di allegati sicuri non associato esistente.</span><span class="sxs-lookup"><span data-stu-id="99df8-236">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="99df8-237">Una regola degli allegati sicuri non può essere associata a più criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-237">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="99df8-238">È possibile configurare le impostazioni seguenti nei nuovi criteri allegati sicuri in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="99df8-238">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="99df8-239">Creare il nuovo criterio come disabilitato (_abilitato_ `$false` nel cmdlet **New-SafeAttachmentRule).**</span><span class="sxs-lookup"><span data-stu-id="99df8-239">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="99df8-240">Impostare la priorità del criterio durante la creazione (_Priority_ ) nel _\<Number\>_ cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="99df8-240">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="99df8-241">Un nuovo criterio allegati sicuri creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-241">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="99df8-242">Passaggio 1: Utilizzare PowerShell per creare un criterio allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-242">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="99df8-243">Per creare un criterio allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-243">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="99df8-244">In questo esempio viene creato un criterio allegati sicuri denominato Contoso All con i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="99df8-244">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="99df8-245">Bloccare i messaggi che vengono trovati come contenenti malware dall'analisi dei documenti sicuri (non viene utilizzato il parametro _Action_ e il valore predefinito è `Block` ).</span><span class="sxs-lookup"><span data-stu-id="99df8-245">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="99df8-246">Il reindirizzamento è abilitato e i messaggi che contengono malware vengono inviati a sec-ops@contoso.com per l'analisi e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="99df8-246">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="99df8-247">Se l'analisi degli allegati sicuri non è disponibile o si verificano errori, non recapitare il messaggio (non viene utilizzato il parametro _ActionOnError_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="99df8-247">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="99df8-248">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="99df8-248">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="99df8-249">Passaggio 2: Utilizzare PowerShell per creare una regola degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-249">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="99df8-250">Per creare una regola per gli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-250">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="99df8-251">In questo esempio viene creata una regola per gli allegati sicuri denominata Contoso All con le seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="99df8-251">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="99df8-252">La regola è associata al criterio degli allegati sicuri denominato Contoso All.</span><span class="sxs-lookup"><span data-stu-id="99df8-252">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="99df8-253">La regola si applica a tutti i destinatari nel contoso.com dominio.</span><span class="sxs-lookup"><span data-stu-id="99df8-253">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="99df8-254">Poiché non viene utilizzato il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="99df8-254">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="99df8-255">La regola è abilitata (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="99df8-255">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="99df8-256">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="99df8-256">For detailed syntax and parameter information, see [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="99df8-257">Utilizzare PowerShell per visualizzare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-257">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="99df8-258">Per visualizzare i criteri allegati sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-258">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="99df8-259">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-259">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="99df8-260">In questo esempio vengono restituite informazioni dettagliate per il criterio allegati sicuri denominato Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="99df8-260">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="99df8-261">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="99df8-261">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="99df8-262">Utilizzare PowerShell per visualizzare le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-262">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="99df8-263">Per visualizzare le regole degli allegati sicuri esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-263">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="99df8-264">In questo esempio viene restituito un elenco riepilogativo di tutte le regole degli allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="99df8-264">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="99df8-265">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="99df8-265">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="99df8-266">In questo esempio vengono restituite informazioni dettagliate per la regola degli allegati sicuri denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="99df8-266">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="99df8-267">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="99df8-267">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="99df8-268">Utilizzare PowerShell per modificare i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-268">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="99df8-269">Non è possibile rinominare un criterio allegati sicuri in PowerShell (il cmdlet **Set-SafeAttachmentPolicy** non ha un _parametro_ Name).</span><span class="sxs-lookup"><span data-stu-id="99df8-269">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="99df8-270">Quando si rinomina un criterio Allegati sicuri nel Centro sicurezza & conformità, si rinomina solo la regola degli allegati _sicuri._</span><span class="sxs-lookup"><span data-stu-id="99df8-270">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="99df8-271">In caso contrario, le stesse impostazioni sono disponibili quando si crea un criterio allegati sicuri come descritto nel passaggio [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Utilizzare PowerShell per creare una sezione dei criteri allegati sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="99df8-271">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="99df8-272">Per modificare un criterio allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-272">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="99df8-273">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="99df8-273">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="99df8-274">Utilizzare PowerShell per modificare le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-274">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="99df8-275">L'unica impostazione non disponibile quando si modifica una regola degli allegati sicuri in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="99df8-275">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="99df8-276">Per abilitare o disabilitare le regole degli allegati sicuri esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="99df8-276">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="99df8-277">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nel passaggio [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Utilizzare PowerShell per creare una regola degli allegati sicuri più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="99df8-277">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="99df8-278">Per modificare una regola degli allegati sicuri, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-278">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="99df8-279">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="99df8-279">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="99df8-280">Abilitazione o disabilitazione delle regole degli allegati sicuri tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="99df8-280">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="99df8-281">L'abilitazione o la disabilitazione di una regola degli allegati sicuri in PowerShell abilita o disabilita l'intero criterio Allegati sicuri (la regola degli allegati sicuri e il criterio degli allegati sicuri assegnato).</span><span class="sxs-lookup"><span data-stu-id="99df8-281">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="99df8-282">Per abilitare o disabilitare una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-282">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="99df8-283">In questo esempio viene disabilitata la regola degli allegati sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="99df8-283">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="99df8-284">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="99df8-284">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="99df8-285">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) [e Disable-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="99df8-285">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="99df8-286">Utilizzare PowerShell per impostare la priorità delle regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-286">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="99df8-287">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="99df8-287">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="99df8-288">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="99df8-288">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="99df8-289">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="99df8-289">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="99df8-290">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="99df8-290">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="99df8-291">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="99df8-291">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="99df8-292">Per impostare la priorità di una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-292">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="99df8-p124">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="99df8-p124">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="99df8-295">**Nota:** per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-SafeAttachmentRule.**</span><span class="sxs-lookup"><span data-stu-id="99df8-295">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="99df8-296">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="99df8-296">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="99df8-297">Utilizzare PowerShell per rimuovere i criteri allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-297">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="99df8-298">Quando si utilizza PowerShell per rimuovere un criterio allegati sicuri, la regola degli allegati sicuri corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="99df8-298">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="99df8-299">Per rimuovere un criterio allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-299">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="99df8-300">In questo esempio viene rimosso il criterio allegati sicuri denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="99df8-300">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="99df8-301">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)</span><span class="sxs-lookup"><span data-stu-id="99df8-301">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="99df8-302">Utilizzare PowerShell per rimuovere le regole degli allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="99df8-302">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="99df8-303">Quando si utilizza PowerShell per rimuovere una regola degli allegati sicuri, il criterio degli allegati sicuri corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="99df8-303">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="99df8-304">Per rimuovere una regola degli allegati sicuri in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="99df8-304">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="99df8-305">In questo esempio viene rimossa la regola degli allegati sicuri denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="99df8-305">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="99df8-306">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SafeAttachmentRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)</span><span class="sxs-lookup"><span data-stu-id="99df8-306">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="99df8-307">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="99df8-307">How do you know these procedures worked?</span></span>

<span data-ttu-id="99df8-308">Per verificare che i criteri allegati sicuri siano stati creati, modificati o rimossi correttamente, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="99df8-308">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="99df8-309">Nel Centro sicurezza & conformità passare a **Allegati** sicuri dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="99df8-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="99df8-310">Verificare l'elenco dei criteri, i relativi **valori di** stato e i relativi **valori di** priorità.</span><span class="sxs-lookup"><span data-stu-id="99df8-310">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="99df8-311">Per visualizzare altri dettagli, selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="99df8-311">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="99df8-312">In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, sostituire con il nome del criterio o della regola, eseguire il comando seguente \<Name\> e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="99df8-312">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="99df8-313">Per verificare che allegati sicuri eseere in corso l'analisi dei messaggi, controllare i report di Defender per Office 365 disponibili.</span><span class="sxs-lookup"><span data-stu-id="99df8-313">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="99df8-314">Per altre informazioni, vedere [Visualizzare i report per Defender per Office 365](view-reports-for-atp.md) e Usare Esplora risorse nel Centro sicurezza & [conformità.](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="99df8-314">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>
