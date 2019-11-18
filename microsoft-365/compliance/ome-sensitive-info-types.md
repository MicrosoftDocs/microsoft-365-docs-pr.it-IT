---
title: Creare criteri del tipo di informazioni sensibili per l'organizzazione con Office 365 Message Encryption
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
description: 'Riepilogo: criteri di crittografia dei messaggi di Office 365 per i tipi di informazioni riservate.'
ms.openlocfilehash: 8632a0419b443d2810afd3554da572ab2197ae2a
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "38690546"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-office-365-message-encryption"></a><span data-ttu-id="4df70-103">Creare criteri del tipo di informazioni sensibili per l'organizzazione con Office 365 Message Encryption</span><span class="sxs-lookup"><span data-stu-id="4df70-103">Create a sensitive information type policy for your organization using Office 365 Message Encryption</span></span>

<span data-ttu-id="4df70-104">È possibile utilizzare le regole del flusso di posta di Exchange o la prevenzione della perdita di dati (DLP) di Office 365 per creare un criterio tipo di informazioni riservate con la crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4df70-104">You can use either Exchange mail flow rules or Office 365 Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="4df70-105">Per creare una regola del flusso di posta di Exchange, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4df70-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="4df70-106">Per creare il criterio mediante le regole del flusso di posta nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="4df70-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="4df70-107">Accedere all'interfaccia di amministrazione di Exchange (EAC) e passare a \*\*\*\* > **regole**del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="4df70-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="4df70-108">Nella pagina regole creare una regola che applica la crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4df70-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="4df70-109">È possibile creare una regola in base a condizioni quali la presenza di determinate parole chiave o tipi di informazioni riservate nel messaggio o nell'allegato.</span><span class="sxs-lookup"><span data-stu-id="4df70-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="4df70-110">Per creare il criterio mediante le regole del flusso di posta in PowerShell</span><span class="sxs-lookup"><span data-stu-id="4df70-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="4df70-111">Utilizzare un account aziendale o dell'Istituto di istruzione che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4df70-111">Use a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="4df70-112">Per istruzioni, vedere [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="4df70-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="4df70-113">Utilizzare i cmdlet Set-IRMConfiguration e New-TransportRule per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="4df70-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="4df70-114">Esempio di regola del flusso di posta creato con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4df70-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="4df70-115">Eseguire i comandi seguenti in PowerShell per creare una regola del flusso di posta di Exchange che crittografa automaticamente i messaggi inviati all'esterno dell'organizzazione con il criterio di *sola crittografia* se i messaggi di posta elettronica o i relativi allegati contengono i seguenti tipi di informazioni riservate:</span><span class="sxs-lookup"><span data-stu-id="4df70-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the *Encrypt-Only* policy if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="4df70-116">Numero di Routing ABA</span><span class="sxs-lookup"><span data-stu-id="4df70-116">ABA routing number</span></span>
- <span data-ttu-id="4df70-117">Numero di carta di credito</span><span class="sxs-lookup"><span data-stu-id="4df70-117">Credit card Number</span></span>
- <span data-ttu-id="4df70-118">Numero dell'agenzia di applicazione della droga (DEA)</span><span class="sxs-lookup"><span data-stu-id="4df70-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="4df70-119">STATI UNITI/REGNO UNITO</span><span class="sxs-lookup"><span data-stu-id="4df70-119">U.S. / U.K.</span></span> <span data-ttu-id="4df70-120">passport number</span><span class="sxs-lookup"><span data-stu-id="4df70-120">passport number</span></span>
- <span data-ttu-id="4df70-121">Numero di conto corrente bancario degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="4df70-121">U.S. bank account number</span></span>
- <span data-ttu-id="4df70-122">Stati Uniti - Codice identificativo del contribuente individuale (ITIN)</span><span class="sxs-lookup"><span data-stu-id="4df70-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="4df70-123">Stati Uniti - Numero di previdenza sociale (SSN)</span><span class="sxs-lookup"><span data-stu-id="4df70-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="4df70-124">Per ulteriori informazioni, vedere [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) e [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="4df70-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-irmconfiguration?view=exchange-ps) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule?view=exchange-ps).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="4df70-125">Modalità di accesso degli allegati ai destinatari</span><span class="sxs-lookup"><span data-stu-id="4df70-125">How recipients access attachments</span></span>

<span data-ttu-id="4df70-126">Dopo che Office 365 ha crittografato un messaggio, i destinatari hanno accesso illimitato agli allegati quando accedono e aprono la posta elettronica crittografata.</span><span class="sxs-lookup"><span data-stu-id="4df70-126">After Office 365 encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="4df70-127">Per preparare questa modifica</span><span class="sxs-lookup"><span data-stu-id="4df70-127">To prepare for this change</span></span>

<span data-ttu-id="4df70-128">Potrebbe essere necessario aggiornare la documentazione per gli utenti finali applicabile e i materiali di formazione per preparare le persone all'interno dell'organizzazione per questa modifica.</span><span class="sxs-lookup"><span data-stu-id="4df70-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="4df70-129">Condividere queste risorse di crittografia dei messaggi di Office 365 con gli utenti in base alle esigenze:</span><span class="sxs-lookup"><span data-stu-id="4df70-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="4df70-130">Inviare, visualizzare e rispondere a messaggi crittografati in Outlook per PC</span><span class="sxs-lookup"><span data-stu-id="4df70-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="4df70-131">Video di Office 365 Essentials: crittografia dei messaggi di Office</span><span class="sxs-lookup"><span data-stu-id="4df70-131">Office 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="4df70-132">Visualizzare queste modifiche nel log di controllo</span><span class="sxs-lookup"><span data-stu-id="4df70-132">View these changes in the Audit log</span></span>

<span data-ttu-id="4df70-133">Office 365 verifica questa attività e la rende disponibile per gli amministratori di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4df70-133">Office 365 audits this activity and makes it available to Office 365 administrators.</span></span> <span data-ttu-id="4df70-134">L'operazione è' New-TransportRule ' e un frammento di una voce di controllo di esempio dalla ricerca del registro di controllo nel centro sicurezza & conformità è riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4df70-134">The operation is ‘New-TransportRule’ and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications”…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="4df70-135">Per disabilitare o personalizzare i criteri dei tipi di informazioni riservate</span><span class="sxs-lookup"><span data-stu-id="4df70-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="4df70-136">Dopo aver creato la regola del flusso di posta di Exchange, è possibile [disabilitare o modificare la regola](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) accedendo alle**regole** del **flusso** > di posta nell'interfaccia di amministrazione di Exchange (EAC) e disabilitando la regola "*crittografare i messaggi di posta elettronica sensibili in uscita (* escludendo la regola)".</span><span class="sxs-lookup"><span data-stu-id="4df70-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule “*Encrypt outbound sensitive emails (out of box rule)*”.</span></span>
