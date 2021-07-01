---
title: Configurare IRM per l'uso di un server AD RMS locale
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Informazioni su come configurare Information Rights Management (IRM) in Exchange Online per l'utilizzo di un server Active Directory Rights Management Service (AD RMS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c42d793639a9efaf94e3222a172ea192d1e03d3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227236"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="3ca7f-103">Configurare IRM per l'uso di un server AD RMS locale</span><span class="sxs-lookup"><span data-stu-id="3ca7f-103">Configure IRM to use an on-premises AD RMS server</span></span>

<span data-ttu-id="3ca7f-104">Per l'utilizzo con le distribuzioni locali, Information Rights Management (IRM) in Exchange Online utilizza Active Directory Rights Management Services (AD RMS), una tecnologia di protezione delle informazioni in Windows Server 2008 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="3ca7f-105">La protezione IRM viene applicata alla posta elettronica applicando un modello dei criteri dei diritti AD RMS a un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="3ca7f-106">I diritti sono allegati al messaggio stesso, in modo che la protezione si verifichi online e offline e all'interno e all'esterno del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>

<span data-ttu-id="3ca7f-107">In questo argomento viene illustrato come configurare IRM per utilizzare un server AD RMS.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="3ca7f-108">Per informazioni sull'uso delle nuove funzionalità per Office 365 Message Encryption con Azure Active Directory e Azure Rights Management, vedere le domande Office 365 Message Encryption [domande frequenti su Office 365 Message Encryption.](./ome-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="3ca7f-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](./ome-faq.yml).</span></span>

