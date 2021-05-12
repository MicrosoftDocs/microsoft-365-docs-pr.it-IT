---
title: 'Presto disponibile: Configurare SharePoint come origine di contenuto didattico per Microsoft Viva Learning (anteprima)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Informazioni su come configurare SharePoint come origine di contenuto didattico per Microsoft Viva Learning (Anteprima).
ms.openlocfilehash: 2bed3a42d62e2aab2165ee38379eb07503807e6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333579"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="0fb03-103">Presto disponibile: Configurare SharePoint come origine di contenuto didattico per Microsoft Viva Learning (anteprima)</span><span class="sxs-lookup"><span data-stu-id="0fb03-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="0fb03-104">Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="0fb03-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="0fb03-105">È possibile configurare SharePoint come origine di contenuto didattico per rendere disponibile il contenuto dell'organizzazione in Viva Learning (Preview).</span><span class="sxs-lookup"><span data-stu-id="0fb03-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="0fb03-106">Panoramica</span><span class="sxs-lookup"><span data-stu-id="0fb03-106">Overview</span></span>

<span data-ttu-id="0fb03-107">L'amministratore della knowledge base (o amministratore globale) fornisce un URL del sito in cui il servizio di apprendimento può creare una posizione centralizzata vuota, ovvero l'archivio contenuto app di apprendimento, sotto forma di elenco strutturato di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0fb03-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="0fb03-108">Questo elenco può essere utilizzato dall'organizzazione per ospitare collegamenti a cartelle di SharePoint tra società che contengono contenuto didattico.</span><span class="sxs-lookup"><span data-stu-id="0fb03-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="0fb03-109">Gli amministratori sono responsabili della raccolta e della cura di un elenco di URL per le cartelle.</span><span class="sxs-lookup"><span data-stu-id="0fb03-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="0fb03-110">Queste cartelle devono includere solo il contenuto che può essere reso disponibile in Viva Learning (Anteprima).</span><span class="sxs-lookup"><span data-stu-id="0fb03-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="0fb03-111">Viva Learning (Anteprima) supporta i tipi di documento seguenti:</span><span class="sxs-lookup"><span data-stu-id="0fb03-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="0fb03-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="0fb03-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="0fb03-113">Audio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="0fb03-113">Audio (.m4a)</span></span>
- <span data-ttu-id="0fb03-114">Video (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="0fb03-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="0fb03-115">Per ulteriori informazioni, vedere [Limiti di SharePoint.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)</span><span class="sxs-lookup"><span data-stu-id="0fb03-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="0fb03-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0fb03-116">Permissions</span></span>

<span data-ttu-id="0fb03-117">Gli URL delle cartelle della raccolta documenti possono essere raccolti da qualsiasi sito di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0fb03-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="0fb03-118">Viva Learning (Anteprima) segue tutte le autorizzazioni di contenuto esistenti.</span><span class="sxs-lookup"><span data-stu-id="0fb03-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="0fb03-119">Di conseguenza, solo il contenuto per cui un utente dispone dell'autorizzazione di accesso è disponibile per la ricerca e visibile all'interno di Viva Learning (Anteprima).</span><span class="sxs-lookup"><span data-stu-id="0fb03-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="0fb03-120">Qualsiasi contenuto all'interno di queste cartelle sarà disponibile per la ricerca, ma è possibile utilizzare solo il contenuto per cui il singolo dipendente dispone delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0fb03-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="0fb03-121">L'eliminazione del contenuto dall'archivio dell'organizzazione non è attualmente supportata.</span><span class="sxs-lookup"><span data-stu-id="0fb03-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="0fb03-122">Per rimuovere il contenuto inavvicinatamente in superficie, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="0fb03-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="0fb03-123">Per limitare l'accesso alla raccolta documenti, selezionare **l'opzione Mostra** azioni e quindi selezionare **Gestisci accesso.**</span><span class="sxs-lookup"><span data-stu-id="0fb03-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Pagina raccolta documenti in SharePoint con l'opzione Mostra azioni con l'opzione Gestisci accesso elevato.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="0fb03-125">Eliminare il documento originale all'interno della raccolta documenti.</span><span class="sxs-lookup"><span data-stu-id="0fb03-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="0fb03-126">Per ulteriori informazioni, vedere [Condivisione e autorizzazioni nell'esperienza moderna di SharePoint.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="0fb03-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="0fb03-127">Learning Service</span><span class="sxs-lookup"><span data-stu-id="0fb03-127">Learning Service</span></span>

<span data-ttu-id="0fb03-128">Il servizio di apprendimento usa gli URL delle cartelle forniti per ottenere i metadati da tutto il contenuto archiviato in tali cartelle.</span><span class="sxs-lookup"><span data-stu-id="0fb03-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="0fb03-129">Entro 24 ore dalla fornitura dell'URL della cartella nel repository centralizzato, i dipendenti possono cercare e utilizzare il contenuto dell'organizzazione all'interno di Viva Learning (Anteprima).</span><span class="sxs-lookup"><span data-stu-id="0fb03-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="0fb03-130">Tutte le modifiche apportate al contenuto, inclusi i metadati e le autorizzazioni aggiornati, verranno applicate anche nel servizio di apprendimento entro 24 ore.</span><span class="sxs-lookup"><span data-stu-id="0fb03-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="0fb03-131">Configurare SharePoint come origine</span><span class="sxs-lookup"><span data-stu-id="0fb03-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="0fb03-132">Per eseguire queste attività, è necessario essere un amministratore globale, un amministratore di SharePoint o un amministratore della knowledge base di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0fb03-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="0fb03-133">Per configurare SharePoint come origini di contenuto di apprendimento in Viva Learning (Anteprima), attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="0fb03-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="0fb03-134">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni**  >  **Impostazioni organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="0fb03-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="0fb03-135">Nella scheda **Servizi della**  pagina Impostazioni organizzazione selezionare Viva **Learning (anteprima).**</span><span class="sxs-lookup"><span data-stu-id="0fb03-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Pagina Impostazioni nell'interfaccia di amministrazione di Microsoft 365 che mostra Viva Learning elencato.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="0fb03-137">Nel riquadro **Viva Learning (Anteprima),** in SharePoint, fornisce l'URL del sito di SharePoint in cui si desidera che Viva Learning (Anteprima) crei un archivio centralizzato.</span><span class="sxs-lookup"><span data-stu-id="0fb03-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Riquadro di apprendimento nell'interfaccia di amministrazione di Microsoft 365 che mostra SharePoint selezionato.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="0fb03-139">Un elenco di SharePoint viene creato automaticamente all'interno del sito di SharePoint specificato.</span><span class="sxs-lookup"><span data-stu-id="0fb03-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Elenco di SharePoint appena creato all'interno del sito di SharePoint.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="0fb03-141">Nel riquadro di spostamento sinistro del sito di SharePoint selezionare **Contenuto** del sito  >  **Learning App Content Repository**.</span><span class="sxs-lookup"><span data-stu-id="0fb03-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![Elenco di SharePoint che mostra la struttura di spostamento contenuto del sito e la sezione Archivio contenuto app di apprendimento.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="0fb03-143">Nella pagina **Archivio contenuto app di** apprendimento popolare l'elenco di SharePoint con gli URL nelle cartelle del contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="0fb03-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="0fb03-144">Seleziona **Nuovo** per visualizzare il **pannello Nuovo** elemento.</span><span class="sxs-lookup"><span data-stu-id="0fb03-144">Select **New** to view the **New item** panel.</span></span> 

       ![Pagina Learning Content Repository in SharePoint con l'opzione New.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="0fb03-146">Nel campo **Titolo del**  riquadro Nuovo elemento aggiungere un nome di directory di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="0fb03-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="0fb03-147">Nel campo **URL cartella** aggiungere l'URL alla cartella del contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="0fb03-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="0fb03-148">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0fb03-148">Select **Save**.</span></span>

       ![Riquadro Nuovo elemento in SharePoint che mostra i campi Titolo e URL cartella.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="0fb03-150">La **pagina Archivio contenuto app di** apprendimento viene aggiornata con il nuovo contenuto di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="0fb03-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Pagina Learning Content Repository in SharePoint che mostra le informazioni aggiornate.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="0fb03-152">Per consentire un accesso più ampio all'archivio di contenuto app di apprendimento, presto sarà disponibile un collegamento all'elenco nell'interfaccia Viva Learning (anteprima), in cui gli utenti possono richiedere l'accesso e, in ultima analisi, aiutare a popolare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="0fb03-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="0fb03-153">I proprietari del sito e gli amministratori globali saranno tenuti a concedere l'accesso all'elenco.</span><span class="sxs-lookup"><span data-stu-id="0fb03-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="0fb03-154">Access è specifico solo per l'elenco e non si applica al sito in cui è archiviato l'elenco.</span><span class="sxs-lookup"><span data-stu-id="0fb03-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="0fb03-155">Per ulteriori informazioni, vedere [Fornire il contenuto dell'organizzazione](#provide-your-own-organizations-content) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0fb03-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="0fb03-156">Gestione raccolta documenti URL cartella</span><span class="sxs-lookup"><span data-stu-id="0fb03-156">Folder URL document library curation</span></span>

<span data-ttu-id="0fb03-157">I metadati predefiniti ,ad esempio la data di modifica, creati da, il nome del documento, il tipo di contenuto e il nome dell'organizzazione, vengono automaticamente estratti in Viva Learning (Anteprima) dall'API di Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="0fb03-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="0fb03-158">Per migliorare l'individuazione complessiva e la pertinenza della ricerca del contenuto, è consigliabile aggiungere una **colonna Descrizione.**</span><span class="sxs-lookup"><span data-stu-id="0fb03-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="0fb03-159">Per aggiungere una **colonna Description** alla pagina della raccolta documenti, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="0fb03-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="0fb03-160">Nella pagina **Documenti** selezionare **Aggiungi colonna.**</span><span class="sxs-lookup"><span data-stu-id="0fb03-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="0fb03-161">Selezionare **l'opzione** Mostra azioni e quindi selezionare **Riga di testo singola.**</span><span class="sxs-lookup"><span data-stu-id="0fb03-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Pagina Documenti in SharePoint che mostra le opzioni Mostra azioni con l'opzione Riga di testo singola evidenziata.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="0fb03-163">Nel campo **Nome del** riquadro  Crea colonna aggiungere un nome descrittivo per la colonna.</span><span class="sxs-lookup"><span data-stu-id="0fb03-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="0fb03-164">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0fb03-164">Select **Save**.</span></span>

     ![Creare un pannello a colonne in SharePoint che mostra il nome e altri campi.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="0fb03-166">Nella **colonna** Descrizione della **pagina** Documenti aggiungere descrizioni personalizzate per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="0fb03-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="0fb03-167">Se non viene fornita alcuna descrizione, Viva Learning (Anteprima) fornirà un messaggio predefinito che evidenzia il contenuto come dalla raccolta di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0fb03-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Pagina Documenti in SharePoint che mostra le descrizioni nella colonna Descrizione.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="0fb03-169">Fornire il contenuto dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="0fb03-169">Provide your own organization's content</span></span>

<span data-ttu-id="0fb03-170">Gli amministratori della knowledge base possono accedere all'archivio di contenuto app di apprendimento dell'organizzazione in SharePoint, dove possono fornire riferimenti a raccolte documenti tra organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0fb03-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="0fb03-171">Il contenuto all'interno di queste raccolte verrà quindi visualizzato come contenuto di apprendimento in Viva Learning (Anteprima).</span><span class="sxs-lookup"><span data-stu-id="0fb03-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="0fb03-172">In Viva Learning (Anteprima) seleziona **Altre opzioni** (**...**) e quindi seleziona **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="0fb03-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![Pagina raccolta di SharePoint con l'opzione Altre opzioni e impostazioni.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="0fb03-174">In **Impostazioni** selezionare **Autorizzazioni.**</span><span class="sxs-lookup"><span data-stu-id="0fb03-174">Under **Settings**, select **Permissions**.</span></span>

     ![Pagina dell'opzione Impostazioni in SharePoint che mostra le opzioni Autorizzazioni e Controlla accesso.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="0fb03-176">Selezionare **Controlla accesso** per connettersi alla raccolta centralizzata dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0fb03-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
