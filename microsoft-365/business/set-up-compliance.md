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
ms.openlocfilehash: 2c95ad3f36df28af2c68cd11192bcfe92dfe29e3
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841174"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="2b434-103">Funzionalità di conformità della configurazione</span><span class="sxs-lookup"><span data-stu-id="2b434-103">Set up compliance features</span></span>

<span data-ttu-id="2b434-104">Microsoft 365 Business Premium include funzionalità per proteggere i dati e i dispositivi e consente di proteggere le informazioni riservate dei clienti.</span><span class="sxs-lookup"><span data-stu-id="2b434-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="2b434-105">Configurare le funzionalità DLP</span><span class="sxs-lookup"><span data-stu-id="2b434-105">Set up DLP features</span></span>

<span data-ttu-id="2b434-106">Vedere [Creare un criterio DLP da un modello](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) per un esempio su come configurare un criterio per la protezione dalla perdita di dati personali.</span><span class="sxs-lookup"><span data-stu-id="2b434-106">See [Create a DLP policy from a template](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="2b434-107">DLP include molti modelli di criteri pronti all'uso per molte impostazioni locali diverse.</span><span class="sxs-lookup"><span data-stu-id="2b434-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="2b434-108">Ad esempio, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data e così via.</span><span class="sxs-lookup"><span data-stu-id="2b434-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="2b434-109">Vedere [Cosa includono i modelli di criteri DLP per](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) un elenco completo.</span><span class="sxs-lookup"><span data-stu-id="2b434-109">See [What the DLP policy templates include](https://docs.microsoft.com/microsoft-365/compliance/what-the-dlp-policy-templates-include) for a full list.</span></span> <span data-ttu-id="2b434-110">Tutti questi modelli possono essere abilitati in modo simile all'esempio di modello di informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="2b434-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="2b434-111">Configurare la conservazione della posta elettronica con Archiviazione Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2b434-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="2b434-112">**Archiviazione Exchange Online** licenze consentono di mantenere gli standard normativi e di conformità preservando il contenuto della posta elettronica per eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="2b434-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="2b434-113">Consente inoltre di ridurre i rischi in caso di un'azione legale e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="2b434-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="2b434-114">È possibile utilizzare la conservazione per controversia legale per conservare tutto il contenuto di un utente o utilizzare i criteri di conservazione per personalizzare ciò che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="2b434-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="2b434-115">**Conservazione per controversia legale:** È possibile conservare tutto il contenuto della cassetta postale, inclusi gli elementi eliminati, inserendo l'intera cassetta postale di un utente in conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="2b434-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="2b434-116">Per impostare la conservazione per controversia legale in una cassetta postale, nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="2b434-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="2b434-117">Nel riquadro di spostamento sinistro passare a **Utenti** \> **attivi.**</span><span class="sxs-lookup"><span data-stu-id="2b434-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="2b434-118">Selezionare un utente di cui si desidera mantenere la conservazione per controversia legale nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="2b434-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="2b434-119">Nel riquadro degli utenti espandere **Impostazioni posta** e accanto ad **Altre impostazioni** scegliere Modifica proprietà **di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="2b434-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="2b434-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span><span class="sxs-lookup"><span data-stu-id="2b434-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="2b434-121">Nella finestra **di dialogo di conservazione** per controversia legale è possibile specificare la durata della conservazione per controversia legale nel campo Durata blocco per **controversia** legale.</span><span class="sxs-lookup"><span data-stu-id="2b434-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="2b434-122">Lasciare vuoto il campo se si desidera inserire un'esenzione infinita.</span><span class="sxs-lookup"><span data-stu-id="2b434-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="2b434-123">È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web che potrebbe essere necessario spiegare di più sulla conservazione per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="2b434-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="2b434-124">\>**Salva**.</span><span class="sxs-lookup"><span data-stu-id="2b434-124">\> **Save**.</span></span>
    
<span data-ttu-id="2b434-125">**Conservazione:** È possibile abilitare criteri di conservazione personalizzati, ad esempio, per conservare per un periodo di tempo specifico o eliminare definitivamente il contenuto alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="2b434-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="2b434-126">Per ulteriori informazioni, vedere [Panoramica dei criteri di conservazione.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)</span><span class="sxs-lookup"><span data-stu-id="2b434-126">To learn more, see [Overview of retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="2b434-127">Configurare le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="2b434-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="2b434-128">Le etichette di riservatezza sono disponibili con Azure Information Protection (AIP) Piano 1 e consentono di classificare e facoltativamente proteggere i documenti e i messaggi di posta elettronica applicando etichette.</span><span class="sxs-lookup"><span data-stu-id="2b434-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="2b434-129">Le etichette possono essere applicate automaticamente dagli amministratori che definiscono regole e condizioni, manualmente dagli utenti o utilizzando una combinazione in cui agli utenti vengono forniti suggerimenti.</span><span class="sxs-lookup"><span data-stu-id="2b434-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="2b434-130">Per configurare le etichette di riservatezza, visualizzare il video [per creare e gestire le etichette di](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) riservatezza.</span><span class="sxs-lookup"><span data-stu-id="2b434-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="2b434-131">Installare manualmente il client Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="2b434-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="2b434-132">Per installare manualmente il client AIP:</span><span class="sxs-lookup"><span data-stu-id="2b434-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="2b434-133">Scaricare **AzinfoProtection_UL.exe** dall'Area [download Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="2b434-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="2b434-134">È possibile verificare che l'installazione sia stata completata  visualizzando un documento di Word e verificando che l'opzione Riservatezza sia disponibile nella **scheda** Home.</span><span class="sxs-lookup"><span data-stu-id="2b434-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="2b434-135">![Elenco a discesa Della scheda Protezione in un documento di Word.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="2b434-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="2b434-136">Per ulteriori informazioni, vedere [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="2b434-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
