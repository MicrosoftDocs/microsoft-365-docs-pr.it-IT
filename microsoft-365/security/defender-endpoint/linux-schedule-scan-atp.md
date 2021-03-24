---
title: Come pianificare le analisi con Microsoft Defender for Endpoint (Linux)
description: Scopri come pianificare un tempo di analisi automatica per Microsoft Defender for Endpoint (Linux) per proteggere meglio le risorse dell'organizzazione.
keywords: microsoft, defender, atp, linux, scansioni, antivirus, microsoft defender for endpoint (linux)
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
ms.openlocfilehash: d3f5d4c490e28c7985a0420fa5013a8e0f51a167
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065722"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-linux"></a>Pianificare le analisi con Microsoft Defender for Endpoint (Linux)

Per eseguire un'analisi per Linux, vedi [Comandi supportati.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-resources#supported-commands)

Linux (e Unix) dispongono di uno strumento denominato **crontab** (simile all'Utilità di pianificazione) per poter eseguire attività pianificate.

## <a name="pre-requisite"></a>Prerequisiti

> [!NOTE]
> Per ottenere un elenco di tutti i fusi orari, eseguire il comando seguente: `timedatectl list-timezones`<br>
> Esempi di fusi orario:
> - `America/Los_Angeles`
> - `America/New_York`
> - `America/Chicago`
> - `America/Denver`

## <a name="to-set-the-cron-job"></a>Per impostare il processo Cron
Utilizzare i comandi seguenti:

**Per eseguire il backup delle voci crontab**

`sudo crontab -l > /var/tmp/cron_backup_200919.dat`

> [!NOTE]
> Dove 200919 == YRMMDD

> [!TIP]
> Eseguire questa operazione prima di modificare o rimuovere. <br>

Per modificare la crontab e aggiungere un nuovo processo come utente radice: <br>
`sudo crontab -e`

> [!NOTE]
> L'editor predefinito è VIM.

Potrebbe essere visualizzato:

0 * * * * /etc/opt/microsoft/mdatp/logrorate.sh

Premere "Insert"

Aggiungere le voci seguenti:

CRON_TZ=America/Los_Angeles

0 2 * * sat /bin/mdatp scan quick > ~/mdatp_cron_job.log

> [!NOTE]
>In questo esempio è stato impostato su 00 minuti, 2:00. (ora in formato 24 ore), qualsiasi giorno del mese, qualsiasi mese, il sabato. Il che significa che verrà eseguito il sabato alle 2:00. Pacifico (UTC -8).

Premere "Esc"

Digitare ":wq" senza virgolette doppie.

> [!NOTE]
> w == write, q == quit

Per visualizzare i processi cron, digitare `sudo crontab -l`

:::image type="content" source="/microsoft-365/security/defender-endpoint/images/linux-mdatp-1" alt-text="linux mdatp":::

**Per esaminare l'esecuzione dei processi cron**

`sudo grep mdatp /var/log/cron`

**Per esaminare il mdatp_cron_job.log**

`sudo nano mdatp_cron_job.log`

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

+—————- minuto (valori: 0 – 59) (caratteri speciali: , – * /)  <br>
| +————- ora (valori: 0 – 23) (caratteri speciali: , – * /) <br>
| | +———- giorno del mese (valori: 1 – 31) (caratteri speciali: , – * / L W C)  <br>
| | | +——- mese (valori: 1 – 12) (caratteri speciali: ,- * / )  <br>
| | | | +—- giorno della settimana (valori: 0 – 6) (Domenica=0 o 7) (caratteri speciali: , – * / L W C) <br>
| | | | | comando*****da eseguire


