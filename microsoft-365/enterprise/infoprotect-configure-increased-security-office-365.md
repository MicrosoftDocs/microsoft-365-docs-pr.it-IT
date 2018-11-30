---
title: 'Passaggio 3: configurare un livello di sicurezza maggiore per Office 365'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Capire e configurare un livello di sicurezza maggiore per Office 365, tra cui Office 365 ATP.
ms.openlocfilehash: 0344778b8d8f9940dc6267a39eac2f4cfb261f9a
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868805"
---
# <a name="step-3-configure-increased-security-for-office-365"></a><span data-ttu-id="6faf7-103">Passaggio 3: configurare un livello di sicurezza maggiore per Office 365</span><span class="sxs-lookup"><span data-stu-id="6faf7-103">Step 3: Configure increased security for Office 365</span></span>

<span data-ttu-id="6faf7-104">*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6faf7-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="6faf7-105">Per assicurarsi che l'abbonamento a Office 365 e i relativi dati siano protetti da minacce, vedere [Configurare il tenant di Office 365 per una maggiore sicurezza](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) e configurare la protezione aggiuntiva seguente:</span><span class="sxs-lookup"><span data-stu-id="6faf7-105">To ensure that your Office 365 subscription and its data start off and remain secure from malicious threats, see [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) and configure the following additional security:</span></span>

- <span data-ttu-id="6faf7-106">Criteri di gestione delle minacce nel Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="6faf7-106">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="6faf7-107">Impostazioni tenant aggiuntive di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6faf7-107">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="6faf7-108">Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint</span><span class="sxs-lookup"><span data-stu-id="6faf7-108">Tenant-wide sharing policies in the SharePoint admin center</span></span>
- <span data-ttu-id="6faf7-109">Impostazioni di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6faf7-109">Settings in Azure Active Directory</span></span>

<span data-ttu-id="6faf7-110">Una volta configurato, è possibile ottenere informazioni sullo stato di sicurezza in:</span><span class="sxs-lookup"><span data-stu-id="6faf7-110">Once configured, you can obtain information about your security status from:</span></span>

- <span data-ttu-id="6faf7-111">Dashboard e report nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="6faf7-111">Dashboards and reports in the Security & Compliance Center</span></span>
- [<span data-ttu-id="6faf7-112">Secure Score di Office 365</span><span class="sxs-lookup"><span data-stu-id="6faf7-112">Office 365 Secure Score</span></span>](https://securescore.office.com/)
 
  <span data-ttu-id="6faf7-113">Per accedere a questa pagina, è necessario effettuare l'accesso come amministratore del tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="6faf7-113">To access this page, you must be signed in as an Office 365 tenant admin.</span></span>

<span data-ttu-id="6faf7-114">È anche possibile usare Cloud App Security o Office 365 Cloud App Security per monitorare gli eventi e le azioni di sicurezza. Per ulteriori informazioni, vedere [Panoramica di Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span><span class="sxs-lookup"><span data-stu-id="6faf7-114">You can also use Cloud App Security or Office 365 Cloud App Security to monitor for security events and act. For more information, see [Overview of Office 365 Cloud App Security](https://support.office.com/article/Overview-of-Office-365-Cloud-App-Security-81f0ee9a-9645-45ab-ba56-de9cbccab475).</span></span>

<span data-ttu-id="6faf7-115">Una funzionalità di sicurezza aggiuntiva è Office 365 Advanced Threat Protection (ATP), che consente all'organizzazione di collaborare in modo più sicuro attraverso:</span><span class="sxs-lookup"><span data-stu-id="6faf7-115">An additional security feature is Office 365 Advanced Threat Protection (ATP), which helps your organization collaborate more securely by:</span></span>

- <span data-ttu-id="6faf7-116">La protezione dei collegamenti e degli allegati nella posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6faf7-116">Protecting links and attachments in email.</span></span> 
- <span data-ttu-id="6faf7-117">La fornitura di funzionalità spoof intelligence e anti-phishing per la posta elettronica in Exchange Online e nei file in SharePoint Online, OneDrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6faf7-117">Providing spoof intelligence and anti-phishing capabilities for email in Exchange Online and files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> 

>[!Note]
><span data-ttu-id="6faf7-p101">Office 365 ATP è incluso in Microsoft 365 Enterprise E5. Se si dispone di Microsoft 365 Enterprise E3, è possibile acquistare licenze singole licenze di ATP.</span><span class="sxs-lookup"><span data-stu-id="6faf7-p101">Office 365 ATP is included with Microsoft 365 Enterprise E5. If you have Microsoft 365 Enterprise E3, you can purchase individual licenses for ATP.</span></span>
>

<span data-ttu-id="6faf7-120">Per attivare Office 365 ATP, vedere [Attivarlo](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="6faf7-120">To enable Office 365 ATP, see [Turn it on](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="6faf7-121">Per ulteriori informazioni, vedere [Office 365 ATP per SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span><span class="sxs-lookup"><span data-stu-id="6faf7-121">For more information, see [Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607).</span></span>


|||
|:-------|:-----|
|![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6faf7-123">Guida al laboratorio di testing: configurazione della sicurezza aumentata di Office 365</span><span class="sxs-lookup"><span data-stu-id="6faf7-123">Test Lab Guide: Configure increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="6faf7-124">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step4) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6faf7-124">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6faf7-125">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6faf7-125">Next step</span></span>


|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="6faf7-126">Configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="6faf7-126">Configure privileged access management</span></span>](infoprotect-configure-privileged-access-management.md)|


