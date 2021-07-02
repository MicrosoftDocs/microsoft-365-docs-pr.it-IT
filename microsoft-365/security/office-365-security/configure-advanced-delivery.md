---
title: Configurare il recapito di simulazioni di phishing di terze parti agli utenti e messaggi non filtrati alle cassette postali secOps
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Gli amministratori possono imparare a utilizzare i criteri di recapito avanzati in Exchange Online Protection (EOP) per identificare i messaggi che non devono essere filtrati in scenari supportati specifici (simulazioni di phishing di terze parti e messaggi recapitati alle cassette postali secOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 053f88da96983b03ad03e75c11a4fa692ac6a850
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256868"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a><span data-ttu-id="51ee9-103">Configurare il recapito di simulazioni di phishing di terze parti agli utenti e messaggi non filtrati alle cassette postali secOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-103">Configure the delivery of third-party phishing simulations to users and unfiltered messages to SecOps mailboxes</span></span>

<span data-ttu-id="51ee9-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="51ee9-104">**Applies to**</span></span>
- [<span data-ttu-id="51ee9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="51ee9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="51ee9-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="51ee9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="51ee9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51ee9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="51ee9-108">La funzionalità descritta in questo articolo è disponibile in Anteprima, non è disponibile per tutti gli utenti ed è soggetta a modifiche.</span><span class="sxs-lookup"><span data-stu-id="51ee9-108">The feature that's described in this article is in Preview, isn't available to everyone, and is subject to change.</span></span>

<span data-ttu-id="51ee9-109">Per proteggere [l'organizzazione](secure-by-default.md)per impostazione predefinita, Exchange Online Protection (EOP) non consente elenchi attendibili o bypass di filtro per i messaggi identificati come malware o phishing ad alta probabilità.</span><span class="sxs-lookup"><span data-stu-id="51ee9-109">To keep your organization [secure by default](secure-by-default.md), Exchange Online Protection (EOP) does not allow safe lists or filtering bypass for messages that are identified as malware or high confidence phishing.</span></span> <span data-ttu-id="51ee9-110">Esistono tuttavia scenari specifici che richiedono il recapito di messaggi non filtrati.</span><span class="sxs-lookup"><span data-stu-id="51ee9-110">But, there are specific scenarios that require the delivery of unfiltered messages.</span></span> <span data-ttu-id="51ee9-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="51ee9-111">For example:</span></span>

- <span data-ttu-id="51ee9-112">**Simulazioni di phishing di terze** parti: gli attacchi simulati consentono di identificare gli utenti vulnerabili prima che un attacco reale influisca sull'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="51ee9-112">**Third-party phishing simulations**: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="51ee9-113">Cassette postali delle operazioni di sicurezza **(SecOps):** cassette postali dedicate utilizzate dai team di sicurezza per raccogliere e analizzare i messaggi non filtrati (buoni e non).</span><span class="sxs-lookup"><span data-stu-id="51ee9-113">**Security operations (SecOps) mailboxes**: Dedicated mailboxes that are used by security teams to collect and analyze unfiltered messages (both good and bad).</span></span>

<span data-ttu-id="51ee9-114">È possibile utilizzare _i criteri di_ recapito avanzati in Microsoft 365 per impedire che questi messaggi in questi scenari _specifici_ vengano filtrati. <sup>\*</sup> Il criterio di recapito avanzato garantisce che i messaggi in questi scenari raggiunga i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-114">You use the _advanced delivery policy_ in Microsoft 365 to prevent these messages _in these specific scenarios_ from being filtered.<sup>\*</sup> The advanced delivery policy ensures that messages in these scenarios achieve the following results:</span></span>

- <span data-ttu-id="51ee9-115">I filtri in EOP e Microsoft Defender per Office 365 non esempre alcuna azione su questi messaggi.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51ee9-115">Filters in EOP and Microsoft Defender for Office 365 take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="51ee9-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="51ee9-116">[Zero-hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup></span></span>
- <span data-ttu-id="51ee9-117">[Gli avvisi di](alerts.md) sistema predefiniti non vengono attivati per questi scenari.</span><span class="sxs-lookup"><span data-stu-id="51ee9-117">[Default system alerts](alerts.md) aren't triggered for these scenarios.</span></span>
- <span data-ttu-id="51ee9-118">[AIR e clustering in Defender per Office 365](office-365-air.md) ignora questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="51ee9-118">[AIR and clustering in Defender for Office 365](office-365-air.md) ignores these messages.</span></span>
- <span data-ttu-id="51ee9-119">In particolare per simulazioni di phishing di terze parti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-119">Specifically for third-party phishing simulations:</span></span>
  - <span data-ttu-id="51ee9-120">[Gli invii di](admin-submission.md) amministratori generano una risposta automatica che indica che il messaggio fa parte di una campagna di simulazione di phishing e non è una minaccia reale.</span><span class="sxs-lookup"><span data-stu-id="51ee9-120">[Admin submissions](admin-submission.md) generates an automatic response saying that the message is part of a phishing simulation campaign and isn't a real threat.</span></span> <span data-ttu-id="51ee9-121">Gli avvisi e AIR non verranno attivati.</span><span class="sxs-lookup"><span data-stu-id="51ee9-121">Alerts and AIR will not be triggered.</span></span>
  - <span data-ttu-id="51ee9-122">[Cassaforte link in Defender per Office 365](safe-links.md) non blocca o fa detonare gli URL identificati in modo specifico in questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="51ee9-122">[Safe Links in Defender for Office 365](safe-links.md) doesn't block or detonate the specifically identified URLs in these messages.</span></span>
  - <span data-ttu-id="51ee9-123">[Cassaforte allegati in Defender per Office 365](safe-attachments.md) non fa detonare gli allegati in questi messaggi.</span><span class="sxs-lookup"><span data-stu-id="51ee9-123">[Safe Attachments in Defender for Office 365](safe-attachments.md) doesn't detonate attachments in these messages.</span></span>

<span data-ttu-id="51ee9-124"><sup>\*</sup> Non è possibile ignorare il filtro antimalware o ZAP per il malware.</span><span class="sxs-lookup"><span data-stu-id="51ee9-124"><sup>\*</sup> You can't bypass malware filtering or ZAP for malware.</span></span>

<span data-ttu-id="51ee9-125">I messaggi identificati dal criterio di recapito avanzato non sono minacce alla sicurezza, quindi i messaggi vengono contrassegnati come sostituzioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="51ee9-125">Messages that are identified by the advanced delivery policy aren't security threats, so the messages are marked as system overrides.</span></span> <span data-ttu-id="51ee9-126">Gli amministratori possono filtrare e analizzare queste sostituzioni di sistema nelle esperienze seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-126">Admins can filter and analyze these system overrides in the following experiences:</span></span>

- [<span data-ttu-id="51ee9-127">Threat Explorer/Rilevamenti in tempo reale in Defender per Office 365 piano 2</span><span class="sxs-lookup"><span data-stu-id="51ee9-127">Threat Explorer/Real-time detections in Defender for Office 365 plan 2</span></span>](threat-explorer.md)
- <span data-ttu-id="51ee9-128">Pagina [Entità e-mail in Esplora minacce/Rilevamenti in tempo reale](mdo-email-entity-page.md)</span><span class="sxs-lookup"><span data-stu-id="51ee9-128">The [Email entity Page in Threat Explorer/Real-time detections](mdo-email-entity-page.md)</span></span>
- <span data-ttu-id="51ee9-129">Rapporto [sullo stato di Threat Protection](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="51ee9-129">The [Threat protection status report](view-email-security-reports.md#threat-protection-status-report)</span></span>
- [<span data-ttu-id="51ee9-130">Ricerca avanzata in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="51ee9-130">Advanced hunting in Microsoft Defender for Endpoint</span></span>](../defender-endpoint/advanced-hunting-overview.md)
- [<span data-ttu-id="51ee9-131">Visualizzazioni campagna</span><span class="sxs-lookup"><span data-stu-id="51ee9-131">Campaign Views</span></span>](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51ee9-132">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="51ee9-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51ee9-133">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="51ee9-133">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="51ee9-134">Per passare direttamente alla **pagina Recapito avanzato,** aprire <https://security.microsoft.com/advanceddelivery> .</span><span class="sxs-lookup"><span data-stu-id="51ee9-134">To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery>.</span></span>

- <span data-ttu-id="51ee9-135">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51ee9-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="51ee9-136">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-136">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="51ee9-137">Per creare, modificare o rimuovere le impostazioni configurate nel criterio di  recapito avanzato, è necessario essere membri del  gruppo di ruoli Amministratore della sicurezza nel portale **di Microsoft 365 Defender** e membri del gruppo di ruoli Gestione organizzazione in **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="51ee9-137">To create, modify, or remove configured settings in the advanced delivery policy, you need to be a member of the **Security Administrator** role group in the **Microsoft 365 Defender portal** and a member of the **Organization Management** role group in **Exchange Online**.</span></span>
  - <span data-ttu-id="51ee9-138">Per l'accesso in sola lettura ai criteri di recapito avanzati, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="51ee9-138">For read-only access to the advanced delivery policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="51ee9-139">Per ulteriori informazioni, vedere [Autorizzazioni nel portale Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Autorizzazioni in [Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="51ee9-139">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > <span data-ttu-id="51ee9-140">L'aggiunta di utenti al ruolo Azure Active Directory corrispondente offre agli utenti  le autorizzazioni necessarie nel portale Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51ee9-140">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="51ee9-141">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="51ee9-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="51ee9-142">Utilizzare il portale Microsoft 365 Defender per configurare le cassette postali SecOps nel criterio di recapito avanzato</span><span class="sxs-lookup"><span data-stu-id="51ee9-142">Use the Microsoft 365 Defender portal to configure SecOps mailboxes in the advanced delivery policy</span></span>

1. <span data-ttu-id="51ee9-143">Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione \> **& regole** \> **Criteri** di minaccia sezione Regole \>  \> **Recapito avanzato**.</span><span class="sxs-lookup"><span data-stu-id="51ee9-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="51ee9-144">Nella pagina **Recapito avanzato** verificare che la scheda Cassetta postale **SecOps** sia selezionata e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-144">On the **Advanced delivery** page, verify that the **SecOps mailbox** tab is selected, and then do one of the following steps:</span></span>
   - <span data-ttu-id="51ee9-145">Fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="51ee9-145">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="51ee9-146">Se non sono presenti simulazioni di phishing configurate, fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-146">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="51ee9-147">Nel riquadro a comparsa Modifica cassette postali **SecOps** visualizzato, immettere una cassetta postale di Exchange Online esistente che si desidera designare come cassetta postale SecOps eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-147">On the **Edit SecOps mailboxes** flyout that opens, enter an existing Exchange Online mailbox that you want to designate as SecOps mailbox by doing one of the following steps:</span></span>
   - <span data-ttu-id="51ee9-148">Fare clic nella casella, lasciare che l'elenco delle cassette postali si risolva e quindi selezionare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="51ee9-148">Click in the box, let the list of mailboxes resolve, and then select the mailbox.</span></span>
   - <span data-ttu-id="51ee9-149">Fare clic nella casella iniziare a digitare un identificatore per la cassetta postale (nome, nome visualizzato, alias, indirizzo di posta elettronica, nome account e così via) e selezionare la cassetta postale (nome visualizzato) dai risultati.</span><span class="sxs-lookup"><span data-stu-id="51ee9-149">Click in the box start typing an identifier for the mailbox (name, display name, alias, email address, account name, etc.), and select the mailbox (display name) from the results.</span></span>

     <span data-ttu-id="51ee9-150">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="51ee9-150">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="51ee9-151">I gruppi di distribuzione non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="51ee9-151">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="51ee9-152">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="51ee9-152">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="51ee9-154">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="51ee9-154">next to the value.</span></span>

4. <span data-ttu-id="51ee9-155">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="51ee9-155">When you're finished, click **Save**.</span></span>

<span data-ttu-id="51ee9-156">Le voci della cassetta postale SecOps configurate vengono visualizzate nella scheda Cassetta postale **SecOps.** Per apportare modifiche, fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica** nella scheda.</span><span class="sxs-lookup"><span data-stu-id="51ee9-156">The SecOps mailbox entries that you configured are displayed on the **SecOps mailbox** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="51ee9-157">Usare il portale Microsoft 365 Defender per configurare simulazioni di phishing di terze parti nel criterio di recapito avanzato</span><span class="sxs-lookup"><span data-stu-id="51ee9-157">Use the Microsoft 365 Defender portal to configure third-party phishing simulations in the advanced delivery policy</span></span>

1. <span data-ttu-id="51ee9-158">Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione \> **& regole** \> **Criteri** di minaccia sezione Regole \>  \> **Recapito avanzato**.</span><span class="sxs-lookup"><span data-stu-id="51ee9-158">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Rules** section \> **Advanced delivery**.</span></span>

2. <span data-ttu-id="51ee9-159">Nella pagina **Recapito avanzato** selezionare la scheda **Simulazione di phishing** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-159">On the **Advanced delivery** page, select the **Phishing simulation** tab, and then do one of the following steps:</span></span>
   - <span data-ttu-id="51ee9-160">Fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="51ee9-160">Click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span>
   - <span data-ttu-id="51ee9-161">Se non sono presenti simulazioni di phishing configurate, fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-161">If there are no configured phishing simulations, click **Add**.</span></span>

3. <span data-ttu-id="51ee9-162">Nel riquadro **a comparsa Modifica simulazione di phishing** di terze parti visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-162">On the **Edit third-party phishing simulation** flyout that opens, configure the following settings:</span></span>

   - <span data-ttu-id="51ee9-163">**Dominio di** invio: espandere questa impostazione e immettere almeno un dominio dell'indirizzo di posta elettronica (ad esempio, contoso.com) facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella.</span><span class="sxs-lookup"><span data-stu-id="51ee9-163">**Sending domain**: Expand this setting and enter at least one email address domain (for example, contoso.com) by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="51ee9-164">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="51ee9-164">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="51ee9-165">È possibile aggiungere fino a 10 voci.</span><span class="sxs-lookup"><span data-stu-id="51ee9-165">You can add up to 10 entries.</span></span>
   - <span data-ttu-id="51ee9-166">**IP** di invio: espandere questa impostazione e immettere almeno un indirizzo IPv4 valido facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella.</span><span class="sxs-lookup"><span data-stu-id="51ee9-166">**Sending IP**: Expand this setting and enter at least one valid IPv4 address is required by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="51ee9-167">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="51ee9-167">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="51ee9-168">È possibile aggiungere fino a 10 voci.</span><span class="sxs-lookup"><span data-stu-id="51ee9-168">You can add up to 10 entries.</span></span> <span data-ttu-id="51ee9-169">I valori validi sono:</span><span class="sxs-lookup"><span data-stu-id="51ee9-169">Valid values are:</span></span>
     - <span data-ttu-id="51ee9-170">IP singolo: ad esempio, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="51ee9-170">Single IP: For example, 192.168.1.1.</span></span>
     - <span data-ttu-id="51ee9-171">Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="51ee9-171">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
     - <span data-ttu-id="51ee9-172">IP CIDR: ad esempio, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="51ee9-172">CIDR IP: For example, 192.168.0.1/25.</span></span>
   - <span data-ttu-id="51ee9-173">URL di simulazione da **consentire:** espandere questa impostazione e facoltativamente immettere URL specifici che fanno parte della campagna di simulazione di phishing che non devono essere bloccati o detonati facendo clic nella casella, immettendo un valore e quindi premendo INVIO o selezionando il valore visualizzato sotto la casella.</span><span class="sxs-lookup"><span data-stu-id="51ee9-173">**Simulation URLs to allow**: Expand this setting and optionally enter specific URLs that are part of your phishing simulation campaign that should not be blocked or detonated by clicking in the box, entering a value, and then pressing Enter or selecting the value that's displayed below the box.</span></span> <span data-ttu-id="51ee9-174">È possibile aggiungere fino a 10 voci.</span><span class="sxs-lookup"><span data-stu-id="51ee9-174">You can add up to 10 entries.</span></span>

   <span data-ttu-id="51ee9-175">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="51ee9-175">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="51ee9-177">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="51ee9-177">next to the value.</span></span>

4. <span data-ttu-id="51ee9-178">Al termine, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-178">When you're finished, do one of the following steps:</span></span>
   - <span data-ttu-id="51ee9-179">**Prima volta**: fare **clic su Aggiungi** e quindi su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-179">**First time**: Click **Add**, and then click **Close**.</span></span>
   - <span data-ttu-id="51ee9-180">**Modifica esistente**: fare clic **su Salva** e quindi su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-180">**Edit existing**: Click **Save** and then click **Close**.</span></span>

<span data-ttu-id="51ee9-181">Le voci di simulazione di phishing di terze parti configurate vengono visualizzate nella **scheda Simulazione di** phishing. Per apportare modifiche, fare ![ clic su Modifica icona ](../../media/m365-cc-sc-edit-icon.png) **Modifica** nella scheda.</span><span class="sxs-lookup"><span data-stu-id="51ee9-181">The third-party phishing simulation entries that you configured are displayed on the **Phishing simulation** tab. To make changes, click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit** on the tab.</span></span>

## <a name="additional-scenarios-that-require-filtering-bypass"></a><span data-ttu-id="51ee9-182">Scenari aggiuntivi che richiedono il bypass del filtro</span><span class="sxs-lookup"><span data-stu-id="51ee9-182">Additional scenarios that require filtering bypass</span></span>

<span data-ttu-id="51ee9-183">Oltre ai due scenari che possono essere utili per i criteri di recapito avanzati, esistono altri scenari che potrebbero richiedere l'esclusione del filtro:</span><span class="sxs-lookup"><span data-stu-id="51ee9-183">In addition to the two scenarios that the advanced delivery policy can help you with, there are other scenarios that might require you bypass filtering:</span></span>

- <span data-ttu-id="51ee9-184">**Filtri di terze parti:** se il *record* MX del dominio non punta a Office 365 (i messaggi vengono instradati da un'altra [parte),](secure-by-default.md) la protezione per impostazione predefinita non *è disponibile.*</span><span class="sxs-lookup"><span data-stu-id="51ee9-184">**Third-party filters**: If your domain's MX record *doesn't* point to Office 365 (messages are routed somewhere else first), [secure by default](secure-by-default.md) *is not available*.</span></span> <span data-ttu-id="51ee9-185">Se si desidera aggiungere la protezione, è necessario abilitare il filtro avanzato per i connettori (noto anche come *skip listing*).</span><span class="sxs-lookup"><span data-stu-id="51ee9-185">If you'd like to add protection, you'll need to enable Enhanced Filtering for Connectors (also known as *skip listing*).</span></span> <span data-ttu-id="51ee9-186">Per ulteriori informazioni, vedere [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span><span class="sxs-lookup"><span data-stu-id="51ee9-186">For more information, see [Manage mail flow using a third-party cloud service with Exchange Online](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud).</span></span> <span data-ttu-id="51ee9-187">Se non si desidera utilizzare il filtro avanzato per i connettori, utilizzare le regole del flusso di posta (note anche come regole di trasporto) per ignorare il filtro Microsoft per i messaggi già valutati dal filtro di terze parti.</span><span class="sxs-lookup"><span data-stu-id="51ee9-187">If you don't want Enhanced Filtering for Connectors,use mail flow rules (also known as transport rules) to bypass Microsoft filtering for messages that have already been evaluated by third-party filtering.</span></span> <span data-ttu-id="51ee9-188">Per ulteriori informazioni, vedere [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span><span class="sxs-lookup"><span data-stu-id="51ee9-188">For more information, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).</span></span>

- <span data-ttu-id="51ee9-189">**Falsi positivi in** esame: è possibile consentire temporaneamente a Determinati messaggi ancora [](admin-submission.md) analizzati da Microsoft tramite invii da parte dell'amministratore di segnalare a Microsoft messaggi positivi noti erroneamente contrassegnati come non corretti (falsi positivi).</span><span class="sxs-lookup"><span data-stu-id="51ee9-189">**False positives under review**: You might want to temporarily allow certain messages that are still being analyzed by Microsoft via [admin submissions](admin-submission.md) to report known good messages that are incorrectly being marked as bad to Microsoft (false positives).</span></span> <span data-ttu-id="51ee9-190">Come per tutte le sostituzioni, è **_consigliabile_** che queste quote siano temporanee.</span><span class="sxs-lookup"><span data-stu-id="51ee9-190">As with all overrides, we **_highly recommended_** that these allowances are temporary.</span></span>

## <a name="exchange-online-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a><span data-ttu-id="51ee9-191">Exchange Online Procedure di PowerShell per le cassette postali SecOps nei criteri di recapito avanzati</span><span class="sxs-lookup"><span data-stu-id="51ee9-191">Exchange Online PowerShell procedures for SecOps mailboxes in the advanced delivery policy</span></span>

<span data-ttu-id="51ee9-192">In Exchange Online PowerShell, gli elementi di base delle cassette postali SecOps nei criteri di recapito avanzato sono:</span><span class="sxs-lookup"><span data-stu-id="51ee9-192">In Exchange Online PowerShell, the basic elements of SecOps mailboxes in the advanced delivery policy are:</span></span>

- <span data-ttu-id="51ee9-193">**Il criterio di sostituzione SecOps**: controllato dai cmdlet **\* -SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-193">**The SecOps override policy**: Controlled by the **\*-SecOpsOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="51ee9-194">**Regola di override SecOps**: controllata dai cmdlet **\* -SecOpsOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-194">**The SecOps override rule**: Controlled by the **\*-SecOpsOverrideRule** cmdlets.</span></span>

<span data-ttu-id="51ee9-195">Questo comportamento ha i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-195">This behavior has the following results:</span></span>

- <span data-ttu-id="51ee9-196">Si crea prima il criterio, quindi si crea la regola che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="51ee9-196">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="51ee9-197">Quando si rimuove un criterio da PowerShell, viene rimossa anche la regola corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51ee9-197">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="51ee9-198">Quando si rimuove una regola da PowerShell, il criterio corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="51ee9-198">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="51ee9-199">È necessario rimuovere manualmente il criterio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51ee9-199">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-secops-mailboxes"></a><span data-ttu-id="51ee9-200">Utilizzare PowerShell per configurare le cassette postali SecOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-200">Use PowerShell to configure SecOps mailboxes</span></span>

<span data-ttu-id="51ee9-201">La configurazione di una cassetta postale SecOps nei criteri di recapito avanzati in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="51ee9-201">Configuring a SecOps mailbox in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="51ee9-202">Creare il criterio di sostituzione SecOps.</span><span class="sxs-lookup"><span data-stu-id="51ee9-202">Create the SecOps override policy.</span></span>
2. <span data-ttu-id="51ee9-203">Creare la regola di sostituzione SecOps che specifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="51ee9-203">Create the SecOps override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a><span data-ttu-id="51ee9-204">Passaggio 1: Utilizzare PowerShell per creare il criterio di sostituzione SecOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-204">Step 1: Use PowerShell to create the SecOps override policy</span></span>

<span data-ttu-id="51ee9-205">Per creare il criterio di sostituzione SecOps, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51ee9-205">To create the SecOps override policy, use the following syntax:</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

<span data-ttu-id="51ee9-206">**Nota:** indipendentemente dal valore Name specificato, il nome del criterio sarà SecOpsOverridePolicy, pertanto è consigliabile utilizzare tale valore.</span><span class="sxs-lookup"><span data-stu-id="51ee9-206">**Note**: Regardless of the Name value you specify, the policy name will be SecOpsOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="51ee9-207">In questo esempio viene creato il criterio cassetta postale SecOps.</span><span class="sxs-lookup"><span data-stu-id="51ee9-207">This example creates the SecOps mailbox policy.</span></span>

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

<span data-ttu-id="51ee9-208">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-208">For detailed syntax and parameter information, see [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a><span data-ttu-id="51ee9-209">Passaggio 2: Utilizzare PowerShell per creare la regola di sostituzione SecOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-209">Step 2: Use PowerShell to create the SecOps override rule</span></span>

<span data-ttu-id="51ee9-210">In questo esempio viene creata la regola della cassetta postale SecOps con le impostazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="51ee9-210">This example creates the SecOps mailbox rule with the specified settings.</span></span>

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

<span data-ttu-id="51ee9-211">\*\*Nota:\*\*\*\*Indipendentemente dal valore Name specificato, il nome della regola sarà SecOpsOverrideRule dove è un valore GUID univoco \<GUID\> \<GUID\> (ad esempio, 6fed4b63-3563-495d-a481-b24a311f8329).</span><span class="sxs-lookup"><span data-stu-id="51ee9-211">**Note**: \*\*Regardless of the Name value you specify, the rule name will be SecOpsOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, 6fed4b63-3563-495d-a481-b24a311f8329).</span></span>

<span data-ttu-id="51ee9-212">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="51ee9-212">For detailed syntax and parameter information, see [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule).</span></span>

### <a name="use-powershell-to-view-the-secops-override-policy"></a><span data-ttu-id="51ee9-213">Utilizzare PowerShell per visualizzare il criterio di sostituzione SecOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-213">Use PowerShell to view the SecOps override policy</span></span>

<span data-ttu-id="51ee9-214">In questo esempio vengono restituite informazioni dettagliate sul solo criterio cassetta postale SecOps.</span><span class="sxs-lookup"><span data-stu-id="51ee9-214">This example returns detailed information about the one and only SecOps mailbox policy.</span></span>

```powershell
Get-SecOpsOverridePolicy
```

<span data-ttu-id="51ee9-215">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-215">For detailed syntax and parameter information, see [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-view-secops-override-rules"></a><span data-ttu-id="51ee9-216">Usare PowerShell per visualizzare le regole di sostituzione secOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-216">Use PowerShell to view SecOps override rules</span></span>

<span data-ttu-id="51ee9-217">In questo esempio vengono restituite informazioni dettagliate sulle regole di override secOps.</span><span class="sxs-lookup"><span data-stu-id="51ee9-217">This example returns detailed information about SecOps override rules.</span></span>

```powershell
Get-SecOpsOverrideRule
```

<span data-ttu-id="51ee9-218">Anche se il comando precedente deve restituire una sola regola, eventuali regole in sospeso potrebbero essere incluse nei risultati.</span><span class="sxs-lookup"><span data-stu-id="51ee9-218">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="51ee9-219">In questo esempio vengono identificate la regola valida (una) e tutte le regole non valide.</span><span class="sxs-lookup"><span data-stu-id="51ee9-219">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="51ee9-220">Dopo aver identificato le regole non valide, è possibile rimuoverle utilizzando il cmdlet **Remove-SecOpsOverrideRule** come descritto [più avanti in questo articolo.](#use-powershell-to-remove-secops-override-rules)</span><span class="sxs-lookup"><span data-stu-id="51ee9-220">After you identify the invalid rules, you can remove them by using the **Remove-SecOpsOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-secops-override-rules).</span></span>

<span data-ttu-id="51ee9-221">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span><span class="sxs-lookup"><span data-stu-id="51ee9-221">For detailed syntax and parameter information, see [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)</span></span>

### <a name="use-powershell-to-modify-the-secops-override-policy"></a><span data-ttu-id="51ee9-222">Utilizzare PowerShell per modificare il criterio di sostituzione SecOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-222">Use PowerShell to modify the SecOps override policy</span></span>

<span data-ttu-id="51ee9-223">Per modificare il criterio di sostituzione SecOps, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51ee9-223">To modify the SecOps override policy, use the following syntax:</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

<span data-ttu-id="51ee9-224">In questo esempio viene secops2@contoso.com criteri di sostituzione SecOps.</span><span class="sxs-lookup"><span data-stu-id="51ee9-224">This example adds secops2@contoso.com to the SecOps override policy.</span></span>

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

<span data-ttu-id="51ee9-225">**Nota:** se esiste una regola di sostituzione SecOps valida associata, verranno aggiornati anche gli indirizzi di posta elettronica nella regola.</span><span class="sxs-lookup"><span data-stu-id="51ee9-225">**Note**: If an associated, valid SecOps override rule exists, the email addresses in the rule will also be updated.</span></span>

<span data-ttu-id="51ee9-226">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-226">For detailed syntax and parameter information, see [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-secops-override-rule"></a><span data-ttu-id="51ee9-227">Utilizzare PowerShell per modificare una regola di sostituzione secOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-227">Use PowerShell to modify a SecOps override rule</span></span>

<span data-ttu-id="51ee9-228">Il cmdlet **Set-SecOpsOverrideRule** non modifica gli indirizzi di posta elettronica nella regola di sostituzione SecOps.</span><span class="sxs-lookup"><span data-stu-id="51ee9-228">The **Set-SecOpsOverrideRule** cmdlet does not modify the email addresses in the SecOps override rule.</span></span> <span data-ttu-id="51ee9-229">Per modificare gli indirizzi di posta elettronica nella regola di sostituzione SecOps, utilizzare il cmdlet **Set-SecOpsOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-229">To modify the email addresses in the SecOps override rule, use the **Set-SecOpsOverridePolicy** cmdlet.</span></span>

<span data-ttu-id="51ee9-230">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="51ee9-230">For detailed syntax and parameter information, see [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule).</span></span>

### <a name="use-powershell-to-remove-the-secops-override-policy"></a><span data-ttu-id="51ee9-231">Utilizzare PowerShell per rimuovere il criterio di sostituzione SecOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-231">Use PowerShell to remove the SecOps override policy</span></span>

<span data-ttu-id="51ee9-232">In questo esempio vengono rimossi il criterio Cassetta postale SecOps e la regola corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51ee9-232">This example removes the SecOps Mailbox policy and the corresponding rule.</span></span>

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

<span data-ttu-id="51ee9-233">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-233">For detailed syntax and parameter information, see [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-secops-override-rules"></a><span data-ttu-id="51ee9-234">Usare PowerShell per rimuovere le regole di sostituzione secOps</span><span class="sxs-lookup"><span data-stu-id="51ee9-234">Use PowerShell to remove SecOps override rules</span></span>

<span data-ttu-id="51ee9-235">Per rimuovere una regola di sostituzione SecOps, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51ee9-235">To remove a SecOps override rule, use the following syntax:</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="51ee9-236">In questo esempio viene rimossa la regola di sostituzione SecOps specificata.</span><span class="sxs-lookup"><span data-stu-id="51ee9-236">This example removes the specified SecOps override rule.</span></span>

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

<span data-ttu-id="51ee9-237">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span><span class="sxs-lookup"><span data-stu-id="51ee9-237">For detailed syntax and parameter information, see [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule).</span></span>

## <a name="exchange-online-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a><span data-ttu-id="51ee9-238">Exchange Online Procedure di PowerShell per simulazioni di phishing di terze parti nei criteri di recapito avanzati</span><span class="sxs-lookup"><span data-stu-id="51ee9-238">Exchange Online PowerShell procedures for third-party phishing simulations in the advanced delivery policy</span></span>

<span data-ttu-id="51ee9-239">In Exchange Online PowerShell, gli elementi di base delle simulazioni di phishing di terze parti nei criteri di recapito avanzato sono:</span><span class="sxs-lookup"><span data-stu-id="51ee9-239">In Exchange Online PowerShell, the basic elements of third-party phishing simulations in the advanced delivery policy are:</span></span>

- <span data-ttu-id="51ee9-240">**Il criterio di sostituzione della simulazione di phishing**: controllato dai cmdlet **\* -PhishSimOverridePolicy.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-240">**The phishing simulation override policy**: Controlled by the **\*-PhishSimOverridePolicy** cmdlets.</span></span>
- <span data-ttu-id="51ee9-241">**Regola di sostituzione della simulazione di phishing**: controllata dai cmdlet **\* -PhishSimOverrideRule.**</span><span class="sxs-lookup"><span data-stu-id="51ee9-241">**The phishing simulation override rule**: Controlled by the **\*-PhishSimOverrideRule** cmdlets.</span></span>

<span data-ttu-id="51ee9-242">Questo comportamento ha i risultati seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-242">This behavior has the following results:</span></span>

- <span data-ttu-id="51ee9-243">Si crea prima il criterio, quindi si crea la regola che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="51ee9-243">You create the policy first, then you create the rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="51ee9-244">Le impostazioni del criterio e della regola vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="51ee9-244">You modify the settings in the policy and the rule separately.</span></span>
- <span data-ttu-id="51ee9-245">Quando si rimuove un criterio da PowerShell, viene rimossa anche la regola corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51ee9-245">When you remove a policy from PowerShell, the corresponding rule is also removed.</span></span>
- <span data-ttu-id="51ee9-246">Quando si rimuove una regola da PowerShell, il criterio corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="51ee9-246">When you remove a rule from PowerShell, the corresponding policy is not removed.</span></span> <span data-ttu-id="51ee9-247">È necessario rimuovere manualmente il criterio corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51ee9-247">You need to remove the corresponding policy manually.</span></span>

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a><span data-ttu-id="51ee9-248">Usare PowerShell per configurare simulazioni di phishing di terze parti</span><span class="sxs-lookup"><span data-stu-id="51ee9-248">Use PowerShell to configure third-party phishing simulations</span></span>

<span data-ttu-id="51ee9-249">La configurazione di una simulazione di phishing di terze parti nei criteri di recapito avanzati in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="51ee9-249">Configuring a third-party phishing simulation in the advanced delivery policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="51ee9-250">Creare il criterio di sostituzione della simulazione di phishing.</span><span class="sxs-lookup"><span data-stu-id="51ee9-250">Create the phishing simulation override policy.</span></span>
2. <span data-ttu-id="51ee9-251">Creare la regola di sostituzione della simulazione di phishing che specifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="51ee9-251">Create the phishing simulation override rule that specifies the policy that the rule applies to.</span></span>

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a><span data-ttu-id="51ee9-252">Passaggio 1: Usare PowerShell per creare il criterio di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-252">Step 1: Use PowerShell to create the phishing simulation override policy</span></span>

<span data-ttu-id="51ee9-253">In questo esempio viene creato il criterio di sostituzione della simulazione di phishing.</span><span class="sxs-lookup"><span data-stu-id="51ee9-253">This example creates the phishing simulation override policy.</span></span>

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

<span data-ttu-id="51ee9-254">**Nota:** indipendentemente dal valore Name specificato, il nome del criterio sarà PhishSimOverridePolicy, pertanto è consigliabile utilizzare tale valore.</span><span class="sxs-lookup"><span data-stu-id="51ee9-254">**Note**: Regardless of the Name value you specify, the policy name will be PhishSimOverridePolicy, so you might as well use that value.</span></span>

<span data-ttu-id="51ee9-255">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-255">For detailed syntax and parameter information, see [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a><span data-ttu-id="51ee9-256">Passaggio 2: Utilizzare PowerShell per creare la regola di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-256">Step 2: Use PowerShell to create the phishing simulation override rule</span></span>

<span data-ttu-id="51ee9-257">Usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51ee9-257">Use the following syntax:</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

<span data-ttu-id="51ee9-258">Indipendentemente dal valore Name specificato, il nome della regola sarà PhishSimOverrideRule dove è un valore GUID univoco \<GUID\> \<GUID\> (ad esempio, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span><span class="sxs-lookup"><span data-stu-id="51ee9-258">Regardless of the Name value you specify, the rule name will be PhishSimOverrideRule\<GUID\> where \<GUID\> is a unique GUID value (for example, a0eae53e-d755-4a42-9320-b9c6b55c5011).</span></span>

<span data-ttu-id="51ee9-259">Una voce di indirizzo IP valida è uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-259">A valid IP address entry is one of the following values:</span></span>

- <span data-ttu-id="51ee9-260">IP singolo: ad esempio, 192.168.1.1.</span><span class="sxs-lookup"><span data-stu-id="51ee9-260">Single IP: For example, 192.168.1.1.</span></span>
- <span data-ttu-id="51ee9-261">Intervallo IP: ad esempio, 192.168.0.1-192.168.0.254.</span><span class="sxs-lookup"><span data-stu-id="51ee9-261">IP range: For example, 192.168.0.1-192.168.0.254.</span></span>
- <span data-ttu-id="51ee9-262">IP CIDR: ad esempio, 192.168.0.1/25.</span><span class="sxs-lookup"><span data-stu-id="51ee9-262">CIDR IP: For example, 192.168.0.1/25.</span></span>

<span data-ttu-id="51ee9-263">In questo esempio viene creata la regola di sostituzione della simulazione di phishing con le impostazioni specificate.</span><span class="sxs-lookup"><span data-stu-id="51ee9-263">This example creates the phishing simulation override rule with the specified settings.</span></span>

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

<span data-ttu-id="51ee9-264">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="51ee9-264">For detailed syntax and parameter information, see [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a><span data-ttu-id="51ee9-265">Usare PowerShell per visualizzare il criterio di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-265">Use PowerShell to view the phishing simulation override policy</span></span>

<span data-ttu-id="51ee9-266">In questo esempio vengono restituite informazioni dettagliate sull'unico criterio di sostituzione della simulazione di phishing.</span><span class="sxs-lookup"><span data-stu-id="51ee9-266">This example returns detailed information about the one and only phishing simulation override policy.</span></span>

```powershell
Get-PhishSimOverridePolicy
```

<span data-ttu-id="51ee9-267">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-267">For detailed syntax and parameter information, see [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a><span data-ttu-id="51ee9-268">Usare PowerShell per visualizzare le regole di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-268">Use PowerShell to view phishing simulation override rules</span></span>

<span data-ttu-id="51ee9-269">In questo esempio vengono restituite informazioni dettagliate sulle regole di sostituzione della simulazione di phishing.</span><span class="sxs-lookup"><span data-stu-id="51ee9-269">This example returns detailed information about phishing simulation override rules.</span></span>

```powershell
Get-PhishSimOverrideRule
```

<span data-ttu-id="51ee9-270">Anche se il comando precedente deve restituire una sola regola, eventuali regole in sospeso potrebbero essere incluse nei risultati.</span><span class="sxs-lookup"><span data-stu-id="51ee9-270">Although the previous command should return only one rule, any rules that are pending deletion might also be included in the results.</span></span>

<span data-ttu-id="51ee9-271">In questo esempio vengono identificate la regola valida (una) e tutte le regole non valide.</span><span class="sxs-lookup"><span data-stu-id="51ee9-271">This example identifies the valid rule (one) and any invalid rules.</span></span>

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

<span data-ttu-id="51ee9-272">Dopo aver identificato le regole non valide, è possibile rimuoverle utilizzando il cmdlet **Remove-PhisSimOverrideRule** come descritto [più avanti in questo articolo.](#use-powershell-to-remove-phishing-simulation-override-rules)</span><span class="sxs-lookup"><span data-stu-id="51ee9-272">After you identify the invalid rules, you can remove them by using the **Remove-PhisSimOverrideRule** cmdlet as described [later in this article](#use-powershell-to-remove-phishing-simulation-override-rules).</span></span>

<span data-ttu-id="51ee9-273">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="51ee9-273">For detailed syntax and parameter information, see [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a><span data-ttu-id="51ee9-274">Utilizzare PowerShell per modificare il criterio di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-274">Use PowerShell to modify the phishing simulation override policy</span></span>

<span data-ttu-id="51ee9-275">Per modificare il criterio di sostituzione della simulazione di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51ee9-275">To modify the phishing simulation override policy, use the following syntax:</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="51ee9-276">In questo esempio viene disabilitato il criterio di sostituzione della simulazione di phishing.</span><span class="sxs-lookup"><span data-stu-id="51ee9-276">This example disables the phishing simulation override policy.</span></span>

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

<span data-ttu-id="51ee9-277">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-277">For detailed syntax and parameter information, see [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-modify-a-phishing-simulation-override-rule"></a><span data-ttu-id="51ee9-278">Utilizzare PowerShell per modificare una regola di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-278">Use PowerShell to modify a phishing simulation override rule</span></span>

<span data-ttu-id="51ee9-279">Per modificare la regola di sostituzione della simulazione di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51ee9-279">To modify the phishing simulation override rule, use the following syntax:</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

<span data-ttu-id="51ee9-280">In questo esempio viene modificata la regola di sostituzione della simulazione di phishing specificata con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="51ee9-280">This example modifies the specified phishing simulation override rule with the following settings:</span></span>

- <span data-ttu-id="51ee9-281">Aggiungere la voce di dominio blueyonderairlines.com.</span><span class="sxs-lookup"><span data-stu-id="51ee9-281">Add the domain entry blueyonderairlines.com.</span></span>
- <span data-ttu-id="51ee9-282">Rimuovere la voce dell'indirizzo IP 192.168.1.55.</span><span class="sxs-lookup"><span data-stu-id="51ee9-282">Remove the IP address entry 192.168.1.55.</span></span>

<span data-ttu-id="51ee9-283">Si noti che queste modifiche non influiscono sulle voci esistenti.</span><span class="sxs-lookup"><span data-stu-id="51ee9-283">Note that these changes don't affect existing entries.</span></span>

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

<span data-ttu-id="51ee9-284">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="51ee9-284">For detailed syntax and parameter information, see [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule).</span></span>

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a><span data-ttu-id="51ee9-285">Usare PowerShell per rimuovere un criterio di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-285">Use PowerShell to remove a phishing simulation override policy</span></span>

<span data-ttu-id="51ee9-286">In questo esempio vengono rimossi il criterio di sostituzione della simulazione di phishing e la regola corrispondente.</span><span class="sxs-lookup"><span data-stu-id="51ee9-286">This example removes the phishing simulation override policy and the corresponding rule.</span></span>

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

<span data-ttu-id="51ee9-287">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span><span class="sxs-lookup"><span data-stu-id="51ee9-287">For detailed syntax and parameter information, see [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy).</span></span>

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a><span data-ttu-id="51ee9-288">Usare PowerShell per rimuovere le regole di sostituzione della simulazione di phishing</span><span class="sxs-lookup"><span data-stu-id="51ee9-288">Use PowerShell to remove phishing simulation override rules</span></span>

<span data-ttu-id="51ee9-289">Per rimuovere una regola di sostituzione della simulazione di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="51ee9-289">To remove a phishing simulation override rule, use the following syntax:</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

<span data-ttu-id="51ee9-290">In questo esempio viene rimossa la regola di sostituzione della simulazione di phishing specificata.</span><span class="sxs-lookup"><span data-stu-id="51ee9-290">This example removes the specified phishing simulation override rule.</span></span>

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

<span data-ttu-id="51ee9-291">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span><span class="sxs-lookup"><span data-stu-id="51ee9-291">For detailed syntax and parameter information, see [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule).</span></span>
