---
title: Creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità
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
ms.openlocfilehash: fbce658eadbffb22d4d8ba65d040503a5854b77f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083158"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="a7c0a-103">Creare un tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a7c0a-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

## <a name="summary"></a><span data-ttu-id="a7c0a-104">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a7c0a-104">Summary</span></span>

<span data-ttu-id="a7c0a-105">Leggere questo articolo per creare un [tipo di informazioni sensibili personalizzato](custom-sensitive-info-types.md) nel Centro sicurezza e conformità ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-105">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="a7c0a-106">I tipi di informazioni sensibili personalizzati creati con questo metodo vengono aggiunti al pacchetto di regole denominato `Microsoft.SCCManaged.CustomRulePack`.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-106">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="a7c0a-107">È anche possibile creare tipi di informazioni sensibili personalizzati usando PowerShell e le funzionalità del classificatore Exact Data Match.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-107">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="a7c0a-108">Per altre informazioni su questi metodi, vedere:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-108">To learn more about those methods, see:</span></span>
- <span data-ttu-id="a7c0a-109">[Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a7c0a-109">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>
- [<span data-ttu-id="a7c0a-110">Creare un tipo di informazioni sensibili personalizzato per DLP con Exact Data Match (EDM)</span><span class="sxs-lookup"><span data-stu-id="a7c0a-110">Create a custom sensitive information type with Exact Data Match (Preview)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a><span data-ttu-id="a7c0a-111">Prima di iniziare...</span><span class="sxs-lookup"><span data-stu-id="a7c0a-111">Before you begin</span></span>

- <span data-ttu-id="a7c0a-112">L'organizzazione deve disporre di un abbonamento, ad esempio Office 365 Enterprise, che includa le funzionalità per la prevenzione della perdita dei dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-112">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="a7c0a-113">Vedere la descrizione del servizio [Criteri di messaggistica e conformità](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-113">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="a7c0a-p104">I tipi di informazioni sensibili personalizzati richiedono una certa familiarità con le espressioni regolari (RegEx). Per ulteriori informazioni sul motore Boost.RegEx (in precedenza noto come RegEx++) utilizzato per l'elaborazione del testo, vedere [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p104">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="a7c0a-116">Il Supporto tecnico Microsoft non può dare assistenza con la creazione di classificazioni personalizzate o modelli di espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-116">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="a7c0a-117">I tecnici del supporto possono fornire supporto limitato per la funzionalità, ad esempio fornire esempi di modelli di espressioni regolari a scopo di test o aiutare nella risoluzione dei problemi di un modello di espressione regolare esistente che non si attiva come previsto. Non possono garantire che qualsiasi sviluppo personalizzato di corrispondenza del contenuto soddisfi i requisiti o gli obblighi del cliente.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-117">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="a7c0a-118">La prevenzione della perdita dei dati usa il crawler di ricerca per identificare e classificare le informazioni sensibili nei siti di SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-118">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="a7c0a-119">Per identificare il nuovo tipo di informazioni sensibili personalizzato nel contenuto esistente, è necessario ripetere la ricerca per indicizzazione del contenuto.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-119">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="a7c0a-120">Il contenuto viene sottoposto a ricerca per indicizzazione in base a una pianificazione, ma è possibile ripetere manualmente la ricerca per indicizzazione del contenuto per una raccolta siti, un elenco o una raccolta.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-120">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="a7c0a-121">Per altre informazioni, vedere [Richiedere manualmente la ricerca per indicizzazione e la reindicizzazione di un sito, di una raccolta o di un elenco](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-121">For more information, see [Manually request crawling and re-indexing of a site, a library or a listhttp://go.microsoft.com/fwlink/p/?LinkID=627457](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a7c0a-122">Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a7c0a-122">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="a7c0a-123">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-123">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="a7c0a-124">Le impostazioni sono abbastanza chiare e vengono spiegate nella pagina della procedura guidata associata:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-124">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="a7c0a-125">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a7c0a-125">**Name**</span></span>

- <span data-ttu-id="a7c0a-126">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a7c0a-126">**Description**</span></span>

- <span data-ttu-id="a7c0a-127">**Prossimità**</span><span class="sxs-lookup"><span data-stu-id="a7c0a-127">**Proximity**</span></span>

- <span data-ttu-id="a7c0a-128">**Livello di probabilità**</span><span class="sxs-lookup"><span data-stu-id="a7c0a-128">**Confidence level**</span></span>

- <span data-ttu-id="a7c0a-129">**Elemento pattern principale** (parole chiave, espressione regolare o dizionario)</span><span class="sxs-lookup"><span data-stu-id="a7c0a-129">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="a7c0a-130">Facoltativo **Elementi pattern di supporto** (parole chiave, espressione regolare o dizionario) e un valore di **costo minimo** corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-130">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="a7c0a-p107">Ecco uno scenario: si desidera un tipo di informazioni sensibili personalizzato che rilevi i numeri dipendente di 9 cifre nel contenuto, con le parole chiave "dipendente", "ID" e "badge". Per creare un tipo di informazioni sensibili personalizzato, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p107">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="a7c0a-133">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-133">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Crea](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="a7c0a-135">Nella pagina **Scegliere un nome e una descrizione** che viene visualizzata, immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-135">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="a7c0a-136">**Nome**: ID dipendente.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-136">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="a7c0a-137">**Descrizione**: Rilevare i numeri ID dipendente di Contoso di 9 cifre.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-137">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Pagina con nome e descrizione](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="a7c0a-139">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-139">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="a7c0a-140">Nella pagina **Requisiti per la corrispondenza** che viene visualizzata, fare clic su **Aggiungi un elemento** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-140">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="a7c0a-141">**Rilevare il contenuto che contiene**:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-141">**Detect content containing**:</span></span>
 
      <span data-ttu-id="a7c0a-p108">a. Fare clic su **Una qualsiasi di queste condizioni** e selezionare **Espressione regolare**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p108">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="a7c0a-p109">b. Nella casella di espressione regolare, immettere `(\s)(\d{9})(\s)` (numeri di 9 cifre racchiusi da spazi).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p109">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="a7c0a-146">**Elementi di supporto**: fare clic su **Aggiungi gli elementi di supporto** e selezionare **Contiene questo elenco di parole chiave**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-146">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="a7c0a-147">Nell'area **Contiene questo elenco di parole chiave** che viene visualizzata, configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-147">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="a7c0a-148">**Elenco di parole chiave**: immettere il valore seguente: dipendente,ID,badge.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-148">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="a7c0a-149">**Numero minimo**: lasciare il valore predefinito 1.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-149">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="a7c0a-150">Lasciare il valore 60 del **Livello di probabilità** predefinito.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-150">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="a7c0a-151">Lasciare il valore 300 della **Prossimità dei caratteri** predefinito.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-151">Leave the default **Character proximity** value 300.</span></span>

    ![Pagina Requisiti per la corrispondenza](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="a7c0a-153">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="a7c0a-154">Nella pagina **Verifica e completamento** che viene visualizzata, controllare le impostazioni e fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-154">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Pagina Verifica e completamento](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="a7c0a-p110">La pagina successiva invita a testare il nuovo tipo di informazioni sensibili personalizzato facendo clic su **Sì**. Per ulteriori informazioni, vedere **Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità**. Per testare la regola in un secondo momento, fare clic su [No](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p110">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Pagina Suggerimenti per il test](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a7c0a-160">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="a7c0a-160">How do you know this worked?</span></span>

<span data-ttu-id="a7c0a-161">Per verificare che sia stato creato correttamente un nuovo tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-161">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="a7c0a-162">Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e verificare che sia presente il nuovo tipo di informazioni sensibili personalizzato.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-162">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="a7c0a-p111">Testare il nuovo tipo di informazioni sensibili personalizzato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p111">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a7c0a-165">Modificare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a7c0a-165">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="a7c0a-166">**Note**:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-166">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="a7c0a-p112">È possibile modificare solo i tipi di informazioni sensibili personalizzati; non è possibile modificare quelli predefiniti. Tuttavia, è possibile usare PowerShell per esportare i tipi di informazioni sensibili personalizzati predefiniti, personalizzarli e importarli come tipi di informazioni sensibili personalizzati. Per ulteriori informazioni, vedere [Personalizzare un tipo di informazioni sensibili predefinito](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p112">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="a7c0a-p113">È possibile modificare solo i tipi di informazioni riservate personalizzati creati nell'interfaccia utente. Se è stata usata la [procedura di PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) per importare un pacchetto di regole di tipo di informazioni riservate personalizzato, si riceverà un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p113">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="a7c0a-172">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**, selezionare il tipo di informazioni sensibili personalizzato da modificare e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-172">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Posizione dei tipi di informazioni riservate e pulsante Modifica](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="a7c0a-p114">Le stesse opzioni sono disponibili qui come quando è stato creato il tipo di informazioni sensibili personalizzato nel Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p114">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a7c0a-176">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="a7c0a-176">How do you know this worked?</span></span>

<span data-ttu-id="a7c0a-177">Per verificare che sia stato modificato correttamente un tipo di informazioni sensibili, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-177">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="a7c0a-178">Accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare le proprietà del tipo di informazioni sensibili personalizzato modificato.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-178">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="a7c0a-p115">Testare il tipo di informazioni sensibili personalizzato modificato. Per ulteriori informazioni, vedere [Testare i tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p115">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a7c0a-181">Rimuovere tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a7c0a-181">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="a7c0a-182">**Note**:</span><span class="sxs-lookup"><span data-stu-id="a7c0a-182">**Notes**:</span></span>

- <span data-ttu-id="a7c0a-183">È possibile rimuovere i tipi di informazioni sensibili personalizzati; non è possibile rimuovere quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-183">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="a7c0a-184">Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-184">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="a7c0a-185">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** e selezionare uno o più tipi di informazioni sensibili personalizzati da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-185">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="a7c0a-186">Nel menu a comparsa che viene visualizzato, fare clic su **Elimina** (o **Eliminare i tipi di informazioni sensibili** se ne sono stati selezionati più di uno).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-186">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Elimina](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="a7c0a-188">Nel messaggio di avviso che viene visualizzato, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-188">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a7c0a-189">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="a7c0a-189">How do you know this worked?</span></span>

<span data-ttu-id="a7c0a-190">Per accertarsi di aver rimosso correttamente un tipo di informazioni sensibili personalizzato, accedere a **Classificazioni** \> **Tipi di informazioni sensibili** per verificare che il tipo di informazioni sensibili personalizzato non sia più presente.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-190">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="a7c0a-191">Testare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="a7c0a-191">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="a7c0a-192">Nel Centro sicurezza e conformità, accedere a **Classificazioni** \> **Tipi di informazioni sensibili**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-192">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="a7c0a-p116">Selezionare uno o più tipi di informazioni sensibili personalizzati da testare. Nel menu a comparsa che viene visualizzato, fare clic su **Tipo di test** (o **Test dei tipi di informazioni sensibili** se ne sono stati selezionati più di uno).</span><span class="sxs-lookup"><span data-stu-id="a7c0a-p116">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Posizione dei tipi di informazioni riservate e pulsante Tipo di test](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="a7c0a-196">Nella pagina **Carica file da testare** che viene visualizzata, caricare un documento per il test trascinando e rilasciando un file o facendo clic su **Sfoglia** e selezionando un file.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-196">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Pagina Carica file da testare](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="a7c0a-198">Fare clic sul pulsante **Test** per testare il documento per individuare le corrispondenze al criterio nel file.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-198">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="a7c0a-199">Nella pagina **Risultati corrispondenza** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a7c0a-199">On the **Match results** page, click **Finish**.</span></span>

    ![Risultati corrispondenza](media/scc-cust-sens-info-type-test-results.png)