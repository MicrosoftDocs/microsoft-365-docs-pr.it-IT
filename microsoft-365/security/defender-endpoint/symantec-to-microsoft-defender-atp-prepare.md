---
title: Da Symantec a Microsoft Defender per endpoint - Fase 1, Preparazione
description: Questa è la fase 1, Preparare, della migrazione da Symantec a Microsoft Defender per Endpoint.
keywords: migrazione, Microsoft Defender for Endpoint, edr
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: bba48803863cd330b371c24600239462b1ca9250
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327415"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Eseguire la migrazione da Symantec - Fase 1: preparare la migrazione

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: preparazione](images/phase-diagrams/prepare.png)<br/>Fase 1: preparazione |[![Fase 2: configurazione](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: configurazione](symantec-to-microsoft-defender-atp-setup.md) |[![Phase 3: onboarding](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: onboarding](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*Sei qui!*| | |


**Benvenuti nella fase di preparazione della [migrazione da Symantec a Microsoft Defender for Endpoint.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** 

Questa fase di migrazione include i passaggi seguenti:
1. [Ottenere Microsoft Defender per Endpoint](#get-microsoft-defender-for-endpoint).
2. [Concedere l'accesso a Microsoft Defender Security Center.](#grant-access-to-the-microsoft-defender-security-center)
3. [Configurare le impostazioni di connettività Internet e proxy del dispositivo](#configure-device-proxy-and-internet-connectivity-settings).

## <a name="get-microsoft-defender-for-endpoint"></a>Ottenere Microsoft Defender per Endpoint

Per iniziare, devi disporre di Microsoft Defender per Endpoint, con le licenze assegnate e di cui è stato eseguito il provisioning.

1. Acquista o prova Microsoft Defender for Endpoint oggi stesso. [Visita Microsoft Defender for Endpoint per avviare una versione di valutazione gratuita o richiedere un preventivo.](https://aka.ms/mdatp) 
2. Verificare che il provisioning delle licenze sia stato eseguito correttamente. [Controllare lo stato della licenza](production-deployment.md#check-license-state).
3. In quanto amministratore globale o amministratore della sicurezza, configura l'istanza cloud dedicata di Microsoft Defender per Endpoint. Vedere [Microsoft Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).
4. Se gli endpoint (ad esempio i dispositivi) nell'organizzazione usano un proxy per accedere a Internet, vedi Configurazione di rete di [Microsoft Defender for Endpoint.](production-deployment.md#network-configuration)
 
A questo punto, si è pronti a concedere l'accesso agli amministratori della sicurezza e agli operatori di sicurezza che utilizzeranno Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> Microsoft Defender Security Center viene talvolta definito portale di Microsoft Defender for Endpoint. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Concedere l'accesso a Microsoft Defender Security Center

Microsoft Defender Security Center ( ) consente di accedere e configurare funzionalità di [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) Microsoft Defender per Endpoint. Per altre informazioni, vedi [Panoramica di Microsoft Defender Security Center.](use.md)

Le autorizzazioni per Microsoft Defender Security Center possono essere concesse utilizzando le autorizzazioni di base o il controllo di accesso basato sui ruoli(RBAC). È consigliabile usare RBAC in modo da avere un controllo più granulare sulle autorizzazioni.

1. Pianificare i ruoli e le autorizzazioni per gli amministratori della sicurezza e gli operatori di sicurezza. Vedere [Controllo dell'accesso basato sui ruoli](prepare-deployment.md#role-based-access-control).
2. Configurare e configurare il controllo degli accessi in base al ruolo. Ti consigliamo di [usare Intune](/mem/intune/fundamentals/what-is-intune) per configurare RBAC, soprattutto se l'organizzazione usa una combinazione di dispositivi Windows 10, macOS, iOS e Android. Vedi [configurare RBAC con Intune.](/mem/intune/fundamentals/role-based-access-control)<br/>
   Se l'organizzazione richiede un metodo diverso da Intune, scegliere una delle opzioni seguenti:
    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Gestion avancée des stratégies de groupe](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Admin Center](/windows-server/manage/windows-admin-center/overview)
3. Concedere l'accesso a Microsoft Defender Security Center. (Serve assistenza? Vedere [Manage portal access using RBAC](rbac.md).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurare le impostazioni di connettività Internet e proxy del dispositivo

Per abilitare la comunicazione tra i dispositivi e Microsoft Defender for Endpoint, configura le impostazioni proxy e Internet. Nella tabella seguente sono inclusi i collegamenti alle risorse che è possibile utilizzare per configurare le impostazioni proxy e Internet per diversi sistemi operativi e funzionalità:

|Funzionalità  | Sistema operativo | Risorse |
|:----|:----|:---|
|[Rilevamento e risposta degli endpoint](overview-endpoint-detection-response.md) (EDR) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o versione successiva](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurare le impostazioni di connettività Internet e proxy del computer](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configurare le impostazioni di connettività Proxy e Internet](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (High Sierra)  |[Microsoft Defender for Endpoint in macOS: Connessioni di rete](microsoft-defender-endpoint-mac.md#network-connections) |
|[Antivirus Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o versione successiva](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurare e convalidare le connessioni di rete di Windows Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Antivirus |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)  |[Microsoft Defender per Endpoint su Mac: connessioni di rete](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o superiore<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender per Endpoint su Linux: connessioni di rete](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>Passaggio successivo

**Congratulazioni**! Hai completato la **fase di preparazione** della migrazione da [Symantec a Microsoft Defender per Endpoint!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Procedere alla configurazione di Microsoft Defender per Endpoint.](symantec-to-microsoft-defender-atp-setup.md)
