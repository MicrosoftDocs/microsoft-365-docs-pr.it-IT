---
title: Sicurezza documenti di Office 365 ATP
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
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827470"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="85d80-103">Documenti attendibili in Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="85d80-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="85d80-104">Documenti attendibili è una funzionalità di sicurezza di Microsoft 365 E5 o Microsoft 365 E5 che utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare documenti e file aperti in [visualizzazione protetta](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="85d80-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="85d80-105">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="85d80-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="85d80-106">I documenti attendibili sono ora generalmente disponibili per gli utenti con Office versione 2004 (12730. x) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="85d80-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="85d80-107">Questa funzionalità è disattivata per impostazione predefinita e dovrà essere abilitata dall'amministratore della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="85d80-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="85d80-108">Questa funzionalità è disponibile solo per gli utenti che dispongono della licenza di sicurezza *microsoft 365 E5* o *Microsoft 365 E5* (non inclusa nei piani di Office 365 ATP).</span><span class="sxs-lookup"><span data-stu-id="85d80-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="85d80-109">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="85d80-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="85d80-110">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="85d80-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="85d80-111">Prima di poter eseguire le procedure descritte in questo argomento, è necessario disporre delle autorizzazioni assegnate.</span><span class="sxs-lookup"><span data-stu-id="85d80-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="85d80-112">Per abilitare e configurare documenti attendibili, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="85d80-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="85d80-113">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="85d80-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="85d80-114">In che modo Microsoft gestisce i dati?</span><span class="sxs-lookup"><span data-stu-id="85d80-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="85d80-115">Per proteggersi, i documenti sicuri inviano i file al cloud di [protezione avanzata delle minacce di Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="85d80-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="85d80-116">Informazioni dettagliate su come Microsoft Defender Advanced Threat Protection gestisce i dati possono essere trovati [qui](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="85d80-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="85d80-117">Oltre alle linee guida sopra riportate, i file inviati dai documenti attendibili non vengono conservati in Defender oltre il tempo necessario per l'analisi, che in genere è inferiore a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="85d80-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="85d80-118">Utilizzare il Centro sicurezza & conformità per configurare i documenti attendibili</span><span class="sxs-lookup"><span data-stu-id="85d80-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="85d80-119">Aprire il Centro sicurezza & Compliance all'indirizzo <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="85d80-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="85d80-120">Accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.</span><span class="sxs-lookup"><span data-stu-id="85d80-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="85d80-121">Nella sezione **informazioni su come mantenere la sicurezza per la protezione di un file da aprire visualizzazione protetta esterna in applicazioni di Office** , configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="85d80-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="85d80-122">**Attivazione di documenti attendibili per i client di Office**</span><span class="sxs-lookup"><span data-stu-id="85d80-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="85d80-123">**Consenti agli utenti di fare clic su una visualizzazione protetta anche se i documenti sicuri identificano il file come dannoso**: si consiglia di non abilitare questa opzione.</span><span class="sxs-lookup"><span data-stu-id="85d80-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="85d80-124">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="85d80-124">When you're finished, click **Save**.</span></span>

![Pagina allegati sicuri ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="85d80-126">Utilizzare Exchange Online PowerShell o standalone EOP PowerShell per configurare documenti sicuri</span><span class="sxs-lookup"><span data-stu-id="85d80-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="85d80-127">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="85d80-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="85d80-128">Il parametro _EnableSafeDocs_ consente di abilitare o disabilitare i documenti attendibili per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="85d80-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="85d80-129">Il parametro _AllowSafeDocsOpen_ consente o impedisce agli utenti di lasciare la visualizzazione protetta, ovvero l'apertura del documento, se il documento è stato identificato come dannoso.</span><span class="sxs-lookup"><span data-stu-id="85d80-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="85d80-130">In questo esempio vengono abilitati i documenti attendibili per l'intera organizzazione e viene impedito agli utenti di aprire documenti identificati come dannosi dalla visualizzazione protetta.</span><span class="sxs-lookup"><span data-stu-id="85d80-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="85d80-131">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="85d80-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="85d80-132">Come verificare se l'operazione ha avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="85d80-132">How do I know this worked?</span></span>

<span data-ttu-id="85d80-133">Per verificare di aver abilitato e configurato documenti attendibili, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85d80-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="85d80-134">Nel centro sicurezza & conformità andare al criterio di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri di ATP**e verificare che le selezioni nelle **persone di supporto siano sicure quando si considera attendibile un file per aprire la visualizzazione protetta esterna nella sezione applicazioni di Office** .</span><span class="sxs-lookup"><span data-stu-id="85d80-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="85d80-135">Eseguire il seguente comando in PowerShell di Exchange Online e verificare i valori delle proprietà:</span><span class="sxs-lookup"><span data-stu-id="85d80-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
