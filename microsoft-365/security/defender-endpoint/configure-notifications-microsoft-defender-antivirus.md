---
title: Configurare Antivirus Microsoft Defender notifiche
description: Informazioni su come configurare e personalizzare le notifiche standard e Antivirus Microsoft Defender notifiche sugli endpoint.
keywords: notifiche, difensore, antivirus, endpoint, gestione, amministratore
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572346"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configurare le notifiche visualizzate negli endpoint

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In Windows 10, le notifiche delle applicazioni sul rilevamento e la correzione del malware sono più robuste, coerenti e concise.

Le notifiche vengono visualizzate sugli endpoint quando vengono completate le scansioni attivate manualmente e pianificate e vengono rilevate minacce. Queste notifiche vengono visualizzate anche nel **Centro notifiche e** viene visualizzato un riepilogo delle scansioni e dei rilevamenti delle minacce a intervalli di tempo regolari.

È inoltre possibile configurare la modalità di vengono visualizzate le notifiche standard sugli endpoint, ad esempio le notifiche per il riavvio o quando una minaccia è stata rilevata e riparato.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configurare le notifiche aggiuntive visualizzate negli endpoint

È possibile configurare la visualizzazione di notifiche aggiuntive, ad esempio riepiloghi recenti del rilevamento delle minacce, [nell'app Sicurezza di Windows e](microsoft-defender-security-center-antivirus.md) con Criteri di gruppo.

> [!NOTE]
> In Windows 10, la versione 1607 della funzionalità era denominata **Notifiche avanzate** e poteva essere **configurata in Windows Impostazioni** Update &  >  **security**  >  **Windows Defender**. Nelle impostazioni di Criteri di gruppo in tutte le Windows 10 di controllo, viene denominato **Notifiche avanzate**.

> [!IMPORTANT]
> La disattivazione di notifiche aggiuntive non disattiva le notifiche critiche, ad esempio gli avvisi di rilevamento e correzione delle minacce.

**Usa l'app Sicurezza di Windows per disabilitare notifiche aggiuntive:**

1. Aprire l Sicurezza di Windows applicazione facendo clic sull'icona scudo nella barra delle applicazioni o cercando sicurezza nel menu **di avvio**.

2. Selezionare **Virus & protezione dalle minacce** (o l'icona scudo sulla barra dei menu sinistra) e quindi selezionare Impostazioni di protezione da virus & **minaccia**

3. Scorrere fino alla sezione **Notifiche** e fare clic su **Modifica impostazioni notifica**.

4. Passare a Disattivato **o** Attiva **per disabilitare** o abilitare notifiche aggiuntive.

**Utilizzare Criteri di gruppo per disabilitare notifiche aggiuntive:**

1. Nel computer di gestione Criteri di gruppo aprire Console Gestione Criteri di gruppo , [fare clic con](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere la struttura ad **albero per Windows componenti > Antivirus Microsoft Defender > Reporting**.

5. Fare doppio clic **su Disattiva notifiche avanzate e** impostare l'opzione su **Abilitato**. Fare clic su **OK**. Ciò impedirà la visualizzazione di notifiche aggiuntive.

## <a name="configure-standard-notifications-on-endpoints"></a>Configurare le notifiche standard sugli endpoint

È possibile utilizzare Criteri di gruppo per:

- Visualizzare testo aggiuntivo e personalizzato sugli endpoint quando l'utente deve eseguire un'azione
- Nascondere tutte le notifiche sugli endpoint
- Nascondere le notifiche di riavvio sugli endpoint

Nascondere le notifiche può essere utile in situazioni in cui non è possibile nascondere l'intera Antivirus Microsoft Defender interfaccia. Per [ulteriori informazioni, vedere Impedire agli utenti di visualizzare o interagire con Antivirus Microsoft Defender'interfaccia](prevent-end-user-interaction-microsoft-defender-antivirus.md) utente di windows. 

> [!NOTE]
> L'occultamento delle notifiche si verificherà solo negli endpoint in cui il criterio è stato distribuito. Le notifiche relative alle azioni che devono essere intraprese (ad esempio un riavvio) verranno comunque visualizzate nel [dashboard di Microsoft Endpoint Manager Endpoint Protection di monitoraggio e nei report](/configmgr/protect/deploy-use/monitor-endpoint-protection). 

Per istruzioni su come aggiungere informazioni di contatto personalizzate alle notifiche visualizzate dagli utenti nei computer, vedere Personalizzare [l'app Sicurezza di Windows'organizzazione.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

**Usare Criteri di gruppo per nascondere le notifiche:**

1. Nel computer di gestione Criteri di gruppo aprire Console Gestione [Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo passare** a Configurazione computer **e** fare clic su **Modelli amministrativi**.

3. Espandere la struttura ad **albero per Windows componenti > Antivirus Microsoft Defender > interfaccia client**. 

4. Fare doppio clic su **Elimina tutte le notifiche** e impostare l'opzione su **Abilitato**. Fare clic su **OK**. Ciò impedirà la visualizzazione di notifiche aggiuntive.

**Utilizzare Criteri di gruppo per nascondere le notifiche di riavvio:**

1. Nel computer di gestione Criteri di gruppo aprire Console Gestione Criteri di gruppo , [fare clic con](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere la struttura ad **albero per Windows componenti > Antivirus Microsoft Defender > interfaccia client**.

5. Fare doppio clic su **Elimina notifiche di riavvio e** impostare l'opzione su **Abilitato**. Fare clic su **OK**. Ciò impedirà la visualizzazione di notifiche aggiuntive.

## <a name="related-topics"></a>Argomenti correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurare l'interazione dell'utente finale con Antivirus Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)
