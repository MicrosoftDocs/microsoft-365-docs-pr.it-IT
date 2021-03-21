---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a usare le regole del flusso di posta (note anche come regole di trasporto) per ricevere copie dei messaggi che gli utenti segnalano a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 34857c368fc910eeb43f6a78c490b9ad7568db1c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918631"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="9f8b3-103">Usare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9f8b3-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9f8b3-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="9f8b3-104">**Applies to**</span></span>
- [<span data-ttu-id="9f8b3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9f8b3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9f8b3-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="9f8b3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9f8b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9f8b3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="9f8b3-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, esistono diversi modi per segnalare i messaggi a Microsoft per l'analisi, come descritto in Segnalare messaggi e file a [Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9f8b3-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="9f8b3-109">È possibile creare una regola del flusso di posta (nota anche come regola di trasporto) che cerca i messaggi che gli utenti segnalano a Microsoft ed è possibile configurare i destinatari Ccn per ricevere copie di questi messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="9f8b3-110">È possibile creare la regola del flusso di posta nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9f8b3-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9f8b3-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9f8b3-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9f8b3-112">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="9f8b3-113">In particolare, è necessario il ruolo **Regole** di trasporto, assegnato ai gruppi  di ruoli **Gestione** **organizzazione,** Gestione conformità (amministratori globali) e Gestione record per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="9f8b3-114">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9f8b3-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="9f8b3-115">Autorizzazioni in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9f8b3-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="9f8b3-116">Autorizzazioni in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="9f8b3-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="9f8b3-117">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9f8b3-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="9f8b3-118">Per aprire l'interfaccia di amministrazione di Exchange in Exchange Online, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="9f8b3-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="9f8b3-119">Per aprire l'interfaccia di amministrazione di Exchange in EOP autonomo, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="9f8b3-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9f8b3-120">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9f8b3-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9f8b3-121">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9f8b3-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9f8b3-122">Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e in EOP autonomo, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9f8b3-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="9f8b3-123">Regole del flusso di posta (regole di trasporto) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9f8b3-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="9f8b3-124">Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9f8b3-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="9f8b3-125">Azioni delle regole del flusso di posta in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9f8b3-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="9f8b3-126">Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per ricevere copie dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="9f8b3-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="9f8b3-127">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="9f8b3-128">Fare **clic su** Aggiungi Icona Aggiungi e quindi selezionare Crea una nuova ![ ](../../media/ITPro-EAC-AddIcon.png) **regola.**</span><span class="sxs-lookup"><span data-stu-id="9f8b3-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="9f8b3-129">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9f8b3-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="9f8b3-130">**Nome**: immettere un nome descrittivo univoco per la regola.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="9f8b3-131">Ad esempio, Ccn Messaggi segnalati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="9f8b3-132">Fare **clic su Altre opzioni.**</span><span class="sxs-lookup"><span data-stu-id="9f8b3-132">Click **More Options**.</span></span>

   - <span data-ttu-id="9f8b3-133">Applica questa regola  **se**: Selezionare L'indirizzo del destinatario include una delle seguenti parole: nella finestra di dialogo Specifica parole o frasi visualizzata immettere uno dei valori seguenti, fare clic su Aggiungi icona Aggiungi e ripetere \>    ![ l'operazione fino a quando non sono stati immessi tutti i ](../../media/ITPro-EAC-AddIcon.png) valori.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="9f8b3-134">Per modificare una voce, selezionarla e fare clic **su Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="9f8b3-135">Per rimuovere una voce, selezionarla e fare clic **su Rimuovi** ![ Icona ](../../media/ITPro-EAC-DeleteIcon.png) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="9f8b3-136">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="9f8b3-137">**Eseguire le operazioni seguenti:** Selezionare **Aggiungi** \> **destinatari alla casella Ccn**.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="9f8b3-138">Nella finestra di dialogo visualizzata individuare e selezionare i destinatari che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="9f8b3-139">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="9f8b3-140">È possibile effettuare ulteriori selezioni per controllare la regola, testarla, attivare la regola in un periodo di tempo specifico e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="9f8b3-141">È consigliabile testare la regola prima di applicarla.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="9f8b3-142">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="9f8b3-143">Utilizzare PowerShell per creare una regola del flusso di posta per ricevere copie dei messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="9f8b3-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="9f8b3-144">In questo esempio viene creata una nuova regola del flusso di posta denominata Ccn Messaggi segnalati a Microsoft che cerca i messaggi di posta elettronica segnalati a Microsoft utilizzando i metodi descritti in questo articolo e aggiunge gli utenti laura@contoso.com e julia@contoso.com come destinatari Ccn.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="9f8b3-145">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="9f8b3-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9f8b3-146">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="9f8b3-146">How do you know this worked?</span></span>

<span data-ttu-id="9f8b3-147">Per verificare di aver configurato regole del flusso di posta per ricevere copie dei messaggi segnalati, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f8b3-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="9f8b3-148">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta Regole selezionare la regola fare clic \>  \> su \> **Modifica** Icona Modifica e verificare ![ le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="9f8b3-149">In PowerShell, eseguire il comando seguente per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9f8b3-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="9f8b3-150">Inviare messaggi di prova a uno degli indirizzi di posta elettronica di segnalazione e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="9f8b3-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>