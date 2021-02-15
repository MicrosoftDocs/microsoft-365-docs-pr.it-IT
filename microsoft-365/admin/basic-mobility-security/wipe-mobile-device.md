---
title: Cancellare un dispositivo mobile in Sicurezza e mobilità di base
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
description: Usa i dispositivi mobili e la sicurezza di base predefiniti per rimuovere le informazioni dai dispositivi registrati.
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876829"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="faaf0-103">Cancellare un dispositivo mobile in Sicurezza e mobilità di base</span><span class="sxs-lookup"><span data-stu-id="faaf0-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="faaf0-104">È possibile usare basic mobility and security integrata per Microsoft 365 per rimuovere solo le informazioni dell'organizzazione o per eseguire un ripristino delle impostazioni predefinite per eliminare tutte le informazioni da un dispositivo mobile e ripristinarlo nelle impostazioni di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="faaf0-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="faaf0-105">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="faaf0-105">Before you begin</span></span>

<span data-ttu-id="faaf0-106">I dispositivi mobili possono archiviare informazioni riservate dell'organizzazione e fornire l'accesso alle risorse di Microsoft 365 dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="faaf0-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="faaf0-107">Per proteggere le informazioni dell'organizzazione, è possibile eseguire il ripristino delle impostazioni di fabbrica o rimuovere i dati aziendali:</span><span class="sxs-lookup"><span data-stu-id="faaf0-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="faaf0-108">**Reimpostazione delle** impostazioni di fabbrica: elimina tutti i dati nel dispositivo mobile di un utente, incluse le applicazioni installate, le foto e le informazioni personali.</span><span class="sxs-lookup"><span data-stu-id="faaf0-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="faaf0-109">Al termine della cancellazione, il dispositivo viene ripristinato alle impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="faaf0-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="faaf0-110">**Rimuovere i dati aziendali:** rimuove solo i dati dell'organizzazione e lascia le applicazioni installate, le foto e le informazioni personali nel dispositivo mobile di un utente.</span><span class="sxs-lookup"><span data-stu-id="faaf0-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="faaf0-111">**Quando un dispositivo viene cancellato (reimpostazione delle impostazioni di fabbrica** o rimozione dei dati aziendali), il dispositivo viene rimosso dall'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="faaf0-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="faaf0-112">**Reimpostazione automatica** di un dispositivo: è possibile configurare un criterio di sicurezza e mobilità di base che reimposta automaticamente un dispositivo dopo che l'utente ha tentato invano di immettere la password del dispositivo per un numero specifico di volte.</span><span class="sxs-lookup"><span data-stu-id="faaf0-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="faaf0-113">A tale scopo, seguire i passaggi descritti in [Creare criteri di sicurezza dei dispositivi in dispositivi mobili e sicurezza di base.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="faaf0-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="faaf0-114">**Se si vuole conoscere l'esperienza utente quando** si cancella il dispositivo, vedere   [Qual è l'impatto dell'utente e del dispositivo?](#whats-the-user-and-device-impact).</span><span class="sxs-lookup"><span data-stu-id="faaf0-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="faaf0-115">Cancellare un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="faaf0-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="faaf0-116">Passare all'interfaccia di amministrazione di [Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)</span><span class="sxs-lookup"><span data-stu-id="faaf0-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>

2. <span data-ttu-id="faaf0-117">Digita Gestione dispositivi mobili nel campo di ricerca e seleziona **Gestione dispositivi** mobili nell'elenco dei risultati.</span><span class="sxs-lookup"><span data-stu-id="faaf0-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opzione di gestione dei dispositivi mobili Di base per dispositivi mobili e Secruity":::

3. <span data-ttu-id="faaf0-119">Selezionare **Gestisci dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="faaf0-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="faaf0-120">Selezionare il dispositivo da cui cancellare i dati.</span><span class="sxs-lookup"><span data-stu-id="faaf0-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="faaf0-121">Selezionare **Gestisci.**</span><span class="sxs-lookup"><span data-stu-id="faaf0-121">Select **Manage**.</span></span>

6. <span data-ttu-id="faaf0-122">Selezionare il tipo di cancellazione remota da eseguire.</span><span class="sxs-lookup"><span data-stu-id="faaf0-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="faaf0-123">Per eseguire una cancellazione completa e ripristinare le impostazioni predefinite del dispositivo, selezionare **Reimpostazione delle impostazioni predefinite.**</span><span class="sxs-lookup"><span data-stu-id="faaf0-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="faaf0-124">Per eseguire una cancellazione selettiva ed eliminare solo le informazioni sull'organizzazione di Microsoft 365, selezionare **Rimuovi dati aziendali.**</span><span class="sxs-lookup"><span data-stu-id="faaf0-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="faaf0-125">Per rimuovere il dispositivo dall'organizzazione, selezionare **Rimuovi dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="faaf0-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="faaf0-126">Selezionare **Sì** per confermare.</span><span class="sxs-lookup"><span data-stu-id="faaf0-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="faaf0-127">Come è possibile sapere se l'operazione ha funzionato?</span><span class="sxs-lookup"><span data-stu-id="faaf0-127">How do I know it worked?</span></span>

<span data-ttu-id="faaf0-128">Il dispositivo mobile non viene più visualizzato nell'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="faaf0-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="faaf0-129">Perché vuoi cancellare un dispositivo?</span><span class="sxs-lookup"><span data-stu-id="faaf0-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="faaf0-130">Cancellare un dispositivo per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="faaf0-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="faaf0-131">I dispositivi mobili come smartphone e tablet diventano sempre più completi.</span><span class="sxs-lookup"><span data-stu-id="faaf0-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="faaf0-132">Ciò significa che è più facile per gli utenti archiviare informazioni aziendali sensibili, ad esempio l'identificazione personale o le comunicazioni riservate, e accedervi in viaggio.</span><span class="sxs-lookup"><span data-stu-id="faaf0-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="faaf0-133">Se uno di questi dispositivi mobili viene smarrito o rubato, la pulizia del dispositivo può impedire che le informazioni dell'organizzazione finiranno nelle mani sbagliate.</span><span class="sxs-lookup"><span data-stu-id="faaf0-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="faaf0-134">Quando un utente lascia l'organizzazione con un dispositivo personale registrato in Sicurezza e mobilità di base, puoi impedire alle informazioni dell'organizzazione di usare tale utente eseguendo un ripristino delle impostazioni di fabbrica.</span><span class="sxs-lookup"><span data-stu-id="faaf0-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="faaf0-135">Se l'organizzazione fornisce dispositivi mobili agli utenti, potrebbe essere necessario riassegnare i dispositivi di tanto in tanto.</span><span class="sxs-lookup"><span data-stu-id="faaf0-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="faaf0-136">L'esecuzione di una reimpostazione delle impostazioni di fabbrica su un dispositivo prima di assegnarla a un nuovo utente garantisce che tutte le informazioni riservate del proprietario precedente siano eliminate.</span><span class="sxs-lookup"><span data-stu-id="faaf0-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="faaf0-137">Qual è l'impatto di utenti e dispositivi?</span><span class="sxs-lookup"><span data-stu-id="faaf0-137">What's the user and device impact?</span></span>

<span data-ttu-id="faaf0-138">La cancellazione viene inviata immediatamente al dispositivo mobile e il dispositivo viene contrassegnato come non conforme in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="faaf0-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="faaf0-139">Mentre tutti i dati vengono rimossi quando un dispositivo viene reimpostato sui valori predefiniti delle impostazioni predefinite, la tabella seguente descrive il contenuto rimosso per ogni tipo di dispositivo quando un dispositivo viene rimosso dai dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="faaf0-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="faaf0-140">**Impace del contenuto**</span><span class="sxs-lookup"><span data-stu-id="faaf0-140">**Content impace**</span></span>|<span data-ttu-id="faaf0-141">**iOS 10 e versioni successive**</span><span class="sxs-lookup"><span data-stu-id="faaf0-141">**iOS 10 and later**</span></span>|<span data-ttu-id="faaf0-142">**Android 5 e versioni successive**</span><span class="sxs-lookup"><span data-stu-id="faaf0-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="faaf0-143">I dati delle app di Microsoft 365 vengono cancellati se il dispositivo è protetto dai criteri di protezione delle app di Intune.</span><span class="sxs-lookup"><span data-stu-id="faaf0-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="faaf0-144">Le app non vengono rimosse.</span><span class="sxs-lookup"><span data-stu-id="faaf0-144">The apps aren't removed.</span></span> <span data-ttu-id="faaf0-145">Per i dispositivi non protetti dai criteri di gestione delle applicazioni mobili (MAM, Mobile Application Management), Outlook e OneDrive non rimuoverà i dati memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="faaf0-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="faaf0-146">**Nota** Per applicare i criteri di protezione delle app di Intune, è necessario disporre di una licenza di Intune.</span><span class="sxs-lookup"><span data-stu-id="faaf0-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="faaf0-147">Sì</span><span class="sxs-lookup"><span data-stu-id="faaf0-147">Yes</span></span>|<span data-ttu-id="faaf0-148">Sì</span><span class="sxs-lookup"><span data-stu-id="faaf0-148">Yes</span></span>|
|<span data-ttu-id="faaf0-149">Le impostazioni dei criteri applicate da Dispositivi mobili e sicurezza di base ai dispositivi non vengono più applicate; gli utenti possono modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="faaf0-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="faaf0-150">Sì</span><span class="sxs-lookup"><span data-stu-id="faaf0-150">Yes</span></span>|<span data-ttu-id="faaf0-151">Sì</span><span class="sxs-lookup"><span data-stu-id="faaf0-151">Yes</span></span>|
|<span data-ttu-id="faaf0-152">I profili di posta elettronica creati da Basic Mobility and Security vengono rimossi e i messaggi di posta elettronica memorizzati nella cache nel dispositivo vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="faaf0-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="faaf0-153">Sì</span><span class="sxs-lookup"><span data-stu-id="faaf0-153">Yes</span></span>|<span data-ttu-id="faaf0-154">N/D</span><span class="sxs-lookup"><span data-stu-id="faaf0-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="faaf0-155">L'app Portale aziendale è disponibile nell'App Store per iOS e nel Play Store per dispositivi Android.</span><span class="sxs-lookup"><span data-stu-id="faaf0-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="faaf0-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="faaf0-156">Related topics</span></span>

[<span data-ttu-id="faaf0-157">Impostare Basic Mobility + Security</span><span class="sxs-lookup"><span data-stu-id="faaf0-157">Set up Basic Mobility and Security</span></span>](set-up.md)