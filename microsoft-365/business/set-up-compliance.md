---
title: Aumentare la protezione dalle minacce per Microsoft 365 Business Premium
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Configurare le funzionalità di conformità per evitare la perdita di dati e proteggere le informazioni riservate dei clienti.
ms.openlocfilehash: 9b900367c22ec5bb5c2719af63049045ecd5e466
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402695"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="381ec-103">Funzionalità di conformità della configurazione</span><span class="sxs-lookup"><span data-stu-id="381ec-103">Set up compliance features</span></span>

<span data-ttu-id="381ec-104">Microsoft 365 Business Premium è dotato di funzionalità per proteggere i dati e i dispositivi, nonché per garantire la sicurezza delle informazioni riservate e dei clienti.</span><span class="sxs-lookup"><span data-stu-id="381ec-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="381ec-105">Configurare le funzionalità DLP</span><span class="sxs-lookup"><span data-stu-id="381ec-105">Set up DLP features</span></span>

<span data-ttu-id="381ec-106">Vedere [creare un criterio DLP da un modello](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) per un esempio su come impostare un criterio per proteggere le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="381ec-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="381ec-107">DLP viene fornito con molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse.</span><span class="sxs-lookup"><span data-stu-id="381ec-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="381ec-108">Ad esempio, Australia Financial Data, Canada Personal Information Act, US Financial Data e così via.</span><span class="sxs-lookup"><span data-stu-id="381ec-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="381ec-109">Vedere [cosa includono i modelli di criteri DLP](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) per un elenco completo.</span><span class="sxs-lookup"><span data-stu-id="381ec-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="381ec-110">Tutti questi modelli possono essere abilitati in modo analogo all'esempio del modello PII.</span><span class="sxs-lookup"><span data-stu-id="381ec-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="381ec-111">Configurare la conservazione della posta elettronica con archiviazione Exchange Online</span><span class="sxs-lookup"><span data-stu-id="381ec-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="381ec-112">Le funzionalità di licenza di **archiviazione di Exchange Online** aiutano a mantenere la conformità e gli standard normativi preservando il contenuto della posta elettronica per eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="381ec-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="381ec-113">Consente inoltre di ridurre il rischio se esiste una causa legale e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="381ec-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="381ec-114">È possibile utilizzare il blocco per controversia legale per mantenere tutto il contenuto di un utente o utilizzare i criteri di conservazione per personalizzare gli elementi che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="381ec-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="381ec-115">**Blocco per controversia legale:** È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="381ec-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="381ec-116">Per inserire una cassetta postale per il blocco per controversia legale, nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="381ec-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="381ec-117">Nella barra di spostamento a sinistra, passare a utenti attivi degli **utenti** \> **Active users**.</span><span class="sxs-lookup"><span data-stu-id="381ec-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="381ec-118">Selezionare un utente la cui cassetta postale si desidera inserire nel blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="381ec-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="381ec-119">Nel riquadro utente espandere Impostazioni di **posta elettronica**e accanto a **altre impostazioni**scegliere **modifica proprietà di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="381ec-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="381ec-120">Nella pagina Cassetta postale per l'utente, scegliere \* \* funzionalità cassetta postale \* \* sulla barra di spostamento sinistra e quindi scegliere il collegamento **attiva** in **blocco per controversia legale**.</span><span class="sxs-lookup"><span data-stu-id="381ec-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="381ec-121">Nella finestra di dialogo **blocco per controversia legale** , è possibile specificare la durata del blocco per controversia legale nel campo **Durata blocco** per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="381ec-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="381ec-122">Lasciare vuoto il campo se si desidera inserire un blocco infinito.</span><span class="sxs-lookup"><span data-stu-id="381ec-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="381ec-123">È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web potrebbe essere necessario spiegarne di più sul blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="381ec-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="381ec-124">\>**Save**.</span><span class="sxs-lookup"><span data-stu-id="381ec-124">\> **Save**.</span></span>
    
<span data-ttu-id="381ec-125">**Conservazione:** È possibile abilitare i criteri di conservazione personalizzati, ad esempio per mantenere un determinato intervallo di tempo o eliminare il contenuto in modo permanente alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="381ec-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="381ec-126">Per ulteriori informazioni, vedere [Overview of Retention Policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span><span class="sxs-lookup"><span data-stu-id="381ec-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="381ec-127">Configurare le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="381ec-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="381ec-128">Le etichette di riservatezza sono dotate di Azure Information Protection (AIP) piano 1 e consentono di classificare e, facoltativamente, proteggere i documenti e i messaggi di posta elettronica applicando etichette.</span><span class="sxs-lookup"><span data-stu-id="381ec-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="381ec-129">Le etichette possono essere applicate automaticamente dagli amministratori che definiscono le regole e le condizioni, manualmente dagli utenti o utilizzando una combinazione in cui gli utenti ricevono consigli.</span><span class="sxs-lookup"><span data-stu-id="381ec-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="381ec-130">Per impostare le etichette di riservatezza, vedere [creare e gestire le etichette di riservatezza](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span><span class="sxs-lookup"><span data-stu-id="381ec-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="381ec-131">Installare il client Azure Information Protection manualmente</span><span class="sxs-lookup"><span data-stu-id="381ec-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="381ec-132">Per installare manualmente il client AIP:</span><span class="sxs-lookup"><span data-stu-id="381ec-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="381ec-133">Scaricare **AzinfoProtection_UL. exe** dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="381ec-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="381ec-134">È possibile verificare che l'installazione abbia avuto esito positivo visualizzando un documento di Word e assicurandosi che l'opzione **sensitivity** sia disponibile nella scheda **Home** .</span><span class="sxs-lookup"><span data-stu-id="381ec-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="381ec-135">![Elenco a discesa della scheda protezione in un documento di Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="381ec-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="381ec-136">Per ulteriori informazioni, vedere [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="381ec-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
