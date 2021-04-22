---
title: Come pianificare le analisi con Microsoft Defender for Endpoint (Linux)
description: Scopri come pianificare un tempo di analisi automatica per Microsoft Defender for Endpoint (Linux) per proteggere meglio le risorse dell'organizzazione.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, analisi, antivirus, microsoft defender for endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f868570fccf9b30cde5f16aa8e71292fb8b09497
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933134"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="29493-104">Pianificare le analisi con Microsoft Defender for Endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="29493-104">Schedule scans with Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="29493-105">Per eseguire un'analisi per Linux, vedi [Comandi supportati.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)</span><span class="sxs-lookup"><span data-stu-id="29493-105">To run a scan for Linux, see [Supported Commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands).</span></span>

<span data-ttu-id="29493-106">Linux (e Unix) dispongono di uno strumento denominato **crontab** (simile all'Utilità di pianificazione) per poter eseguire attività pianificate.</span><span class="sxs-lookup"><span data-stu-id="29493-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="29493-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="29493-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="29493-108">Per ottenere un elenco di tutti i fusi orari, eseguire il comando seguente: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="29493-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="29493-109">Esempi di fusi orario:</span><span class="sxs-lookup"><span data-stu-id="29493-109">Examples for timezones:</span></span>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="29493-110">Per impostare il processo Cron</span><span class="sxs-lookup"><span data-stu-id="29493-110">To set the Cron job</span></span>
<span data-ttu-id="29493-111">Utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="29493-111">Use the following commands:</span></span>

<span data-ttu-id="29493-112">**Per eseguire il backup delle voci crontab**</span><span class="sxs-lookup"><span data-stu-id="29493-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> <span data-ttu-id="29493-113">Dove 200919 == YRMMDD</span><span class="sxs-lookup"><span data-stu-id="29493-113">Where 200919 == YRMMDD</span></span>

> [!TIP]
> <span data-ttu-id="29493-114">Eseguire questa operazione prima di modificare o rimuovere.</span><span class="sxs-lookup"><span data-stu-id="29493-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="29493-115">Per modificare la crontab e aggiungere un nuovo processo come utente radice:</span><span class="sxs-lookup"><span data-stu-id="29493-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="29493-116">L'editor predefinito è VIM.</span><span class="sxs-lookup"><span data-stu-id="29493-116">The default editor is VIM.</span></span>

<span data-ttu-id="29493-117">Potrebbe essere visualizzato:</span><span class="sxs-lookup"><span data-stu-id="29493-117">You might see:</span></span>

<span data-ttu-id="29493-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="29493-118">0 \* \* \* \* /etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="29493-119">Premere "Insert"</span><span class="sxs-lookup"><span data-stu-id="29493-119">Press “Insert”</span></span>

<span data-ttu-id="29493-120">Aggiungere le voci seguenti:</span><span class="sxs-lookup"><span data-stu-id="29493-120">Add the following entries:</span></span>

<span data-ttu-id="29493-121">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="29493-121">CRON_TZ=America/Los_Angeles</span></span>

<span data-ttu-id="29493-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="29493-122">0 2 \* \* sat /bin/mdatp scan quick > ~/mdatp_cron_job.log</span></span>

> [!NOTE]
><span data-ttu-id="29493-123">In questo esempio è stato impostato su 00 minuti, 2:00.</span><span class="sxs-lookup"><span data-stu-id="29493-123">In this example, we have  set it to 00 minutes, 2 a.m.</span></span> <span data-ttu-id="29493-124">(ora in formato 24 ore), qualsiasi giorno del mese, qualsiasi mese, il sabato.</span><span class="sxs-lookup"><span data-stu-id="29493-124">(hour in 24 hour format), any day of the month, any month, on Saturdays.</span></span> <span data-ttu-id="29493-125">Il che significa che verrà eseguito il sabato alle 2:00.</span><span class="sxs-lookup"><span data-stu-id="29493-125">Meaning it will run Saturdays at 2:00 a.m.</span></span> <span data-ttu-id="29493-126">Pacifico (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="29493-126">Pacific (UTC –8).</span></span>

<span data-ttu-id="29493-127">Premere "Esc"</span><span class="sxs-lookup"><span data-stu-id="29493-127">Press “Esc”</span></span>

<span data-ttu-id="29493-128">Digitare ":wq" senza virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="29493-128">Type “:wq” without the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="29493-129">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="29493-129">w == write, q == quit</span></span>

<span data-ttu-id="29493-130">Per visualizzare i processi cron, digitare `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="29493-130">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

<span data-ttu-id="29493-132">**Per esaminare l'esecuzione dei processi cron**</span><span class="sxs-lookup"><span data-stu-id="29493-132">**To inspect cron job runs**</span></span>

`sudo grep mdatp /var/log/cron`

<span data-ttu-id="29493-133">**Per esaminare il mdatp_cron_job.log**</span><span class="sxs-lookup"><span data-stu-id="29493-133">**To inspect the mdatp_cron_job.log**</span></span>

`sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="29493-134">Per coloro che usano Ansible, Chef o Puppet</span><span class="sxs-lookup"><span data-stu-id="29493-134">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="29493-135">Utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="29493-135">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="29493-136">Per impostare i processi cron in Ansible</span><span class="sxs-lookup"><span data-stu-id="29493-136">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="29493-137">Per altre informazioni, vedere [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).</span><span class="sxs-lookup"><span data-stu-id="29493-137">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="29493-138">Per impostare i crontabs in Chef</span><span class="sxs-lookup"><span data-stu-id="29493-138">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="29493-139">Per altre informazioni, vedere [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).</span><span class="sxs-lookup"><span data-stu-id="29493-139">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="29493-140">Per impostare i processi cron in Puppet</span><span class="sxs-lookup"><span data-stu-id="29493-140">To set cron jobs in Puppet</span></span>
<span data-ttu-id="29493-141">Tipo di risorsa: cron</span><span class="sxs-lookup"><span data-stu-id="29493-141">Resource Type: cron</span></span>

<span data-ttu-id="29493-142">Per altre informazioni, vedere [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).</span><span class="sxs-lookup"><span data-stu-id="29493-142">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="29493-143">Automazione con Puppet: processi Cron e attività pianificate</span><span class="sxs-lookup"><span data-stu-id="29493-143">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="29493-144">Per altre informazioni, vedere [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).</span><span class="sxs-lookup"><span data-stu-id="29493-144">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="29493-145">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="29493-145">Additional information</span></span>

<span data-ttu-id="29493-146">**Per ottenere assistenza con crontab**</span><span class="sxs-lookup"><span data-stu-id="29493-146">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="29493-147">**Per ottenere un elenco di file crontab dell'utente corrente**</span><span class="sxs-lookup"><span data-stu-id="29493-147">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="29493-148">**Per ottenere un elenco di file crontab di un altro utente**</span><span class="sxs-lookup"><span data-stu-id="29493-148">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="29493-149">**Per eseguire il backup delle voci crontab**</span><span class="sxs-lookup"><span data-stu-id="29493-149">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="29493-150">Eseguire questa operazione prima di modificare o rimuovere.</span><span class="sxs-lookup"><span data-stu-id="29493-150">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="29493-151">**Per ripristinare le voci crontab**</span><span class="sxs-lookup"><span data-stu-id="29493-151">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="29493-152">**Per modificare la crontab e aggiungere un nuovo processo come utente radice**</span><span class="sxs-lookup"><span data-stu-id="29493-152">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="29493-153">**Per modificare la crontab e aggiungere un nuovo processo**</span><span class="sxs-lookup"><span data-stu-id="29493-153">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="29493-154">**Per modificare le voci crontab di altri utenti**</span><span class="sxs-lookup"><span data-stu-id="29493-154">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="29493-155">**Per rimuovere tutte le voci crontab**</span><span class="sxs-lookup"><span data-stu-id="29493-155">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="29493-156">**Per rimuovere le voci crontab di altri utenti**</span><span class="sxs-lookup"><span data-stu-id="29493-156">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="29493-157">**Spiegazione**</span><span class="sxs-lookup"><span data-stu-id="29493-157">**Explanation**</span></span>

<span data-ttu-id="29493-158">+—————- minuto (valori: 0 – 59) (caratteri speciali: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="29493-158">+—————- minute (values: 0 – 59) (special characters: , – \* /)</span></span>  <br>
<span data-ttu-id="29493-159">| +————- ora (valori: 0 – 23) (caratteri speciali: , – \* /)</span><span class="sxs-lookup"><span data-stu-id="29493-159">| +————- hour (values: 0 – 23) (special characters: , – \* /)</span></span> <br>
<span data-ttu-id="29493-160">| | +———- giorno del mese (valori: 1 – 31) (caratteri speciali: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="29493-160">| | +———- day of month (values: 1 – 31) (special characters: , – \* / L W C)</span></span>  <br>
<span data-ttu-id="29493-161">| | | +——- mese (valori: 1 – 12) (caratteri speciali: ,- \* / )</span><span class="sxs-lookup"><span data-stu-id="29493-161">| | | +——- month (values: 1 – 12) (special characters: ,- \* / )</span></span>  <br>
<span data-ttu-id="29493-162">| | | | +—- giorno della settimana (valori: 0 – 6) (Domenica=0 o 7) (caratteri speciali: , – \* / L W C)</span><span class="sxs-lookup"><span data-stu-id="29493-162">| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – \* / L W C)</span></span> <br>
<span data-ttu-id="29493-163">| | | | | comando\*\*\*\*\*da eseguire</span><span class="sxs-lookup"><span data-stu-id="29493-163">| | | | |\*\*\*\*\*command to be executed</span></span>


