---
title: Usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699161"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="1c8dd-103">Usare la procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="1c8dd-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="1c8dd-104">[La creazione di un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) comporta molti passaggi.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="1c8dd-105">È possibile usare questa procedura guidata per creare lo schema e i file modello del tipo di informazioni sensibili (pacchetto di regole) per semplificare il processo.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="1c8dd-106">La procedura guidata per lo schema Exact Data Match e per il tipo di informazioni sensibili è disponibile unicamente per i cloud World Wide e GCC.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="1c8dd-107">Questa procedura guidata può essere usata al posto di:</span><span class="sxs-lookup"><span data-stu-id="1c8dd-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="1c8dd-108">Definire lo schema per il database delle informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="1c8dd-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="1c8dd-109">Configurare un modello (pacchetto di regole)</span><span class="sxs-lookup"><span data-stu-id="1c8dd-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="1c8dd-110">passaggi nella [Parte 1: Configurare una classificazione basata su EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="1c8dd-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="1c8dd-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1c8dd-111">Pre-requisites</span></span>

1. <span data-ttu-id="1c8dd-112">Acquisire familiarità con i passaggi per creare un tipo di informazioni sensibili con il [flusso di lavoro in breve](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) EDM.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="1c8dd-113">Seguire i passaggi nella sezione [Salvare i dati sensibili in formato .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="1c8dd-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="1c8dd-114">Usare la procedura guidata per lo schema Exact Data Match e per il modello del tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="1c8dd-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="1c8dd-115">Nel centro conformità Microsoft 365 per il tenant andare a **Classificazione dei dati** > **Corrispondenze dei dati esatte**.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="1c8dd-116">Scegliere **Creare schema EDM** per aprire il riquadro a comparsa della configurazione della procedura guidata per lo schema.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Riquadro a comparsa della configurazione della procedura guidata per la creazione dello schema EDM.](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="1c8dd-118">Immettere il **Nome** e la **Descrizione** appropriati.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="1c8dd-119">Scegliere **Ignorare delimitatori e punteggiatura per tutti i campi dello schema** se si desidera questo comportamento.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="1c8dd-120">Per scoprire ulteriori informazioni sulla configurazione di EDM per ignorare maiuscole o minuscole e delimitatori, vedere [Creare un tipo di informazioni sensibili personalizzato con una classificazione basata su Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="1c8dd-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="1c8dd-121">Immettere i valori desiderati per il **campo n.1 dello schema** e aggiungere più campi secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1c8dd-122">Almeno un campo dello schema, ma non più di cinque, deve essere designato come disponibile per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="1c8dd-123">Scegliere Salva.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-123">Choose save.</span></span> <span data-ttu-id="1c8dd-124">Ora lo schema sarà incluso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="1c8dd-125">Scegliere **tipi di informazioni sensibili EDM** e **Creare un tipo di informazioni sensibili EDM** per aprire la configurazione guidata per il tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="1c8dd-126">Scegliere **Scegliere uno schema EDM esistente** e scegliere lo schema creato nei passaggi 2-6 in elenco.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="1c8dd-127">Scegliere **Avanti** e **Creare modello**.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="1c8dd-128">Scegliere il **Livello di confidenza** e l'**Elemento primario**.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="1c8dd-129">Per scoprire ulteriori informazioni sulla configurazione di un modello, vedere [Creare un tipo di informazioni sensibili personalizzato nel Centro conformità](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="1c8dd-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="1c8dd-130">Scegliere il **Tipo di informazioni sensibili dell'elemento primario** da associare.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="1c8dd-131">Vedere [Definizioni dell'entità del tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md) per scoprire ulteriori informazioni sui tipi di informazioni sensibili disponibili.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="1c8dd-132">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-132">Choose **Done**.</span></span>

13. <span data-ttu-id="1c8dd-133">Scegliere il **Livello di confidenza e la vicinanza del carattere** desiderati.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="1c8dd-134">Questo sarà il valore predefinito per il tipo completo di informazioni sensibili EDM</span><span class="sxs-lookup"><span data-stu-id="1c8dd-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="1c8dd-135">Scegliere **Creare modello** se si desidera creare modelli aggiuntivi per il tipo di informazioni sensibili EDM.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="1c8dd-136">Scegliere **Avanti** e compilare i campi **Nome** e **Descrizione per gli amministratori**.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="1c8dd-137">Rivedere e scegliere **Invia**.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="1c8dd-138">È possibile eliminare o modificare il modello del tipo di informazioni sensibili dai controlli di modifica ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c8dd-139">Se si desidera rimuovere uno schema già associato a un tipo di informazioni sensibili EDM, è necessario eliminare innanzi tutto il tipo di informazioni sensibili EDM, quindi eliminare lo schema.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="1c8dd-140">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="1c8dd-140">Post steps</span></span>

<span data-ttu-id="1c8dd-141">Dopo aver usato questa configurazione guidata per creare lo schema EDM e i file modello (pacchetto di regole), è ancora necessario eseguire i passaggi nella [Parte 2: hashing e caricamento dei dati sensibili](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) prima di poter usare il tipo di informazioni sensibili EDM personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1c8dd-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>