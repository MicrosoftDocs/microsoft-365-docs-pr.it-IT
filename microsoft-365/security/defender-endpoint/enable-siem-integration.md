---
title: Abilitare l'integrazione SIEM in Microsoft Defender for Endpoint
description: Abilitare l'integrazione SIEM per ricevere i rilevamenti nella soluzione siEM (Security Information and Event Management).
keywords: abilitare il connettore siem, il siem, il connettore, le informazioni di sicurezza e gli eventi
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 337eb28b7e4b4a7c57b63ff45fb1cea81db43604
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068205"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3bdd3-104">Abilitare l'integrazione SIEM in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3bdd3-104">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3bdd3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3bdd3-105">**Applies to:**</span></span>
- [<span data-ttu-id="3bdd3-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="3bdd3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


><span data-ttu-id="3bdd3-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3bdd3-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3bdd3-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

<span data-ttu-id="3bdd3-109">Abilita l'integrazione delle informazioni di sicurezza e della gestione degli eventi (SIEM) in modo da poter estrarre i rilevamenti da Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-109">Enable security information and event management (SIEM) integration so you can pull detections from Microsoft Defender Security Center.</span></span> <span data-ttu-id="3bdd3-110">Rilevamenti pull usando la soluzione SIEM o connettendosi direttamente all'API REST dei rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-110">Pull detections using your SIEM solution or by connecting directly to the detections REST API.</span></span>

>[!NOTE]
>- <span data-ttu-id="3bdd3-111">[Microsoft Defender for Endpoint Alert](alerts.md) è composto da uno o più rilevamenti.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="3bdd3-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) è composto dall'evento sospetto che si è verificato nel dispositivo e dai relativi dettagli di avviso.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
>- <span data-ttu-id="3bdd3-113">L'API microsoft Defender for Endpoint Alert è l'API più recente per il consumo di avvisi e contiene un elenco dettagliato di prove correlate per ogni avviso.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-113">The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="3bdd3-114">Per ulteriori informazioni, vedere [Metodi e proprietà degli](alerts.md) avvisi e Avvisi [elenco.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="3bdd3-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3bdd3-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3bdd3-115">Prerequisites</span></span>

- <span data-ttu-id="3bdd3-116">L'utente che attiva l'impostazione deve disporre delle autorizzazioni per creare un'app in Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="3bdd3-116">The user who activates the setting must have permissions to create an app in Azure Active Directory (AAD).</span></span> <span data-ttu-id="3bdd3-117">Si tratta di un utente con i ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3bdd3-117">This is someone with the following roles:</span></span> 

  - <span data-ttu-id="3bdd3-118">Amministratore della sicurezza e amministratore globale</span><span class="sxs-lookup"><span data-stu-id="3bdd3-118">Security Administrator and either Global Administrator</span></span>
  - <span data-ttu-id="3bdd3-119">Amministratore applicazione cloud</span><span class="sxs-lookup"><span data-stu-id="3bdd3-119">Cloud Application Administrator</span></span>
  - <span data-ttu-id="3bdd3-120">Amministratore dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="3bdd3-120">Application Administrator</span></span>
  - <span data-ttu-id="3bdd3-121">Proprietario dell'entità servizio</span><span class="sxs-lookup"><span data-stu-id="3bdd3-121">Owner of the service principal</span></span>

- <span data-ttu-id="3bdd3-122">Durante l'attivazione iniziale, viene visualizzata una schermata popup per l'immissione delle credenziali.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-122">During the initial activation, a pop-up screen is displayed for credentials to be entered.</span></span> <span data-ttu-id="3bdd3-123">Assicurarsi di consentire i popup per questo sito.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-123">Make sure that you allow pop-ups for this site.</span></span>

## <a name="enabling-siem-integration"></a><span data-ttu-id="3bdd3-124">Abilitazione dell'integrazione SIEM</span><span class="sxs-lookup"><span data-stu-id="3bdd3-124">Enabling SIEM integration</span></span> 
1. <span data-ttu-id="3bdd3-125">Nel riquadro di spostamento selezionare **Impostazioni**  >  **SIEM.**</span><span class="sxs-lookup"><span data-stu-id="3bdd3-125">In the navigation pane, select **Settings** > **SIEM**.</span></span>

    ![Immagine dell'integrazione SIEM dal menu Impostazioni1](images/enable_siem.png)

    >[!TIP]
    ><span data-ttu-id="3bdd3-127">Se si verifica un errore durante il tentativo di abilitare l'applicazione connettore SIEM, controllare le impostazioni di blocco popup del browser.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-127">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="3bdd3-128">È possibile che la nuova finestra venga aperta quando si abilita la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-128">It might be blocking the new window being opened when you enable the capability.</span></span> 

2. <span data-ttu-id="3bdd3-129">Selezionare **Abilita integrazione SIEM.**</span><span class="sxs-lookup"><span data-stu-id="3bdd3-129">Select **Enable SIEM integration**.</span></span> <span data-ttu-id="3bdd3-130">In questo modo viene attivata la sezione dei dettagli di accesso del connettore **SIEM** con valori precompilato e viene creata un'applicazione nel tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3bdd3-130">This activates the **SIEM connector access details** section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span>

    > [!WARNING]
    ><span data-ttu-id="3bdd3-131">Il segreto client viene visualizzato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-131">The client secret is only displayed once.</span></span> <span data-ttu-id="3bdd3-132">Assicurarsi di conservare una copia in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-132">Make sure you keep a copy of it in a safe place.</span></span><br>
     

    ![Immagine dell'integrazione SIEM dal menu Impostazioni2](images/siem_details.png)

3. <span data-ttu-id="3bdd3-134">Scegliere il tipo di SIEM utilizzato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-134">Choose the SIEM type you use in your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3bdd3-135">Se si seleziona HP ArcSight, sarà necessario salvare questi due file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="3bdd3-135">If you select HP ArcSight, you'll need to save these two configuration files:</span></span><br>
   > - <span data-ttu-id="3bdd3-136">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="3bdd3-136">WDATP-connector.jsonparser.properties</span></span>
   > - <span data-ttu-id="3bdd3-137">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="3bdd3-137">WDATP-connector.properties</span></span> <br>

   <span data-ttu-id="3bdd3-138">Se vuoi connetterti direttamente all'API REST dei rilevamenti tramite l'accesso a livello di codice, scegli **API generica.**</span><span class="sxs-lookup"><span data-stu-id="3bdd3-138">If you want to connect directly to the detections REST API through programmatic access, choose **Generic API**.</span></span>

4. <span data-ttu-id="3bdd3-139">Copiare i singoli valori o selezionare **Salva dettagli nel file** per scaricare un file contenente tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-139">Copy the individual values or select **Save details to file** to download a file that contains all the values.</span></span>

5. <span data-ttu-id="3bdd3-140">Seleziona **Genera token per** ottenere un token di accesso e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-140">Select **Generate tokens** to get an access and refresh token.</span></span>
  
   > [!NOTE]
   > <span data-ttu-id="3bdd3-141">Dovrai generare un nuovo token Refresh ogni 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-141">You'll need to generate a new Refresh token every 90 days.</span></span> 

6. <span data-ttu-id="3bdd3-142">Segui le istruzioni per la [creazione di una registrazione dell'app Azure AD](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) per Microsoft Defender per Endpoint e assegna le autorizzazioni corrette per leggere gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-142">Follow the instructions for [creating an Azure AD app registration for Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) and assign the correct permissions to it to read alerts.</span></span>

<span data-ttu-id="3bdd3-143">Ora puoi procedere con la configurazione della soluzione SIEM o la connessione all'API REST dei rilevamenti tramite l'accesso programmatico.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-143">You can now proceed with configuring your SIEM solution or connecting to the detections REST API through programmatic access.</span></span> <span data-ttu-id="3bdd3-144">Dovrai usare i token durante la configurazione della soluzione SIEM per consentirla di ricevere i rilevamenti da Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-144">You'll need to use the tokens when configuring your SIEM solution to allow it to receive detections from Microsoft Defender Security Center.</span></span>

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a><span data-ttu-id="3bdd3-145">Integrare Microsoft Defender per Endpoint con IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="3bdd3-145">Integrate Microsoft Defender for Endpoint with IBM QRadar</span></span> 
<span data-ttu-id="3bdd3-146">Puoi configurare IBM QRadar per raccogliere i rilevamenti da Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="3bdd3-146">You can configure IBM QRadar to collect detections from Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3bdd3-147">Per ulteriori informazioni, vedere [IBM Knowledge Center.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)</span><span class="sxs-lookup"><span data-stu-id="3bdd3-147">For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

## <a name="see-also"></a><span data-ttu-id="3bdd3-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bdd3-148">See also</span></span>
- [<span data-ttu-id="3bdd3-149">Configurare HP ArcSight per eseguire il pull dei rilevamenti di Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3bdd3-149">Configure HP ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="3bdd3-150">Campi di Microsoft Defender per il rilevamento degli endpoint</span><span class="sxs-lookup"><span data-stu-id="3bdd3-150">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="3bdd3-151">Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST</span><span class="sxs-lookup"><span data-stu-id="3bdd3-151">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="3bdd3-152">Risolvere i problemi di integrazione degli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="3bdd3-152">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
