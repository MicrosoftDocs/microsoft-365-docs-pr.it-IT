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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Configurare le funzionalità di conformità per impedire la perdita di dati e i dati sensibili dell'etichetta.
ms.openlocfilehash: a0ba2fa6dbe7c786d577ad7098c1790f569f5acc
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453918"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="881f8-103">Funzionalità di conformità della configurazione</span><span class="sxs-lookup"><span data-stu-id="881f8-103">Set up compliance features</span></span>

<span data-ttu-id="881f8-104">Microsoft 365 business è dotato di funzionalità per proteggere i dati e i dispositivi, nonché per garantire la protezione delle informazioni riservate per i propri clienti e le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="881f8-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="881f8-105">Configurare le funzionalità DLP</span><span class="sxs-lookup"><span data-stu-id="881f8-105">Set up DLP features</span></span>

<span data-ttu-id="881f8-106">Vedere [creare un criterio DLP da un modello](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) per un esempio su come impostare un criterio per proteggere le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="881f8-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="881f8-107">DLP viene fornito con molti modelli di criteri pronti per l'uso per molte impostazioni locali diverse.</span><span class="sxs-lookup"><span data-stu-id="881f8-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="881f8-108">Ad esempio, Australia Financial Data, Canada Personal Information Act, US Financial Data, ecc. Vedere [cosa includono i modelli di criteri DLP](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) per un elenco completo.</span><span class="sxs-lookup"><span data-stu-id="881f8-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="881f8-109">Tutti questi modelli possono essere abilitati in modo analogo all'esempio del modello PII.</span><span class="sxs-lookup"><span data-stu-id="881f8-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="881f8-110">Configurare la conservazione della posta elettronica con archiviazione Exchange Online</span><span class="sxs-lookup"><span data-stu-id="881f8-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="881f8-111">Le funzionalità di licenza di **archiviazione di Exchange Online** aiutano a mantenere la conformità e gli standard normativi preservando il contenuto della posta elettronica per eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="881f8-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="881f8-112">Consente inoltre di ridurre i rischi in caso di una querela e consente di recuperare i dati dopo una violazione della sicurezza o quando è necessario recuperare gli elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="881f8-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="881f8-113">È possibile utilizzare il blocco per controversia legale per mantenere tutto il contenuto di un utente o utilizzare i criteri di conservazione per personalizzare gli elementi che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="881f8-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="881f8-114">**Blocco per controversia legale:** È possibile mantenere tutti i contenuti delle cassette postali, compresi gli elementi eliminati, inserendo l'intera cassetta postale di un utente sul blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="881f8-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="881f8-115">Per inserire una cassetta postale per il blocco per controversia legale, nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="881f8-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="881f8-116">Nella barra di spostamento a sinistra, passare a utenti **attivi**degli **utenti** \> .</span><span class="sxs-lookup"><span data-stu-id="881f8-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="881f8-117">Selezionare un utente la cui cassetta postale si desidera inserire nel blocco per controversia legale e nel riquadro utente espandere **impostazioni di posta elettronica** e accanto a **altre impostazioni** scegliere **modifica proprietà di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="881f8-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="881f8-118">Nella pagina Cassetta postale per l'utente, scegliere \* \* funzionalità cassetta postale \* \* sulla barra di spostamento sinistra e quindi scegliere il collegamento **attiva** in **blocco per controversia legale**.</span><span class="sxs-lookup"><span data-stu-id="881f8-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="881f8-119">Nella finestra di dialogo **blocco per controversia legale** è possibile specificare la durata del blocco per controversia legale nel campo **durata** conservazione per controversia legale, lasciare vuoto il campo se si desidera inserire un blocco infinito.</span><span class="sxs-lookup"><span data-stu-id="881f8-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="881f8-120">È inoltre possibile aggiungere note e indirizzare il proprietario della cassetta postale a un sito Web che potrebbe essere necessario spiegare meglio il \> **salvataggio**del blocco per controversia legale.</span><span class="sxs-lookup"><span data-stu-id="881f8-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="881f8-121">**Conservazione:** È possibile abilitare i criteri di conservazione personalizzati, ad esempio per mantenere un determinato intervallo di tempo o eliminare il contenuto in modo permanente alla fine del periodo di conservazione.</span><span class="sxs-lookup"><span data-stu-id="881f8-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="881f8-122">Per ulteriori informazioni, vedere [Overview of Retention Policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="881f8-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="881f8-123">Configurare le etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="881f8-123">Set up Sensitivity labels</span></span>

<span data-ttu-id="881f8-124">Le etichette di riservatezza sono dotate di Azure Information Protection (AIP) piano 1 e consentono di classificare e facoltativamente proteggere i documenti e i messaggi di posta elettronica applicando etichette.</span><span class="sxs-lookup"><span data-stu-id="881f8-124">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="881f8-125">Le etichette possono essere applicate automaticamente dagli amministratori che definiscono le regole e le condizioni, manualmente dagli utenti o utilizzando una combinazione in cui gli utenti ricevono consigli.</span><span class="sxs-lookup"><span data-stu-id="881f8-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="881f8-126">Per impostare le etichette di riservatezza, vedere [creare e gestire le etichette di riservatezza](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span><span class="sxs-lookup"><span data-stu-id="881f8-126">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/en-us/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="881f8-127">Installare il client Azure Information Protection manualmente</span><span class="sxs-lookup"><span data-stu-id="881f8-127">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="881f8-128">Per installare manualmente il client AIP:</span><span class="sxs-lookup"><span data-stu-id="881f8-128">To manually install the AIP client:</span></span>

1. <span data-ttu-id="881f8-129">Scaricare **AzinfoProtection_UL. exe** dall' [area download Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="881f8-129">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="881f8-130">È possibile verificare che l'installazione abbia avuto esito positivo visualizzando un documento di Word e assicurandosi che l'opzione **sensitivity** sia disponibile nella scheda **Home** .</span><span class="sxs-lookup"><span data-stu-id="881f8-130">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="881f8-131">![Elenco a discesa della scheda protezione in un documento di Word.](media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="881f8-131">![Protection tab drop-down in a Word document.](media/word-sensitivity.png)</span></span>

<span data-ttu-id="881f8-132">Per ulteriori informazioni, vedere [installare il client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="881f8-132">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
