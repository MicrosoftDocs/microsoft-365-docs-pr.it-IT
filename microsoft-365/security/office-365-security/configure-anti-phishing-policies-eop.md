---
title: Configurare il criterio anti-phishing predefinito in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come modificare le impostazioni di anti-spoofing disponibili nei criteri anti-phishing predefiniti nelle organizzazioni di Office 365 con le cassette postali di Exchange Online.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537534"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="4f82f-103">Configurare il criterio anti-phishing predefinito in EOP</span><span class="sxs-lookup"><span data-stu-id="4f82f-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="4f82f-104">Le organizzazioni di Office 365 con le cassette postali di Exchange Online e le organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online dispongono di un criterio antiphishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="4f82f-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="4f82f-105">Questo criterio contiene un numero limitato di funzionalità di anti-spoofing che sono abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4f82f-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="4f82f-106">Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="4f82f-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="4f82f-107">Le organizzazioni di Office 365 che dispongono di cassette postali di Exchange Online possono modificare il criterio anti-phishing predefinito nel centro sicurezza & conformità di Office 365 o in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4f82f-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="4f82f-108">Le organizzazioni di EOP autonome senza le cassette postali di Exchange Online non possono modificare i criteri anti-phishing predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4f82f-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="4f82f-109">Per informazioni sulla creazione e la modifica dei criteri di anti-phishing ATP più avanzati disponibili in Office 365 Advanced Threat Protection, vedere [configurare i criteri di anti-phishing ATP in office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4f82f-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4f82f-110">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4f82f-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4f82f-111">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4f82f-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4f82f-112">Per passare direttamente alla pagina **anti-phishing** , utilizzare <https://protection.office.com/antiphishing>.</span><span class="sxs-lookup"><span data-stu-id="4f82f-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="4f82f-113">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4f82f-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4f82f-114">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="4f82f-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="4f82f-115">Per aggiungere, modificare ed eliminare i criteri di anti-phishing, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="4f82f-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="4f82f-116">Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="4f82f-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="4f82f-117">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità di Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4f82f-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="4f82f-118">Per le impostazioni consigliate per il criterio anti-phishing predefinito, vedere [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="4f82f-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="4f82f-119">Consentire l'applicazione dei criteri aggiornati fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="4f82f-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="4f82f-120">Per informazioni su dove vengono applicati i criteri di anti-phishing nella pipeline dei filtri, vedere [ordine e precedenza della protezione della posta elettronica in Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="4f82f-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="4f82f-121">Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito</span><span class="sxs-lookup"><span data-stu-id="4f82f-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="4f82f-122">Il criterio anti-phishing predefinito è denominato Office365 antiphishing default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="4f82f-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="4f82f-123">Per modificare il criterio anti-phishing predefinito, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f82f-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="4f82f-124">Nel centro sicurezza & conformità, accedere a **criterio** \> di **gestione** \> delle minacce **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="4f82f-125">Nella pagina **anti-phishing** fare clic su **criteri predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="4f82f-126">Viene visualizzata la pagina **modifica il criterio Office365 antiphishing predefinita** .</span><span class="sxs-lookup"><span data-stu-id="4f82f-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="4f82f-127">Nella sezione **spoofing** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="4f82f-128">Si noti che queste impostazioni sono identiche alle impostazioni di spoofing disponibili nei criteri di anti-phishing ATP.</span><span class="sxs-lookup"><span data-stu-id="4f82f-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="4f82f-129">**Impostazioni del filtro di spoofing**: il valore predefinito **è attivato**e si consiglia di lasciarlo acceso.</span><span class="sxs-lookup"><span data-stu-id="4f82f-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="4f82f-130">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="4f82f-131">Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="4f82f-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="4f82f-132">Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Office 365; è invece possibile abilitare il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="4f82f-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="4f82f-133">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="4f82f-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="4f82f-134">**Abilita funzionalità mittente non autenticato**: aggiunge un punto interrogativo alla foto del mittente se il messaggio non supera i controlli di autenticazione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4f82f-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="4f82f-135">Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="4f82f-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="4f82f-136">Il valore predefinito è **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-136">The default value is **On**.</span></span> <span data-ttu-id="4f82f-137">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="4f82f-138">**Azioni**: specificare l'azione da intraprendere per i messaggi che non superano l'intelligence spoof:</span><span class="sxs-lookup"><span data-stu-id="4f82f-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="4f82f-139">**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio**:</span><span class="sxs-lookup"><span data-stu-id="4f82f-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="4f82f-140">**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** (questo è il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="4f82f-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="4f82f-141">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="4f82f-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="4f82f-142">**Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="4f82f-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="4f82f-143">È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="4f82f-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="4f82f-144">È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:</span><span class="sxs-lookup"><span data-stu-id="4f82f-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="4f82f-145">**Abilitare la protezione antispoofing**</span><span class="sxs-lookup"><span data-stu-id="4f82f-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="4f82f-146">**Abilitare la funzionalità mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="4f82f-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="4f82f-147">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="4f82f-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="4f82f-148">Tornare alla pagina **Edit your Policy Office365 antiphishing default** , rivedere le impostazioni e fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="4f82f-149">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di anti-phishing predefiniti</span><span class="sxs-lookup"><span data-stu-id="4f82f-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="4f82f-150">Nel centro sicurezza & conformità e passare a **criteri** \> di **gestione** \> delle minacce **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="4f82f-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="4f82f-151">Fare clic su **criteri predefiniti** per visualizzare i criteri di anti-phishing predefiniti.</span><span class="sxs-lookup"><span data-stu-id="4f82f-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="4f82f-152">Utilizzo di PowerShell di Exchange Online per configurare i criteri di anti-phishing predefiniti</span><span class="sxs-lookup"><span data-stu-id="4f82f-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="4f82f-153">Utilizzo di PowerShell per visualizzare i criteri anti-phishing predefiniti</span><span class="sxs-lookup"><span data-stu-id="4f82f-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="4f82f-154">Per visualizzare i criteri anti-phishing predefiniti, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4f82f-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="4f82f-155">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="4f82f-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="4f82f-156">Utilizzo di PowerShell per modificare il criterio anti-phishing predefinito</span><span class="sxs-lookup"><span data-stu-id="4f82f-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="4f82f-157">Per modificare i criteri anti-phishing predefiniti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4f82f-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="4f82f-158">In questo esempio viene modificata l'azione per i messaggi falsificati che non riescono a controllare l'autenticazione in quarantena.</span><span class="sxs-lookup"><span data-stu-id="4f82f-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="4f82f-159">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="4f82f-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4f82f-160">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="4f82f-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="4f82f-161">Per verificare di aver configurato correttamente il criterio anti-phishing predefinito, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f82f-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="4f82f-162">Nel centro sicurezza & conformità, accedere **a criterio di** \> **gestione** \> delle minacce **anti-phishing** \> fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="4f82f-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="4f82f-163">In PowerShell di Exchange Online, eseguire il comando riportato di seguito e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4f82f-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
