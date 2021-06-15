---
title: Configurare Antivirus Microsoft Defender notifiche
description: Informazioni su come configurare e personalizzare le notifiche Antivirus Microsoft Defender standard e aggiuntive sugli endpoint.
keywords: notifiche, defender, antivirus, endpoint, gestione, amministratore
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926239"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configurare le notifiche che vengono visualizzate negli endpoint

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In Windows 10, le notifiche delle applicazioni relative al rilevamento e alla correzione di malware sono più affidabili, coerenti e concise.

Le notifiche vengono visualizzate sugli endpoint quando vengono completate analisi attivate manualmente e pianificate e vengono rilevate minacce. Queste notifiche vengono visualizzate anche nel **Centro notifiche** e un riepilogo delle analisi e dei rilevamenti delle minacce viene visualizzato a intervalli di tempo regolari.

Puoi anche configurare la modalità di visualizzazione delle notifiche standard sugli endpoint, ad esempio le notifiche per il riavvio o quando è stata rilevata e corretti una minaccia.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configurare le notifiche aggiuntive visualizzate sugli endpoint

Puoi configurare la visualizzazione di notifiche aggiuntive, ad esempio riepiloghi di rilevamento delle minacce recenti, [nell'app](microsoft-defender-security-center-antivirus.md) Sicurezza di Windows e con Criteri di gruppo.

> [!NOTE]
> In Windows 10 versione 1607 la funzionalità  era denominata Notifiche avanzate e poteva essere configurata in Windows Impostazioni Aggiornamento &  >  **sicurezza**  >  **Windows Defender**. Nelle impostazioni di Criteri di gruppo in tutte le versioni di Windows 10, si chiama **Notifiche avanzate.**

> [!IMPORTANT]
> La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.

**Usa l'app Sicurezza di Windows per disabilitare notifiche aggiuntive:**

1. Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando sicurezza nel menu **Start.**

2. Seleziona **Riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona **Impostazioni** protezione da & virus

3. Scorrere fino alla **sezione Notifiche** e fare clic su Modifica **impostazioni notifica.**

4. Fai scorrere **l'interruttore su Disattivato** o **Attivato** per disabilitare o abilitare notifiche aggiuntive.

**Utilizzare Criteri di gruppo per disabilitare notifiche aggiuntive:**

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > Reporting**.

5. Fai doppio clic **su Disattiva notifiche avanzate** e imposta l'opzione su **Abilitato.** Fare clic su **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

## <a name="configure-standard-notifications-on-endpoints"></a>Configurare le notifiche standard sugli endpoint

È possibile utilizzare Criteri di gruppo per:

- Visualizzare testo aggiuntivo personalizzato sugli endpoint quando l'utente deve eseguire un'azione
- Nascondere tutte le notifiche sugli endpoint
- Nascondere le notifiche di riavvio sugli endpoint

Nascondere le notifiche può essere utile in situazioni in cui non è possibile nascondere l'intera Antivirus Microsoft Defender interfaccia. Per altre informazioni, vedi Impedire agli utenti di visualizzare o interagire con [Antivirus Microsoft Defender'interfaccia](prevent-end-user-interaction-microsoft-defender-antivirus.md) utente. 

> [!NOTE]
> Le notifiche nascoste verranno eseguite solo sugli endpoint in cui è stato distribuito il criterio. Le notifiche relative alle azioni che devono essere eseguite (ad esempio un riavvio) verranno comunque visualizzate nel dashboard e nei report Microsoft Endpoint Manager Endpoint Protection [monitoraggio.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Per [istruzioni su come aggiungere](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) informazioni di contatto personalizzate alle notifiche visualizzate dagli utenti nei computer, vedi Personalizzare l'app Sicurezza di Windows per l'organizzazione.

**Usare Criteri di gruppo per nascondere le notifiche:**

1. Nel computer di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender >'interfaccia client**. 

4. Fare doppio clic **su Elimina tutte le notifiche** e impostare l'opzione su **Abilitato.** Fare clic su **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

**Usare Criteri di gruppo per nascondere le notifiche di riavvio:**

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender >'interfaccia client**.

5. Fai doppio clic **su Elimina le notifiche di riavvio** e imposta l'opzione su **Abilitato.** Fare clic su **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

## <a name="related-topics"></a>Argomenti correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurare l'interazione dell'utente finale con Antivirus Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)
