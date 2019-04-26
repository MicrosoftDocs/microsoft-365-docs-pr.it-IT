---
title: 'Passaggio 3: Configurare un livello di sicurezza maggiore per Microsoft 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare un livello di sicurezza maggiore per Microsoft 365.
ms.openlocfilehash: a1976a9305c40d721bd56a4b21b8a52552c1a9dc
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285080"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="58377-103">Passaggio 3: Configurare un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58377-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="58377-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="58377-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="58377-105">Per assicurarsi che l'abbonamento a Microsoft 365 e i relativi dati siano protetti da minacce, configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="58377-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see Configure your Office 365 tenant for increased security and configure the following additional security:</span></span>

- [<span data-ttu-id="58377-106">Ottimizzare i criteri di gestione delle minacce</span><span class="sxs-lookup"><span data-stu-id="58377-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="58377-107">Impostazioni tenant aggiuntive di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="58377-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="58377-108">Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="58377-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="58377-109">Impostazioni di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="58377-109">Settings in Azure Active Directory</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="58377-110">Una volta configurati questi elementi, è possibile ottenere informazioni sullo stato di sicurezza in:</span><span class="sxs-lookup"><span data-stu-id="58377-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="58377-111">Dashboard e report nel Centro sicurezza Microsoft</span><span class="sxs-lookup"><span data-stu-id="58377-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="58377-112">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="58377-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="58377-113">Una funzionalità di sicurezza aggiuntiva è [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), che consente all'organizzazione di collaborare in modo più sicuro attraverso:</span><span class="sxs-lookup"><span data-stu-id="58377-113">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="58377-114">La protezione dei [collegamenti](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) e degli [allegati](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) nella posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="58377-114">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="58377-115">La fornitura di funzionalità spoof intelligence e anti-phishing per la posta elettronica in Exchange Online e nei [file in SharePoint Online, OneDrive for Business e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="58377-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

<span data-ttu-id="58377-116">Office 365 ATP è disponibile solo con Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="58377-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="58377-118">Guida al lab di test: Configurare un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58377-118">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="58377-119">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step4) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="58377-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="58377-120">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="58377-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="58377-121">Configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="58377-121">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


