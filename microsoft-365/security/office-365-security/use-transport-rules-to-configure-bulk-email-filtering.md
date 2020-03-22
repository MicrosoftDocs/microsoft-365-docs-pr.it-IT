---
title: Utilizzare le regole del flusso di posta per filtrare la posta elettronica in blocco in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come utilizzare le regole del flusso di posta in Exchange Online Protection per il filtro della posta elettronica in blocco.
ms.openlocfilehash: 2ac81d798af957f23f95b92f633b93bdda677991
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895048"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a><span data-ttu-id="700cc-103">Utilizzare le regole del flusso di posta per filtrare la posta elettronica in blocco in Office 365</span><span class="sxs-lookup"><span data-stu-id="700cc-103">Use mail flow rules to filter bulk email in Office 365</span></span>

<span data-ttu-id="700cc-104">Se si è un cliente di Office 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, EOP utilizza criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) messaggi in ingresso per la posta indesiderata e di massa (nota anche come posta grigia).</span><span class="sxs-lookup"><span data-stu-id="700cc-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="700cc-105">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="700cc-105">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="700cc-106">Se si desiderano ulteriori opzioni per filtrare la posta in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nella posta in blocco e contrassegnare i messaggi come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="700cc-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="700cc-107">Per ulteriori informazioni sulla posta in blocco, vedere [Qual è la differenza tra posta elettronica indesiderata e posta elettronica](what-s-the-difference-between-junk-email-and-bulk-email.md) in blocco e [livello di reclamo in blocco (BCL) in Office 365](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="700cc-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="700cc-108">In questo argomento viene illustrato come creare queste regole del flusso di posta elettronica nell'interfaccia di amministrazione di Exchange (EAC) e in PowerShell (Exchange Online PowerShell per i clienti di Office 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.</span><span class="sxs-lookup"><span data-stu-id="700cc-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="700cc-109">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="700cc-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="700cc-110">Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="700cc-110">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="700cc-111">In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="700cc-111">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="700cc-112">Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="700cc-112">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="700cc-113">Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="700cc-113">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="700cc-114">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="700cc-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="700cc-115">Per connettersi a PowerShell di Exchange Online Protection autonomo, vedere [connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="700cc-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="700cc-116">Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online e EOP autonomo, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="700cc-116">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="700cc-117">Regole del flusso di posta (regole di trasporto) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="700cc-117">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="700cc-118">Condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="700cc-118">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="700cc-119">Azioni delle regole del flusso di posta in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="700cc-119">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="700cc-120">L'elenco delle parole e dei modelli di testo utilizzati per identificare la posta in blocco negli esempi non è esaustivo. è possibile aggiungere e rimuovere le voci in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="700cc-120">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="700cc-121">Tuttavia, sono un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="700cc-121">However, they are a good starting point.</span></span>

- <span data-ttu-id="700cc-p106">La ricerca di due parole o sequenze di testo nell'oggetto o in altri campi dell'intestazione avviene *dopo* che il messaggio è stato decodificato tramite metodo di codifica per il trasferimento dei contenuti che è stato usato per trasmettere il messaggio binario tra i server SMTP in testo ASCII. Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="700cc-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="700cc-124">Le procedure seguenti contrassegnano un messaggio di massa come posta indesiderata per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="700cc-124">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="700cc-125">Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole solo a destinatari specifici, in modo da poter utilizzare il filtro aggressivo su alcuni utenti di alto livello, mentre gli altri utenti (che principalmente ricevono la posta elettronica in blocco) non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="700cc-125">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="700cc-126">Utilizzo di EAC per creare regole del flusso di posta che filtrano la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="700cc-126">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="700cc-127">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="700cc-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="700cc-128">Fare **Add** ![clic su Aggiungi](../../media/ITPro-EAC-AddIcon.png) icona e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="700cc-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="700cc-129">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="700cc-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="700cc-130">**Nome**: immettere un nome univoco descrittivo per la regola.</span><span class="sxs-lookup"><span data-stu-id="700cc-130">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="700cc-131">Fare clic su **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="700cc-131">Click **More Options**.</span></span>

   - <span data-ttu-id="700cc-132">**Applica questa regola se**: configurare una delle impostazioni seguenti per cercare il contenuto nei messaggi utilizzando espressioni regolari (Regex) o parole o frasi:</span><span class="sxs-lookup"><span data-stu-id="700cc-132">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="700cc-133">**L'oggetto o il corpo del corpo** \> o dell'oggetto **corrisponde a questi modelli di testo**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti,](../../media/ITPro-EAC-AddIcon.png)fare clic su **Aggiungi** ![icona e ripetere il numero di volte necessario.</span><span class="sxs-lookup"><span data-stu-id="700cc-133">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      <span data-ttu-id="700cc-134">Per modificare una voce, selezionarla e fare **Edit** ![clic su modifica](../../media/ITPro-EAC-EditIcon.png)icona modifica.</span><span class="sxs-lookup"><span data-stu-id="700cc-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="700cc-135">Per rimuovere una voce, selezionarla e fare **Remove** ![clic su Rimuovi](../../media/ITPro-EAC-DeleteIcon.png)icona Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="700cc-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="700cc-136">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="700cc-136">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="700cc-137">**L'oggetto o il corpo dell'oggetto** \> o **del corpo include una di queste parole**: nella finestra di dialogo **specifica parole o frasi** visualizzata, immettere uno dei valori seguenti, fare clic](../../media/ITPro-EAC-AddIcon.png)su **Aggiungi** ![icona e ripetere il numero di volte necessario.</span><span class="sxs-lookup"><span data-stu-id="700cc-137">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat as many times as necessary.</span></span>

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

      <span data-ttu-id="700cc-138">Per modificare una voce, selezionarla e fare **Edit** ![clic su modifica](../../media/ITPro-EAC-EditIcon.png)icona modifica.</span><span class="sxs-lookup"><span data-stu-id="700cc-138">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="700cc-139">Per rimuovere una voce, selezionarla e fare **Remove** ![clic su Rimuovi](../../media/ITPro-EAC-DeleteIcon.png)icona Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="700cc-139">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="700cc-140">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="700cc-140">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="700cc-141">**Eseguire le operazioni seguenti**: selezionare **modifica le proprietà** \> del messaggio **impostare il livello di probabilità di posta indesiderata (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="700cc-141">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="700cc-142">Nella finestra di dialogo **specifica SCL** visualizzata, configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="700cc-142">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="700cc-143">Per contrassegnare i messaggi come **posta indesiderata**, selezionare **6**.</span><span class="sxs-lookup"><span data-stu-id="700cc-143">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="700cc-144">L'azione configurata per il filtraggio della **posta indesiderata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Sposta messaggio nella cartella posta indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="700cc-144">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="700cc-145">Per contrassegnare i messaggi come **posta indesiderata con elevata sicurezza** selezionare **9**.</span><span class="sxs-lookup"><span data-stu-id="700cc-145">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="700cc-146">L'azione configurata per il filtro di protezione da posta indesiderata con **sicurezza elevata** nei criteri di protezione da posta indesiderata viene applicata ai messaggi (il valore predefinito è **Move Message to junk email Folder**).</span><span class="sxs-lookup"><span data-stu-id="700cc-146">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="700cc-147">Per ulteriori informazioni sui valori SCL, vedere [livello di probabilità di posta indesiderata (SCL) in Office 365](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="700cc-147">For more information about SCL values, see [Spam confidence level (SCL) in Office 365](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="700cc-148">Al termine, fare clic su **Salva**</span><span class="sxs-lookup"><span data-stu-id="700cc-148">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="700cc-149">Utilizzo di PowerShell per creare regole del flusso di posta che filtrano la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="700cc-149">Use PowerShell to create a mail flow rules that filter bulk email</span></span>

<span data-ttu-id="700cc-150">Utilizzare la sintassi seguente per creare una o entrambe le regole del flusso di posta (espressioni regolari e parole):</span><span class="sxs-lookup"><span data-stu-id="700cc-150">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="700cc-151">In questo esempio viene creata una nuova regola denominata "filtro posta elettronica in blocco" che utilizza lo stesso elenco di espressioni regolari di precedenza nell'argomento per impostare i messaggi come **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="700cc-151">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="700cc-152">In questo esempio viene creata una nuova regola denominata "Bulk Email Filtering-Words" che utilizza lo stesso elenco di parole di precedenza nell'argomento per impostare i messaggi come **posta indesiderata con elevata attendibilità**.</span><span class="sxs-lookup"><span data-stu-id="700cc-152">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="700cc-153">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="700cc-153">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="700cc-154">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="700cc-154">How do you know this worked?</span></span>

<span data-ttu-id="700cc-155">Per verificare di aver configurato le regole del flusso di posta per filtrare la posta elettronica in blocco, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="700cc-155">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="700cc-156">Nell'interfaccia di amministrazione di Exchange, andare a **regole** \> del **flusso** \> di **Edit** ![posta selezionare la](../../media/ITPro-EAC-EditIcon.png)regola \> fare clic su Modifica icona modifica e verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="700cc-156">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="700cc-157">In PowerShell, sostituire \<il nome\> della regola con il nome della regola ed eseguire il comando seguente per verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="700cc-157">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="700cc-158">Da un account esterno, inviare un messaggio di prova a un destinatario coinvolto che contiene una delle frasi o modelli di testo e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="700cc-158">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
