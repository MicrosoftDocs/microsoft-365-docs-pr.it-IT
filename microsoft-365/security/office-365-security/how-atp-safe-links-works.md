---
title: Funzionamento di collegamenti sicuri di Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: La funzionalità collegamenti sicuri fornisce il tempo di fare clic sulla verifica dei link ipertestuali nei documenti di Office e nei messaggi di posta elettronica. Leggere questo articolo per informazioni su come funzionano i collegamenti sicuri di ATP.
ms.openlocfilehash: c87eef2afbb3a694d9906de0c6c43bfeb576782b
ms.sourcegitcommit: 004f01fc5d5bdb8aac03d69692d86c38b5e05e14
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "42333683"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="d59bc-104">Funzionamento di collegamenti sicuri di Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="d59bc-104">How Office 365 ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="d59bc-105">Per il corretto funzionamento dei collegamenti sicuri di Office 365 ATP, tutti i servizi di Office 365 devono essere presenti nella stessa versione.</span><span class="sxs-lookup"><span data-stu-id="d59bc-105">For Office 365 ATP Safe Links to operate correctly, all of the Office 365 services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="d59bc-106">Funzionamento dei collegamenti sicuri di ATP con gli URL nella posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d59bc-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="d59bc-107">A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL nella posta elettronica (ospitati in Office 365, non in locale):</span><span class="sxs-lookup"><span data-stu-id="d59bc-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="d59bc-108">Gli utenti ricevono messaggi di posta elettronica, alcuni dei quali contengono URL.</span><span class="sxs-lookup"><span data-stu-id="d59bc-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="d59bc-109">Tutti i messaggi di posta elettronica passano attraverso Exchange Online Protection, dove vengono applicati i filtri Internet (IP) e busta, la protezione antimalware basata sulle firme, i filtri anti-spam e antivirus.</span><span class="sxs-lookup"><span data-stu-id="d59bc-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="d59bc-110">La posta elettronica arriva nelle cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="d59bc-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="d59bc-111">Un utente accede a Office 365 e passa alla posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d59bc-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="d59bc-112">L'utente apre un messaggio di posta elettronica e fa clic su un URL nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d59bc-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="d59bc-113">La caratteristica collegamenti sicuri ATP verifica immediatamente l'URL prima di aprire il sito Web.</span><span class="sxs-lookup"><span data-stu-id="d59bc-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="d59bc-114">L'URL viene identificato come bloccato, dannoso o sicuro.</span><span class="sxs-lookup"><span data-stu-id="d59bc-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="d59bc-115">Se l'URL è incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="d59bc-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d59bc-116">Se l'URL è associato a un sito Web che è stato determinato come dannoso, viene visualizzata una [pagina di avviso](atp-safe-links-warning-pages.md) .</span><span class="sxs-lookup"><span data-stu-id="d59bc-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="d59bc-117">Se l'URL passa a un file scaricabile e i criteri per i [collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) dell'organizzazione sono configurati per l'analisi di tali contenuti, il file scaricabile viene controllato.</span><span class="sxs-lookup"><span data-stu-id="d59bc-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d59bc-118">Se l'URL è determinato per la sicurezza, il sito Web verrà aperto.</span><span class="sxs-lookup"><span data-stu-id="d59bc-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="d59bc-119">Funzionamento dei collegamenti sicuri di ATP con gli URL nei documenti di Office</span><span class="sxs-lookup"><span data-stu-id="d59bc-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="d59bc-120">A livello elevato, ecco come funziona la protezione dei [collegamenti sicuri di ATP](atp-safe-links.md) per gli URL nelle applicazioni di Office 365 ProPlus o Business Premium (versioni correnti di Word, Excel e PowerPoint su Windows, Mac o in un browser, app di Office su dispositivi iOS o Android, Visio su Windows, OneNote in un browser):</span><span class="sxs-lookup"><span data-stu-id="d59bc-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="d59bc-121">Gli utenti hanno installato Office 365 ProPlus o Business Premium nel computer, nello smartphone o nel tablet.</span><span class="sxs-lookup"><span data-stu-id="d59bc-121">People have installed Office 365 ProPlus or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="d59bc-122">(Oppure, utilizzano Office nel browser).</span><span class="sxs-lookup"><span data-stu-id="d59bc-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="d59bc-123">Un utente apre una parola, Excel, PowerPoint, OneNote (nel browser) o Visio (su desktop) e accede a Office 365 Enterprise utilizzando l'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="d59bc-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="d59bc-124">Il documento contiene gli URL.</span><span class="sxs-lookup"><span data-stu-id="d59bc-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="d59bc-125">Quando l'utente fa clic su un URL del documento, il collegamento è controllato dal servizio collegamenti sicuri di ATP.</span><span class="sxs-lookup"><span data-stu-id="d59bc-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="d59bc-126">Se l'URL è associato a un sito Web incluso nell' [elenco degli URL bloccati personalizzati](set-up-a-custom-blocked-urls-list-wtih-atp.md)dell'organizzazione, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="d59bc-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d59bc-127">Se l'URL è associato a un sito Web che è stato determinato come dannoso, l'utente viene indirizzato a una [pagina di avviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="d59bc-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="d59bc-128">Se l'URL passa a un file scaricabile e i [criteri dei collegamenti sicuri di ATP](set-up-atp-safe-links-policies.md) sono configurati per l'analisi di tali download, viene controllato il file scaricabile.</span><span class="sxs-lookup"><span data-stu-id="d59bc-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="d59bc-129">Se l'URL è considerato sicuro, l'utente viene reindirizzato al sito Web.</span><span class="sxs-lookup"><span data-stu-id="d59bc-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="d59bc-130">Se il controllo URL ha esito negativo, la protezione dei collegamenti sicuri non verrà attivata.</span><span class="sxs-lookup"><span data-stu-id="d59bc-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="d59bc-131">Nei client desktop, l'utente verrà avvisato prima di procedere al sito.</span><span class="sxs-lookup"><span data-stu-id="d59bc-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="d59bc-132">All'inizio di ogni sessione potrebbero essere necessari alcuni secondi per verificare che l'utente disponga di collegamenti sicuri di ATP per Office abilitato.</span><span class="sxs-lookup"><span data-stu-id="d59bc-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
