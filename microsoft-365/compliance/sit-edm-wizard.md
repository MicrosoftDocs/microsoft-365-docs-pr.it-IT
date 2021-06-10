---
title: Usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9d6f870239b963ee7483b9f08e93e40b10f4f0b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878005"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="bf70a-103">Usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="bf70a-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="bf70a-104">[La creazione di un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) comporta molti passaggi.</span><span class="sxs-lookup"><span data-stu-id="bf70a-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="bf70a-105">È possibile utilizzare questa procedura guidata per creare lo schema e i file di modello SIT (Sensitive Information Type) (pacchetto di regole) per semplificare il processo.</span><span class="sxs-lookup"><span data-stu-id="bf70a-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="bf70a-106">La procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili è disponibile unicamente per i cloud World Wide e GCC.</span><span class="sxs-lookup"><span data-stu-id="bf70a-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="bf70a-107">Questa procedura guidata può essere usata al posto di:</span><span class="sxs-lookup"><span data-stu-id="bf70a-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="bf70a-108">Definire lo schema per il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="bf70a-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="bf70a-109">Configurare un modello (pacchetto di regole)</span><span class="sxs-lookup"><span data-stu-id="bf70a-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="bf70a-110">passaggi nella [Parte 1: Configurare una classificazione basata su EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="bf70a-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="bf70a-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bf70a-111">Pre-requisites</span></span>

1. <span data-ttu-id="bf70a-112">Acquisire familiarità con i passaggi per creare un tipo di informazioni sensibili con il [flusso di lavoro in breve](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) EDM.</span><span class="sxs-lookup"><span data-stu-id="bf70a-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="bf70a-113">Eseguire la procedura descritta in Salvare i dati [sensibili in .csv o in formato tsv.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format)</span><span class="sxs-lookup"><span data-stu-id="bf70a-113">Perform the steps in [Save sensitive data in .csv or .tsv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format).</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="bf70a-114">Usare la procedura guidata per lo schema Exact Data Match e per il modello del tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="bf70a-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="bf70a-115">Nel centro conformità Microsoft 365 per il tenant andare a **Classificazione dei dati** > **Corrispondenze dei dati esatte**.</span><span class="sxs-lookup"><span data-stu-id="bf70a-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="bf70a-116">Scegliere **Creare schema EDM** per aprire il riquadro a comparsa della configurazione della procedura guidata per lo schema.</span><span class="sxs-lookup"><span data-stu-id="bf70a-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Riquadro a comparsa della configurazione della procedura guidata per la creazione dello schema EDM.](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="bf70a-118">Immettere il **Nome** e la **Descrizione** appropriati.</span><span class="sxs-lookup"><span data-stu-id="bf70a-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="bf70a-119">Se **si desidera questo comportamento,** scegliere Ignora delimitatori e punteggiatura per tutti i campi dello schema.</span><span class="sxs-lookup"><span data-stu-id="bf70a-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="bf70a-120">Per ulteriori informazioni sulla configurazione di EDM in modo che ignori la distinzione tra maiuscole e minuscole o i delimitatori, vedere [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="bf70a-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="bf70a-121">Immettere i valori desiderati per il **campo n.1 dello schema** e aggiungere più campi secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="bf70a-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="bf70a-122">Almeno un campo dello schema, ma non più di cinque, deve essere designato come disponibile per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="bf70a-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="bf70a-123">Scegliere Salva.</span><span class="sxs-lookup"><span data-stu-id="bf70a-123">Choose save.</span></span> <span data-ttu-id="bf70a-124">Ora lo schema sarà incluso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="bf70a-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="bf70a-125">Scegliere **tipi di informazioni sensibili EDM** e **Creare un tipo di informazioni sensibili EDM** per aprire la configurazione guidata per il tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="bf70a-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="bf70a-126">Scegliere **Scegliere uno schema EDM esistente** e scegliere lo schema creato nei passaggi 2-6 in elenco.</span><span class="sxs-lookup"><span data-stu-id="bf70a-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="bf70a-127">Scegliere **Avanti** e **Creare modello**.</span><span class="sxs-lookup"><span data-stu-id="bf70a-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="bf70a-128">Scegliere il **Livello di confidenza** e l'**Elemento primario**.</span><span class="sxs-lookup"><span data-stu-id="bf70a-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="bf70a-129">Per scoprire ulteriori informazioni sulla configurazione di un modello, vedere [Creare un tipo di informazioni sensibili personalizzato nel Centro conformità](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="bf70a-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="bf70a-130">Scegliere il **Tipo di informazioni sensibili dell'elemento primario** da associare.</span><span class="sxs-lookup"><span data-stu-id="bf70a-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="bf70a-131">Vedere [Definizioni dell'entità del tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md) per scoprire ulteriori informazioni sui tipi di informazioni sensibili disponibili.</span><span class="sxs-lookup"><span data-stu-id="bf70a-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="bf70a-132">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="bf70a-132">Choose **Done**.</span></span>

13. <span data-ttu-id="bf70a-133">Scegliere il **Livello di confidenza e la vicinanza del carattere** desiderati.</span><span class="sxs-lookup"><span data-stu-id="bf70a-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="bf70a-134">Questo sarà il valore predefinito per il tipo completo di informazioni sensibili EDM</span><span class="sxs-lookup"><span data-stu-id="bf70a-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="bf70a-135">Scegliere **Crea modello se** si desidera creare modelli aggiuntivi per il tipo di informazioni riservate EDM.</span><span class="sxs-lookup"><span data-stu-id="bf70a-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="bf70a-136">Scegliere **Avanti** e compilare i campi **Nome** e **Descrizione per gli amministratori**.</span><span class="sxs-lookup"><span data-stu-id="bf70a-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="bf70a-137">Rivedere e scegliere **Invia**.</span><span class="sxs-lookup"><span data-stu-id="bf70a-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="bf70a-138">È possibile eliminare o modificare il modello del tipo di informazioni sensibili dai controlli di modifica ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="bf70a-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf70a-139">Se si desidera rimuovere uno schema già associato a un tipo di informazioni sensibili EDM, è necessario eliminare innanzi tutto il tipo di informazioni sensibili EDM, quindi eliminare lo schema.</span><span class="sxs-lookup"><span data-stu-id="bf70a-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="bf70a-140">Passaggi successivi alla creazione</span><span class="sxs-lookup"><span data-stu-id="bf70a-140">Post creation steps</span></span>

<span data-ttu-id="bf70a-141">Dopo aver usato questa configurazione guidata per creare lo schema EDM e i file modello (pacchetto di regole), è ancora necessario eseguire i passaggi nella [Parte 2: hashing e caricamento dei dati sensibili](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) prima di poter usare il tipo di informazioni sensibili EDM personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bf70a-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="bf70a-142">Dopo aver verificato che la tabella delle informazioni riservate sia stata caricata correttamente, puoi verificare che funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="bf70a-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="bf70a-143">Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.</span><span class="sxs-lookup"><span data-stu-id="bf70a-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="bf70a-144">Seleziona il sit EDM nell'elenco e quindi seleziona **Test** nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="bf70a-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="bf70a-145">Upload un elemento che contiene dati che si desidera rilevare, ad esempio creare un elemento contenente alcuni dei dati nella tabella delle informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="bf70a-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="bf70a-146">Se è stata utilizzata la funzionalità di corrispondenza configurabile nello schema per definire delimitatori ignorati, verificare che l'elemento includa esempi con e senza tali delimitatori.</span><span class="sxs-lookup"><span data-stu-id="bf70a-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="bf70a-147">Dopo il caricamento e l'analisi del file, verificare la presenza di corrispondenze al file SIT EDM.</span><span class="sxs-lookup"><span data-stu-id="bf70a-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="bf70a-148">Se la **funzione Test** in SIT rileva una corrispondenza, verificare che non sia stata tagliata o estratta in modo non corretto.</span><span class="sxs-lookup"><span data-stu-id="bf70a-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="bf70a-149">Ad esempio, estraendo solo una sottostringa della stringa completa che dovrebbe rilevare o raccogliendo solo la prima parola in una stringa di più parole o includendo simboli o caratteri aggiuntivi nell'estrazione.</span><span class="sxs-lookup"><span data-stu-id="bf70a-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="bf70a-150">Per [informazioni di riferimento sul linguaggio](/dotnet/standard/base-types/regular-expression-language-quick-reference) delle espressioni regolari, vedere Regular Expression Language - Guida di riferimento rapido.</span><span class="sxs-lookup"><span data-stu-id="bf70a-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="bf70a-151">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="bf70a-151">Troubleshooting</span></span>

<span data-ttu-id="bf70a-152">Se non vengono trovate corrispondenze, provare a eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf70a-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="bf70a-153">Verificare che i dati sensibili siano stati caricati correttamente utilizzando i comandi illustrati nelle indicazioni per il caricamento dei dati sensibili [tramite lo strumento EDM.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="bf70a-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="bf70a-154">Verificare che gli esempi immessi nell'elemento siano presenti nella tabella delle informazioni riservate e che i delimitatori ignorati siano corretti.</span><span class="sxs-lookup"><span data-stu-id="bf70a-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="bf70a-155">**Testa** il sit usato quando hai configurato l'elemento principale in ognuno dei tuoi modelli.</span><span class="sxs-lookup"><span data-stu-id="bf70a-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="bf70a-156">Ciò confermerà che il sit è in grado di corrispondere agli esempi nell'elemento.</span><span class="sxs-lookup"><span data-stu-id="bf70a-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="bf70a-157">Se l'elemento SIT selezionato per un elemento primario nel tipo EDM non trova una corrispondenza nell'elemento o trova meno corrispondenze del previsto, verificare che supporti i separatori e i delimitatori presenti nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="bf70a-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="bf70a-158">Assicurarsi di includere i delimitatori ignorati definiti nello schema.</span><span class="sxs-lookup"><span data-stu-id="bf70a-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="bf70a-159">Se la **funzione Test** non rileva alcun contenuto, verificare se la funzione SIT selezionata include i requisiti per altre parole chiave o altre convalide.</span><span class="sxs-lookup"><span data-stu-id="bf70a-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="bf70a-160">Per i SIT predefiniti, vedi [Definizioni](sensitive-information-type-entity-definitions.md) di entità dei tipi di informazioni riservate per verificare quali sono i requisiti minimi per la corrispondenza di ogni tipo.</span><span class="sxs-lookup"><span data-stu-id="bf70a-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
