---
title: Utilizzare le regole del flusso di posta per il livello SCL nei messaggi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Informazioni su come creare regole del flusso di posta (regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata (SCL) dei messaggi in Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 791e6747e1ffa92d54e7d4f4a6c257c3aad4c0d9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195856"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="fc955-103">Utilizzare le regole del flusso di posta per impostare il livello di probabilità di posta indesiderata (SCL) nei messaggi in EOP</span><span class="sxs-lookup"><span data-stu-id="fc955-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fc955-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online, EOP utilizza criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro della posta indesiderata o criteri di filtro del contenuto) per l'analisi della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="fc955-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="fc955-105">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fc955-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="fc955-106">Se si desidera contrassegnare messaggi specifici come posta indesiderata prima che vengano persino analizzati tramite il filtro posta indesiderata oppure contrassegnare i messaggi in modo che ignorino il filtro posta indesiderata, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per identificare i messaggi e impostare il livello di probabilità di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="fc955-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="fc955-107">Per ulteriori informazioni sul livello SCL, vedere [Spam Confidence Level (SCL) in EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="fc955-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fc955-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="fc955-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fc955-109">Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fc955-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="fc955-110">In particolare, è necessario che venga assegnato il ruolo **regole di trasporto** , assegnato ai ruoli Gestione **organizzazione**, **Gestione conformità**e **record** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fc955-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="fc955-111">Per altre informazioni, vedere [Gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="fc955-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="fc955-112">Per aprire EAC in Exchange Online, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="fc955-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="fc955-113">Per ulteriori informazioni sulle regole del flusso di posta in Exchange Online, vedere [Mail Flow Rules (Transport Rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="fc955-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="fc955-114">Utilizzo dell'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta che imposta il livello SCL di un messaggio</span><span class="sxs-lookup"><span data-stu-id="fc955-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="fc955-115">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="fc955-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="fc955-116">Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="fc955-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="fc955-117">Nella pagina **Nuova regola** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="fc955-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="fc955-118">**Nome**: immettere un nome univoco descrittivo per la regola.</span><span class="sxs-lookup"><span data-stu-id="fc955-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="fc955-119">Fare clic su **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="fc955-119">Click **More Options**.</span></span>

   - <span data-ttu-id="fc955-120">**Applica questa regola se**: selezionare una o più condizioni per identificare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="fc955-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="fc955-121">Per ulteriori informazioni, vedere [condizioni ed eccezioni della regola del flusso di posta (predicati) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="fc955-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="fc955-122">**Eseguire le operazioni seguenti**: selezionare **modifica le proprietà del messaggio** \> **impostare il livello di probabilità di posta indesiderata (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="fc955-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="fc955-123">Nella finestra di dialogo **specifica SCL** che viene visualizzata, configurare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="fc955-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="fc955-124">**Ignorare il filtro posta indesiderata**: i messaggi ignoreranno il filtro posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="fc955-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="fc955-125">Fare molta attenzione a consentire ai messaggi di ignorare il filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="fc955-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="fc955-126">Gli utenti malintenzionati possono utilizzare questa vulnerabilità per inviare tentativi di phishing e altri messaggi dannosi all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fc955-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="fc955-127">Le regole del flusso di posta richiedono più di un solo indirizzo di posta elettronica o dominio del mittente.</span><span class="sxs-lookup"><span data-stu-id="fc955-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="fc955-128">Per ulteriori informazioni, vedere [creare elenchi di mittenti attendibili in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="fc955-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="fc955-129">**da 0 a 4**: il messaggio viene inviato tramite filtro di posta indesiderata per ulteriori elaborazioni.</span><span class="sxs-lookup"><span data-stu-id="fc955-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="fc955-130">**5 o 6**: il messaggio è contrassegnato come **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="fc955-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="fc955-131">L'azione configurata per il filtraggio della **posta indesiderata** nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è **Sposta messaggio nella cartella posta indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="fc955-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="fc955-132">**da 7 a 9**: il messaggio è contrassegnato come **posta indesiderata con elevata sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="fc955-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="fc955-133">L'azione configurata per il filtro di **protezione da posta indesiderata con sicurezza elevata** nei criteri di protezione da posta indesiderata viene applicata al messaggio (il valore predefinito è **Move Message to junk email Folder**).</span><span class="sxs-lookup"><span data-stu-id="fc955-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="fc955-134">Specificare le proprietà aggiuntive desiderate per la regola.</span><span class="sxs-lookup"><span data-stu-id="fc955-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="fc955-135">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fc955-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="fc955-136">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="fc955-136">How do you know this worked?</span></span>

<span data-ttu-id="fc955-137">Per verificare la corretta esecuzione di questa procedura, inviare un messaggio di posta elettronica a un utente all'interno dell'organizzazione e verificare che l'azione eseguita sul messaggio sia come previsto.</span><span class="sxs-lookup"><span data-stu-id="fc955-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="fc955-138">Se ad esempio si **imposta il livello di probabilità di posta indesiderata (SCL)** per **ignorare il filtro posta indesiderata**, il messaggio dovrà essere inviato alla cartella posta in arrivo del destinatario specificato.</span><span class="sxs-lookup"><span data-stu-id="fc955-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="fc955-139">Tuttavia, se si **imposta il livello di probabilità di posta indesiderata (SCL)** su **9**e l'azione di protezione da posta indesiderata **elevata** per i criteri di protezione da posta indesiderata applicabili è quella di spostare il messaggio nella cartella posta indesiderata, il messaggio deve essere inviato alla cartella posta indesiderata del destinatario specificato.</span><span class="sxs-lookup"><span data-stu-id="fc955-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
