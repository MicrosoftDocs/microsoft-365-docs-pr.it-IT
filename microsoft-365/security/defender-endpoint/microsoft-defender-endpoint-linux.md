---
title: Microsoft Defender per Endpoint su Linux
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender per Endpoint in Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0e09a313b512135785050abd5aa61bb9576ce1d8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274941"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender per Endpoint su Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Questo argomento descrive come installare, configurare, aggiornare e usare Microsoft Defender per Endpoint in Linux.

> [!CAUTION]
> L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Microsoft Defender for Endpoint su Linux può causare problemi di prestazioni ed effetti collaterali imprevedibili. Se la protezione degli endpoint non Microsoft è un requisito assoluto nell'ambiente, puoi comunque sfruttare in modo sicuro la funzionalità Defender for Endpoint in Linux EDR dopo aver configurato la funzionalità antivirus per l'esecuzione in [modalità passiva.](linux-preferences.md#enable--disable-passive-mode)

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a>Come installare Microsoft Defender per Endpoint in Linux

### <a name="prerequisites"></a>Prerequisiti

- Accesso al Microsoft Defender Security Center portale
- Distribuzione Linux con [systemd](https://systemd.io/) system manager
- Esperienza a livello di principiante in script Linux e BASH
- Privilegi amministrativi nel dispositivo (in caso di distribuzione manuale)

> [!NOTE]
>  Microsoft Defender per l'agente Endpoint su Linux è indipendente [dall'agente OMS.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent) Microsoft Defender for Endpoint si basa sulla propria pipeline di telemetria indipendente.
> 
> Microsoft Defender per Endpoint su Linux non è ancora integrato nel Centro sicurezza di Azure.



### <a name="installation-instructions"></a>Istruzioni di installazione

Esistono diversi metodi e strumenti di distribuzione che puoi usare per installare e configurare Microsoft Defender per Endpoint in Linux.

In generale, è necessario eseguire la procedura seguente:

- Assicurati di avere un abbonamento a Microsoft Defender for Endpoint e di avere accesso al [portale di Microsoft Defender for Endpoint.](microsoft-defender-security-center.md)
- Distribuire Microsoft Defender per Endpoint su Linux usando uno dei metodi di distribuzione seguenti:
  - Lo strumento da riga di comando:
    - [Distribuzione manuale](linux-install-manually.md)
  - Strumenti di gestione di terze parti:
    - [Distribuire con lo strumento di gestione della configurazione di Puppet](linux-install-with-puppet.md)
    - [Distribuire con lo strumento di gestione della configurazione di Ansible](linux-install-with-ansible.md)

Se si verificano errori di installazione, fare riferimento a Risoluzione dei problemi di installazione [in Microsoft Defender per Endpoint su Linux.](linux-support-install.md)



### <a name="system-requirements"></a>Requisiti di sistema

- Distribuzioni e versioni supportate del server Linux:

  - Red Hat Enterprise Linux 7.2 o versione successiva
  - CentOS 7.2 o versione successiva
  - Ubuntu 16,04 LTS o superiore
  - Debian 9 o versione successiva
  - SUSE Linux Enterprise Server 12 o versione successiva
  - Oracle Linux 7.2 o versione successiva

    > [!NOTE]
    > Le distribuzioni e le versioni non elencate in modo esplicito non sono supportate (anche se derivano dalle distribuzioni ufficialmente supportate).


- Versione kernel minima 3.10.0-327

- `fanotify`L'opzione kernel deve essere abilitata

  > [!CAUTION]
  > L'esecuzione di Defender per Endpoint su Linux affiancata ad altre soluzioni di sicurezza basate su base non `fanotify` è supportata. Può portare a risultati imprevedibili, tra cui l'sospensione del sistema operativo.

- Spazio su disco: 1 GB

- /opt/microsoft/mdatp/sbin/wdavdaemon richiede l'autorizzazione eseguibile. Per ulteriori informazioni, vedere "Verificare che il daemon abbia l'autorizzazione eseguibile" in Risolvere i problemi di installazione di [Microsoft Defender per Endpoint su Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)

- Memoria: 1 GB

    > [!NOTE]
    > Assicurati di avere spazio libero su disco in /var.

- La soluzione attualmente offre protezione in tempo reale per i tipi di file system seguenti:

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni in uscita tra il servizio e gli endpoint.

- Il framework di controllo ( `auditd` ) deve essere abilitato.
  > [!NOTE]
  > Gli eventi di sistema acquisiti dalle regole aggiunte a verranno aggiunti a (s) e potrebbero influire sul controllo `/etc/audit/rules.d/` `audit.log` dell'host e sulla raccolta a monte. Gli eventi aggiunti da Microsoft Defender per Endpoint su Linux saranno contrassegnati con `mdatp` la chiave.

### <a name="network-connections"></a>Connessioni di rete

Nel seguente foglio di calcolo scaricabile sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi. È consigliabile assicurarsi che non siano presenti regole di filtro di rete o firewall che negherebbero l'accesso a questi URL. In caso contrario, potrebbe essere necessario creare una regola *di* autorizzazione specifica per loro.

| Foglio di calcolo dell'elenco dei domini | Descrizione |
|:-----|:-----|
|![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/>  | Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo. <br><br>[Scaricare il foglio di calcolo qui.](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> Per un elenco di URL più specifico, vedere [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).

Defender for Endpoint può individuare un server proxy utilizzando i metodi di individuazione seguenti:
- Proxy trasparente
- Configurazione manuale del proxy statico

Se un proxy o un firewall blocca il traffico anonimo, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza. Per i proxy trasparenti, non è necessaria alcuna configurazione aggiuntiva per Defender per Endpoint. Per il proxy statico, seguire i passaggi descritti in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).

> [!WARNING]
> PAC, WPAD e proxy autenticati non sono supportati. Verificare che sia in uso solo un proxy statico o trasparente.
>
> Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza. Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Defender per Endpoint su Linux agli URL rilevanti senza intercettazione. L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.

Per la procedura di risoluzione dei problemi, vedi Risolvere i problemi [di connettività cloud per Microsoft Defender per Endpoint su Linux.](linux-support-connectivity.md)

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a>Come aggiornare Microsoft Defender per Endpoint su Linux

Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità. Per aggiornare Microsoft Defender per Endpoint su Linux, fare riferimento [a Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux.](linux-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a>Come configurare Microsoft Defender per Endpoint su Linux

Le indicazioni su come configurare il prodotto in ambienti aziendali sono disponibili in Impostare le preferenze [per Microsoft Defender per Endpoint su Linux.](linux-preferences.md)

## <a name="resources"></a>Risorse

- Per ulteriori informazioni sulla registrazione, la disinstallazione o altri argomenti, vedere [Resources](linux-resources.md).
