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
ms.openlocfilehash: 7ebb37e80cae0e9dd70d01600c47bd1459c122c3
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194902"
---
# <a name="schedule-an-update-of-the-microsoft-defender-for-endpoint-linux"></a>Pianificare un aggiornamento di Microsoft Defender per Endpoint (Linux)

Per eseguire un aggiornamento in Microsoft Defender for Endpoint su Linux, vedi [Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux.](/microsoft-365/security/defender-endpoint/linux-updates)

Linux (e Unix) dispongono di uno strumento denominato **crontab** (simile all'Utilità di pianificazione) per poter eseguire attività pianificate.

## <a name="pre-requisite"></a>Prerequisiti

> [!NOTE]
> Per ottenere un elenco di tutti i fusi orari, eseguire il comando seguente: `timedatectl list-timezones`<br>
> Esempi di fusi orario: <br>
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Per impostare il processo Cron
Utilizzare i comandi seguenti:

**Per eseguire il backup delle voci crontab**

`sudo crontab -l > /var/tmp/cron_backup_201118.dat`

> [!NOTE]
> Dove 201118 == AAMMDD

> [!TIP]
> Eseguire questa operazione prima di modificare o rimuovere. <br>

Per modificare la crontab e aggiungere un nuovo processo come utente radice: <br>
`sudo crontab -e`

> [!NOTE]
> L'editor predefinito è VIM.

Potrebbe essere visualizzato:

0****/etc/opt/microsoft/mdatp/logrorate.sh

E

02**sat /bin/mdatp scan quick>~/mdatp_cron_job.log

Vedere [Pianificare le analisi con Microsoft Defender for Endpoint (Linux)](linux-schedule-scan-atp.md)

Premere "Insert"

Aggiungere le voci seguenti:

CRON_TZ=America/Los_Angeles

> #<a name="rhel-and-variants-centos-and-oracle-linux"></a>! RHEL e varianti (CentOS e Oracle Linux)

`06**sun[$(date +\%d) -le 15] sudo yum update mdatp>>~/mdatp_cron_job.log`

> #<a name="sles-and-variants"></a>! SLES e varianti

`06**sun[$(date +\%d) -le 15] sudo zypper update mdatp>>~/mdatp_cron_job.log`

> #<a name="ubuntu-and-debian-systems"></a>! Sistemi Ubuntu e Debian

`0 6 * * sun [$(date +\%d) -le 15] sudo apt-get install --only-upgrade mdatp>>~/mdatp_cron_job.log`

> [!NOTE]
> Negli esempi precedenti, viene impostato su 00 minuti, alle 6.00 (ora in formato 24 ore), qualsiasi giorno del mese, qualsiasi mese, la domenica. [$(date + d) -le 15] == Non verrà eseguito a meno che non sia uguale o inferiore al \% 15° giorno (terza settimana). Questo significa che verrà eseguito ogni 3 domeniche(7) del mese alle 6.00. Pacifico (UTC -8).

Premere "Esc"

Digitare ":wq" w/o le virgolette doppie.

> [!NOTE]
> w == write, q == quit

Per visualizzare i processi cron, digitare `sudo crontab -l`

:::image type="content" source="images/update-MDE-linux-4634577.jpg" alt-text="aggiornare Defender per Endpoint su Linux":::

Per esaminare l'esecuzione del processo cron: `sudo grep mdatp /var/log/cron`

Per esaminare il mdatp_cron_job.log `sudo nano mdatp_cron_job.log`

## <a name="for-those-who-use-ansible-chef-or-puppet"></a>Per coloro che usano Ansible, Chef o Puppet

Utilizzare i comandi seguenti:
### <a name="to-set-cron-jobs-in-ansible"></a>Per impostare i processi cron in Ansible

`cron – Manage cron.d and crontab entries`

Per altre informazioni, vedere [https://docs.ansible.com/ansible/latest/modules/cron_module.html](https://docs.ansible.com/ansible/latest/modules/cron_module.html).

### <a name="to-set-crontabs-in-chef"></a>Per impostare i crontabs in Chef
`cron resource`

Per altre informazioni, vedere [https://docs.chef.io/resources/cron/](https://docs.chef.io/resources/cron/).

### <a name="to-set-cron-jobs-in-puppet"></a>Per impostare i processi cron in Puppet
Tipo di risorsa: cron

Per altre informazioni, vedere [https://puppet.com/docs/puppet/5.5/types/cron.html](https://puppet.com/docs/puppet/5.5/types/cron.html).

Automazione con Puppet: processi Cron e attività pianificate

Per altre informazioni, vedere [https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/](https://puppet.com/blog/automating-puppet-cron-jobs-and-scheduled-tasks/).

## <a name="additional-information"></a>Informazioni aggiuntive

**Per ottenere assistenza con crontab**

`man crontab`

**Per ottenere un elenco di file crontab dell'utente corrente**

`crontab -l`

**Per ottenere un elenco di file crontab di un altro utente**

`crontab -u username -l`

**Per eseguire il backup delle voci crontab**

`crontab -l > /var/tmp/cron_backup.dat`

> [!TIP]
> Eseguire questa operazione prima di modificare o rimuovere. <br>

**Per ripristinare le voci crontab**

`crontab /var/tmp/cron_backup.dat`

**Per modificare la crontab e aggiungere un nuovo processo come utente radice**

`sudo crontab -e`

**Per modificare la crontab e aggiungere un nuovo processo**

`crontab -e`

**Per modificare le voci crontab di altri utenti**

`crontab -u username -e`

**Per rimuovere tutte le voci crontab**

`crontab -r`

**Per rimuovere le voci crontab di altri utenti**

`crontab -u username -r`

**Spiegazione**

<pre>
+—————- minute (values: 0 – 59) (special characters: , – * /)  <br>
| +————- hour (values: 0 – 23) (special characters: , – * /) <br>
| | +———- day of month (values: 1 – 31) (special characters: , – * / L W C)  <br>
| | | +——- month (values: 1 – 12) (special characters: ,- * / )  <br>
| | | | +—- day of week (values: 0 – 6) (Sunday=0 or 7) (special characters: , – * / L W C) <br>
| | | | |*****command to be executed
</pre>

