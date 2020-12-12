---
title: Sicurezza documenti in Microsoft Defender per Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni sui documenti attendibili in Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.openlocfilehash: 0acb5d4ee0c80deebc4d0b040b046d63037037a7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659874"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="ea7d0-103">Sicurezza documenti in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ea7d0-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ea7d0-104">Documenti attendibili è una funzionalità di sicurezza di Microsoft 365 E5 o Microsoft 365 E5 che utilizza [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare documenti e file aperti in [visualizzazione protetta](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ea7d0-105">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="ea7d0-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ea7d0-106">I documenti attendibili sono disponibili solo per gli utenti con licenze di sicurezza *microsoft 365 E5* o *Microsoft 365 E5* .</span><span class="sxs-lookup"><span data-stu-id="ea7d0-106">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="ea7d0-107">Queste licenze non sono incluse in Microsoft Defender per i piani di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-107">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="ea7d0-108">I documenti attendibili sono supportati in Microsoft 365 Apps for Enterprise (in precedenza noto come Office 365 ProPlus) versione 2004 o successiva.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-108">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="ea7d0-109">Aprire il Centro sicurezza e conformità in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-109">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="ea7d0-110">Per passare direttamente alla pagina degli **allegati sicuri di ATP** , Apri <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="ea7d0-110">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="ea7d0-111">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ea7d0-112">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-112">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ea7d0-113">Per configurare le impostazioni di documenti attendibili, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="ea7d0-113">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ea7d0-114">Per l'accesso in sola lettura alle impostazioni di documenti attendibili, è necessario essere membri dei gruppi di ruoli **lettore globale** o lettore di **sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="ea7d0-114">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ea7d0-115">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-115">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="ea7d0-116">**Note**:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-116">**Notes**:</span></span>

  - <span data-ttu-id="ea7d0-117">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-117">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ea7d0-118">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-118">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="ea7d0-119">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-119">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="ea7d0-120">In che modo Microsoft gestisce i dati?</span><span class="sxs-lookup"><span data-stu-id="ea7d0-120">How does Microsoft handle your data?</span></span>

<span data-ttu-id="ea7d0-121">Per garantire la protezione, i documenti attendibili inviano file a [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-121">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="ea7d0-122">Informazioni dettagliate su come Microsoft Defender for Endpoint gestisce i dati possono essere reperiti qui: [Microsoft Defender per l'archiviazione dei dati endpoint e la privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-122">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="ea7d0-123">I file inviati dai documenti attendibili non vengono conservati in Defender oltre il tempo necessario per l'analisi (in genere, meno di 24 ore).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-123">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="ea7d0-124">Utilizzare il Centro sicurezza & conformità per configurare i documenti attendibili</span><span class="sxs-lookup"><span data-stu-id="ea7d0-124">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="ea7d0-125">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \>  \> **allegati sicuri ATP** e quindi fare clic su **Impostazioni globali**.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="ea7d0-126">Nelle **Impostazioni globali** volare che viene visualizzato, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-126">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ea7d0-127">**Attivare documenti attendibili per i client di Office**: spostare l'interruttore verso destra per attivare la caratteristica: ![ Toggle on ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="ea7d0-127">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="ea7d0-128">**Consenti agli utenti di fare clic su una visualizzazione protetta anche se i documenti sicuri identificano il file come dannoso**: si consiglia di lasciare questa opzione disattivata (lasciare l'interruttore a sinistra: disattivazione ![ ](../../media/scc-toggle-off.png) ).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-128">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="ea7d0-129">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-129">When you're finished, click **Save**.</span></span>

   ![Impostazioni dei documenti attendibili dopo la selezione delle impostazioni globali nella pagina allegati sicuri.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="ea7d0-131">Utilizzo di PowerShell di Exchange Online per configurare documenti sicuri</span><span class="sxs-lookup"><span data-stu-id="ea7d0-131">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="ea7d0-132">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-132">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="ea7d0-133">Il parametro _EnableSafeDocs_ consente di abilitare o disabilitare i documenti attendibili per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-133">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="ea7d0-134">Il parametro _AllowSafeDocsOpen_ consente o impedisce agli utenti di lasciare la visualizzazione protetta, ovvero l'apertura del documento, se il documento è stato identificato come dannoso.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-134">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="ea7d0-135">In questo esempio vengono abilitati i documenti attendibili per l'intera organizzazione e viene impedito agli utenti di aprire documenti identificati come dannosi dalla visualizzazione protetta.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-135">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="ea7d0-136">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="ea7d0-136">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="ea7d0-137">Come verificare se l'operazione ha avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="ea7d0-137">How do I know this worked?</span></span>

<span data-ttu-id="ea7d0-138">Per verificare di aver abilitato e configurato documenti attendibili, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-138">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="ea7d0-139">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \>  \> **allegati sicuri ATP**, fare clic su **Impostazioni globali** e verificare l' **attivazione dei documenti attendibili per i client di Office** e **consentire agli utenti di fare clic su tramite visualizzazione protetta anche se i documenti sicuri identificano il file come impostazioni dannose** .</span><span class="sxs-lookup"><span data-stu-id="ea7d0-139">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="ea7d0-140">Eseguire il seguente comando in PowerShell di Exchange Online e verificare i valori delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-140">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="ea7d0-141">I file seguenti sono disponibili per testare la protezione dei documenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-141">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="ea7d0-142">Questi documenti sono simili al file EICAR.TXT per testare le soluzioni anti-malware e antivirus.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-142">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="ea7d0-143">I file non sono nocivi, ma attivano la protezione dei documenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-143">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="ea7d0-144">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="ea7d0-144">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="ea7d0-145">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="ea7d0-145">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="ea7d0-146">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="ea7d0-146">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
