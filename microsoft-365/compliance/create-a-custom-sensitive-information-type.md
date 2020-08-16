---
title: Creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Scoprire come creare, modificare, rimuovere e testare tipi di informazioni sensibili personalizzati per la prevenzione della perdita dei dati (DLP) nell'interfaccia utente grafica nel Centro sicurezza e conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c54cd9d4969c87bbd83b3048883d8a84dd9bc59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686660"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="63ef1-103">Creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="63ef1-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="63ef1-104">Leggere questo articolo per creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="63ef1-104">Read this article to create a custom sensitive information type in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="63ef1-105">I tipi di informazioni sensibili personalizzati creati con questo metodo vengono aggiunti al pacchetto di regole denominato `Microsoft.SCCManaged.CustomRulePack`.</span><span class="sxs-lookup"><span data-stu-id="63ef1-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="63ef1-106">È anche possibile creare tipi di informazioni sensibili personalizzati usando PowerShell e le funzionalità del classificatore Exact Data Match.</span><span class="sxs-lookup"><span data-stu-id="63ef1-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="63ef1-107">Per altre informazioni su questi metodi, vedere:</span><span class="sxs-lookup"><span data-stu-id="63ef1-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="63ef1-108">Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="63ef1-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="63ef1-109">Creare un tipo di informazioni sensibili personalizzato per DLP con Exact Data Match (EDM)</span><span class="sxs-lookup"><span data-stu-id="63ef1-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

