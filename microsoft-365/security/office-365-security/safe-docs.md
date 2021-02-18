---
title: Sicurezza documenti in Microsoft Defender per Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni su Documenti sicuri in Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288586"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="9a74f-103">Sicurezza documenti in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9a74f-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9a74f-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="9a74f-104">**Applies to**</span></span>
- [<span data-ttu-id="9a74f-105">Microsoft Defender per Office 365 Piano 2</span><span class="sxs-lookup"><span data-stu-id="9a74f-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9a74f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a74f-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="9a74f-107">Documenti sicuri è una funzionalità di Microsoft 365 E5 o Microsoft 365 E5 Security che usa [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare documenti e file aperti in Visualizzazione [protetta.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="9a74f-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9a74f-108">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="9a74f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9a74f-109">Documenti sicuri è disponibile solo per gli utenti con licenze Di sicurezza di *Microsoft 365 E5* o *Microsoft 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="9a74f-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="9a74f-110">Queste licenze non sono incluse nei piani di Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a74f-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="9a74f-111">Documenti sicuri è supportato in Microsoft 365 Apps for enterprise (in precedenza noto come Office 365 ProPlus) versione 2004 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9a74f-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="9a74f-112">Aprire il Centro sicurezza e conformità in <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="9a74f-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="9a74f-113">Per passare direttamente alla pagina **Allegati sicuri di ATP,** aprire <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="9a74f-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="9a74f-114">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9a74f-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9a74f-115">È necessario disporre delle autorizzazioni nel Centro sicurezza e conformità per poter eseguire le procedure contenute in questo articolo:</span><span class="sxs-lookup"><span data-stu-id="9a74f-115">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="9a74f-116">Per configurare le impostazioni di Documenti sicuri, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9a74f-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="9a74f-117">Per l'accesso in sola lettura alle impostazioni di  Documenti sicuri, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore **di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9a74f-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="9a74f-118">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9a74f-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="9a74f-119">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a74f-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9a74f-120">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9a74f-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="9a74f-121">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9a74f-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="9a74f-122">In che modo Microsoft gestisce i dati?</span><span class="sxs-lookup"><span data-stu-id="9a74f-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="9a74f-123">Per proteggere l'utente, i documenti sicuri inviano i file al cloud [di Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="9a74f-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="9a74f-124">I dettagli su come Microsoft Defender per Endpoint gestisce i dati sono disponibili qui: [Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="9a74f-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="9a74f-125">I file inviati da Documenti sicuri non vengono conservati in Defender oltre il tempo necessario per l'analisi (in genere, meno di 24 ore).</span><span class="sxs-lookup"><span data-stu-id="9a74f-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="9a74f-126">Usare il Centro sicurezza & conformità per configurare Documenti sicuri</span><span class="sxs-lookup"><span data-stu-id="9a74f-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="9a74f-127">Nel Centro sicurezza & conformità passare **a** Allegati sicuri dei criteri di gestione delle minacce ATP e quindi fare clic \>  \> su **Impostazioni globali.**</span><span class="sxs-lookup"><span data-stu-id="9a74f-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="9a74f-128">Nel **riquadro a comparsa** Impostazioni globali visualizzato configura le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a74f-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9a74f-129">**Attivare Documenti sicuri per i client di Office:** spostare l'interruttore a destra per attivare la funzionalità: ![ attiva. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="9a74f-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="9a74f-130">**Consentire agli** utenti di fare clic su Visualizzazione protetta anche se Documenti sicuri identifica il file come dannoso: è consigliabile lasciare disattivata questa opzione (lasciare l'interruttore a sinistra: ![ ](../../media/scc-toggle-off.png) Disattiva).</span><span class="sxs-lookup"><span data-stu-id="9a74f-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="9a74f-131">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9a74f-131">When you're finished, click **Save**.</span></span>

   ![Impostazioni di Documenti sicuri dopo aver selezionato Impostazioni globali nella pagina Allegati sicuri.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="9a74f-133">Utilizzare PowerShell di Exchange Online per configurare Documenti sicuri</span><span class="sxs-lookup"><span data-stu-id="9a74f-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="9a74f-134">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9a74f-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="9a74f-135">Il _parametro EnableSafeDocs_ consente di abilitare o disabilitare Documenti sicuri per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a74f-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="9a74f-136">Il _parametro AllowSafeDocsOpen_ consente o impedisce agli utenti di uscire da Visualizzazione protetta, ovvero l'apertura del documento, se il documento è stato identificato come dannoso.</span><span class="sxs-lookup"><span data-stu-id="9a74f-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="9a74f-137">In questo esempio vengono abilitati i documenti sicuri per l'intera organizzazione e viene impedito agli utenti di aprire documenti identificati come dannosi da Visualizzazione protetta.</span><span class="sxs-lookup"><span data-stu-id="9a74f-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="9a74f-138">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="9a74f-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="9a74f-139">Come verificare se l'operazione ha avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="9a74f-139">How do I know this worked?</span></span>

<span data-ttu-id="9a74f-140">Per verificare di aver abilitato e configurato Documenti sicuri, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a74f-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="9a74f-141">Nel Centro sicurezza & conformità passare  a Allegati sicuri \>  \> **ATP**   dei criteri di  gestione delle minacce, fare clic su Impostazioni globali e verificare l'opzione Attiva documenti sicuri per i client di Office e Consenti agli utenti di fare clic su Visualizzazione protetta anche se Documenti sicuri identifica il file come impostazioni dannose.</span><span class="sxs-lookup"><span data-stu-id="9a74f-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="9a74f-142">Eseguire il comando seguente in PowerShell di Exchange Online e verificare i valori delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="9a74f-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="9a74f-143">I file seguenti sono disponibili per testare la protezione dei documenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="9a74f-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="9a74f-144">Questi documenti sono simili al file EICAR.TXT per testare le soluzioni antimalware e antivirus.</span><span class="sxs-lookup"><span data-stu-id="9a74f-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="9a74f-145">I file non sono dannosi, ma attiveranno la protezione dei documenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="9a74f-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="9a74f-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="9a74f-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="9a74f-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="9a74f-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="9a74f-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="9a74f-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
