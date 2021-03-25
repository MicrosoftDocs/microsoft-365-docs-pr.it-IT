---
title: Nuovi profili di configurazione per macOS Catalina e versioni più recenti di macOS
description: In questo argomento vengono descritte le modifiche che devono essere apportate per trarre vantaggio dalle estensioni di sistema, che sostituggono le estensioni del kernel in macOS Catalina e le versioni più recenti di macOS.
keywords: microsoft, defender, atp, mac, kernel, sistema, estensioni, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: c46ae6e690f0127a7ae412101f5183d0fe8c183e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066381"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a><span data-ttu-id="f676a-104">Nuovi profili di configurazione per macOS Catalina e versioni più recenti di macOS</span><span class="sxs-lookup"><span data-stu-id="f676a-104">New configuration profiles for macOS Catalina and newer versions of macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f676a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f676a-105">**Applies to:**</span></span>
- [<span data-ttu-id="f676a-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f676a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f676a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f676a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f676a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="f676a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f676a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="f676a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f676a-110">In linea con l'evoluzione di macOS, stiamo preparando un aggiornamento di Microsoft Defender per Endpoint per Mac che sfrutta le estensioni di sistema anziché le estensioni del kernel.</span><span class="sxs-lookup"><span data-stu-id="f676a-110">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="f676a-111">Questo aggiornamento sarà applicabile solo a macOS Catalina (10.15.4) e alle versioni più recenti di macOS.</span><span class="sxs-lookup"><span data-stu-id="f676a-111">This update will only be applicable to macOS Catalina (10.15.4) and newer versions of macOS.</span></span>

<span data-ttu-id="f676a-112">Se hai distribuito Microsoft Defender per Endpoint per Mac in un ambiente gestito (tramite JAMF, Intune o un'altra soluzione MDM), devi distribuire nuovi profili di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f676a-112">If you have deployed Microsoft Defender for Endpoint for Mac in a managed environment (through JAMF, Intune, or another MDM solution), you must deploy new configuration profiles.</span></span> <span data-ttu-id="f676a-113">Se non si esegue questa procedura, gli utenti riceveranno richieste di approvazione per eseguire questi nuovi componenti.</span><span class="sxs-lookup"><span data-stu-id="f676a-113">Failure to do these steps will result in users getting approval prompts to run these new components.</span></span>

## <a name="jamf"></a><span data-ttu-id="f676a-114">JAMF</span><span class="sxs-lookup"><span data-stu-id="f676a-114">JAMF</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="f676a-115">Criteri estensioni di sistema</span><span class="sxs-lookup"><span data-stu-id="f676a-115">System Extensions Policy</span></span>

<span data-ttu-id="f676a-116">Per approvare le estensioni di sistema, crea il payload seguente:</span><span class="sxs-lookup"><span data-stu-id="f676a-116">To approve the system extensions, create the following payload:</span></span>

1. <span data-ttu-id="f676a-117">In **Computers > Configuration Profiles selezionare** Options > System **Extensions**.</span><span class="sxs-lookup"><span data-stu-id="f676a-117">In **Computers > Configuration Profiles** select **Options > System Extensions**.</span></span>
2. <span data-ttu-id="f676a-118">Selezionare **Estensioni di sistema consentite** nell'elenco a discesa **Tipi** di estensione di sistema.</span><span class="sxs-lookup"><span data-stu-id="f676a-118">Select **Allowed System Extensions** from the **System Extension Types** drop-down list.</span></span>
3. <span data-ttu-id="f676a-119">Usa **UBF8T346G9** per l'ID team.</span><span class="sxs-lookup"><span data-stu-id="f676a-119">Use **UBF8T346G9** for Team Id.</span></span>
4. <span data-ttu-id="f676a-120">Aggiungere gli identificatori bundle seguenti **all'elenco Estensioni di sistema** consentite:</span><span class="sxs-lookup"><span data-stu-id="f676a-120">Add the following bundle identifiers to the **Allowed System Extensions** list:</span></span>

    - <span data-ttu-id="f676a-121">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="f676a-121">**com.microsoft.wdav.epsext**</span></span>
    - <span data-ttu-id="f676a-122">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="f676a-122">**com.microsoft.wdav.netext**</span></span>

    ![Screenshot delle estensioni di sistema approvate](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a><span data-ttu-id="f676a-124">Privacy Preferences Policy Control</span><span class="sxs-lookup"><span data-stu-id="f676a-124">Privacy Preferences Policy Control</span></span>

<span data-ttu-id="f676a-125">Aggiungi il payload JAMF seguente per concedere l'accesso completo al disco a Microsoft Defender for Endpoint Endpoint Security Extension.</span><span class="sxs-lookup"><span data-stu-id="f676a-125">Add the following JAMF payload to grant Full Disk Access to the Microsoft Defender for Endpoint Endpoint Security Extension.</span></span> <span data-ttu-id="f676a-126">Questo criterio è un requisito preliminare per l'esecuzione dell'estensione nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f676a-126">This policy is a pre-requisite for running the extension on your device.</span></span>

1. <span data-ttu-id="f676a-127">Seleziona **Opzioni**  >  **Privacy Preferenze Controllo criteri**.</span><span class="sxs-lookup"><span data-stu-id="f676a-127">Select **Options** > **Privacy Preferences Policy Control**.</span></span>
2. <span data-ttu-id="f676a-128">Utilizzare `com.microsoft.wdav.epsext` come **identificatore** e come `Bundle ID` tipo **bundle**.</span><span class="sxs-lookup"><span data-stu-id="f676a-128">Use `com.microsoft.wdav.epsext` as the **Identifier** and `Bundle ID` as **Bundle type**.</span></span>
3. <span data-ttu-id="f676a-129">Imposta requisito di codice su `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="f676a-129">Set Code Requirement to `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
4. <span data-ttu-id="f676a-130">Imposta **App o servizio** su **SystemPolicyAllFiles e** accedi a **Allow**.</span><span class="sxs-lookup"><span data-stu-id="f676a-130">Set **App or service** to **SystemPolicyAllFiles** and access to **Allow**.</span></span>

    ![Privacy Preferences Policy Control](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a><span data-ttu-id="f676a-132">Criteri di estensione di rete</span><span class="sxs-lookup"><span data-stu-id="f676a-132">Network Extension Policy</span></span>

<span data-ttu-id="f676a-133">Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender per Endpoint per Mac esamina il traffico socket e segnala queste informazioni al portale di Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="f676a-133">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="f676a-134">Il criterio seguente consente all'estensione di rete di eseguire questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f676a-134">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="f676a-135">JAMF non dispone del supporto incorporato per i criteri di filtro dei contenuti, che sono un requisito preliminare per l'abilitazione delle estensioni di rete installate da Microsoft Defender per Endpoint per Mac nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f676a-135">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint for Mac installs on the device.</span></span> <span data-ttu-id="f676a-136">Inoltre, JAMF a volte modifica il contenuto dei criteri distribuiti.</span><span class="sxs-lookup"><span data-stu-id="f676a-136">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="f676a-137">Di conseguenza, i passaggi seguenti forniscono una soluzione alternativa che implica la firma del profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f676a-137">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="f676a-138">Salva il contenuto seguente nel dispositivo con `com.microsoft.network-extension.mobileconfig` un editor di testo:</span><span class="sxs-lookup"><span data-stu-id="f676a-138">Save the following content to your device as `com.microsoft.network-extension.mobileconfig` using a text editor:</span></span>

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. <span data-ttu-id="f676a-139">Verificare che il file precedente sia stato copiato correttamente eseguendo `plutil` l'utilità nel terminale:</span><span class="sxs-lookup"><span data-stu-id="f676a-139">Verify that the above file was copied correctly by running the `plutil` utility in the Terminal:</span></span>

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    <span data-ttu-id="f676a-140">Ad esempio, se il file è stato archiviato in Documenti:</span><span class="sxs-lookup"><span data-stu-id="f676a-140">For example, if the file was stored in Documents:</span></span>

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    <span data-ttu-id="f676a-141">Verificare che il comando esere `OK` .</span><span class="sxs-lookup"><span data-stu-id="f676a-141">Verify that the command outputs `OK`.</span></span>
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. <span data-ttu-id="f676a-142">Seguire le istruzioni in [questa pagina](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) per creare un certificato di firma utilizzando l'autorità di certificazione predefinita di JAMF.</span><span class="sxs-lookup"><span data-stu-id="f676a-142">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority.</span></span>

4. <span data-ttu-id="f676a-143">Dopo aver creato e installato il certificato nel dispositivo, esegui il comando seguente dal terminale per firmare il file:</span><span class="sxs-lookup"><span data-stu-id="f676a-143">After the certificate is created and installed to your device, run the following command from the Terminal to sign the file:</span></span>

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    <span data-ttu-id="f676a-144">Ad esempio, se il nome del certificato è **SigningCertificate** e il file firmato verrà archiviato in Documenti:</span><span class="sxs-lookup"><span data-stu-id="f676a-144">For example, if the certificate name is **SigningCertificate** and the signed file is going to be stored in Documents:</span></span>
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. <span data-ttu-id="f676a-145">Dal portale JAMF, accedere a **Profili di configurazione e** fare clic sul pulsante **Carica.**</span><span class="sxs-lookup"><span data-stu-id="f676a-145">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> <span data-ttu-id="f676a-146">Selezionare `com.microsoft.network-extension.signed.mobileconfig` quando richiesto per il file.</span><span class="sxs-lookup"><span data-stu-id="f676a-146">Select `com.microsoft.network-extension.signed.mobileconfig` when prompted for the file.</span></span>

## <a name="intune"></a><span data-ttu-id="f676a-147">Intune</span><span class="sxs-lookup"><span data-stu-id="f676a-147">Intune</span></span>

### <a name="system-extensions-policy"></a><span data-ttu-id="f676a-148">Criteri estensioni di sistema</span><span class="sxs-lookup"><span data-stu-id="f676a-148">System Extensions Policy</span></span>

<span data-ttu-id="f676a-149">Per approvare le estensioni di sistema:</span><span class="sxs-lookup"><span data-stu-id="f676a-149">To approve the system extensions:</span></span>

1. <span data-ttu-id="f676a-150">In Intune apri **Gestisci**  >  **configurazione dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="f676a-150">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="f676a-151">Selezionare **Gestisci**  >  **profili**  >  **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="f676a-151">Select **Manage** > **Profiles** > **Create Profile**.</span></span>
2. <span data-ttu-id="f676a-152">Scegliere un nome per il profilo.</span><span class="sxs-lookup"><span data-stu-id="f676a-152">Choose a name for the profile.</span></span> <span data-ttu-id="f676a-153">Modificare **Platform=macOS** in **Profile type=Extensions**.</span><span class="sxs-lookup"><span data-stu-id="f676a-153">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="f676a-154">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f676a-154">Select **Create**.</span></span>
3. <span data-ttu-id="f676a-155">Nella scheda `Basics` assegna un nome al nuovo profilo.</span><span class="sxs-lookup"><span data-stu-id="f676a-155">In the `Basics` tab, give a name to this new profile.</span></span>
4. <span data-ttu-id="f676a-156">Nella scheda `Configuration settings` aggiungere le voci seguenti nella `Allowed system extensions` sezione:</span><span class="sxs-lookup"><span data-stu-id="f676a-156">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="f676a-157">Identificatore bundle</span><span class="sxs-lookup"><span data-stu-id="f676a-157">Bundle identifier</span></span>         | <span data-ttu-id="f676a-158">Identificatore del team</span><span class="sxs-lookup"><span data-stu-id="f676a-158">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="f676a-159">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="f676a-159">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="f676a-160">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="f676a-160">UBF8T346G9</span></span>
    <span data-ttu-id="f676a-161">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="f676a-161">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="f676a-162">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="f676a-162">UBF8T346G9</span></span>

    ![Screenshot dei profili di configurazione del sistema](images/mac-system-extension-intune2.png)

5. <span data-ttu-id="f676a-164">Nella scheda `Assignments` assegna questo profilo a Tutti gli utenti & Tutti i **dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f676a-164">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="f676a-165">Esaminare e creare questo profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f676a-165">Review and create this configuration profile.</span></span>

### <a name="create-and-deploy-the-custom-configuration-profile"></a><span data-ttu-id="f676a-166">Creare e distribuire il profilo di configurazione personalizzato</span><span class="sxs-lookup"><span data-stu-id="f676a-166">Create and deploy the Custom Configuration Profile</span></span>

<span data-ttu-id="f676a-167">Il profilo di configurazione seguente abilita l'estensione di rete e concede l'accesso completo al disco all'estensione di sistema Endpoint Security.</span><span class="sxs-lookup"><span data-stu-id="f676a-167">The following configuration profile enables the network extension and grants Full Disk Access to the Endpoint Security system extension.</span></span> 

<span data-ttu-id="f676a-168">Salvare il contenuto seguente in un file denominato **sysext.xml**:</span><span class="sxs-lookup"><span data-stu-id="f676a-168">Save the following content to a file named **sysext.xml**:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="f676a-169">Verificare che il file precedente sia stato copiato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f676a-169">Verify that the above file was copied correctly.</span></span> <span data-ttu-id="f676a-170">Dal terminale, eseguire il comando seguente e verificare che esere `OK` :</span><span class="sxs-lookup"><span data-stu-id="f676a-170">From the Terminal, run the following command and verify that it outputs `OK`:</span></span>

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

<span data-ttu-id="f676a-171">Per distribuire questo profilo di configurazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="f676a-171">To deploy this custom configuration profile:</span></span>

1.  <span data-ttu-id="f676a-172">In Intune apri **Gestisci**  >  **configurazione dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="f676a-172">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="f676a-173">Selezionare **Gestisci**  >  **profili**  >  **Crea profilo.**</span><span class="sxs-lookup"><span data-stu-id="f676a-173">Select **Manage** > **Profiles** > **Create profile**.</span></span>
2. <span data-ttu-id="f676a-174">Scegliere un nome per il profilo.</span><span class="sxs-lookup"><span data-stu-id="f676a-174">Choose a name for the profile.</span></span> <span data-ttu-id="f676a-175">Modificare **Platform=macOS** e **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="f676a-175">Change **Platform=macOS** and **Profile type=Custom**.</span></span> <span data-ttu-id="f676a-176">Selezionare **Configura**.</span><span class="sxs-lookup"><span data-stu-id="f676a-176">Select **Configure**.</span></span>
3.  <span data-ttu-id="f676a-177">Apri il profilo di configurazione e carica **sysext.xml**.</span><span class="sxs-lookup"><span data-stu-id="f676a-177">Open the configuration profile and upload **sysext.xml**.</span></span> <span data-ttu-id="f676a-178">Questo file è stato creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="f676a-178">This file was created in the preceding step.</span></span>
4.  <span data-ttu-id="f676a-179">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="f676a-179">Select **OK**.</span></span>

    ![Screenshot dell'estensione di sistema in Intune](images/mac-system-extension-intune.png)

5. <span data-ttu-id="f676a-181">Nella scheda `Assignments` assegna questo profilo a Tutti gli utenti & Tutti i **dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="f676a-181">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>
6. <span data-ttu-id="f676a-182">Esaminare e creare questo profilo di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f676a-182">Review and create this configuration profile.</span></span>
