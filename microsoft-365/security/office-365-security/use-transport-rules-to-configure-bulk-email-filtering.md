---
title: Utilizzare le regole del flusso di posta per filtrare la posta elettronica in blocco
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come utilizzare le regole del flusso di posta (regole di trasporto) per identificare e filtrare la posta in blocco (Gray mail) in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c6a8ad5dd2752f86c0ff9ec96dafe621804b4856
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197304"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="26619-103">Usare le regole del flusso di posta per filtrare la posta in blocco in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="26619-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="26619-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP utilizza criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per l'analisi dei messaggi in ingresso per la posta indesiderata e per l'invio di massa</span><span class="sxs-lookup"><span data-stu-id="26619-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="26619-105">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="26619-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="26619-106">Se si desiderano ulteriori opzioni per filtrare la posta in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nella posta in blocco e contrassegnare i messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="26619-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="26619-107">Per ulteriori informazioni sulla posta in blocco, vedere [Qual è la differenza tra posta elettronica indesiderata e posta elettronica](what-s-the-difference-between-junk-email-and-bulk-email.md) in blocco e [livello di reclamo in blocco (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="26619-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="26619-108">In questo argomento viene illustrato come creare queste regole del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="26619-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="26619-109">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="26619-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="26619-110">Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="26619-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="26619-111">In Exchange Online, vedere la voce "flusso di posta" in [autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="26619-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="26619-112">In EOP autonomo, è necessario il ruolo regole di trasporto, assegnato ai ruoli OrganizationManagement, ComplianceManagement e RecordsManagement per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="26619-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="26619-113">Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="26619-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="26619-114">Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="26619-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="26619-115">Per aprire EAC in EOP autonomo, vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="26619-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="26619-116">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="26619-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="26619-117">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="26619-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="26619-118">Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="26619-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="26619-119">Regole del flusso di posta (regole di trasporto) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26619-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="26619-120">Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26619-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="26619-121">Azioni delle regole del flusso di posta in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26619-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="26619-122">L'elenco delle parole e dei modelli di testo utilizzati per identificare la posta in blocco negli esempi non è esaustivo. è possibile aggiungere e rimuovere le voci in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="26619-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="26619-123">Tuttavia, sono un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="26619-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="26619-p107">La ricerca di due parole o sequenze di testo nell'oggetto o in altri campi dell'intestazione avviene *dopo* che il messaggio è stato decodificato tramite metodo di codifica per il trasferimento dei contenuti che è stato usato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="26619-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="26619-126">Le procedure seguenti contrassegnano un messaggio di massa come posta indesiderata per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="26619-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="26619-127">Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole solo a destinatari specifici, in modo da poter utilizzare il filtro aggressivo su alcuni utenti di alto livello, mentre gli altri utenti (che principalmente ricevono la posta elettronica in blocco) non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="26619-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="26619-128">Utilizzo di EAC per creare regole del flusso di posta che filtrano la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="26619-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="26619-129">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="26619-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="26619-130">Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="26619-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="26619-131">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="26619-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="26619-132">**Nome**: immettere un nome univoco descrittivo per la regola.</span><span class="sxs-lookup"><span data-stu-id="26619-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="26619-133">Fare clic su **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="26619-133">Click **More Options**.</span></span>

   - <span data-ttu-id="26619-134">**Applica questa regola se**: configurare una delle impostazioni seguenti per cercare il contenuto nei messaggi utilizzando espressioni regolari (Regex) o parole o frasi:</span><span class="sxs-lookup"><span data-stu-id="26619-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="26619-135">**L'oggetto o il corpo** \> l' **oggetto o il corpo corrisponde a questi modelli di testo**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e ripetere fino a quando non sono stati immessi tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="26619-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="26619-136">Per modificare una voce, selezionarla e fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="26619-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="26619-137">Per rimuovere una voce, selezionarla e fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="26619-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="26619-138">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="26619-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="26619-139">**L'oggetto o il corpo** \> l' **oggetto o il corpo include una di queste parole**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e ripetere fino a quando non sono stati immessi tutti i valori.</span><span class="sxs-lookup"><span data-stu-id="26619-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="26619-140">Per modificare una voce, selezionarla e fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="26619-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="26619-141">Per rimuovere una voce, selezionarla e fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="26619-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="26619-142">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="26619-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="26619-143">**Eseguire le operazioni seguenti**: selezionare **modifica le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="26619-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="26619-144">Nella finestra di dialogo **specifica SCL** visualizzata, configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="26619-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="26619-145">Per contrassegnare i messaggi come **posta indesiderata**, selezionare **6**.</span><span class="sxs-lookup"><span data-stu-id="26619-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="26619-146">L'azione configurata per il filtraggio della **posta indesiderata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Sposta messaggio nella cartella posta indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="26619-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="26619-147">Per contrassegnare i messaggi come **posta indesiderata con elevata sicurezza** selezionare **9**.</span><span class="sxs-lookup"><span data-stu-id="26619-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="26619-148">L'azione configurata per il filtro di protezione da posta indesiderata con **sicurezza elevata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Move Message to junk email Folder**).</span><span class="sxs-lookup"><span data-stu-id="26619-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="26619-149">Per ulteriori informazioni sui valori SCL, vedere [Spam Confidence Level (SCL) in EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="26619-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="26619-150">Al termine, fare clic su **Salva**</span><span class="sxs-lookup"><span data-stu-id="26619-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="26619-151">Utilizzo di PowerShell per creare regole del flusso di posta che filtrano la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="26619-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="26619-152">Utilizzare la sintassi seguente per creare una o entrambe le regole del flusso di posta (espressioni regolari e parole):</span><span class="sxs-lookup"><span data-stu-id="26619-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="26619-153">In questo esempio viene creata una nuova regola denominata "filtro posta elettronica in blocco" che utilizza lo stesso elenco di espressioni regolari di precedenza nell'argomento per impostare i messaggi come **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="26619-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="26619-154">In questo esempio viene creata una nuova regola denominata "Bulk Email Filtering-Words" che utilizza lo stesso elenco di parole di precedenza nell'argomento per impostare i messaggi come **posta indesiderata con elevata attendibilità**.</span><span class="sxs-lookup"><span data-stu-id="26619-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="26619-155">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="26619-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="26619-156">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="26619-156">How do you know this worked?</span></span>

<span data-ttu-id="26619-157">Per verificare di aver configurato le regole del flusso di posta per filtrare la posta elettronica in blocco, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="26619-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="26619-158">Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \> **Rules** \> selezionare la regola \> fare clic su **Modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) e verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="26619-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="26619-159">In PowerShell, sostituire \<Rule Name\> con il nome della regola ed eseguire il comando riportato di seguito per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="26619-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="26619-160">Da un account esterno, inviare un messaggio di prova a un destinatario coinvolto che contiene una delle frasi o modelli di testo e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="26619-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
