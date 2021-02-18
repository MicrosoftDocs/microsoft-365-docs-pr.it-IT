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
description: Gli amministratori di Microsoft 365 possono imparare a recuperare da un attacco ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 120dd9ae71f04d6921fae95965f56f0a08f1280c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289306"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="cf989-103">Ripristino da un attacco ransomware in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf989-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cf989-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="cf989-104">**Applies to**</span></span>
- [<span data-ttu-id="cf989-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cf989-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cf989-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="cf989-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="cf989-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf989-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="cf989-108">Anche se si prendono tutte le precauzioni necessarie per proteggere l'organizzazione, è comunque possibile essere vittima di un [attacco ransomware.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)</span><span class="sxs-lookup"><span data-stu-id="cf989-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="cf989-109">Ransomware è una grande azienda e gli attacchi sono molto sofisticati.</span><span class="sxs-lookup"><span data-stu-id="cf989-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="cf989-110">I passaggi descritti in questo articolo offrono la migliore possibilità di recuperare i dati e arrestare la diffusione interna dell'infezione.</span><span class="sxs-lookup"><span data-stu-id="cf989-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="cf989-111">Prima di iniziare, considera i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="cf989-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="cf989-112">Non c'è garanzia che il pagamento del riscatto restituirà l'accesso ai file.</span><span class="sxs-lookup"><span data-stu-id="cf989-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="cf989-113">Infatti, pagare il riscatto può fare di te un obiettivo per più ransomware.</span><span class="sxs-lookup"><span data-stu-id="cf989-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="cf989-114">Se hai già pagato, ma hai recuperato senza usare la soluzione dell'utente malintenzionato, contatta la tua banca per verificare se può bloccare la transazione.</span><span class="sxs-lookup"><span data-stu-id="cf989-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="cf989-115">Si consiglia inoltre di segnalare l'attacco ransomware alle forze dell'ordine, ai siti Web di segnalazione delle truffe e a Microsoft, come descritto più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="cf989-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="cf989-116">È importante rispondere rapidamente all'attacco e alle sue conseguenze.</span><span class="sxs-lookup"><span data-stu-id="cf989-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="cf989-117">Maggiore è il tempo di attesa, meno è probabile che sia possibile ripristinare i dati interessati.</span><span class="sxs-lookup"><span data-stu-id="cf989-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="cf989-118">Passaggio 1: Verificare i backup</span><span class="sxs-lookup"><span data-stu-id="cf989-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="cf989-119">Se si dispone di backup offline, è  probabile che sia possibile ripristinare i dati crittografati dopo aver rimosso il payload ransomware (malware) dall'ambiente.</span><span class="sxs-lookup"><span data-stu-id="cf989-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="cf989-120">Se non si dispone di backup o se i backup sono stati interessati anche dal ransomware, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="cf989-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="cf989-121">Passaggio 2: disabilitare la Exchange ActiveSync e la sincronizzazione di OneDrive</span><span class="sxs-lookup"><span data-stu-id="cf989-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="cf989-122">Il punto chiave qui è arrestare la diffusione della crittografia dei dati da parte del ransomware.</span><span class="sxs-lookup"><span data-stu-id="cf989-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="cf989-123">Se si sospetta che la posta elettronica sia una destinazione della crittografia ransomware, disabilitare temporaneamente l'accesso degli utenti alle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="cf989-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="cf989-124">Exchange ActiveSync sincronizza i dati tra i dispositivi e le cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf989-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="cf989-125">Per disabilitare Exchange ActiveSync per una cassetta postale, vedere Come disabilitare Exchange ActiveSync [per gli utenti in Exchange Online.](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="cf989-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="cf989-126">Per disabilitare altri tipi di accesso a una cassetta postale, vedere:</span><span class="sxs-lookup"><span data-stu-id="cf989-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="cf989-127">[Abilitare o disabilitare MAPI per una cassetta postale.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)</span><span class="sxs-lookup"><span data-stu-id="cf989-127">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="cf989-128">Abilitare o disabilitare l'accesso POP3 o IMAP4 per un utente</span><span class="sxs-lookup"><span data-stu-id="cf989-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="cf989-129">La sospensione della sincronizzazione di OneDrive consente di proteggere i dati del cloud dall'aggiornamento da parte di dispositivi potenzialmente infetti.</span><span class="sxs-lookup"><span data-stu-id="cf989-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="cf989-130">Per altre informazioni, vedere [Come sospendere e riprendere la sincronizzazione in OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)</span><span class="sxs-lookup"><span data-stu-id="cf989-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="cf989-131">Passaggio 3: rimuovere il malware dai dispositivi interessati</span><span class="sxs-lookup"><span data-stu-id="cf989-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="cf989-132">Eseguire un'analisi antivirus completa e corrente su tutti i computer e dispositivi sospetti per rilevare e rimuovere il payload associato al ransomware.</span><span class="sxs-lookup"><span data-stu-id="cf989-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="cf989-133">Non dimenticare di analizzare i dispositivi che sincronizzano i dati o le destinazioni delle unità di rete mappate.</span><span class="sxs-lookup"><span data-stu-id="cf989-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="cf989-134">È possibile utilizzare [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (per client meno [recenti) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span><span class="sxs-lookup"><span data-stu-id="cf989-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="cf989-135">Un'alternativa che consente anche di rimuovere ransomware o malware è lo Strumento di rimozione [malware .](https://www.microsoft.com/download/details.aspx?id=9905)</span><span class="sxs-lookup"><span data-stu-id="cf989-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="cf989-136">Se queste opzioni non funzionano, è possibile provare Windows Defender [offline](https://support.microsoft.com/help/17466) o risolvere i problemi relativi al rilevamento e [alla rimozione di malware.](https://support.microsoft.com/help/4466982)</span><span class="sxs-lookup"><span data-stu-id="cf989-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="cf989-137">Passaggio 4: Recuperare i file in un computer o un dispositivo pulito</span><span class="sxs-lookup"><span data-stu-id="cf989-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="cf989-138">Dopo aver completato il passaggio precedente per rimuovere il payload ransomware dall'ambiente (che impedirà al ransomware di crittografare o rimuovere i file), puoi usare Cronologia file [in](https://support.microsoft.com/help/17128) Windows 10 e Windows 8.1 o Protezione di sistema in Windows 7 per tentare di recuperare i file e le cartelle locali.</span><span class="sxs-lookup"><span data-stu-id="cf989-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="cf989-139">**Note**:</span><span class="sxs-lookup"><span data-stu-id="cf989-139">**Notes**:</span></span>

- <span data-ttu-id="cf989-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span><span class="sxs-lookup"><span data-stu-id="cf989-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="cf989-141">In questo caso, è necessario utilizzare i backup su unità esterne o dispositivi che non sono stati interessati dal ransomware o OneDrive, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="cf989-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="cf989-142">Se una cartella è sincronizzata con OneDrive e non si usa la versione più recente di Windows, potrebbero esserci alcune limitazioni con Cronologia file.</span><span class="sxs-lookup"><span data-stu-id="cf989-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="cf989-143">Passaggio 5: Recuperare i file in OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cf989-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="cf989-144">Il ripristino dei file in OneDrive for Business consente di ripristinare l'intero OneDrive a un punto nel tempo precedente negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="cf989-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="cf989-145">Per ulteriori informazioni, vedere [Ripristinare OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)</span><span class="sxs-lookup"><span data-stu-id="cf989-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="cf989-146">Passaggio 6: Recuperare la posta elettronica eliminata</span><span class="sxs-lookup"><span data-stu-id="cf989-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="cf989-147">Nel raro caso in cui il ransomware ha eliminato tutti i messaggi di posta elettronica, è probabile che sia possibile recuperare gli elementi eliminati.</span><span class="sxs-lookup"><span data-stu-id="cf989-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="cf989-148">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="cf989-148">For more information, see:</span></span>

- [<span data-ttu-id="cf989-149">Recupero dei messaggi eliminati nella cassetta postale di un utente</span><span class="sxs-lookup"><span data-stu-id="cf989-149">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="cf989-150">Ripristinare gli elementi eliminati in Outlook per Windows</span><span class="sxs-lookup"><span data-stu-id="cf989-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="cf989-151">Passaggio 7: Ri-abilitare la sincronizzazione Exchange ActiveSync e OneDrive</span><span class="sxs-lookup"><span data-stu-id="cf989-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="cf989-152">Dopo aver pulito i computer e i dispositivi e aver ripristinato i dati, è possibile ri-abilitare la sincronizzazione di Exchange ActiveSync e OneDrive precedentemente disabilitata nel [passaggio 2.](#step-2-disable-exchange-activesync-and-onedrive-sync)</span><span class="sxs-lookup"><span data-stu-id="cf989-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="cf989-153">Passaggio 8 (facoltativo): Bloccare la sincronizzazione di OneDrive per estensioni di file specifiche</span><span class="sxs-lookup"><span data-stu-id="cf989-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="cf989-154">Dopo il ripristino, è possibile impedire ai client di OneDrive for Business di sincronizzare i tipi di file interessati da questo ransomware.</span><span class="sxs-lookup"><span data-stu-id="cf989-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="cf989-155">Per ulteriori informazioni, vedere [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="cf989-155">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="cf989-156">Segnalare l'attacco</span><span class="sxs-lookup"><span data-stu-id="cf989-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="cf989-157">Contattare le forze dell'ordine</span><span class="sxs-lookup"><span data-stu-id="cf989-157">Contact law enforcement</span></span>

<span data-ttu-id="cf989-158">È consigliabile contattare le forze dell'ordine locali o federali.</span><span class="sxs-lookup"><span data-stu-id="cf989-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="cf989-159">Ad esempio, se si è negli Stati Uniti, è possibile contattare l'ufficio sul campo [locale dell'FBI,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) o [Secret Service.](http://www.secretservice.gov/)</span><span class="sxs-lookup"><span data-stu-id="cf989-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="cf989-160">Inviare un report al sito Web di segnalazione delle truffe nel proprio paese</span><span class="sxs-lookup"><span data-stu-id="cf989-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="cf989-161">I siti Web di segnalazione delle truffe forniscono informazioni su come prevenire ed evitare le truffe.</span><span class="sxs-lookup"><span data-stu-id="cf989-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="cf989-162">Forniscono anche meccanismi per segnalare se sei stato vittima di una frode.</span><span class="sxs-lookup"><span data-stu-id="cf989-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="cf989-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="cf989-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="cf989-164">Canada: [Centro antifrode canadese](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="cf989-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="cf989-165">Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="cf989-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="cf989-166">Germania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="cf989-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="cf989-167">Irlanda: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="cf989-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="cf989-168">Nuova Zelanda: [truffe agli affari dei consumatori](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="cf989-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="cf989-169">Regno Unito: frode [in azioni](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="cf989-169">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="cf989-170">Stati Uniti: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="cf989-170">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="cf989-171">Se il tuo paese non è elencato, chiedi alle forze dell'ordine locali o federali.</span><span class="sxs-lookup"><span data-stu-id="cf989-171">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="cf989-172">Inviare messaggi di posta elettronica a Microsoft</span><span class="sxs-lookup"><span data-stu-id="cf989-172">Submit email messages to Microsoft</span></span>

<span data-ttu-id="cf989-173">È possibile segnalare i messaggi di phishing che contengono ransomware utilizzando uno dei diversi metodi.</span><span class="sxs-lookup"><span data-stu-id="cf989-173">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="cf989-174">Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="cf989-174">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf989-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf989-175">See also</span></span>

- [<span data-ttu-id="cf989-176">Ransomware</span><span class="sxs-lookup"><span data-stu-id="cf989-176">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="cf989-177">Risposta ransomware: pagare o non pagare?</span><span class="sxs-lookup"><span data-stu-id="cf989-177">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="cf989-178">Norsk 2016 risponde all'attacco ransomware con trasparenza</span><span class="sxs-lookup"><span data-stu-id="cf989-178">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="cf989-179">Rilevamento e ripristino di file ransomware in OneDrive</span><span class="sxs-lookup"><span data-stu-id="cf989-179">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="cf989-180">Report Intelligence per la sicurezza Microsoft</span><span class="sxs-lookup"><span data-stu-id="cf989-180">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="cf989-181">Attivare o disattivare le macro nei file di Office</span><span class="sxs-lookup"><span data-stu-id="cf989-181">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="cf989-182">Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="cf989-182">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="cf989-183">Un aggiornamento inevaso: la sicurezza di nuova generazione in Windows 10 si dimostra resiliente contro gli attacchi ransomware nel 2017</span><span class="sxs-lookup"><span data-stu-id="cf989-183">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="cf989-184">No mas, Samas: What's in this ransomware's modus operandi?</span><span class="sxs-lookup"><span data-stu-id="cf989-184">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="cf989-185">Malware bloccante, antimalware per evitarlo</span><span class="sxs-lookup"><span data-stu-id="cf989-185">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="cf989-186">MSRT luglio 2016: Cerber ransomware</span><span class="sxs-lookup"><span data-stu-id="cf989-186">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="cf989-187">Le tre teste del ransomware Cerberus simile a Cerber</span><span class="sxs-lookup"><span data-stu-id="cf989-187">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="cf989-188">Troldesh ransomware influenzato dal (il) codice Da Tutto</span><span class="sxs-lookup"><span data-stu-id="cf989-188">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