> [!NOTE]
> <span data-ttu-id="63ef1-110">Microsoft 365 Information Protection supporta in anteprima i set di caratteri a due byte per le lingue seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ef1-110">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="63ef1-111">Cinese (semplificato)</span><span class="sxs-lookup"><span data-stu-id="63ef1-111">Chinese (simplified)</span></span>
> - <span data-ttu-id="63ef1-112">Cinese (tradizionale)</span><span class="sxs-lookup"><span data-stu-id="63ef1-112">Chinese (traditional)</span></span>
> - <span data-ttu-id="63ef1-113">Coreano</span><span class="sxs-lookup"><span data-stu-id="63ef1-113">Korean</span></span>
> - <span data-ttu-id="63ef1-114">Giapponese</span><span class="sxs-lookup"><span data-stu-id="63ef1-114">Japanese</span></span>
> 
><span data-ttu-id="63ef1-115">Questa versione di anteprima è disponibile solo nel cloud commerciale e l'implementazione è limitata ai paesi o alle aree geografiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ef1-115">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="63ef1-116">Giappone</span><span class="sxs-lookup"><span data-stu-id="63ef1-116">Japan</span></span>
> - <span data-ttu-id="63ef1-117">Corea del Sud</span><span class="sxs-lookup"><span data-stu-id="63ef1-117">Korea</span></span>
> - <span data-ttu-id="63ef1-118">Cina</span><span class="sxs-lookup"><span data-stu-id="63ef1-118">China</span></span>
> - <span data-ttu-id="63ef1-119">RAS di Hong Kong</span><span class="sxs-lookup"><span data-stu-id="63ef1-119">Hong Kong</span></span>
> - <span data-ttu-id="63ef1-120">RAS di Macao</span><span class="sxs-lookup"><span data-stu-id="63ef1-120">Macau</span></span>
> - <span data-ttu-id="63ef1-121">Taiwan</span><span class="sxs-lookup"><span data-stu-id="63ef1-121">Taiwan</span></span>
>
><span data-ttu-id="63ef1-122">Il supporto è disponibile per i tipi di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="63ef1-122">This support is available for sensitive information types.</span></span> <span data-ttu-id="63ef1-123">Per altre informazioni, vedere [Note sulla versione del supporto della protezione delle informazioni per i set di caratteri a due byte (anteprima)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="63ef1-123">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="63ef1-124">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="63ef1-124">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="63ef1-125">È necessario avere le autorizzazioni di amministratore globale o di amministratore della conformità per creare, testare e distribuire un tipo personalizzato di informazioni riservate tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="63ef1-125">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="63ef1-126">Vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) di Office 365.</span><span class="sxs-lookup"><span data-stu-id="63ef1-126">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="63ef1-127">L'organizzazione deve disporre di un abbonamento, ad esempio Office 365 Enterprise, che includa le funzionalità per la prevenzione della perdita dei dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="63ef1-127">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="63ef1-128">Vedere la descrizione del servizio [Criteri di messaggistica e conformità](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span><span class="sxs-lookup"><span data-stu-id="63ef1-128">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="63ef1-p106">I tipi di informazioni sensibili personalizzati richiedono una certa familiarità con le espressioni regolari (RegEx). Per ulteriori informazioni sul motore Boost.RegEx (in precedenza noto come RegEx++) utilizzato per l'elaborazione del testo, vedere [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p106">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="63ef1-131">Il Supporto tecnico Microsoft non può dare assistenza con la creazione di classificazioni personalizzate o modelli di espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="63ef1-131">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="63ef1-132">I tecnici del supporto possono fornire supporto limitato per la funzionalità, ad esempio fornire esempi di modelli di espressioni regolari a scopo di test o aiutare nella risoluzione dei problemi di un modello di espressione regolare esistente che non si attiva come previsto. Non possono garantire che qualsiasi sviluppo personalizzato di corrispondenza del contenuto soddisfi i requisiti o gli obblighi del cliente.</span><span class="sxs-lookup"><span data-stu-id="63ef1-132">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="63ef1-133">La prevenzione della perdita dei dati usa il crawler di ricerca per identificare e classificare le informazioni sensibili nei siti di SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="63ef1-133">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="63ef1-134">Per identificare il nuovo tipo di informazioni sensibili personalizzato nel contenuto esistente, è necessario ripetere la ricerca per indicizzazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="63ef1-134">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="63ef1-135">Il contenuto viene sottoposto a ricerca per indicizzazione in base a una pianificazione, ma è possibile ripetere manualmente la ricerca per indicizzazione del contenuto per una raccolta siti, un elenco o una raccolta.</span><span class="sxs-lookup"><span data-stu-id="63ef1-135">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="63ef1-136">Per altre informazioni, vedere [Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un sito, di una raccolta o di un elenco](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="63ef1-136">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="63ef1-137">Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="63ef1-137">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="63ef1-138">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-138">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="63ef1-139">Le impostazioni sono abbastanza chiare e vengono spiegate nella pagina della procedura guidata associata:</span><span class="sxs-lookup"><span data-stu-id="63ef1-139">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="63ef1-140">**Nome**</span><span class="sxs-lookup"><span data-stu-id="63ef1-140">**Name**</span></span>

- <span data-ttu-id="63ef1-141">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="63ef1-141">**Description**</span></span>

- <span data-ttu-id="63ef1-142">**Prossimità**</span><span class="sxs-lookup"><span data-stu-id="63ef1-142">**Proximity**</span></span>

- <span data-ttu-id="63ef1-143">**Livello di probabilità**</span><span class="sxs-lookup"><span data-stu-id="63ef1-143">**Confidence level**</span></span>

- <span data-ttu-id="63ef1-144">**Elemento pattern principale** (parole chiave, espressione regolare o dizionario)</span><span class="sxs-lookup"><span data-stu-id="63ef1-144">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="63ef1-145">Facoltativo **Elementi pattern di supporto** (parole chiave, espressione regolare o dizionario) e un valore di **costo minimo** corrispondente.</span><span class="sxs-lookup"><span data-stu-id="63ef1-145">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="63ef1-p109">Ecco uno scenario: si desidera un tipo di informazioni sensibili personalizzato che rilevi i numeri dipendente di 9 cifre nel contenuto, con le parole chiave "dipendente", "ID" e "badge". Per creare un tipo di informazioni sensibili personalizzato, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="63ef1-p109">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="63ef1-148">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-148">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Crea](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="63ef1-150">Nella pagina **Scegliere un nome e una descrizione** che viene visualizzata, immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ef1-150">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="63ef1-151">**Nome**: ID dipendente.</span><span class="sxs-lookup"><span data-stu-id="63ef1-151">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="63ef1-152">**Descrizione**: Rilevare i numeri ID dipendente di Contoso di 9 cifre.</span><span class="sxs-lookup"><span data-stu-id="63ef1-152">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Pagina con nome e descrizione](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="63ef1-154">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-154">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="63ef1-155">Nella pagina **Requisiti per la corrispondenza** che viene visualizzata, fare clic su **Aggiungi un elemento** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ef1-155">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="63ef1-156">**Rilevare il contenuto che contiene**:</span><span class="sxs-lookup"><span data-stu-id="63ef1-156">**Detect content containing**:</span></span>
 
      <span data-ttu-id="63ef1-p110">a. Fare clic su **Una qualsiasi di queste condizioni** e selezionare **Espressione regolare**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-p110">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="63ef1-p111">b. Nella casella di espressione regolare, immettere `(\s)(\d{9})(\s)` (numeri di 9 cifre racchiusi da spazi).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p111">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="63ef1-161">**Elementi di supporto**: fare clic su **Aggiungi gli elementi di supporto** e selezionare **Contiene questo elenco di parole chiave**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-161">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="63ef1-162">Nell'area **Contiene questo elenco di parole chiave** che viene visualizzata, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ef1-162">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="63ef1-163">**Elenco di parole chiave**: immettere il valore seguente: dipendente,ID,badge.</span><span class="sxs-lookup"><span data-stu-id="63ef1-163">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="63ef1-164">**Numero minimo**: lasciare il valore predefinito 1.</span><span class="sxs-lookup"><span data-stu-id="63ef1-164">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="63ef1-165">Lasciare il valore 60 del **Livello di probabilità** predefinito.</span><span class="sxs-lookup"><span data-stu-id="63ef1-165">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="63ef1-166">Lasciare il valore 300 della **Prossimità dei caratteri** predefinito.</span><span class="sxs-lookup"><span data-stu-id="63ef1-166">Leave the default **Character proximity** value 300.</span></span>

    ![Pagina Requisiti per la corrispondenza](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="63ef1-168">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-168">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="63ef1-169">Nella pagina **Verifica e completamento** che viene visualizzata, controllare le impostazioni e fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-169">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Pagina Verifica e completamento](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="63ef1-p112">La pagina successiva invita a testare il nuovo tipo di informazioni sensibili personalizzato facendo clic su **Sì**. Per ulteriori informazioni, vedere **Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità**. Per testare la regola in un secondo momento, fare clic su [No](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p112">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Pagina Suggerimenti per il test](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="63ef1-175">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="63ef1-175">How do you know this worked?</span></span>

<span data-ttu-id="63ef1-176">Per verificare che sia stato creato correttamente un nuovo tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ef1-176">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="63ef1-177">Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e verificare che sia presente il nuovo tipo di informazioni sensibili personalizzato.</span><span class="sxs-lookup"><span data-stu-id="63ef1-177">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="63ef1-p113">Testare il nuovo tipo di informazioni sensibili personalizzato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p113">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="63ef1-180">Modificare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="63ef1-180">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="63ef1-181">**Note**:</span><span class="sxs-lookup"><span data-stu-id="63ef1-181">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="63ef1-p114">È possibile modificare solo i tipi di informazioni sensibili personalizzati; non è possibile modificare quelli predefiniti. Tuttavia, è possibile usare PowerShell per esportare i tipi di informazioni sensibili personalizzati predefiniti, personalizzarli e importarli come tipi di informazioni sensibili personalizzati. Per ulteriori informazioni, vedere [Personalizzare un tipo di informazioni sensibili predefinito](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p114">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="63ef1-p115">È possibile modificare solo i tipi di informazioni riservate personalizzati creati nell'interfaccia utente. Se è stata usata la [procedura di PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) per importare un pacchetto di regole di tipo di informazioni riservate personalizzato, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="63ef1-p115">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="63ef1-187">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**, selezionare il tipo di informazioni sensibili personalizzato da modificare e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-187">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Posizione dei tipi di informazioni riservate e pulsante Modifica](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="63ef1-p116">Le stesse opzioni sono disponibili qui come quando è stato creato il tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p116">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="63ef1-191">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="63ef1-191">How do you know this worked?</span></span>

<span data-ttu-id="63ef1-192">Per verificare che sia stato modificato correttamente un tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="63ef1-192">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="63ef1-193">Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare le proprietà del tipo di informazioni sensibili personalizzato modificato.</span><span class="sxs-lookup"><span data-stu-id="63ef1-193">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="63ef1-p117">Testare il tipo di informazioni sensibili personalizzato modificato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p117">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="63ef1-196">Rimuovere tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="63ef1-196">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="63ef1-197">**Note**:</span><span class="sxs-lookup"><span data-stu-id="63ef1-197">**Notes**:</span></span>

- <span data-ttu-id="63ef1-198">È possibile rimuovere i tipi di informazioni sensibili personalizzati; non è possibile rimuovere quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="63ef1-198">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="63ef1-199">Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="63ef1-199">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="63ef1-200">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e selezionare uno o più tipi di informazioni sensibili personalizzati da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="63ef1-200">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="63ef1-201">Nel menu a comparsa che viene visualizzato, fare clic su **Elimina** (o **Eliminare i tipi di informazioni sensibili** se ne sono stati selezionati più di uno).</span><span class="sxs-lookup"><span data-stu-id="63ef1-201">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Elimina](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="63ef1-203">Nel messaggio di avviso che viene visualizzato, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-203">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="63ef1-204">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="63ef1-204">How do you know this worked?</span></span>

<span data-ttu-id="63ef1-205">Per accertarsi di aver rimosso correttamente un tipo di informazioni sensibili personalizzato, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare che il tipo di informazioni sensibili personalizzato non sia più presente.</span><span class="sxs-lookup"><span data-stu-id="63ef1-205">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="63ef1-206">Testare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="63ef1-206">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="63ef1-207">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-207">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="63ef1-p118">Selezionare uno o più tipi di informazioni sensibili personalizzati da testare. Nel menu a comparsa che viene visualizzato, fare clic su **Tipo di test** (o **Test dei tipi di informazioni sensibili** se ne sono stati selezionati più di uno).</span><span class="sxs-lookup"><span data-stu-id="63ef1-p118">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Tipo di test](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="63ef1-211">Nella pagina **Carica file da testare** che viene visualizzata, caricare un documento per il test trascinando e rilasciando un file o facendo clic su **Sfoglia** e selezionando un file.</span><span class="sxs-lookup"><span data-stu-id="63ef1-211">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Pagina Carica file da testare](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="63ef1-213">Fare clic sul pulsante **Test** per testare il documento per individuare le corrispondenze al criterio nel file.</span><span class="sxs-lookup"><span data-stu-id="63ef1-213">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="63ef1-214">Nella pagina **Risultati corrispondenza** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="63ef1-214">On the **Match results** page, click **Finish**.</span></span>

    ![Risultati corrispondenza](../media/scc-cust-sens-info-type-test-results.png)
