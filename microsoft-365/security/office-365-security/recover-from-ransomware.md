---
title: Ripristinare da un attacco ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 amministratori possono imparare a eseguire il ripristino da un attacco ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 608fac50fc65f20a612b80ed151252eb2a0c2e01
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415554"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="a1748-103">Ripristino da un attacco ransomware in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a1748-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a1748-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="a1748-104">**Applies to**</span></span>
- [<span data-ttu-id="a1748-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a1748-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a1748-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="a1748-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a1748-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1748-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a1748-108">Anche se si prende ogni precauzione per proteggere l'organizzazione, è comunque possibile essere vittima di un [attacco ransomware.](/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="a1748-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="a1748-109">Il ransomware è una grande azienda e gli attacchi sono molto sofisticati.</span><span class="sxs-lookup"><span data-stu-id="a1748-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="a1748-110">I passaggi descritti in questo articolo offrono la migliore possibilità di recuperare i dati e arrestare la diffusione interna dell'infezione.</span><span class="sxs-lookup"><span data-stu-id="a1748-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="a1748-111">Prima di iniziare, considera i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="a1748-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="a1748-112">Non c'è alcuna garanzia che il pagamento del riscatto restituirà l'accesso ai file.</span><span class="sxs-lookup"><span data-stu-id="a1748-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="a1748-113">Infatti, il pagamento del riscatto può fare di te un obiettivo per più ransomware.</span><span class="sxs-lookup"><span data-stu-id="a1748-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="a1748-114">Se hai già pagato, ma hai recuperato senza usare la soluzione dell'autore dell'attacco, contatta la tua banca per vedere se è in grado di bloccare la transazione.</span><span class="sxs-lookup"><span data-stu-id="a1748-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="a1748-115">È inoltre consigliabile segnalare l'attacco ransomware alle forze dell'ordine, ai siti Web di segnalazione delle truffe e a Microsoft, come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a1748-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="a1748-116">È importante rispondere rapidamente all'attacco e alle sue conseguenze.</span><span class="sxs-lookup"><span data-stu-id="a1748-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="a1748-117">Maggiore è il tempo di attesa, minore è la probabilità che sia possibile ripristinare i dati interessati.</span><span class="sxs-lookup"><span data-stu-id="a1748-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="a1748-118">Passaggio 1: verificare i backup</span><span class="sxs-lookup"><span data-stu-id="a1748-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="a1748-119">Se si dispone di backup offline, è  probabile che sia possibile ripristinare i dati crittografati dopo aver rimosso il payload ransomware (malware) dall'ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1748-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="a1748-120">Se non si dispone di backup o se i backup sono stati interessati anche dal ransomware, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="a1748-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="a1748-121">Passaggio 2: disabilitare Exchange ActiveSync e sincronizzazione OneDrive</span><span class="sxs-lookup"><span data-stu-id="a1748-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="a1748-122">Il punto chiave è arrestare la diffusione della crittografia dei dati da parte del ransomware.</span><span class="sxs-lookup"><span data-stu-id="a1748-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="a1748-123">Se si sospetta che la posta elettronica sia una destinazione della crittografia ransomware, disabilitare temporaneamente l'accesso utente alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="a1748-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="a1748-124">Exchange ActiveSync sincronizza i dati tra dispositivi e Exchange Online cassette postali.</span><span class="sxs-lookup"><span data-stu-id="a1748-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="a1748-125">Per disabilitare Exchange ActiveSync per una cassetta postale, vedere [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span><span class="sxs-lookup"><span data-stu-id="a1748-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="a1748-126">Per disabilitare altri tipi di accesso a una cassetta postale, vedere:</span><span class="sxs-lookup"><span data-stu-id="a1748-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="a1748-127">[Abilitare o disabilitare MAPI per una cassetta postale](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span><span class="sxs-lookup"><span data-stu-id="a1748-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="a1748-128">Abilitare o disabilitare l'accesso POP3 o IMAP4 per un utente</span><span class="sxs-lookup"><span data-stu-id="a1748-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="a1748-129">La sospensione sincronizzazione OneDrive consente di proteggere i dati cloud dall'aggiornamento da dispositivi potenzialmente infetti.</span><span class="sxs-lookup"><span data-stu-id="a1748-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="a1748-130">Per ulteriori informazioni, vedere Come sospendere e riprendere la [sincronizzazione in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span><span class="sxs-lookup"><span data-stu-id="a1748-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="a1748-131">Passaggio 3: rimuovere il malware dai dispositivi interessati</span><span class="sxs-lookup"><span data-stu-id="a1748-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="a1748-132">Eseguire un'analisi antivirus completa e corrente su tutti i computer e i dispositivi sospetti per rilevare e rimuovere il payload associato al ransomware.</span><span class="sxs-lookup"><span data-stu-id="a1748-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="a1748-133">Non dimenticare di analizzare i dispositivi che sincronizzano i dati o le destinazioni delle unità di rete mappate.</span><span class="sxs-lookup"><span data-stu-id="a1748-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="a1748-134">È possibile utilizzare [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (per i client [meno recenti) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="a1748-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="a1748-135">Un'alternativa che consente anche di rimuovere ransomware o malware è lo Strumento di rimozione [di software dannoso (MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="a1748-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="a1748-136">Se queste opzioni non funzionano, è possibile provare a Windows Defender [offline](https://support.microsoft.com/help/17466) o risolvere i problemi relativi al rilevamento e alla [rimozione di malware.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="a1748-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="a1748-137">Passaggio 4: Ripristinare i file in un computer o un dispositivo pulito</span><span class="sxs-lookup"><span data-stu-id="a1748-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="a1748-138">Dopo aver completato il passaggio precedente per rimuovere il payload ransomware dall'ambiente (che impedirà al ransomware di crittografare o rimuovere i file), è possibile utilizzare Cronologia file [in](https://support.microsoft.com/help/17128) Windows 10 e Windows 8.1 o Protezione del sistema in Windows 7 per tentare di ripristinare i file e le cartelle locali.</span><span class="sxs-lookup"><span data-stu-id="a1748-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="a1748-139">**Note**:</span><span class="sxs-lookup"><span data-stu-id="a1748-139">**Notes**:</span></span>

- <span data-ttu-id="a1748-140">Alcuni ransomware crittograferanno o elimineranno anche le versioni di backup, quindi non puoi usare Cronologia file o Protezione del sistema per ripristinare i file.</span><span class="sxs-lookup"><span data-stu-id="a1748-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="a1748-141">In questo caso, è necessario utilizzare backup su unità esterne o dispositivi che non sono stati interessati dal ransomware o OneDrive come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="a1748-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="a1748-142">Se una cartella è sincronizzata con OneDrive e non si utilizza la versione più recente di Windows, è possibile che l'utilizzo di Cronologia file presenti alcune limitazioni.</span><span class="sxs-lookup"><span data-stu-id="a1748-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="a1748-143">Passaggio 5: Ripristinare i file nel OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a1748-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="a1748-144">File Restore in OneDrive for Business consente di ripristinare l'intero OneDrive a un punto precedente nel tempo negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="a1748-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="a1748-145">Per ulteriori informazioni, vedere [Ripristinare OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span><span class="sxs-lookup"><span data-stu-id="a1748-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="a1748-146">Passaggio 6: Recuperare la posta elettronica eliminata</span><span class="sxs-lookup"><span data-stu-id="a1748-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="a1748-147">Nel raro caso in cui il ransomware ha eliminato tutti i messaggi di posta elettronica, è probabile che sia possibile recuperare gli elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="a1748-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="a1748-148">Per altre informazioni, vedi:</span><span class="sxs-lookup"><span data-stu-id="a1748-148">For more information, see:</span></span>

- [<span data-ttu-id="a1748-149">Recupero dei messaggi eliminati nella cassetta postale di un utente</span><span class="sxs-lookup"><span data-stu-id="a1748-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="a1748-150">Ripristinare gli elementi eliminati in Outlook per Windows</span><span class="sxs-lookup"><span data-stu-id="a1748-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="a1748-151">Passaggio 7: Ri abilitare Exchange ActiveSync e sincronizzazione OneDrive</span><span class="sxs-lookup"><span data-stu-id="a1748-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="a1748-152">Dopo aver pulito i computer e i dispositivi e aver recuperato i dati, è possibile ri-abilitare Exchange ActiveSync e sincronizzazione OneDrive precedentemente disabilitati nel [passaggio 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="a1748-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="a1748-153">Passaggio 8 (facoltativo): bloccare sincronizzazione OneDrive specifiche estensioni di file</span><span class="sxs-lookup"><span data-stu-id="a1748-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="a1748-154">Dopo il ripristino, è possibile impedire OneDrive for Business client di sincronizzare i tipi di file interessati da questo ransomware.</span><span class="sxs-lookup"><span data-stu-id="a1748-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="a1748-155">Per ulteriori informazioni, [vedere Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="a1748-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="a1748-156">Segnalare l'attacco</span><span class="sxs-lookup"><span data-stu-id="a1748-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="a1748-157">Contattare le forze dell'ordine</span><span class="sxs-lookup"><span data-stu-id="a1748-157">Contact law enforcement</span></span>

<span data-ttu-id="a1748-158">È consigliabile contattare le forze dell'ordine locali o federali.</span><span class="sxs-lookup"><span data-stu-id="a1748-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="a1748-159">Ad esempio, se si è negli Stati Uniti, è possibile contattare l'ufficio sul campo locale [dell'FBI,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) [o Secret Service.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="a1748-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="a1748-160">Inviare un report al sito Web di segnalazione delle truffe nel proprio paese</span><span class="sxs-lookup"><span data-stu-id="a1748-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="a1748-161">I siti Web di segnalazione delle truffe forniscono informazioni su come prevenire ed evitare truffe.</span><span class="sxs-lookup"><span data-stu-id="a1748-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="a1748-162">Forniscono anche meccanismi per segnalare se sei stato vittima di una frode.</span><span class="sxs-lookup"><span data-stu-id="a1748-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="a1748-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="a1748-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="a1748-164">Canada: [Centro antifrode canadese](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="a1748-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="a1748-165">Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="a1748-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="a1748-166">Germania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="a1748-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="a1748-167">Irlanda: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="a1748-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="a1748-168">Nuova Zelanda: [truffe agli affari dei consumatori](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="a1748-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="a1748-169">Svizzera [Nazionali Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span><span class="sxs-lookup"><span data-stu-id="a1748-169">Switzerland [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span></span>

- <span data-ttu-id="a1748-170">Regno Unito: [frode d'azione](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="a1748-170">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="a1748-171">Stati Uniti: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="a1748-171">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="a1748-172">Se il paese non è elencato, chiedere alle forze dell'ordine locali o federali.</span><span class="sxs-lookup"><span data-stu-id="a1748-172">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="a1748-173">Inviare messaggi di posta elettronica a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a1748-173">Submit email messages to Microsoft</span></span>

<span data-ttu-id="a1748-174">È possibile segnalare i messaggi di phishing che contengono ransomware utilizzando uno dei diversi metodi.</span><span class="sxs-lookup"><span data-stu-id="a1748-174">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="a1748-175">Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a1748-175">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="additional-ransomware-resources"></a><span data-ttu-id="a1748-176">Risorse ransomware aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a1748-176">Additional ransomware resources</span></span>

<span data-ttu-id="a1748-177">Informazioni chiave del settore:</span><span class="sxs-lookup"><span data-stu-id="a1748-177">Key industry information:</span></span>

- [<span data-ttu-id="a1748-178">Panoramica del ransomware gestito dall'utente</span><span class="sxs-lookup"><span data-stu-id="a1748-178">Human-operated ransomware overview</span></span>](/security/compass/human-operated-ransomware)

- [<span data-ttu-id="a1748-179">Proteggere rapidamente da ransomware ed estorsioni</span><span class="sxs-lookup"><span data-stu-id="a1748-179">Rapidly protect against ransomware and extortion</span></span>](/security/compass/protect-against-ransomware)

- <span data-ttu-id="a1748-180">[L'Intelligence di sicurezza Microsoft report](https://www.microsoft.com/securityinsights/) più recente (vedere pagine 22-24)</span><span class="sxs-lookup"><span data-stu-id="a1748-180">[The latest Microsoft Security Intelligence Report](https://www.microsoft.com/securityinsights/) (see pages 22-24)</span></span>

- <span data-ttu-id="a1748-181">**Ransomware: un report sulle minacce pervasivo** e continuo nel nodo **Analisi** delle minacce del portale Microsoft 365 Defender (vedere questi [requisiti di licenza](/microsoft-365/security/defender/prerequisites#licensing-requirements))</span><span class="sxs-lookup"><span data-stu-id="a1748-181">**Ransomware: A pervasive and ongoing threat** report in the **Threat analytics node** of the Microsoft 365 Defender portal (see these [licensing requirements](/microsoft-365/security/defender/prerequisites#licensing-requirements))</span></span>

<span data-ttu-id="a1748-182">Microsoft 365 protezione:</span><span class="sxs-lookup"><span data-stu-id="a1748-182">Microsoft 365 protection:</span></span>

- [<span data-ttu-id="a1748-183">Protezione da malware e ransomware</span><span class="sxs-lookup"><span data-stu-id="a1748-183">Malware and ransomware protection</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [<span data-ttu-id="a1748-184">Rilevamento ransomware e ripristino dei file in OneDrive</span><span class="sxs-lookup"><span data-stu-id="a1748-184">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)
- [<span data-ttu-id="a1748-185">Abilitare o disabilitare le macro nei Office file</span><span class="sxs-lookup"><span data-stu-id="a1748-185">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)
- [<span data-ttu-id="a1748-186">Impostazioni consigliate per EOP e Microsoft Defender per Office 365 sicurezza</span><span class="sxs-lookup"><span data-stu-id="a1748-186">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

<span data-ttu-id="a1748-187">Post di blog del team di sicurezza Microsoft:</span><span class="sxs-lookup"><span data-stu-id="a1748-187">Microsoft Security team blog posts:</span></span>

- [<span data-ttu-id="a1748-188">Diventare resilienti comprendendo i rischi di cybersecurity: parte 4- Esplorazione delle minacce correnti (maggio 2021)</span><span class="sxs-lookup"><span data-stu-id="a1748-188">Becoming resilient by understanding cybersecurity risks: Part 4—navigating current threats (May 2021)</span></span>](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  <span data-ttu-id="a1748-189">Vedi la **sezione Ransomware.**</span><span class="sxs-lookup"><span data-stu-id="a1748-189">See the **Ransomware** section.</span></span>

- [<span data-ttu-id="a1748-190">Attacchi ransomware gestiti dall'uomo: una catastrofe prevenibile (marzo 2020)</span><span class="sxs-lookup"><span data-stu-id="a1748-190">Human-operated ransomware attacks: A preventable disaster (March 2020)</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
- [<span data-ttu-id="a1748-191">Risposta ransomware: pagare o non pagare? (Dicembre 2019)</span><span class="sxs-lookup"><span data-stu-id="a1748-191">Ransomware response—to pay or not to pay? (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [<span data-ttu-id="a1748-192">Norsk Hydro risponde agli attacchi ransomware con trasparenza (dicembre 2019)</span><span class="sxs-lookup"><span data-stu-id="a1748-192">Norsk Hydro responds to ransomware attack with transparency (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
- [<span data-ttu-id="a1748-193">Un aggiornamento degno: la sicurezza di nuova generazione Windows 10 dimostra resiliente contro gli attacchi ransomware nel 2017 (gennaio 2018)</span><span class="sxs-lookup"><span data-stu-id="a1748-193">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017 (January 2018)</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

