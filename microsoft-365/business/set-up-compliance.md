---
title: Aumentare la protezione dalle minacce per Microsoft 365 business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Configurare Office 365 Advanced Threat Protection e proteggere i dati sensibili.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668391"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="ae0e4-103">Configurare le funzionalità di conformità</span><span class="sxs-lookup"><span data-stu-id="ae0e4-103">Set up compliance features</span></span>

<span data-ttu-id="ae0e4-104">Microsoft 365 business è dotato di funzionalità per proteggere i dati e i dispositivi, nonché per garantire la protezione delle informazioni riservate per i propri clienti e le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="ae0e4-105">Configurare le funzionalità DLP</span><span class="sxs-lookup"><span data-stu-id="ae0e4-105">Set up DLP features</span></span>

<span data-ttu-id="ae0e4-106">Vedere [creare un criterio DLP da un modello](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) per un esempio su come impostare un criterio per proteggere le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="ae0e4-107">DLP viene fornito con molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="ae0e4-108">Ad esempio, Australia Financial Data, Canada Personal Information Act, US Financial Data, ecc. Vedere [cosa includono i modelli di criteri DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) per un elenco completo.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="ae0e4-109">Tutti questi modelli possono essere abilitati in modo analogo all'esempio del modello PII.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="ae0e4-110">Configurare la conservazione della posta elettronica con archiviazione Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ae0e4-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="ae0e4-111">Le funzionalità di licenza di **archiviazione di Exchange Online** aiutano a mantenere la conformità e gli standard normativi preservando il contenuto della posta elettronica per eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="ae0e4-112">Consente inoltre di ridurre i rischi in caso di una querela e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="ae0e4-113">È possibile utilizzare il blocco per controversia legale per mantenere tutto il contenuto di un utente o utilizzare i criteri di conservazione per personalizzare gli elementi che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="ae0e4-114">**Blocco per controversia legale:** È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="ae0e4-115">Per inserire una cassetta postale per il blocco per controversia legale, nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="ae0e4-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="ae0e4-116">Nella barra di spostamento a sinistra, passare a utenti **attivi**degli **utenti** \> .</span><span class="sxs-lookup"><span data-stu-id="ae0e4-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="ae0e4-117">Selezionare un utente la cui cassetta postale si desidera inserire nel blocco per controversia legale e nel riquadro utente espandere **impostazioni di posta elettronica** e accanto a **altre impostazioni** scegliere **modifica proprietà di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="ae0e4-118">Nella pagina Cassetta postale per l'utente, scegliere \* \* funzionalità cassetta postale \* \* sulla barra di spostamento sinistra e quindi scegliere il collegamento **attiva** in **blocco per controversia legale**.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="ae0e4-119">Nella finestra di dialogo **blocco per controversia legale** è possibile specificare la durata del blocco per controversia legale nel campo **durata** conservazione per controversia legale, lasciare vuoto il campo se si desidera inserire un blocco infinito.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="ae0e4-120">È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web che potrebbe essere necessario spiegare meglio il \> **salvataggio**del blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="ae0e4-121">**Conservazione:** È possibile abilitare i criteri di conservazione personalizzati, ad esempio per mantenere un determinato intervallo di tempo o eliminare il contenuto in modo permanente alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="ae0e4-122">Per ulteriori informazioni, vedere [Overview of](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)Retention Policies.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="ae0e4-123">Configurare le funzionalità di protezione delle informazioni di Azure</span><span class="sxs-lookup"><span data-stu-id="ae0e4-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="ae0e4-124">Azure Information Protection (AIP) consente di classificare e facoltativamente, proteggere i documenti e i messaggi di posta elettronica, applicando etichette.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="ae0e4-125">Le etichette possono essere applicate automaticamente dagli amministratori che definiscono le regole e le condizioni, manualmente dagli utenti o utilizzando una combinazione in cui gli utenti ricevono consigli.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="ae0e4-126">In Outlook sul Web è possibile applicare le seguenti etichette e limitazioni predefinite ai messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="ae0e4-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="ae0e4-127">\*\*\*\* Non inoltrare: i destinatari possono leggere il messaggio, ma non possono inoltrare, stampare o copiare il contenuto</span><span class="sxs-lookup"><span data-stu-id="ae0e4-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="ae0e4-128">**Encrypt**: l'intero messaggio è crittografato.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="ae0e4-129">I destinatari devono confermare la propria identità prima di accedere al contenuto crittografato e non possono rimuovere la crittografia.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="ae0e4-130">**Riservato**: fornisce ai dipendenti dell'organizzazione autorizzazioni complete per il contenuto e gli allegati di posta elettronica, ma non per gli utenti esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="ae0e4-131">I proprietari di dati possono monitorare e revocare il contenuto in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="ae0e4-132">**Estremamente riservato**: questa restrizione può essere applicata a dati estremamente riservati, consentendo ai dipendenti di visualizzare, modificare e rispondere, ma non di inoltrare, stampare o copiare i dati.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="ae0e4-133">I proprietari di dati possono monitorare e revocare il contenuto in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="ae0e4-134">Verificare che Azure Information Protection sia attivato</span><span class="sxs-lookup"><span data-stu-id="ae0e4-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="ae0e4-135">Per verificare che AIP sia attivato:</span><span class="sxs-lookup"><span data-stu-id="ae0e4-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="ae0e4-136">Accedere al [portale di Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="ae0e4-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="ae0e4-137">Selezionare **tutti i servizi** e digitare in *Azure Information Protection* nella **casella di ricerca**.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="ae0e4-138">Dopo la visualizzazione dei risultati, fare clic sul pulsante Start next to **Azure Information Protection** per renderlo preferito e facile da trovare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="ae0e4-139">Selezionare **Azure Information** \> Protection **Protection Activation** e verificare che lo stato sia impostato su attivato.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="ae0e4-140">Visualizzare i criteri di protezione delle informazioni di Azure e le etichette predefinite</span><span class="sxs-lookup"><span data-stu-id="ae0e4-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="ae0e4-141">Per visualizzare e modificare le etichette esistenti:</span><span class="sxs-lookup"><span data-stu-id="ae0e4-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="ae0e4-142">Nel dashboard di Azure Information Protection selezionare etichette **classificazioni** \> \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="ae0e4-143">![Etichette standard per Azure Information Protection.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="ae0e4-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="ae0e4-144">È possibile scegliere qualsiasi etichetta per visualizzare le opzioni, è possibile modificare il nome visualizzato, i colori e così via.</span><span class="sxs-lookup"><span data-stu-id="ae0e4-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="ae0e4-145">Se si desidera creare il proprio, vedere [modificare e creare nuove etichette](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) .</span><span class="sxs-lookup"><span data-stu-id="ae0e4-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="ae0e4-146">Installare il client Azure Information Protection manualmente</span><span class="sxs-lookup"><span data-stu-id="ae0e4-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="ae0e4-147">Per installare manualmente il client AIP:</span><span class="sxs-lookup"><span data-stu-id="ae0e4-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="ae0e4-148">Scaricare **AzInfoProtection. exe** dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="ae0e4-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="ae0e4-149">È possibile verificare che l'installazione abbia avuto esito positivo visualizzando un documento di Word e \*\*\*\* assicurandosi che l'opzione Proteggi sia disponibile nella scheda **Home** .</span><span class="sxs-lookup"><span data-stu-id="ae0e4-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="ae0e4-150">![Elenco a discesa della scheda protezione in un documento di Word.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="ae0e4-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="ae0e4-151">Per ulteriori informazioni, vedere [installare il client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="ae0e4-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
