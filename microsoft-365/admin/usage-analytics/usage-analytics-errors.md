---
title: Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Scopri come risolvere i problemi con l'app modello Analisi di utilizzo di Microsoft 365.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580739"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="f0326-103">Risoluzione dei problemi relativi all'analisi dell'utilizzo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0326-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="f0326-104">Esplorare il seguente elenco di messaggi di errore per ottenere assistenza sui problemi più comuni relativi all'analisi dell'utilizzo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="f0326-105">Non è possibile elaborare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="f0326-105">We are unable to process your request.</span></span> <span data-ttu-id="f0326-106">Devi prima sottoscrivere questi dati dall'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f0326-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="f0326-107">**Codice di errore:** 422</span><span class="sxs-lookup"><span data-stu-id="f0326-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="f0326-108">**Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f0326-109">**Causa:** Prima di connetterti all'app, devi sottoscrivere i dati dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f0326-110">Se questo passaggio non viene eseguito per primo, non potrai connetterti all'app modello, anche se fornisci l'ID tenant di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="f0326-111">**Per correggere l'errore:** Per sottoscrivere i dati, passare all'interfaccia di amministrazione Report Utilizzo e individuare il riquadro Analisi di utilizzo di \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 nella pagina del dashboard principale.</span><span class="sxs-lookup"><span data-stu-id="f0326-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f0326-112">Selezionare il **pulsante Introduzione** e  quindi, nel riquadro Report visualizzato, attivare l'impostazione Rendi disponibili i dati per l'analisi di utilizzo di **Microsoft 365** per Power BI e **Salva.**</span><span class="sxs-lookup"><span data-stu-id="f0326-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="f0326-113">Stiamo elaborando i dati</span><span class="sxs-lookup"><span data-stu-id="f0326-113">We are processing your data</span></span>

 <span data-ttu-id="f0326-114">**Dove verrà visualizzato questo messaggio:** Nel riquadro Analisi di utilizzo di **Microsoft 365** nel dashboard **Utilizzo** nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="f0326-115">**Causa:** Quando [acconsenti esplicitamente](enable-usage-analytics.md) alla visualizzazione dei dati nell'app modello dall'interfaccia di amministrazione di Microsoft 365, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f0326-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f0326-116">A seconda delle dimensioni del tenant, questa operazione potrebbe richiedere da 2 a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="f0326-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f0326-117">**Per risolvere il problema:** Sii paziente, ma se il messaggio non cambia in I tuoi dati sono pronti **dopo** 3 giorni, contatta il supporto di [Microsoft 365 per le aziende.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="f0326-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="f0326-118">Non è possibile elaborare la richiesta in questo momento.</span><span class="sxs-lookup"><span data-stu-id="f0326-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="f0326-119">La preparazione dei dati per l'organizzazione non è ancora terminata</span><span class="sxs-lookup"><span data-stu-id="f0326-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="f0326-120">**Codice di errore:** 423</span><span class="sxs-lookup"><span data-stu-id="f0326-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="f0326-121">**Dove verrà visualizzato questo messaggio:** In Power BI, quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f0326-122">**Causa:** Quando scegli [di visualizzare i](enable-usage-analytics.md) dati nell'app modello dall'interfaccia di amministrazione, il sistema Microsoft 365 inizia a generare dati di utilizzo cronologici per la tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f0326-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f0326-123">A seconda delle dimensioni del tenant, questo passaggio può richiedere da due a 48 ore.</span><span class="sxs-lookup"><span data-stu-id="f0326-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f0326-124">**Per risolvere il problema:** Basta essere pazienti, ma se il  messaggio non cambia in I dati sono pronti anche 3 giorni dopo l'avvio, contattare il supporto [di Microsoft 365 per le aziende](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f0326-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="f0326-125">L'ID tenant specificato non è nel formato corretto</span><span class="sxs-lookup"><span data-stu-id="f0326-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="f0326-126">**Codice di errore:** 400</span><span class="sxs-lookup"><span data-stu-id="f0326-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="f0326-127">**Dove verrà visualizzato questo messaggio:** In Power BI, quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f0326-128">**Causa:** L'ID tenant è un GUID e deve essere nel formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span><span class="sxs-lookup"><span data-stu-id="f0326-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="f0326-129">Se si immette un'altra stringa nella casella di input del tenant, verrà visualizzato questo errore.</span><span class="sxs-lookup"><span data-stu-id="f0326-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="f0326-130">**Per correggere l'errore:** Passare all'interfaccia di amministrazione Report Utilizzo e individuare il riquadro Analisi di utilizzo di \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 nella pagina del dashboard principale.</span><span class="sxs-lookup"><span data-stu-id="f0326-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f0326-131">L'ID tenant è elencato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="f0326-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="f0326-132">Puoi copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello.</span><span class="sxs-lookup"><span data-stu-id="f0326-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="f0326-133">L'ID tenant specificato non è stato riconosciuto dal sistema</span><span class="sxs-lookup"><span data-stu-id="f0326-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="f0326-134">**Codice di errore:** 404</span><span class="sxs-lookup"><span data-stu-id="f0326-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="f0326-135">**Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f0326-136">**Causa:** L'ID tenant specificato non è valido o non esiste.</span><span class="sxs-lookup"><span data-stu-id="f0326-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="f0326-137">**Per correggere l'errore:** Passare all'interfaccia di amministrazione Report Utilizzo e individuare il riquadro Analisi di utilizzo di \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 nella pagina del dashboard principale.</span><span class="sxs-lookup"><span data-stu-id="f0326-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f0326-138">L'ID tenant è elencato nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="f0326-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="f0326-139">Puoi copiarlo da qui e incollarlo nella finestra di dialogo per la connessione all'app modello.</span><span class="sxs-lookup"><span data-stu-id="f0326-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="f0326-140">Immettere di nuovo le credenziali per accedere a Power BI</span><span class="sxs-lookup"><span data-stu-id="f0326-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="f0326-141">Codice di errore: 302</span><span class="sxs-lookup"><span data-stu-id="f0326-141">Error Code: 302</span></span>
  
 <span data-ttu-id="f0326-142">**Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f0326-143">**Causa:** il codice di autorizzazione ha avuto esito negativo e potrebbe essere necessario immettere nuovamente le credenziali.</span><span class="sxs-lookup"><span data-stu-id="f0326-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="f0326-144">**Per correggere l'errore:** disconnettersi da Power BI, quindi eseguire di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f0326-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="f0326-145">Non si ha l'autorizzazione giusta per accedere a questi dati.</span><span class="sxs-lookup"><span data-stu-id="f0326-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="f0326-146">Per accedere ai dati da questo servizio, è necessario essere un amministratore globale o un amministratore prodotto</span><span class="sxs-lookup"><span data-stu-id="f0326-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="f0326-147">**Codice di errore:** 403</span><span class="sxs-lookup"><span data-stu-id="f0326-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="f0326-148">**Dove verrà visualizzato questo messaggio:** In Power BI quando ci si connette all'app modello Analisi di utilizzo di Microsoft 365 o quando si chiamano direttamente le API per la creazione di report di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0326-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f0326-149">**Causa:** Il codice di autorizzazione non è riuscito perché l'utente che ha tentato di connettersi all'app modello non dispone del livello di autorizzazione giusto per accedere a questi dati.</span><span class="sxs-lookup"><span data-stu-id="f0326-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="f0326-150">**Per correggere l'errore:** Fornire le credenziali di un utente che è un amministratore globale, un amministratore  di  **Exchange,** un amministratore di **Skype for Business,** un amministratore di **SharePoint,** un lettore globale o un lettore di report per connettersi all'app modello. </span><span class="sxs-lookup"><span data-stu-id="f0326-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="f0326-151">Per [ulteriori informazioni, vedere Informazioni sui](../add-users/about-admin-roles.md) ruoli di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f0326-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="f0326-152">Aggiornamento non riuscito</span><span class="sxs-lookup"><span data-stu-id="f0326-152">Refresh failed</span></span>

 <span data-ttu-id="f0326-153">**Dove viene visualizzato questo messaggio:** messaggio di posta elettronica da Power BI o stato di errore nella cronologia degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="f0326-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="f0326-154">**Causa:** A volte le credenziali dell'utente connesso all'app modello vengono reimpostate e non aggiornate nelle impostazioni di connessione dell'app modello causando la visualizzazione di errori di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f0326-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="f0326-155">**Per correggere l'errore:** In Power BI individuare il set di dati corrispondente all'app  modello Analisi di utilizzo di Microsoft 365, selezionare pianifica l'aggiornamento e fornire le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f0326-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="f0326-156">Se non funziona, cancella la cache e crea di nuovo l'app modello.</span><span class="sxs-lookup"><span data-stu-id="f0326-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
