---
title: Usare le regole del flusso di posta per filtrare la posta elettronica in blocco
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a utilizzare le regole del flusso di posta (regole di trasporto) per identificare e filtrare la posta in blocco (posta grigia) in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8632a0b583ec0457ea1146f0e197321890414ce3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926679"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="9e38d-103">Usare le regole del flusso di posta per filtrare la posta inviata in blocco in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9e38d-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9e38d-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="9e38d-104">**Applies to**</span></span>
- [<span data-ttu-id="9e38d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9e38d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9e38d-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="9e38d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9e38d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e38d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="9e38d-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, EOP utilizza i criteri di protezione da posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per analizzare i messaggi in ingresso alla ricerca di posta indesiderata e posta in blocco (nota anche come posta grigia).</span><span class="sxs-lookup"><span data-stu-id="9e38d-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="9e38d-109">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9e38d-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="9e38d-110">Se si desidera che più opzioni filtrano la posta in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nella posta in blocco e contrassegnare tali messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="9e38d-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="9e38d-111">Per ulteriori informazioni sulla posta in blocco, vedere Qual è la differenza tra posta indesiderata e posta elettronica in [blocco?](what-s-the-difference-between-junk-email-and-bulk-email.md) e Livello di reclamo in blocco [(BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="9e38d-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="9e38d-112">In questo argomento viene illustrato come creare queste regole del flusso di posta nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (Exchange Online PowerShell per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="9e38d-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9e38d-113">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9e38d-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9e38d-114">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online o Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="9e38d-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="9e38d-115">In particolare, è necessario il ruolo **Regole** di trasporto, assegnato ai gruppi  di ruoli **Gestione** **organizzazione,** Gestione conformità (amministratori globali) e Gestione record per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9e38d-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="9e38d-116">Per ulteriori informazioni, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9e38d-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="9e38d-117">Autorizzazioni in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9e38d-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="9e38d-118">Autorizzazioni in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="9e38d-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="9e38d-119">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9e38d-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="9e38d-120">Per aprire l'interfaccia di amministrazione di Exchange in Exchange Online, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="9e38d-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="9e38d-121">Per aprire l'interfaccia di amministrazione di Exchange in EOP autonomo, vedere Interfaccia di amministrazione [di Exchange in EOP autonomo.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="9e38d-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9e38d-122">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e38d-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9e38d-123">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e38d-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9e38d-124">Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e in EOP autonomo, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="9e38d-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="9e38d-125">Regole del flusso di posta (regole di trasporto) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9e38d-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="9e38d-126">Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9e38d-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="9e38d-127">Azioni delle regole del flusso di posta in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9e38d-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="9e38d-128">L'elenco di parole e modelli di testo utilizzati per identificare la posta in blocco negli esempi non è esaustivo. è possibile aggiungere e rimuovere voci in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9e38d-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="9e38d-129">Tuttavia, sono un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="9e38d-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="9e38d-p107">La ricerca di due parole o sequenze di testo nell'oggetto o in altri campi dell'intestazione avviene *dopo* che il messaggio è stato decodificato tramite metodo di codifica per il trasferimento dei contenuti che è stato usato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9e38d-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="9e38d-132">Le procedure seguenti contrassegnano un messaggio in blocco come posta indesiderata per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9e38d-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="9e38d-133">Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole solo a destinatari specifici, in modo da poter utilizzare un filtro aggressivo su alcuni utenti altamente mirati, mentre il resto degli utenti (che ottengono principalmente la posta elettronica in blocco per cui si sono registrati) non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="9e38d-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="9e38d-134">Utilizzo dell'interfaccia di amministrazione di Exchange per creare regole del flusso di posta che filtrano la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="9e38d-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="9e38d-135">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="9e38d-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="9e38d-136">Fare **clic su** Aggiungi Icona Aggiungi e quindi selezionare Crea una nuova ![ ](../../media/ITPro-EAC-AddIcon.png) **regola.**</span><span class="sxs-lookup"><span data-stu-id="9e38d-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="9e38d-137">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9e38d-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="9e38d-138">**Nome**: immettere un nome descrittivo univoco per la regola.</span><span class="sxs-lookup"><span data-stu-id="9e38d-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="9e38d-139">Fare **clic su Altre opzioni.**</span><span class="sxs-lookup"><span data-stu-id="9e38d-139">Click **More Options**.</span></span>

   - <span data-ttu-id="9e38d-140">**Applicare questa regola se**: Configurare una delle impostazioni seguenti per cercare il contenuto dei messaggi utilizzando espressioni regolari (RegEx) o parole o frasi:</span><span class="sxs-lookup"><span data-stu-id="9e38d-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="9e38d-141">**Oggetto o corpo** \> **l'oggetto** o il corpo  corrisponde a questi modelli di testo: nella finestra  di dialogo Specifica parole o frasi visualizzata immettere uno dei valori seguenti, fare clic su Aggiungi icona Aggiungi e ripetere ![ l'operazione fino a quando non sono stati immessi tutti i ](../../media/ITPro-EAC-AddIcon.png) valori.</span><span class="sxs-lookup"><span data-stu-id="9e38d-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="9e38d-142">Per modificare una voce, selezionarla e fare clic **su Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica.</span><span class="sxs-lookup"><span data-stu-id="9e38d-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="9e38d-143">Per rimuovere una voce, selezionarla e fare clic **su Rimuovi** ![ Icona ](../../media/ITPro-EAC-DeleteIcon.png) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="9e38d-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="9e38d-144">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e38d-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="9e38d-145">**Oggetto o corpo** \> **l'oggetto** o il corpo include  una di queste parole: nella finestra di dialogo  Specifica parole o frasi visualizzata immettere uno dei valori seguenti, fare clic su Aggiungi icona Aggiungi e ripetere ![ l'operazione fino a quando non sono stati immessi tutti i ](../../media/ITPro-EAC-AddIcon.png) valori.</span><span class="sxs-lookup"><span data-stu-id="9e38d-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="9e38d-146">Per modificare una voce, selezionarla e fare clic **su Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica.</span><span class="sxs-lookup"><span data-stu-id="9e38d-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="9e38d-147">Per rimuovere una voce, selezionarla e fare clic **su Rimuovi** ![ Icona ](../../media/ITPro-EAC-DeleteIcon.png) Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="9e38d-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="9e38d-148">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e38d-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="9e38d-149">**Eseguire le operazioni seguenti:** Selezionare **Modifica le proprietà del messaggio** impostare il livello di probabilità di posta indesiderata \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="9e38d-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="9e38d-150">Nella finestra **di dialogo Specifica SCL** visualizzata configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e38d-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="9e38d-151">Per contrassegnare i messaggi **come posta** indesiderata, selezionare **6**.</span><span class="sxs-lookup"><span data-stu-id="9e38d-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="9e38d-152">L'azione configurata per  i verdetti del filtro posta indesiderata nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è Sposta messaggio nella cartella Posta **indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="9e38d-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="9e38d-153">Per contrassegnare i messaggi **come posta indesiderata con confidenza elevata,** selezionare **9**.</span><span class="sxs-lookup"><span data-stu-id="9e38d-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="9e38d-154">L'azione configurata per  i verdetti di filtro della posta indesiderata ad alta probabilità nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è Sposta messaggio nella cartella Posta **indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="9e38d-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="9e38d-155">Per ulteriori informazioni sui valori SCL, vedere [Spam confidence level (SCL) in EOP.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="9e38d-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="9e38d-156">Al termine, fare clic su **Salva**</span><span class="sxs-lookup"><span data-stu-id="9e38d-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="9e38d-157">Utilizzare PowerShell per creare regole del flusso di posta che filtrano la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="9e38d-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="9e38d-158">Utilizzare la sintassi seguente per creare una o entrambe le regole del flusso di posta (espressioni regolari e parole):</span><span class="sxs-lookup"><span data-stu-id="9e38d-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="9e38d-159">In questo esempio viene creata una nuova regola denominata "Bulk email filtering - RegEx" che utilizza lo stesso elenco di espressioni regolari riportato in precedenza nell'argomento per impostare i messaggi come **Posta indesiderata.**</span><span class="sxs-lookup"><span data-stu-id="9e38d-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="9e38d-160">In questo esempio viene creata una nuova regola denominata "Bulk email filtering - Words" che utilizza lo stesso elenco di parole riportato in precedenza nell'argomento per impostare i messaggi come posta indesiderata con **alta probabilità.**</span><span class="sxs-lookup"><span data-stu-id="9e38d-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="9e38d-161">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="9e38d-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9e38d-162">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="9e38d-162">How do you know this worked?</span></span>

<span data-ttu-id="9e38d-163">Per verificare di aver configurato le regole del flusso di posta per filtrare la posta elettronica in blocco, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e38d-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="9e38d-164">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso** di posta Regole selezionare la regola fare clic \>  \> su \> **Modifica** Icona Modifica e verificare ![ le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9e38d-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="9e38d-165">In PowerShell, \<Rule Name\> sostituire con il nome della regola ed eseguire il comando seguente per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9e38d-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="9e38d-166">Da un account esterno, inviare un messaggio di prova a un destinatario interessato contenente una delle frasi o dei modelli di testo e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="9e38d-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>