---
title: Configurare Micro Focus ArcSight per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint
description: Configurare Micro Focus ArcSight per ricevere e inviare rilevamenti da Microsoft Defender Security Center
keywords: configurare Micro Focus ArcSight, strumenti di gestione delle informazioni di sicurezza ed eventi, arcsight
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166186"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="a2514-104">Configurare Micro Focus ArcSight per eseguire il pull di Defender per i rilevamenti degli endpoint</span><span class="sxs-lookup"><span data-stu-id="a2514-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2514-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a2514-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2514-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a2514-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a2514-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2514-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a2514-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a2514-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a2514-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a2514-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="a2514-110">Dovrai installare e configurare alcuni file e strumenti per usare Micro Focus ArcSight in modo che possa eseguire il pull di Defender per i rilevamenti degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="a2514-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="a2514-111">[Defender for Endpoint Alert](alerts.md) è composto da uno o più rilevamenti</span><span class="sxs-lookup"><span data-stu-id="a2514-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="a2514-112">[Defender for Endpoint Detection](api-portal-mapping.md) è composto dall'evento sospetto che si è verificato nel dispositivo e dai relativi dettagli di avviso.</span><span class="sxs-lookup"><span data-stu-id="a2514-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a2514-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a2514-113">Before you begin</span></span>

