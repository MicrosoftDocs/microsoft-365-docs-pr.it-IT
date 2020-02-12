---
title: Mittente non verificato
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Outlook.com e Outlook sul Web verificano che il mittente sia quello che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.
ms.openlocfilehash: a6ae80adb9ddae2c675e75d747dda27f09a404fb
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957251"
---
# <a name="unverified-sender"></a><span data-ttu-id="eff63-103">Mittente non verificato</span><span class="sxs-lookup"><span data-stu-id="eff63-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="eff63-104">Questi aggiornamenti stanno per essere implementati e potrebbero non essere disponibili per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="eff63-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="eff63-105">Questa funzionalità è supportata per gli utenti Desktop Enterprise Outlook.com e Enterprise Outlook Win32.</span><span class="sxs-lookup"><span data-stu-id="eff63-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="eff63-106">Non è attualmente disponibile per gli utenti di Office 365 di consumer.</span><span class="sxs-lookup"><span data-stu-id="eff63-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="eff63-107">Per impedire ai messaggi di phishing di raggiungere la propria cassetta postale, Office 365 verifica che i mittenti siano quelli che dicono di essere e contrassegnare i messaggi sospetti come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="eff63-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eff63-108">Quando un messaggio viene contrassegnato come truffa di phishing, in Outlook viene visualizzato un avviso nella parte superiore della pagina, ma è comunque possibile aprire qualsiasi collegamento del messaggio.</span><span class="sxs-lookup"><span data-stu-id="eff63-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="eff63-109">Come è possibile identificare un messaggio sospetto nella cartella posta in arrivo?</span><span class="sxs-lookup"><span data-stu-id="eff63-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="eff63-110">Outlook Mostra gli indicatori quando il mittente di un messaggio non può essere identificato o la sua identità è diversa da quella visualizzata nell'indirizzo da.</span><span class="sxs-lookup"><span data-stu-id="eff63-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="eff63-111">Viene visualizzato un'?' nell'immagine del mittente</span><span class="sxs-lookup"><span data-stu-id="eff63-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="eff63-112">Quando Office 365 non è in grado di verificare l'identità del mittente utilizzando tecniche di autenticazione della posta elettronica, nell'immagine del mittente viene visualizzato il messaggio "?".</span><span class="sxs-lookup"><span data-stu-id="eff63-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![Il messaggio non ha superato la verifica](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="eff63-114">Non tutti i messaggi che non sono in grado di eseguire l'autenticazione sono dannosi.</span><span class="sxs-lookup"><span data-stu-id="eff63-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="eff63-115">Tuttavia, è necessario prestare particolare attenzione all'interazione con i messaggi che non eseguono l'autenticazione se non si riconosce il mittente.</span><span class="sxs-lookup"><span data-stu-id="eff63-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="eff63-116">In alternativa, se si riconosce un mittente che in genere non ha un'?' nell'immagine del mittente, ma si inizia improvvisamente a vederlo, potrebbe essere un segno che il mittente viene falsificato.</span><span class="sxs-lookup"><span data-stu-id="eff63-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="eff63-117">Come gestire i messaggi che ricevono il trattamento dei mittenti non verificati</span><span class="sxs-lookup"><span data-stu-id="eff63-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="eff63-118">Se si è un cliente di Office 365, è possibile gestire questa funzionalità tramite il Centro sicurezza & conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="eff63-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="eff63-119">Nel centro sicurezza & conformità, gli amministratori globali o di sicurezza possono attivarla o disattivarla, tramite la protezione anti-spoofing in base ai criteri phishing.</span><span class="sxs-lookup"><span data-stu-id="eff63-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="eff63-120">Inoltre, è possibile utilizzare il cmdlet **set-AntiPhishPolicy** in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eff63-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="eff63-121">Per informazioni dettagliate, vedere [protezione anti-phishing in Office 365](anti-phishing-protection.md) e [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span><span class="sxs-lookup"><span data-stu-id="eff63-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![Modifica dei mittenti non autenticati nell'interfaccia grafica.](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="eff63-123">Se un amministratore ha identificato un falso positivo e un mittente non deve ricevere il trattamento del mittente non verificato, è possibile eseguire una delle operazioni seguenti per aggiungere il mittente all'elenco Consenti spoofing di informazioni spoof:</span><span class="sxs-lookup"><span data-stu-id="eff63-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="eff63-124">Aggiungere la coppia di domini tramite lo spoofing Intelligence Insight.</span><span class="sxs-lookup"><span data-stu-id="eff63-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="eff63-125">Per informazioni dettagliate, vedere [procedura dettagliata: spoofing Intelligence Insight](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="eff63-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="eff63-126">Aggiungere la coppia di domini tramite il cmdlet **set-PhishFilterPolicy** in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eff63-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="eff63-127">Per informazioni dettagliate, vedere [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) e [set up Office 365 ATP anti-phishing and anti-phishing Policies](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="eff63-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="eff63-128">Inoltre, non viene applicato il trattamento del mittente non verificato se il messaggio è stato recapitato alla posta in arrivo tramite le regole del flusso di posta (note anche come regole di trasporto) oppure l'elenco dei domini attendibili (criteri di protezione dalla posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="eff63-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="eff63-129">Come gestire il tag ' via '</span><span class="sxs-lookup"><span data-stu-id="eff63-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="eff63-130">Se si è un cliente di Office 365, è possibile gestire questa funzionalità tramite il Centro sicurezza & conformità di Office 365, allo stesso modo in cui si gestisce il trattamento dei mittenti non verificati.</span><span class="sxs-lookup"><span data-stu-id="eff63-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="eff63-131">Se si aggiunge il mittente all'elenco di consentiti spoofing Intelligence spoof, il trattamento ' via ' non verrà applicato.</span><span class="sxs-lookup"><span data-stu-id="eff63-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="eff63-132">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="eff63-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="eff63-133">Quali criteri utilizza Outlook.com e Outlook Win32 Desktop per aggiungere le proprietà'?' è via '?</span><span class="sxs-lookup"><span data-stu-id="eff63-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="eff63-134">Per '?' nell'immagine del mittente: Outlook.com richiede che il messaggio passi l'autenticazione SPF o DKIM e riceva un passaggio DMARC oppure un passaggio di autenticazione composita dall'intelligence spoof di Office 365.</span><span class="sxs-lookup"><span data-stu-id="eff63-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="eff63-135">Per informazioni dettagliate, vedere [set up SPF in office 365 per impedire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) e [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="eff63-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="eff63-136">Per il tag Via: se il dominio nell'indirizzo from è diverso dal dominio nella firma di DKIM o nella posta SMTP da, Outlook.com Visualizza il dominio in uno di questi due campi (preferendo la firma di DKIM).</span><span class="sxs-lookup"><span data-stu-id="eff63-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="eff63-137">Come è possibile rimuovere il '?' senza utilizzare l'elenco di consentiti spoof di spoofing Intelligence?</span><span class="sxs-lookup"><span data-stu-id="eff63-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="eff63-138">Per il "?" nell'immagine del mittente: come mittente, è necessario autenticare il messaggio con SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="eff63-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="eff63-139">Per il tag Via: come mittente, è necessario assicurarsi che il dominio nella firma di DKIM o la posta SMTP sia uguale a, o sia un sottodominio di, il dominio nell'indirizzo da.</span><span class="sxs-lookup"><span data-stu-id="eff63-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="eff63-140">Le Outlook.com e il desktop di Outlook Win32 lo mostrano per ogni messaggio che non passa l'autenticazione?</span><span class="sxs-lookup"><span data-stu-id="eff63-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="eff63-141">Non necessariamente.</span><span class="sxs-lookup"><span data-stu-id="eff63-141">Not necessarily.</span></span> <span data-ttu-id="eff63-142">Office 365 può avere altre proprietà all'interno del messaggio per autenticare il mittente.</span><span class="sxs-lookup"><span data-stu-id="eff63-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="eff63-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="eff63-143">Related topics</span></span>

[<span data-ttu-id="eff63-144">Proteggi il tuo account di posta elettronica di Outlook.com</span><span class="sxs-lookup"><span data-stu-id="eff63-144">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="eff63-145">Gestione del phishing o dello spoofing in Outlook.com</span><span class="sxs-lookup"><span data-stu-id="eff63-145">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="eff63-146">Filtrare la posta indesiderata e la posta indesiderata in Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="eff63-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
