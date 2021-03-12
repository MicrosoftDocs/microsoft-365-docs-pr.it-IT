---
title: Creare un criterio del tipo di informazioni riservate tramite crittografia dei messaggi di Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Informazioni su come creare criteri di tipo di informazioni riservate per l'organizzazione tramite crittografia dei messaggi di Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22aec87b149c58b2537f6921fb7c37552ef72f98
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741379"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="832bc-103">Creare un criterio di tipo di informazioni riservate per l'organizzazione tramite crittografia dei messaggi</span><span class="sxs-lookup"><span data-stu-id="832bc-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="832bc-104">È possibile utilizzare le regole del flusso di posta di Exchange o prevenzione della perdita dei dati (DLP) per creare un criterio del tipo di informazioni riservate con crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="832bc-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="832bc-105">Per creare una regola del flusso di posta di Exchange, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="832bc-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="832bc-106">Per creare il criterio utilizzando le regole del flusso di posta nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="832bc-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="832bc-107">Accedere all'interfaccia di amministrazione di Exchange (EAC) e andare a **Flusso di posta**  >  **Regole**.</span><span class="sxs-lookup"><span data-stu-id="832bc-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="832bc-108">Nella pagina Regole creare una regola che applica la crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="832bc-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="832bc-109">È possibile creare una regola in base a condizioni quali la presenza di determinate parole chiave o tipi di informazioni riservate nel messaggio o nell'allegato.</span><span class="sxs-lookup"><span data-stu-id="832bc-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="832bc-110">Per creare il criterio utilizzando le regole del flusso di posta in PowerShell</span><span class="sxs-lookup"><span data-stu-id="832bc-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="832bc-111">Utilizzare un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="832bc-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="832bc-112">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="832bc-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="832bc-113">Utilizzare i Set-IRMConfiguration e New-TransportRule per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="832bc-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="832bc-114">Esempio di regola del flusso di posta creata con PowerShell</span><span class="sxs-lookup"><span data-stu-id="832bc-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="832bc-115">Eseguire i comandi seguenti in PowerShell per creare una regola del flusso di posta di Exchange che crittografi automaticamente i messaggi di posta elettronica inviati all'esterno dell'organizzazione con l'opzione di sola crittografia se i messaggi di posta elettronica o i relativi allegati contengono i tipi di informazioni riservate seguenti:</span><span class="sxs-lookup"><span data-stu-id="832bc-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="832bc-116">Numero di routing ABA</span><span class="sxs-lookup"><span data-stu-id="832bc-116">ABA routing number</span></span>
- <span data-ttu-id="832bc-117">Numero carta di credito</span><span class="sxs-lookup"><span data-stu-id="832bc-117">Credit card Number</span></span>
- <span data-ttu-id="832bc-118">Numero dea (Drug Enforcement Agency)</span><span class="sxs-lookup"><span data-stu-id="832bc-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="832bc-119">Stati Uniti / Regno Unito</span><span class="sxs-lookup"><span data-stu-id="832bc-119">U.S. / U.K.</span></span> <span data-ttu-id="832bc-120">passport number</span><span class="sxs-lookup"><span data-stu-id="832bc-120">passport number</span></span>
- <span data-ttu-id="832bc-121">Numero di conto corrente bancario statunitense</span><span class="sxs-lookup"><span data-stu-id="832bc-121">U.S. bank account number</span></span>
- <span data-ttu-id="832bc-122">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="832bc-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="832bc-123">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="832bc-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="832bc-124">Per ulteriori informazioni, vedere [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) e [New-TransportRule.](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)</span><span class="sxs-lookup"><span data-stu-id="832bc-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="832bc-125">Come i destinatari accedono agli allegati</span><span class="sxs-lookup"><span data-stu-id="832bc-125">How recipients access attachments</span></span>

<span data-ttu-id="832bc-126">Dopo che Microsoft ha crittografato un messaggio, i destinatari hanno accesso illimitato agli allegati quando accedono e aprono la posta elettronica crittografata.</span><span class="sxs-lookup"><span data-stu-id="832bc-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="832bc-127">Per prepararsi a questa modifica</span><span class="sxs-lookup"><span data-stu-id="832bc-127">To prepare for this change</span></span>

<span data-ttu-id="832bc-128">È possibile aggiornare la documentazione e i materiali di formazione applicabili per gli utenti finali per preparare gli utenti dell'organizzazione a questa modifica.</span><span class="sxs-lookup"><span data-stu-id="832bc-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="832bc-129">Condividere queste risorse di Crittografia messaggi di Office 365 con gli utenti in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="832bc-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="832bc-130">Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook per PC</span><span class="sxs-lookup"><span data-stu-id="832bc-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="832bc-131">Microsoft 365 Essentials Video: Crittografia dei messaggi di Office</span><span class="sxs-lookup"><span data-stu-id="832bc-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="832bc-132">Visualizzare queste modifiche nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="832bc-132">View these changes in the audit log</span></span>

<span data-ttu-id="832bc-133">Microsoft 365 controlla questa attività e la rende disponibile per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="832bc-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="832bc-134">L'operazione è "New-TransportRule" e un frammento di una voce di controllo di esempio dalla ricerca del log di controllo nel Centro sicurezza & conformità è riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="832bc-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="832bc-135">Per disabilitare o personalizzare i criteri per i tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="832bc-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="832bc-136">Dopo aver creato la regola del flusso [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) di posta di Exchange, è possibile disabilitare o modificare la regola andando a **Flusso** di posta Regole nell'interfaccia di amministrazione di Exchange (EAC) e disabilitare la regola " Crittografare i messaggi di posta elettronica sensibili in uscita  >   *(regola predefinita)*".</span><span class="sxs-lookup"><span data-stu-id="832bc-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