<span data-ttu-id="a2514-114">La configurazione dello strumento Connettore ArcSight micro focus richiede diversi file di configurazione per il pull e l'analisi dei rilevamenti dall'applicazione Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="a2514-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="a2514-115">In questa sezione vengono fornite le informazioni necessarie per impostare e utilizzare correttamente i file di configurazione necessari.</span><span class="sxs-lookup"><span data-stu-id="a2514-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="a2514-116">Assicurati di aver abilitato la funzionalità di integrazione SIEM **dal** menu Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a2514-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="a2514-117">Per altre informazioni, vedi [Abilitare l'integrazione SIEM in Defender per Endpoint.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="a2514-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="a2514-118">Prepara il file salvato dall'abilitazione della funzionalità di integrazione SIEM.</span><span class="sxs-lookup"><span data-stu-id="a2514-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="a2514-119">Dovrai ottenere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2514-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="a2514-120">URL aggiornamento token OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="a2514-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="a2514-121">OAuth 2.0 Client ID</span><span class="sxs-lookup"><span data-stu-id="a2514-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="a2514-122">Segreto client OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="a2514-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="a2514-123">Avere i seguenti file di configurazione pronti:</span><span class="sxs-lookup"><span data-stu-id="a2514-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="a2514-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="a2514-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="a2514-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="a2514-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="a2514-126">Si sarebbe salvato un file ZIP contenente questi due file quando si è scelto Micro Focus ArcSight come tipo SIEM utilizzato nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a2514-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="a2514-127">Assicurati di generare i token seguenti e di averli pronti:</span><span class="sxs-lookup"><span data-stu-id="a2514-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="a2514-128">Token di accesso</span><span class="sxs-lookup"><span data-stu-id="a2514-128">Access token</span></span>
  - <span data-ttu-id="a2514-129">Token di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="a2514-129">Refresh token</span></span>

  <span data-ttu-id="a2514-130">È possibile generare questi token dalla sezione **configurazione dell'integrazione SIEM** del portale.</span><span class="sxs-lookup"><span data-stu-id="a2514-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="a2514-131">Installare e configurare Micro Focus ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="a2514-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="a2514-132">I passaggi seguenti presuppongono che siano stati completati tutti i passaggi necessari in [Prima di iniziare](#before-you-begin).</span><span class="sxs-lookup"><span data-stu-id="a2514-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="a2514-133">Installare il programma di installazione windows FlexConnector a 32 bit più recente.</span><span class="sxs-lookup"><span data-stu-id="a2514-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="a2514-134">È possibile trovarlo in HPE Software Center.</span><span class="sxs-lookup"><span data-stu-id="a2514-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="a2514-135">Lo strumento viene in genere installato nel percorso predefinito seguente: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</span><span class="sxs-lookup"><span data-stu-id="a2514-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="a2514-136">È possibile scegliere dove salvare lo strumento, ad esempio C: \\ *folder_location*\current\bin dove *folder_location* rappresenta il percorso di installazione.</span><span class="sxs-lookup"><span data-stu-id="a2514-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="a2514-137">Eseguire l'installazione guidata tramite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2514-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="a2514-138">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a2514-138">Introduction</span></span>
   - <span data-ttu-id="a2514-139">Scegli cartella di installazione</span><span class="sxs-lookup"><span data-stu-id="a2514-139">Choose Install Folder</span></span>
   - <span data-ttu-id="a2514-140">Scegli set di installazione</span><span class="sxs-lookup"><span data-stu-id="a2514-140">Choose Install Set</span></span>
   - <span data-ttu-id="a2514-141">Scegli cartella di collegamento</span><span class="sxs-lookup"><span data-stu-id="a2514-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="a2514-142">Riepilogo preinstallazione</span><span class="sxs-lookup"><span data-stu-id="a2514-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="a2514-143">Installazione in corso...</span><span class="sxs-lookup"><span data-stu-id="a2514-143">Installing...</span></span>

   <span data-ttu-id="a2514-144">È possibile mantenere i valori predefiniti per ognuna di queste attività o modificare la selezione in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="a2514-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="a2514-145">Apri Esplora file e individua i due file di configurazione salvati quando hai abilitato la funzionalità di integrazione SIEM.</span><span class="sxs-lookup"><span data-stu-id="a2514-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="a2514-146">Inserire i due file nel percorso di installazione di FlexConnector, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a2514-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="a2514-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="a2514-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="a2514-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="a2514-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="a2514-149">È necessario inserire i file di configurazione in questo percorso, dove *folder_location* rappresenta il percorso in cui è stato installato lo strumento.</span><span class="sxs-lookup"><span data-stu-id="a2514-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="a2514-150">Al termine dell'installazione del connettore principale, viene visualizzata la finestra Configurazione connettore.</span><span class="sxs-lookup"><span data-stu-id="a2514-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="a2514-151">Nella finestra Configurazione connettore selezionare **Aggiungi connettore**.</span><span class="sxs-lookup"><span data-stu-id="a2514-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="a2514-152">Selezionare Type: **ArcSight FlexConnector REST** e fare clic su **Next.**</span><span class="sxs-lookup"><span data-stu-id="a2514-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="a2514-153">Digitare le informazioni seguenti nel modulo dei dettagli del parametro.</span><span class="sxs-lookup"><span data-stu-id="a2514-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="a2514-154">Tutti gli altri valori nel modulo sono facoltativi e possono essere lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="a2514-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="a2514-155">Campo</span><span class="sxs-lookup"><span data-stu-id="a2514-155">Field</span></span></th>
    <th><span data-ttu-id="a2514-156">Valore</span><span class="sxs-lookup"><span data-stu-id="a2514-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="a2514-157">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a2514-157">Configuration File</span></span></td>
    <td><span data-ttu-id="a2514-158">Digitare il nome del file delle proprietà del client.</span><span class="sxs-lookup"><span data-stu-id="a2514-158">Type in the name of the client property file.</span></span> <span data-ttu-id="a2514-159">Il nome deve corrispondere al file fornito nel file ZIP scaricato.</span><span class="sxs-lookup"><span data-stu-id="a2514-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="a2514-160">Ad esempio, se il file di configurazione nella directory flexagent è denominato &quot; &quot;WDATP-Connector.jsonparser.properties, è necessario digitare &quot; &quot; &quot; WDATP-Connector &quot; come nome del file delle proprietà client.</span><span class="sxs-lookup"><span data-stu-id="a2514-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="a2514-161">URL eventi</span><span class="sxs-lookup"><span data-stu-id="a2514-161">Events URL</span></span></td>
    <td><span data-ttu-id="a2514-162">A seconda della posizione del datacenter, selezionare l'URL UE o US:</span><span class="sxs-lookup"><span data-stu-id="a2514-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="a2514-163"><b>Per l'UE</b>: https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="a2514-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="a2514-164"><b>Per gli Stati Uniti:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="a2514-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="a2514-165"><b>Per il Regno</b>Unito : https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="a2514-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="a2514-166">Tipo di autenticazione</span><span class="sxs-lookup"><span data-stu-id="a2514-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="a2514-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="a2514-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="a2514-168">File delle proprietà del client OAuth 2</span><span class="sxs-lookup"><span data-stu-id="a2514-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="a2514-169">Passare al percorso del file <em>wdatp-connector.properties.</em></span><span class="sxs-lookup"><span data-stu-id="a2514-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="a2514-170">Il nome deve corrispondere al file fornito nel file ZIP scaricato.</span><span class="sxs-lookup"><span data-stu-id="a2514-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="a2514-171">Token di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="a2514-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="a2514-172">Puoi ottenere un token di aggiornamento in due modi: generando un token di aggiornamento dalla pagina delle impostazioni <b>SIEM</b> o usando lo strumento restutil.</span><span class="sxs-lookup"><span data-stu-id="a2514-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="a2514-173">Per altre informazioni sulla generazione di un token di aggiornamento dalla configurazione <b>delle</b> preferenze, vedi <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Abilitare l'integrazione SIEM in Defender for Endpoint.</a></span><span class="sxs-lookup"><span data-stu-id="a2514-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="a2514-174"><b>Ottieni il token di aggiornamento usando lo strumento restutil:</b> </span><span class="sxs-lookup"><span data-stu-id="a2514-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="a2514-175">a.</span><span class="sxs-lookup"><span data-stu-id="a2514-175">a.</span></span> <span data-ttu-id="a2514-176">Aprire la finestra del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="a2514-176">Open a command prompt.</span></span> <span data-ttu-id="a2514-177">Passare a C:\<em>folder_location</em>\current\bin dove <em>folder_location</em> rappresenta il percorso in cui è stato installato lo strumento.</span><span class="sxs-lookup"><span data-stu-id="a2514-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="a2514-178">b.</span><span class="sxs-lookup"><span data-stu-id="a2514-178">b.</span></span> <span data-ttu-id="a2514-179">Digitare: <code>arcsight restutil token -config</code> dalla directory bin. Ad esempio: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> verrà aperta una finestra del Web browser.</span><span class="sxs-lookup"><span data-stu-id="a2514-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="a2514-180">c.</span><span class="sxs-lookup"><span data-stu-id="a2514-180">c.</span></span> <span data-ttu-id="a2514-181">Digita le credenziali e quindi fai clic sul campo della password per consentire il reindirizzamento della pagina.</span><span class="sxs-lookup"><span data-stu-id="a2514-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="a2514-182">Nel prompt di accesso immetti le credenziali.</span><span class="sxs-lookup"><span data-stu-id="a2514-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="a2514-183">d.</span><span class="sxs-lookup"><span data-stu-id="a2514-183">d.</span></span> <span data-ttu-id="a2514-184">Al prompt dei comandi viene visualizzato un token di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a2514-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="a2514-185">e.</span><span class="sxs-lookup"><span data-stu-id="a2514-185">e.</span></span> <span data-ttu-id="a2514-186">Copiarlo e incollarlo nel <b>campo Token di</b> aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a2514-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="a2514-187">Il connettore apre una finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="a2514-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="a2514-188">Accedere con le credenziali dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2514-188">Login with your application credentials.</span></span> <span data-ttu-id="a2514-189">Dopo l'accesso, ti verrà richiesto di concedere l'autorizzazione al client OAuth2.</span><span class="sxs-lookup"><span data-stu-id="a2514-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="a2514-190">È necessario concedere l'autorizzazione al client OAuth 2 in modo che la configurazione del connettore possa eseguire l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a2514-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="a2514-191">Se <code>redirect_uri</code> l'URL è https, verrà reindirizzato a un URL nell'host locale.</span><span class="sxs-lookup"><span data-stu-id="a2514-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="a2514-192">Verrà visualizzata una pagina che richiede di considerare attendibile il certificato fornito dal connettore in esecuzione nell'host locale.</span><span class="sxs-lookup"><span data-stu-id="a2514-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="a2514-193">Dovrai considerare attendibile questo certificato se il redirect_uri è https.</span><span class="sxs-lookup"><span data-stu-id="a2514-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="a2514-194">Se tuttavia si specifica un URL http per il redirect_uri, non è necessario fornire il consenso per considerare attendibile il certificato.</span><span class="sxs-lookup"><span data-stu-id="a2514-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="a2514-195">Continuare con la configurazione del connettore tornando alla finestra Configurazione connettore ArcSight micro focus.</span><span class="sxs-lookup"><span data-stu-id="a2514-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="a2514-196">Selezionare **ArcSight Manager (crittografato)** come destinazione e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a2514-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="a2514-197">Digitare l'IP/nome host di destinazione in **Manager Hostname** e le credenziali nel modulo parametri.</span><span class="sxs-lookup"><span data-stu-id="a2514-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="a2514-198">Tutti gli altri valori del modulo devono essere mantenuti con i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a2514-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="a2514-199">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2514-199">Click **Next**.</span></span>

11. <span data-ttu-id="a2514-200">Digitare un nome per il connettore nel modulo dei dettagli del connettore.</span><span class="sxs-lookup"><span data-stu-id="a2514-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="a2514-201">Tutti gli altri valori nel modulo sono facoltativi e possono essere lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="a2514-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="a2514-202">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2514-202">Click **Next**.</span></span>

12. <span data-ttu-id="a2514-203">Viene visualizzata la finestra del certificato di importazione di ESM Manager.</span><span class="sxs-lookup"><span data-stu-id="a2514-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="a2514-204">Selezionare **Importa il certificato per il connettore dalla destinazione e** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a2514-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="a2514-205">Viene **visualizzata la finestra Add connector Summary** e il certificato viene importato.</span><span class="sxs-lookup"><span data-stu-id="a2514-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="a2514-206">Verificare che i dettagli nella finestra **Add connector Summary** siano corretti, quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="a2514-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="a2514-207">Selezionare **Installa come servizio e fare** clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a2514-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="a2514-208">Digitare un nome nel **campo Nome interno** servizio.</span><span class="sxs-lookup"><span data-stu-id="a2514-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="a2514-209">Tutti gli altri valori del modulo possono essere mantenuti con i valori predefiniti o lasciati vuoti.</span><span class="sxs-lookup"><span data-stu-id="a2514-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="a2514-210">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2514-210">Click **Next**.</span></span>

16. <span data-ttu-id="a2514-211">Digitare i parametri del servizio e fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a2514-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="a2514-212">Viene visualizzata una finestra **con il riepilogo del** servizio di installazione.</span><span class="sxs-lookup"><span data-stu-id="a2514-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="a2514-213">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2514-213">Click **Next**.</span></span>

17. <span data-ttu-id="a2514-214">Completare l'installazione selezionando **Esci** e **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a2514-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="a2514-215">Installare e configurare la console Di Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="a2514-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="a2514-216">Eseguire l'installazione guidata tramite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2514-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="a2514-217">Introduzione</span><span class="sxs-lookup"><span data-stu-id="a2514-217">Introduction</span></span>
   - <span data-ttu-id="a2514-218">Contratto di licenza</span><span class="sxs-lookup"><span data-stu-id="a2514-218">License Agreement</span></span>
   - <span data-ttu-id="a2514-219">Avviso speciale</span><span class="sxs-lookup"><span data-stu-id="a2514-219">Special Notice</span></span>
   - <span data-ttu-id="a2514-220">Scegliere la directory di installazione di ArcSight</span><span class="sxs-lookup"><span data-stu-id="a2514-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="a2514-221">Scegli cartella di collegamento</span><span class="sxs-lookup"><span data-stu-id="a2514-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="a2514-222">Riepilogo preinstallazione</span><span class="sxs-lookup"><span data-stu-id="a2514-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="a2514-223">Fare clic su **Installa**.</span><span class="sxs-lookup"><span data-stu-id="a2514-223">Click **Install**.</span></span> <span data-ttu-id="a2514-224">Al termine dell'installazione, viene visualizzata la Configurazione guidata console di ArcSight.</span><span class="sxs-lookup"><span data-stu-id="a2514-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="a2514-225">Digitare localhost in **Manager Host Name** e 8443 in Manager **Port,** quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="a2514-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="a2514-226">Selezionare **Usa connessione diretta,** quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a2514-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="a2514-227">Selezionare **Autenticazione basata su password,** quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a2514-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="a2514-228">Selezionare **Si tratta di un'installazione a utente singolo. (Scelta consigliata)** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a2514-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="a2514-229">Fare **clic su Fine** per uscire dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="a2514-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="a2514-230">Accedi alla console Di Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="a2514-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="a2514-231">Passa a **Set di canali attivi** Nuovo prodotto  >  **dispositivo**  >  **dispositivo**  >  **condizione.**</span><span class="sxs-lookup"><span data-stu-id="a2514-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="a2514-232">Impostare **Device Product = Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="a2514-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="a2514-233">Dopo aver verificato che gli eventi fluiranno verso lo strumento, arrestare di nuovo il processo e passare a Servizi di Windows e avviare ArcSight FlexConnector REST.</span><span class="sxs-lookup"><span data-stu-id="a2514-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="a2514-234">È ora possibile eseguire query nella console Di Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="a2514-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="a2514-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft" as the vendor and "Windows Defender ATP" as the device name.</span><span class="sxs-lookup"><span data-stu-id="a2514-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="a2514-236">Risoluzione dei problemi di connessione Di Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="a2514-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="a2514-237">**Problema:** Impossibile aggiornare il token.</span><span class="sxs-lookup"><span data-stu-id="a2514-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="a2514-238">È possibile trovare il registro in C: \\ *folder_location*\current\logs dove *folder_location* rappresenta il percorso in cui è stato installato lo strumento.</span><span class="sxs-lookup"><span data-stu-id="a2514-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="a2514-239">Apri _agent.log_ e cerca `ERROR/FATAL/WARN` .</span><span class="sxs-lookup"><span data-stu-id="a2514-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="a2514-240">**Sintomo:** Viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="a2514-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="a2514-241">**Soluzione:**</span><span class="sxs-lookup"><span data-stu-id="a2514-241">**Solution:**</span></span>

1. <span data-ttu-id="a2514-242">Interrompere il processo facendo clic su Ctrl + C nella finestra Connettore.</span><span class="sxs-lookup"><span data-stu-id="a2514-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="a2514-243">Fare **clic su Y** quando viene richiesto "Termina processo batch Y/N?".</span><span class="sxs-lookup"><span data-stu-id="a2514-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="a2514-244">Passare alla cartella in cui è stato archiviato il file WDATP-connector.properties e modificarlo per aggiungere il valore seguente: `reauthenticate=true` .</span><span class="sxs-lookup"><span data-stu-id="a2514-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="a2514-245">Riavviare il connettore eseguendo il comando seguente: `arcsight.bat connectors` .</span><span class="sxs-lookup"><span data-stu-id="a2514-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="a2514-246">Viene visualizzata una finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="a2514-246">A browser window appears.</span></span> <span data-ttu-id="a2514-247">Consenti l'esecuzione, dovrebbe scomparire e il connettore dovrebbe essere in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a2514-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="a2514-248">Verificare che il connettore sia in esecuzione arrestando di nuovo il processo.</span><span class="sxs-lookup"><span data-stu-id="a2514-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="a2514-249">Riavviare quindi il connettore e non dovrebbe essere visualizzata alcuna finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="a2514-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2514-250">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a2514-250">Related topics</span></span>
- [<span data-ttu-id="a2514-251">Abilitare l'integrazione SIEM in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2514-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="a2514-252">Eseguire il pull dei rilevamenti agli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="a2514-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="a2514-253">Pull Defender for Endpoint detections using REST API</span><span class="sxs-lookup"><span data-stu-id="a2514-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="a2514-254">Risolvere i problemi di integrazione degli strumenti SIEM</span><span class="sxs-lookup"><span data-stu-id="a2514-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
