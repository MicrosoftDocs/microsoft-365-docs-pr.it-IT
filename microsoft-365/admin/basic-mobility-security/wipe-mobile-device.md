---
title: Cancellare un dispositivo mobile in Dispositivi mobili e sicurezza di base
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Usa dispositivi mobili e sicurezza di base incorporati per rimuovere le informazioni dai dispositivi registrati.
ms.openlocfilehash: ddf13ef6627d70128064e2d8bd185203244b12e4
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819809"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="8e75b-103">Cancellare un dispositivo mobile in Dispositivi mobili e sicurezza di base</span><span class="sxs-lookup"><span data-stu-id="8e75b-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="8e75b-104">È possibile utilizzare la funzionalità di sicurezza e mobilità di base predefinita per Microsoft 365 per rimuovere solo le informazioni dell'organizzazione o per eseguire una reimpostazione di fabbrica per eliminare tutte le informazioni da un dispositivo mobile e ripristinarlo nelle impostazioni di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="8e75b-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8e75b-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8e75b-105">Before you begin</span></span>

<span data-ttu-id="8e75b-106">I dispositivi mobili possono archiviare informazioni riservate dell'organizzazione e fornire l'accesso alle risorse di Microsoft 365 dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8e75b-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="8e75b-107">Per proteggere le informazioni dell'organizzazione, è possibile eseguire la reimpostazione o la rimozione dei dati aziendali:</span><span class="sxs-lookup"><span data-stu-id="8e75b-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="8e75b-108">**Reimpostazione in** fabbrica: elimina tutti i dati nel dispositivo mobile di un utente, incluse le applicazioni installate, le foto e le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="8e75b-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="8e75b-109">Al termine della cancellazione, il dispositivo viene ripristinato con le impostazioni di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="8e75b-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="8e75b-110">**Rimuovi dati aziendali**: rimuove solo i dati dell'organizzazione e lascia le applicazioni, le foto e le informazioni personali installate nel dispositivo mobile di un utente.</span><span class="sxs-lookup"><span data-stu-id="8e75b-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="8e75b-111">**Quando un dispositivo viene cancellato (Reimpostazione in fabbrica o** Rimuovi dati aziendali), il dispositivo viene rimosso dall'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="8e75b-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="8e75b-112">**Reimposta automaticamente un** dispositivo: puoi configurare un criterio di sicurezza e mobilità di base che reimposta automaticamente un dispositivo dopo che l'utente ha tentato invano di immettere la password del dispositivo per un numero specifico di volte.</span><span class="sxs-lookup"><span data-stu-id="8e75b-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="8e75b-113">A tale scopo, seguire i passaggi descritti in [Creare criteri di sicurezza dei dispositivi in dispositivi mobili e sicurezza di base.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8e75b-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="8e75b-114">**Se vuoi conoscere l'esperienza utente durante** la cancellazione del dispositivo, vedi Qual   [è l'impatto dell'utente e del dispositivo?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="8e75b-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="8e75b-115">Cancellare un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="8e75b-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="8e75b-116">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span><span class="sxs-lookup"><span data-stu-id="8e75b-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="8e75b-117">Digita Gestione dispositivi mobili nel campo di ricerca e seleziona **Gestione dispositivi mobili** nell'elenco dei risultati.</span><span class="sxs-lookup"><span data-stu-id="8e75b-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opzione di gestione dei dispositivi mobili di base per dispositivi mobili e secruity":::

3. <span data-ttu-id="8e75b-119">Seleziona **Gestisci dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="8e75b-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="8e75b-120">Selezionare il dispositivo da cui cancellare i dati.</span><span class="sxs-lookup"><span data-stu-id="8e75b-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="8e75b-121">Selezionare **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="8e75b-121">Select **Manage**.</span></span>

6. <span data-ttu-id="8e75b-122">Selezionare il tipo di cancellazione remota da eseguire.</span><span class="sxs-lookup"><span data-stu-id="8e75b-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="8e75b-123">Per eseguire una cancellazione completa e ripristinare le impostazioni di fabbrica del dispositivo, seleziona **Reimpostazione in fabbrica.**</span><span class="sxs-lookup"><span data-stu-id="8e75b-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="8e75b-124">Per eseguire una cancellazione selettiva ed eliminare solo le informazioni dell'organizzazione di Microsoft 365, selezionare **Rimuovi dati aziendali.**</span><span class="sxs-lookup"><span data-stu-id="8e75b-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="8e75b-125">Per rimuovere il dispositivo dall'organizzazione, seleziona **Rimuovi dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="8e75b-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="8e75b-126">Selezionare **Sì** per confermare.</span><span class="sxs-lookup"><span data-stu-id="8e75b-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="8e75b-127">Come si fa a sapere che ha funzionato?</span><span class="sxs-lookup"><span data-stu-id="8e75b-127">How do I know it worked?</span></span>

<span data-ttu-id="8e75b-128">Il dispositivo mobile non viene più visualizzato nell'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="8e75b-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="8e75b-129">Perché vuoi cancellare un dispositivo?</span><span class="sxs-lookup"><span data-stu-id="8e75b-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="8e75b-130">Cancella un dispositivo per questi motivi:</span><span class="sxs-lookup"><span data-stu-id="8e75b-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="8e75b-131">I dispositivi mobili come smartphone e tablet stanno diventando sempre più completi.</span><span class="sxs-lookup"><span data-stu-id="8e75b-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="8e75b-132">Ciò significa che è più facile per gli utenti archiviare informazioni aziendali sensibili, ad esempio l'identificazione personale o le comunicazioni riservate e accedervi in viaggio.</span><span class="sxs-lookup"><span data-stu-id="8e75b-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="8e75b-133">Se uno di questi dispositivi mobili viene perso o rubato, la pulizia del dispositivo può impedire che le informazioni dell'organizzazione finiranno nelle mani sbagliate.</span><span class="sxs-lookup"><span data-stu-id="8e75b-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="8e75b-134">Quando un utente lascia l'organizzazione con un dispositivo personale registrato in Dispositivi mobili e sicurezza di base, puoi impedire alle informazioni dell'organizzazione di accedere a tale utente eseguendo una reimpostazione in fabbrica.</span><span class="sxs-lookup"><span data-stu-id="8e75b-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="8e75b-135">Se l'organizzazione fornisce dispositivi mobili agli utenti, potrebbe essere necessario riassegnare i dispositivi di tanto in tanto.</span><span class="sxs-lookup"><span data-stu-id="8e75b-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="8e75b-136">L'esecuzione di una reimpostazione in fabbrica su un dispositivo prima di assegnarla a un nuovo utente garantisce che le informazioni riservate del proprietario precedente siano eliminate.</span><span class="sxs-lookup"><span data-stu-id="8e75b-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="8e75b-137">Qual è l'impatto su utenti e dispositivi?</span><span class="sxs-lookup"><span data-stu-id="8e75b-137">What's the user and device impact?</span></span>

<span data-ttu-id="8e75b-138">La cancellazione viene inviata immediatamente al dispositivo mobile e il dispositivo viene contrassegnato come non conforme in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8e75b-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="8e75b-139">Mentre tutti i dati vengono rimossi quando un dispositivo viene reimpostato sui valori predefiniti di fabbrica, nella tabella seguente viene descritto il contenuto rimosso per ogni tipo di dispositivo quando si rimuove un dispositivo quando si rimuovono i dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="8e75b-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="8e75b-140">**Impatto sul contenuto**</span><span class="sxs-lookup"><span data-stu-id="8e75b-140">**Content impact**</span></span>|<span data-ttu-id="8e75b-141">**iOS 10 e versioni successive**</span><span class="sxs-lookup"><span data-stu-id="8e75b-141">**iOS 10 and later**</span></span>|<span data-ttu-id="8e75b-142">**Android 5 e versioni successive**</span><span class="sxs-lookup"><span data-stu-id="8e75b-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8e75b-143">I dati delle app di Microsoft 365 vengono cancellati se il dispositivo è protetto dai criteri di Protezione app di Intune.</span><span class="sxs-lookup"><span data-stu-id="8e75b-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="8e75b-144">Le app non vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="8e75b-144">The apps aren't removed.</span></span> <span data-ttu-id="8e75b-145">Per i dispositivi non protetti dai criteri DIM (Mobile Application Management), Outlook e OneDrive non rimuovono i dati memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="8e75b-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="8e75b-146">**Nota** Per l'applicazione dei criteri di protezione delle app di Intune è necessario disporre di una licenza di Intune.</span><span class="sxs-lookup"><span data-stu-id="8e75b-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="8e75b-147">Sì</span><span class="sxs-lookup"><span data-stu-id="8e75b-147">Yes</span></span>|<span data-ttu-id="8e75b-148">Sì</span><span class="sxs-lookup"><span data-stu-id="8e75b-148">Yes</span></span>|
|<span data-ttu-id="8e75b-149">Le impostazioni dei criteri applicate da Dispositivi mobili e sicurezza di base ai dispositivi non vengono più applicate. gli utenti possono modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="8e75b-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="8e75b-150">Sì</span><span class="sxs-lookup"><span data-stu-id="8e75b-150">Yes</span></span>|<span data-ttu-id="8e75b-151">Sì</span><span class="sxs-lookup"><span data-stu-id="8e75b-151">Yes</span></span>|
|<span data-ttu-id="8e75b-152">I profili di posta elettronica creati da Dispositivi mobili e sicurezza di base vengono rimossi e la posta elettronica memorizzata nella cache nel dispositivo viene eliminata.</span><span class="sxs-lookup"><span data-stu-id="8e75b-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="8e75b-153">Sì</span><span class="sxs-lookup"><span data-stu-id="8e75b-153">Yes</span></span>|<span data-ttu-id="8e75b-154">N/D</span><span class="sxs-lookup"><span data-stu-id="8e75b-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="8e75b-155">L'app Portale aziendale è disponibile nell'App Store per iOS e nel Play Store per dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="8e75b-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e75b-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8e75b-156">Related topics</span></span>

[<span data-ttu-id="8e75b-157">Impostare Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="8e75b-157">Set up Basic Mobility and Security</span></span>](set-up.md)