<span data-ttu-id="3ca7f-109">Per ulteriori informazioni su IRM in Exchange Online, vedere [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ca7f-110">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3ca7f-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ca7f-111">Tempo stimato per il completamento di questa attività: 30 minuti</span><span class="sxs-lookup"><span data-stu-id="3ca7f-111">Estimated time to complete this task: 30 minutes</span></span>

- <span data-ttu-id="3ca7f-p103">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Information Rights Management" nell'argomento [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) topic.</span></span>

- <span data-ttu-id="3ca7f-p104">Il server AD RMS deve eseguire Windows Server 2008 o versioni successive. Per i dettagli sulla distribuzione di AD RMS, vedere l'articolo relativo all'[installazione di un cluster AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p104">The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).</span></span>

- <span data-ttu-id="3ca7f-116">Per informazioni su come installare e configurare Windows PowerShell ed eseguire la connessione al servizio, vedere [Connessione a Exchange Online tramite Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-116">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="3ca7f-117">Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo argomento, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di Exchange [in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="3ca7f-p105">Problemi? È possibile richiedere supporto nei forum di Exchange. I forum sono disponibili sui seguenti siti: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) o [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span>

## <a name="how-do-you-do-this"></a><span data-ttu-id="3ca7f-121">Come eseguire l'operazione?</span><span class="sxs-lookup"><span data-stu-id="3ca7f-121">How do you do this?</span></span>
<span data-ttu-id="3ca7f-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="3ca7f-122"><a name="sectionSection1"> </a></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="3ca7f-123">Passaggio 1: Utilizzare la console AD RMS per esportare un dominio di pubblicazione trusted (TPD, trusted publishing domain) da un server AD RMS</span><span class="sxs-lookup"><span data-stu-id="3ca7f-123">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="3ca7f-p106">Il primo passaggio è l'esportazione in un dominio di pubblicazione trusted da un server SD RMS locale ad un file XML. Il dominio di pubblicazione trusted contiene le impostazioni necessarie per utilizzare le funzionalità RMS:</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span>

- <span data-ttu-id="3ca7f-126">il certificato concessore di licenze server (SLC) utilizzato per la firma e la crittografia dei certificati e delle licenze</span><span class="sxs-lookup"><span data-stu-id="3ca7f-126">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>

- <span data-ttu-id="3ca7f-127">gli URL utilizzati per la gestione delle licenze e la pubblicazione</span><span class="sxs-lookup"><span data-stu-id="3ca7f-127">The URLs used for licensing and publishing</span></span>

- <span data-ttu-id="3ca7f-128">i modelli di criteri per i diritti di AD RMS creati con il certificato SLC specifico per quel dominio di pubblicazione trusted</span><span class="sxs-lookup"><span data-stu-id="3ca7f-128">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>

<span data-ttu-id="3ca7f-129">Quando si importa il dominio di pubblicazione trusted, viene archiviato e protetto in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-129">When you import the TPD, it's stored and protected in Exchange Online.</span></span>

1. <span data-ttu-id="3ca7f-130">Aprire la console Active Directory Rights Management Services, quindi espandere il cluster AD RMS.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-130">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>

2. <span data-ttu-id="3ca7f-131">Nell'albero della console, espandere **Criteri di attendibilità**, quindi fare clic su **Domini di pubblicazione trusted**.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-131">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>

3. <span data-ttu-id="3ca7f-132">Selezionare il certificato per il dominio che si desidera esportare nel riquadro dei risultati.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-132">In the results pane, select the certificate for the domain you want to export.</span></span>

4. <span data-ttu-id="3ca7f-133">Nel riquadro **Azioni**, fare clic su **Esporta dominio di pubblicazione trusted**.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-133">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>

5. <span data-ttu-id="3ca7f-p107">Nella casella **File del dominio di pubblicazione**, fare clic su **Salva con nome** per salvare il file in un percorso specifico sul computer locale. Immettere un nome file e assicurarsi di specificare l'estensione del nome file  `.xml` e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p107">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer. Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>

6. <span data-ttu-id="3ca7f-p108">Nelle caselle **Password** e **Conferma password**, digitare una password complessa che sarà utilizzata per crittografare il file del dominio di pubblicazione trusted. Sarà necessario specificare questa password durante l'importazione del dominio di pubblicazione trusted nell'organizzazione di posta elettronica basata su cloud.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span>

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="3ca7f-138">Passaggio 2: utilizzare Exchange Management Shell per importare il disco di configurazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ca7f-138">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="3ca7f-p109">Dopo aver esportato il dominio di pubblicazione trusted in un file XML, è necessario importarlo in Exchange Online. Quando viene importato un dominio di pubblicazione trusted, vengono importati anche i modelli dell'organizzazione AD RMS. Quando viene importato il primo dominio di pubblicazione trusted, diventa quello predefinito per l'organizzazione basata su cloud. Se si importa un altro dominio di pubblicazione trusted, è possibile utilizzare l'opzione **Predefinito** per fare in modo che sia quello predefinito disponibile per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p109">After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span>

<span data-ttu-id="3ca7f-143">Per importare il dominio di pubblicazione trusted, eseguire il seguente comando in Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3ca7f-143">To import the TPD, run the following command in Windows PowerShell:</span></span>

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="3ca7f-p110">È possibile ottenere i valori per i parametri  _ExtranetLicensingUrl_ e  _IntranetLicensingUrl_ nella console Active Directory Rights Management Services. Nell'albero della console, selezionare il cluster AD RMS. Gli URL per la gestione delle licenze vengono visualizzati nel riquadro dei risultati. Questi URL vengono utilizzati dai client di posta elettronica quando è necessario eseguire la decrittografia del contenuto e quando Exchange Online deve scegliere quale dominio di pubblicazione trusted utilizzare.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p110">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console. Select the AD RMS cluster in the console tree. The licensing URLs are displayed in the results pane. These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span>

<span data-ttu-id="3ca7f-p111">Quando si esegue questo comando, viene richiesta una password. Immettere la password specificata durante l'esportazione del dominio di pubblicazione trusted dal server AD RMS.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p111">When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>

<span data-ttu-id="3ca7f-p112">Ad esempio, il comando seguente importa il dominio di pubblicazione trusted, denominato dominio di pubblicazione trusted esportato tramite il file XML esportato dal server AD RMS e salvato nel desktop dell'account amministratore. Il parametro Name viene utilizzato per specificare un nome nel dominio di pubblicazione trusted.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="3ca7f-152">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-152">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="3ca7f-153">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="3ca7f-153">How do you know this step worked?</span></span>

<span data-ttu-id="3ca7f-p113">Per verificare di aver importato il dominio di pubblicazione trusted, eseguire il cmdlet **Get-RMSTrustedPublishingDomain** per recuperare i domini di pubblicazione trusted dell'organizzazione Exchange Online. Per i dettagli, vedere gli esempi in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p113">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization. For details, see the examples in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).</span></span>

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="3ca7f-156">Passaggio 3: Utilizzare Exchange Management Shell per distribuire un modello di criteri per i diritti AD RMS</span><span class="sxs-lookup"><span data-stu-id="3ca7f-156">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="3ca7f-157">Dopo avere importato il dominio di pubblicazione trusted, è necessario assicurarsi che sia distribuito un modello dei criteri dei diritti AD RMS.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-157">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="3ca7f-158">Un modello distribuito è visibile Outlook sul web utenti (in precedenza noti come Outlook Web App), che possono quindi applicare i modelli a un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-158">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>

<span data-ttu-id="3ca7f-159">Per tornare ad un elenco di tutti i modelli contenuti nel dominio di pubblicazione trusted predefinito, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3ca7f-159">To return a list of all templates contained in the default TPD, run the following command:</span></span>

```powershell
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="3ca7f-160">Se il valore del parametro  _Type_ è  `Archived`, il modello non è visibile agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-160">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="3ca7f-161">Solo i modelli distribuiti nel dominio di distribuzione predefinito sono disponibili in Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-161">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>

<span data-ttu-id="3ca7f-162">Per distribuire un modello, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3ca7f-162">To distribute a template, run the following command:</span></span>

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="3ca7f-163">Ad esempio, il comando seguente importa il modello Materiale aziendale riservato.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-163">For example, the following command imports the Company Confidential template.</span></span>

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="3ca7f-164">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) e [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-164">For detailed syntax and parameter information, see [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) and [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).</span></span>

<span data-ttu-id="3ca7f-165">**Il modello Non inoltrare**</span><span class="sxs-lookup"><span data-stu-id="3ca7f-165">**The Do Not Forward template**</span></span>

<span data-ttu-id="3ca7f-p116">Quando si importa il dominio di pubblicazione trusted predefinito dall'organizzazione locale in Exchange Online, viene importato un modello RMS denominato **Non inoltrare**. Per impostazione predefinita, questo modello viene distribuito quando si importa il dominio di pubblicazione trusted predefinito. Non è possibile utilizzare il cmdlet **Set-RMSTemplate** per modificare il modello **Non inoltrare**.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p116">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span>

<span data-ttu-id="3ca7f-p117">Quando viene applicato il modello **Non inoltrare** ad un messaggio, solo i destinatari specificati nel messaggio possono leggerlo. Inoltre, i destinatari non possono eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span>

- <span data-ttu-id="3ca7f-171">Inoltrare il messaggio ad un altra persona.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-171">Forward the message to another person.</span></span>

- <span data-ttu-id="3ca7f-172">Copiare il contenuto dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-172">Copy content from the message.</span></span>

- <span data-ttu-id="3ca7f-173">Stampare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-173">Print the message.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ca7f-174">Il modello **Non inoltrare** non può impedire di copiare le informazioni in un messaggio con programmi di acquisizione schermo di terze parti, fotocamere o utenti che trascrivono manualmente le informazioni</span><span class="sxs-lookup"><span data-stu-id="3ca7f-174">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span>

<span data-ttu-id="3ca7f-p118">È possibile creare ulteriori modelli dei criteri dei diritti AD RMS sul server AD RMS dell'organizzazione locale per soddisfare i requisiti di protezione IRM. Se si creano altri modelli dei criteri dei diritti AD RMS, è necessario esportare nuovamente il dominio di pubblicazione trusted dal server AD RMS locale e aggiornare il dominio di pubblicazione trusted nell'organizzazione di posta elettronica basata su cloud.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="3ca7f-177">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="3ca7f-177">How do you know this step worked?</span></span>

<span data-ttu-id="3ca7f-p119">Per verificare di aver distribuito un modello dei criteri dei diritti AD RMS, eseguire il cmdlet **Get-RMSTemplate** per verificare le proprietà del modello. Per i dettagli, vedere gli esempi in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p119">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties. For details, see the examples in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).</span></span>

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="3ca7f-180">Passaggio 4: Utilizzare Exchange Management Shell per abilitare IRM</span><span class="sxs-lookup"><span data-stu-id="3ca7f-180">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="3ca7f-181">Dopo aver importato il dominio di pubblicazione trusted e distribuito un modello RMS, è necessario abilitare IRM per l'organizzazione di posta elettronica basata su cloud eseguendo il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-181">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="3ca7f-182">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-182">For detailed syntax and parameter information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="3ca7f-183">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="3ca7f-183">How do you know this step worked?</span></span>

<span data-ttu-id="3ca7f-184">Per verificare di aver abilitato IRM, eseguire il cmdlet [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) per verificare la configurazione IRM nell'organizzazione Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3ca7f-184">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) cmdlet to check IRM configuration in the Exchange Online organization.</span></span>

## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="3ca7f-185">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="3ca7f-185">How do you know this task worked?</span></span>
<span data-ttu-id="3ca7f-186"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="3ca7f-186"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="3ca7f-187">Per verificare di aver importato il dominio di pubblicazione trusted e abilitato IRM, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="3ca7f-187">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>

- <span data-ttu-id="3ca7f-p120">Utilizzare il cmdlet **Test-IRMConfiguration** per verificare la funzionalità IRM. Per informazioni dettagliate, vedere "Esempio 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-p120">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality. For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

- <span data-ttu-id="3ca7f-190">Comporre un nuovo messaggio in Outlook sul web e proteggerlo tramite  IRM selezionando l'opzione Imposta autorizzazioni dal menu esteso ( ![ Icona Altre opzioni ](../media/ITPro-EAC-MoreOptionsIcon.gif) ).</span><span class="sxs-lookup"><span data-stu-id="3ca7f-190">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu (![More Options Icon](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>
