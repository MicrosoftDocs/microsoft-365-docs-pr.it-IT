---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come utilizzare le regole del flusso di posta (note anche come regole di trasporto) per ricevere le copie dei messaggi che gli utenti segnalano a Microsoft.
ms.openlocfilehash: 1612adeefff21fa9f149de6537917dd9b8c50b00
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827386"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="585b0-103">Usare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft</span><span class="sxs-lookup"><span data-stu-id="585b0-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="585b0-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, esistono diversi modi per consentire agli utenti di segnalare i messaggi a Microsoft per l'analisi, come descritto in [messaggi e file di report a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="585b0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="585b0-105">È possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che consente di cercare i messaggi che gli utenti riferiscono a Microsoft ed è possibile configurare i destinatari Ccn in modo che ricevano copie dei messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="585b0-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="585b0-106">È possibile creare la regola del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online, standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="585b0-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="585b0-107">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="585b0-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="585b0-108">Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online o EOP.</span><span class="sxs-lookup"><span data-stu-id="585b0-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="585b0-109">In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="585b0-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="585b0-110">Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="585b0-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="585b0-111">Per aprire EAC, vedere interfaccia di amministrazione di Exchange [in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) o interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="585b0-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="585b0-112">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="585b0-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="585b0-113">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="585b0-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="585b0-114">Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="585b0-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="585b0-115">Regole del flusso di posta (regole di trasporto) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="585b0-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="585b0-116">Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="585b0-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="585b0-117">Azioni delle regole del flusso di posta in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="585b0-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="585b0-118">Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="585b0-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="585b0-119">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="585b0-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="585b0-120">Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="585b0-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="585b0-121">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="585b0-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="585b0-122">**Nome**: immettere un nome univoco descrittivo per la regola.</span><span class="sxs-lookup"><span data-stu-id="585b0-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="585b0-123">Ad esempio, i messaggi Ccn segnalati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="585b0-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="585b0-124">Fare clic su **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="585b0-124">Click **More Options**.</span></span>

   - <span data-ttu-id="585b0-125">**Applica questa regola se**: selezionare **l'indirizzo del destinatario** \> **include una**o più delle seguenti parole: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e ripetere fino a quando non sono stati immessi tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="585b0-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="585b0-126">Per modificare una voce, selezionarla e fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="585b0-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="585b0-127">Per rimuovere una voce, selezionarla e fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="585b0-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="585b0-128">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="585b0-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="585b0-129">**Eseguire le operazioni seguenti**: selezionare **Aggiungi destinatari** \> **alla casella Ccn**.</span><span class="sxs-lookup"><span data-stu-id="585b0-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="585b0-130">Nella finestra di dialogo che viene visualizzata, individuare e selezionare i destinatari che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="585b0-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="585b0-131">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="585b0-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="585b0-132">È possibile effettuare selezioni aggiuntive per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="585b0-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="585b0-133">È consigliabile testare la regola prima di applicarla.</span><span class="sxs-lookup"><span data-stu-id="585b0-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="585b0-134">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="585b0-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="585b0-135">Utilizzo di PowerShell per creare una regola del flusso di posta elettronica per ricevere copie dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="585b0-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="585b0-136">In questo esempio viene creata una nuova regola del flusso di posta denominata Ccn messaggi segnalati a Microsoft che consente di cercare i messaggi di posta elettronica segnalati a Microsoft tramite i metodi descritti in questo argomento e di aggiungere gli utenti laura@contoso.com e julia@contoso.com come destinatari Ccn.</span><span class="sxs-lookup"><span data-stu-id="585b0-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="585b0-137">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="585b0-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="585b0-138">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="585b0-138">How do you know this worked?</span></span>

<span data-ttu-id="585b0-139">Per verificare di aver configurato le regole del flusso di posta elettronica per ricevere le copie dei messaggi segnalati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="585b0-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="585b0-140">Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \> **Rules** \> selezionare la regola \> fare clic su **Modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) e verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="585b0-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="585b0-141">In PowerShell, eseguire il comando riportato di seguito per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="585b0-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="585b0-142">Inviare un messaggio di prova a uno degli indirizzi di posta elettronica per la creazione di report e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="585b0-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
