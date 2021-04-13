---
title: Da McAfee a Microsoft Defender for Endpoint - Preparare
description: Questa è la fase 1, Preparare, per la migrazione da McAfee a Microsoft Defender ATP.
keywords: migrazione, windows defender advanced threat protection, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 049539cc5c19d3c6683815d0da949c2a3de10f93
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687794"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>Eseguire la migrazione da McAfee - Fase 1: preparare la migrazione

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: preparazione](images/phase-diagrams/prepare.png)<br/>Fase 1: preparazione |[![Fase 2: configurazione](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: configurazione](mcafee-to-microsoft-defender-setup.md) |[![Phase 3: onboarding](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Fase 3: onboarding](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*Sei qui!*| | |


**Benvenuti nella fase di preparazione della [migrazione da McAfee Endpoint Security (McAfee) a Microsoft Defender for Endpoint.](mcafee-to-microsoft-defender-migration.md#the-migration-process)** 

Questa fase di migrazione include i passaggi seguenti:
1. [Ottenere e distribuire gli aggiornamenti nei dispositivi dell'organizzazione](#get-and-deploy-updates-across-your-organizations-devices)
2. [Ottenere Microsoft Defender per Endpoint](#get-microsoft-defender-for-endpoint).
3. [Concedere l'accesso a Microsoft Defender Security Center.](#grant-access-to-the-microsoft-defender-security-center)
4. [Configurare le impostazioni di connettività Internet e proxy del dispositivo](#configure-device-proxy-and-internet-connectivity-settings).

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Ottenere e distribuire gli aggiornamenti nei dispositivi dell'organizzazione

Come procedura consigliata, mantenere aggiornati i dispositivi e gli endpoint dell'organizzazione. Assicurati che la soluzione McAfee Endpoint Security (McAfee) sia aggiornata e che i sistemi operativi e le app dell'organizzazione siano aggiornati. Questa operazione può aiutare a prevenire i problemi in un secondo momento durante la migrazione a Microsoft Defender per Endpoint e Microsoft Defender Antivirus.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>Verificare che la soluzione McAfee sia aggiornata

Mantenere McAfee aggiornato e assicurarsi che nei dispositivi dell'organizzazione siano disponibili gli aggiornamenti della sicurezza più recenti. Hai bisogno di assistenza? Ecco alcune risorse McAfee:

- [Documentazione del prodotto McAfee Enterprise: Funzionamento di Endpoint Security](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [Articolo tecnico mcAfee Knowledge Center: Centro sicurezza Windows segnala in modo errato che Endpoint Security è disabilitato durante l'esecuzione in Windows 10](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [Articolo tecnico mcAfee Knowledge Center: Windows Security Center segnala che Endpoint Security è disabilitato quando Endpoint Security è in esecuzione](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- McAfee supporta ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Verificare che i dispositivi dell'organizzazione siano aggiornati

Serve assistenza per l'aggiornamento dei dispositivi dell'organizzazione? Vedere le risorse seguenti:

|Sistema operativo | Risorsa |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Come aggiornare il software sul Mac](https://support.apple.com/HT201541)|
|iOS |[Aggiornare l'iPhone, l'iPad o l'iPod touch](https://support.apple.com/HT204204)|
|Android |[Controlla & la versione android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: Aggiornamento del sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Ottenere Microsoft Defender per Endpoint

Dopo aver aggiornato i dispositivi dell'organizzazione, il passaggio successivo consiste nel ottenere Microsoft Defender for Endpoint, assegnare licenze e verificare che il provisioning del servizio sia stato eseguito.

1. Acquista o prova Microsoft Defender for Endpoint oggi stesso. [Avviare una versione di valutazione gratuita o richiedere un preventivo.](https://aka.ms/mdatp) 

2. Verificare che il provisioning delle licenze sia stato eseguito correttamente. [Controllare lo stato della licenza](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).

3. In quanto amministratore globale o amministratore della sicurezza, configura l'istanza cloud dedicata di Microsoft Defender per Endpoint. Vedere [Microsoft Defender for Endpoint setup: Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).

4. Se gli endpoint (ad esempio i dispositivi) nell'organizzazione usano un proxy per accedere a Internet, vedi Configurazione di rete di [Microsoft Defender for Endpoint.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)
 
A questo punto, si è pronti a concedere l'accesso agli amministratori della sicurezza e agli operatori di sicurezza che utilizzeranno Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> Microsoft Defender Security Center viene talvolta definito portale di Microsoft Defender for Endpoint. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Concedere l'accesso a Microsoft Defender Security Center

Microsoft Defender Security Center ( ) consente di accedere e configurare funzionalità di [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender per Endpoint. Per altre informazioni, vedi [Panoramica di Microsoft Defender Security Center.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

Le autorizzazioni per Microsoft Defender Security Center possono essere concesse utilizzando le autorizzazioni di base o il controllo di accesso basato sui ruoli(RBAC). È consigliabile usare RBAC in modo da avere un controllo più granulare sulle autorizzazioni.

1. Pianificare i ruoli e le autorizzazioni per gli amministratori della sicurezza e gli operatori di sicurezza. Vedere [Controllo dell'accesso basato sui ruoli](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).

2. Configurare e configurare il controllo degli accessi in base al ruolo. Ti consigliamo di [usare Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) per configurare RBAC, soprattutto se l'organizzazione usa una combinazione di dispositivi Windows 10, macOS, iOS e Android. Vedi [configurare RBAC con Intune.](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control)

    Se l'organizzazione richiede un metodo diverso da Intune, scegliere una delle opzioni seguenti:
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Gestion avancée des stratégies de groupe](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. Concedere l'accesso a Microsoft Defender Security Center. (Serve assistenza? Vedere [Manage portal access using RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurare le impostazioni di connettività Internet e proxy del dispositivo

Per abilitare la comunicazione tra i dispositivi e Microsoft Defender for Endpoint, configura le impostazioni proxy e Internet. Nella tabella seguente sono inclusi i collegamenti alle risorse che è possibile utilizzare per configurare le impostazioni proxy e Internet per diversi sistemi operativi e funzionalità:

|Funzionalità  | Sistema operativo | Risorse |
|--|--|--|
|[Rilevamento e risposta degli endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o versione successiva](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurare le impostazioni di connettività Internet e proxy del computer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configurare le impostazioni di connettività Proxy e Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)  |[Microsoft Defender for Endpoint in macOS: Connessioni di rete](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o versione successiva](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurare e convalidare le connessioni di rete di Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivirus |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra) |[Microsoft Defender for Endpoint in macOS: Connessioni di rete](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender per Endpoint su Linux: connessioni di rete](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a>Passaggio successivo

**Congratulazioni**! Hai completato la **fase di preparazione** della migrazione da [McAfee a Microsoft Defender for Endpoint!](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Procedere alla configurazione di Microsoft Defender per Endpoint.](mcafee-to-microsoft-defender-setup.md)
