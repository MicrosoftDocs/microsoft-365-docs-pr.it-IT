---
title: 'Passaggio 3: Configurare un livello di sicurezza maggiore per Microsoft 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare un livello di sicurezza maggiore per Microsoft 365.
ms.openlocfilehash: 81c39eb6a51e7596a72721c72084f1f255f7f451
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073636"
---
# <a name="step-3-configure-increased-security-for-microsoft-365"></a><span data-ttu-id="da4e0-103">Passaggio 3: Configurare un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da4e0-103">Step 3: Configure increased security for Microsoft 365</span></span>

<span data-ttu-id="da4e0-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="da4e0-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="da4e0-105">Per assicurarsi che l'abbonamento a Microsoft 365 e i relativi dati siano protetti da minacce, configurare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="da4e0-105">To ensure that your Microsoft 365 subscription and its data start off and remain secure from malicious threats, configure the following:</span></span>

- [<span data-ttu-id="da4e0-106">Ottimizzare i criteri di gestione delle minacce</span><span class="sxs-lookup"><span data-stu-id="da4e0-106">Tune threat management policies</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#tune-threat-management-policies-in-the-office-365-security--compliance-center)
- [<span data-ttu-id="da4e0-107">Impostazioni tenant aggiuntive di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="da4e0-107">Additional Exchange Online tenant-wide settings</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-additional-exchange-online-tenant-wide-settings)
- [<span data-ttu-id="da4e0-108">Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="da4e0-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-tenant-wide-sharing-policies-in-sharepoint-admin-center)
- [<span data-ttu-id="da4e0-109">Impostazioni di Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="da4e0-109">Settings in Azure Active Directory (Azure AD)</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#configure-settings-in-azure-active-directory)

<span data-ttu-id="da4e0-110">Una volta configurati questi elementi, è possibile ottenere informazioni sullo stato di sicurezza in:</span><span class="sxs-lookup"><span data-stu-id="da4e0-110">Once configured, you can obtain information about your security status from:</span></span>

- [<span data-ttu-id="da4e0-111">Dashboard e report nel Centro sicurezza Microsoft</span><span class="sxs-lookup"><span data-stu-id="da4e0-111">Dashboards and reports in the Microsoft security Center</span></span>](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security#view-dashboards-and-reports-in-the-security--compliance-center)
- [<span data-ttu-id="da4e0-112">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="da4e0-112">Microsoft Secure Score</span></span>](https://docs.microsoft.com/office365/securitycompliance/microsoft-secure-score)

<span data-ttu-id="da4e0-113">Una funzionalità di sicurezza aggiuntiva è [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), che consente all'organizzazione di collaborare in modo più sicuro attraverso:</span><span class="sxs-lookup"><span data-stu-id="da4e0-113">An additional security feature is [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="da4e0-114">La protezione dei [collegamenti](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) e degli [allegati](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) nella posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="da4e0-114">Protecting [links](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links) and [attachments](https://docs.microsoft.com/office365/securitycompliance/atp-safe-attachments) in email.</span></span> 
- <span data-ttu-id="da4e0-115">La fornitura di funzionalità spoof intelligence e anti-phishing per la posta elettronica in Exchange Online e nei [file in SharePoint Online, OneDrive for Business e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="da4e0-115">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and [files in SharePoint Online, OneDrive for Business, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/atp-for-spo-odb-and-teams).</span></span> 

<span data-ttu-id="da4e0-116">Office 365 ATP è disponibile solo con Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="da4e0-116">Office 365 ATP is only available with Microsoft 365 Enterprise E5.</span></span>

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="da4e0-118">Guida al lab di test: Configurare un livello di sicurezza maggiore per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da4e0-118">Test Lab Guide: Configure increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="da4e0-119">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step3) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="da4e0-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="da4e0-120">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="da4e0-120">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="da4e0-121">Configurare Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="da4e0-121">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|


