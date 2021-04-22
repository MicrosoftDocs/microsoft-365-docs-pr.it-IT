---
title: Come pianificare un aggiornamento di Microsoft Defender for Endpoint (Linux)
description: Scopri come pianificare un aggiornamento di Microsoft Defender for Endpoint (Linux) per proteggere meglio le risorse dell'organizzazione.
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
ms.openlocfilehash: 22ff42cb399b3d07c0ebd8ec4f947352eb6f44aa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934766"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a><span data-ttu-id="53a51-104">Pianificare un aggiornamento di Microsoft Defender per Endpoint (Linux)</span><span class="sxs-lookup"><span data-stu-id="53a51-104">Schedule an update of the Microsoft Defender for Endpoint (Linux)</span></span>

<span data-ttu-id="53a51-105">Per eseguire un aggiornamento in Microsoft Defender for Endpoint su Linux, vedi [Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates)</span><span class="sxs-lookup"><span data-stu-id="53a51-105">To run an update on Microsoft Defender for Endpoint on Linux, see [Deploy updates for Microsoft Defender for Endpoint on Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-updates).</span></span>

<span data-ttu-id="53a51-106">Linux (e Unix) dispongono di uno strumento denominato **crontab** (simile all'Utilità di pianificazione) per poter eseguire attività pianificate.</span><span class="sxs-lookup"><span data-stu-id="53a51-106">Linux (and Unix) have a tool called **crontab** (similar to Task Scheduler) to be able to run scheduled tasks.</span></span>

## <a name="pre-requisite"></a><span data-ttu-id="53a51-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="53a51-107">Pre-requisite</span></span>

> [!NOTE]
> <span data-ttu-id="53a51-108">Per ottenere un elenco di tutti i fusi orari, eseguire il comando seguente: `timedatectl list-timezones`</span><span class="sxs-lookup"><span data-stu-id="53a51-108">To get a list of all the time zones, run the following command: `timedatectl list-timezones`</span></span><br>
> <span data-ttu-id="53a51-109">Esempi di fusi orario:</span><span class="sxs-lookup"><span data-stu-id="53a51-109">Examples for timezones:</span></span> <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a><span data-ttu-id="53a51-110">Per impostare il processo Cron</span><span class="sxs-lookup"><span data-stu-id="53a51-110">To set the Cron job</span></span>
<span data-ttu-id="53a51-111">Utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a51-111">Use the following commands:</span></span>

<span data-ttu-id="53a51-112">**Per eseguire il backup delle voci crontab**</span><span class="sxs-lookup"><span data-stu-id="53a51-112">**To backup crontab entries**</span></span>

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> <span data-ttu-id="53a51-113">Dove 201118 == AAMMDD</span><span class="sxs-lookup"><span data-stu-id="53a51-113">Where 201118 == YYMMDD</span></span>

> [!TIP]
> <span data-ttu-id="53a51-114">Eseguire questa operazione prima di modificare o rimuovere.</span><span class="sxs-lookup"><span data-stu-id="53a51-114">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="53a51-115">Per modificare la crontab e aggiungere un nuovo processo come utente radice:</span><span class="sxs-lookup"><span data-stu-id="53a51-115">To edit the crontab, and add a new job as a root user:</span></span> <br>
`sudo crontab -e`

> [!NOTE]
> <span data-ttu-id="53a51-116">L'editor predefinito è VIM.</span><span class="sxs-lookup"><span data-stu-id="53a51-116">The default editor is VIM.</span></span>

<span data-ttu-id="53a51-117">Potrebbe essere visualizzato:</span><span class="sxs-lookup"><span data-stu-id="53a51-117">You might see:</span></span>

<span data-ttu-id="53a51-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span><span class="sxs-lookup"><span data-stu-id="53a51-118">0\*\*\*\*/etc/opt/microsoft/mdatp/logrorate.sh</span></span>

<span data-ttu-id="53a51-119">E</span><span class="sxs-lookup"><span data-stu-id="53a51-119">And</span></span>

<span data-ttu-id="53a51-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span><span class="sxs-lookup"><span data-stu-id="53a51-120">02\*\*sat /bin/mdatp scan quick>~/mdatp_cron_job.log</span></span>

<span data-ttu-id="53a51-121">Vedere [Pianificare le analisi con Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span><span class="sxs-lookup"><span data-stu-id="53a51-121">See [Schedule scans with Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)</span></span>

<span data-ttu-id="53a51-122">Premere "Insert"</span><span class="sxs-lookup"><span data-stu-id="53a51-122">Press “Insert”</span></span>

<span data-ttu-id="53a51-123">Aggiungere le voci seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a51-123">Add the following entries:</span></span>

<span data-ttu-id="53a51-124">CRON_TZ=America/Los_Angeles</span><span class="sxs-lookup"><span data-stu-id="53a51-124">CRON_TZ=America/Los_Angeles</span></span>

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="53a51-125">! RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="53a51-125">!RHEL and variants (CentOS and Oracle Linux)</span></span>

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a><span data-ttu-id="53a51-126">! SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="53a51-126">!SLES and variants</span></span>

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a><span data-ttu-id="53a51-127">! Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="53a51-127">!Ubuntu and Debian systems</span></span>

`06**sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> <span data-ttu-id="53a51-128">Negli esempi precedenti, viene impostato su 00 minuti, alle 6.00 (ora in formato 24 ore), qualsiasi giorno del mese, qualsiasi mese, la domenica. [$(date + d) -le 15] == Non verrà eseguito a meno che non sia uguale o inferiore al \% 15° giorno (terza settimana).</span><span class="sxs-lookup"><span data-stu-id="53a51-128">In the examples above, we are setting it to 00 minutes, 6 a.m.(hour in 24 hour format), any day of the month, any month, on Sundays.[$(date +\%d) -le 15] == Won’t run unless it’s equal or less than the 15th day (3rd week).</span></span> <span data-ttu-id="53a51-129">Questo significa che verrà eseguito ogni 3 domeniche(7) del mese alle 6.00.</span><span class="sxs-lookup"><span data-stu-id="53a51-129">Meaning it will run every 3rd Sundays(7) of the month at 6:00 a.m.</span></span> <span data-ttu-id="53a51-130">Pacifico (UTC -8).</span><span class="sxs-lookup"><span data-stu-id="53a51-130">Pacific (UTC -8).</span></span>

<span data-ttu-id="53a51-131">Premere "Esc"</span><span class="sxs-lookup"><span data-stu-id="53a51-131">Press “Esc”</span></span>

<span data-ttu-id="53a51-132">Digitare ":wq" w/o le virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="53a51-132">Type “:wq” w/o the double quotes.</span></span>

> [!NOTE]
> <span data-ttu-id="53a51-133">w == write, q == quit</span><span class="sxs-lookup"><span data-stu-id="53a51-133">w == write, q == quit</span></span>

<span data-ttu-id="53a51-134">Per visualizzare i processi cron, digitare `sudo crontab -l`</span><span class="sxs-lookup"><span data-stu-id="53a51-134">To view your cron jobs, type `sudo crontab -l`</span></span>

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="aggiornare MDE linux":::

<span data-ttu-id="53a51-136">Per esaminare l'esecuzione del processo cron: `sudo grep mdatp /var/log/cron`</span><span class="sxs-lookup"><span data-stu-id="53a51-136">To inspect cron job runs: `sudo grep mdatp /var/log/cron`</span></span>

<span data-ttu-id="53a51-137">Per esaminare il mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span><span class="sxs-lookup"><span data-stu-id="53a51-137">To inspect the mdatp_cron_job.log `sudo nano mdatp_cron_job.log`</span></span>

## <a name="for-those-who-use-ansible-chef-or-puppet"></a><span data-ttu-id="53a51-138">Per coloro che usano Ansible, Chef o Puppet</span><span class="sxs-lookup"><span data-stu-id="53a51-138">For those who use Ansible, Chef, or Puppet</span></span>

<span data-ttu-id="53a51-139">Utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="53a51-139">Use the following commands:</span></span>
### <a name="to-set-cron-jobs-in-ansible"></a><span data-ttu-id="53a51-140">Per impostare i processi cron in Ansible</span><span class="sxs-lookup"><span data-stu-id="53a51-140">To set cron jobs in Ansible</span></span>

`cron – Manage cron.d and crontab entries`

<span data-ttu-id="53a51-141">Per altre informazioni, vedere [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).</span><span class="sxs-lookup"><span data-stu-id="53a51-141">See [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html) for more information.</span></span>

### <a name="to-set-crontabs-in-chef"></a><span data-ttu-id="53a51-142">Per impostare i crontabs in Chef</span><span class="sxs-lookup"><span data-stu-id="53a51-142">To set crontabs in Chef</span></span>
`cron resource`

<span data-ttu-id="53a51-143">Per altre informazioni, vedere [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).</span><span class="sxs-lookup"><span data-stu-id="53a51-143">See [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/) for more information.</span></span>

### <a name="to-set-cron-jobs-in-puppet"></a><span data-ttu-id="53a51-144">Per impostare i processi cron in Puppet</span><span class="sxs-lookup"><span data-stu-id="53a51-144">To set cron jobs in Puppet</span></span>
<span data-ttu-id="53a51-145">Tipo di risorsa: cron</span><span class="sxs-lookup"><span data-stu-id="53a51-145">Resource Type: cron</span></span>

<span data-ttu-id="53a51-146">Per altre informazioni, vedere [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).</span><span class="sxs-lookup"><span data-stu-id="53a51-146">See [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html) for more information.</span></span>

<span data-ttu-id="53a51-147">Automazione con Puppet: processi Cron e attività pianificate</span><span class="sxs-lookup"><span data-stu-id="53a51-147">Automating with Puppet: Cron jobs and scheduled tasks</span></span>

<span data-ttu-id="53a51-148">Per altre informazioni, vedere [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).</span><span class="sxs-lookup"><span data-stu-id="53a51-148">See [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/) for more information.</span></span>

## <a name="additional-information"></a><span data-ttu-id="53a51-149">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="53a51-149">Additional information</span></span>

<span data-ttu-id="53a51-150">**Per ottenere assistenza con crontab**</span><span class="sxs-lookup"><span data-stu-id="53a51-150">**To get help with crontab**</span></span>

`man crontab`

<span data-ttu-id="53a51-151">**Per ottenere un elenco di file crontab dell'utente corrente**</span><span class="sxs-lookup"><span data-stu-id="53a51-151">**To get a list of crontab file of the current user**</span></span>

`crontab -l`

<span data-ttu-id="53a51-152">**Per ottenere un elenco di file crontab di un altro utente**</span><span class="sxs-lookup"><span data-stu-id="53a51-152">**To get a list of crontab file of another user**</span></span>

`crontab -u username -l`

<span data-ttu-id="53a51-153">**Per eseguire il backup delle voci crontab**</span><span class="sxs-lookup"><span data-stu-id="53a51-153">**To backup crontab entries**</span></span>

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> <span data-ttu-id="53a51-154">Eseguire questa operazione prima di modificare o rimuovere.</span><span class="sxs-lookup"><span data-stu-id="53a51-154">Do this before you edit or remove.</span></span> <br>

<span data-ttu-id="53a51-155">**Per ripristinare le voci crontab**</span><span class="sxs-lookup"><span data-stu-id="53a51-155">**To restore crontab entries**</span></span>

`crontab /var/tmp/cron_backup.dat`

<span data-ttu-id="53a51-156">**Per modificare la crontab e aggiungere un nuovo processo come utente radice**</span><span class="sxs-lookup"><span data-stu-id="53a51-156">**To edit the crontab and add a new job as a root user**</span></span>

`sudo crontab -e`

<span data-ttu-id="53a51-157">**Per modificare la crontab e aggiungere un nuovo processo**</span><span class="sxs-lookup"><span data-stu-id="53a51-157">**To edit the crontab and add a new job**</span></span>

`crontab -e`

<span data-ttu-id="53a51-158">**Per modificare le voci crontab di altri utenti**</span><span class="sxs-lookup"><span data-stu-id="53a51-158">**To edit other user’s crontab entries**</span></span>

`crontab -u username -e`

<span data-ttu-id="53a51-159">**Per rimuovere tutte le voci crontab**</span><span class="sxs-lookup"><span data-stu-id="53a51-159">**To remove all crontab entries**</span></span>

`crontab -r`

<span data-ttu-id="53a51-160">**Per rimuovere le voci crontab di altri utenti**</span><span class="sxs-lookup"><span data-stu-id="53a51-160">**To remove other user’s crontab entries**</span></span>

`crontab -u username -r`

<span data-ttu-id="53a51-161">**Spiegazione**</span><span class="sxs-lookup"><span data-stu-id="53a51-161">**Explanation**</span></span>

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

