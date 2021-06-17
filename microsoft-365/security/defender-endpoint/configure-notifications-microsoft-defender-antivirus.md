---
title: Configurare Antivirus Microsoft Defender notifiche
description: Informazioni su come configurare e personalizzare sia le notifiche standard che altre Antivirus Microsoft Defender sugli endpoint.
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
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985409"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>Configurare Antivirus Microsoft Defender notifiche visualizzate sugli endpoint

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In Windows 10, le notifiche delle applicazioni relative al rilevamento e alla correzione di malware sono più affidabili, coerenti e concise. Antivirus Microsoft Defender notifiche vengono visualizzate sugli endpoint quando vengono completate le analisi e vengono rilevate minacce. Le notifiche seguono sia le analisi pianificate che le analisi attivate manualmente. Queste notifiche vengono visualizzate anche nel **Centro notifiche** e un riepilogo delle analisi e dei rilevamenti delle minacce viene visualizzato a intervalli di tempo regolari.

Se si fa parte del team di sicurezza dell'organizzazione, è possibile configurare la modalità di visualizzazione delle notifiche sugli endpoint, ad esempio le notifiche che richiede un riavvio del sistema o che indicano che è stata rilevata e corretti una minaccia.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>Configurare le notifiche antivirus tramite Criteri di gruppo o l Sicurezza di Windows app

Puoi configurare la visualizzazione di notifiche aggiuntive, ad esempio riepiloghi di rilevamento delle minacce recenti, [nell'app](microsoft-defender-security-center-antivirus.md) Sicurezza di Windows e con Criteri di gruppo.

> [!NOTE]
> In Windows 10 versione 1607 la funzionalità  è stata denominata Notifiche avanzate ed è stata configurata in Windows Impostazioni Aggiornamento &  >  **sicurezza**  >  **Windows Defender**. Nelle impostazioni di Criteri di gruppo per tutte le versioni di Windows 10, la funzionalità di notifica è denominata **Notifiche avanzate.**

### <a name="use-group-policy-to-disable-additional-notifications"></a>Usare Criteri di gruppo per disabilitare notifiche aggiuntive

1. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

3. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

4. Selezionare **Modelli amministrativi**.

5. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender** > Reporting**.

6. Fai doppio clic **su Disattiva notifiche avanzate** e imposta l'opzione su **Abilitato.** Infine scegliere **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

> [!IMPORTANT]
> La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Usare l'app Sicurezza di Windows per disabilitare notifiche aggiuntive

1. Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando sicurezza nel menu **Start.**

2. Seleziona **Riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona **Impostazioni** protezione da & virus

3. Scorri fino alla **sezione Notifiche** e seleziona Modifica **impostazioni notifica.**

4. Fai scorrere **l'interruttore su Disattivato** o **Attivato** per disabilitare o abilitare notifiche aggiuntive.

> [!IMPORTANT]
> La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>Configurare le notifiche standard sugli endpoint tramite Criteri di gruppo

È possibile utilizzare Criteri di gruppo per:

- Visualizzare testo aggiuntivo personalizzato sugli endpoint quando l'utente deve eseguire un'azione
- Nascondere tutte le notifiche sugli endpoint
- Nascondere le notifiche di riavvio sugli endpoint

Nascondere le notifiche può essere utile in situazioni in cui non è possibile nascondere l'intera Antivirus Microsoft Defender interfaccia. Per altre informazioni, vedi Impedire agli utenti di visualizzare o interagire con [Antivirus Microsoft Defender'interfaccia](prevent-end-user-interaction-microsoft-defender-antivirus.md) utente. Le notifiche nascoste verranno eseguite solo sugli endpoint in cui è stato distribuito il criterio. Le notifiche relative alle azioni che devono essere eseguite (ad esempio un riavvio) verranno comunque visualizzate nel dashboard e nei report Microsoft Endpoint Manager Endpoint Protection [monitoraggio.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Per aggiungere informazioni di contatto personalizzate alle notifiche degli endpoint, vedi Personalizzare [l'app Sicurezza di Windows per l'organizzazione.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

### <a name="use-group-policy-to-hide-notifications"></a>Usare Criteri di gruppo per nascondere le notifiche

1. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

3. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e quindi selezionare **Modelli amministrativi.**

4. Espandere l'albero per **Windows componenti**  >    >  **Antivirus Microsoft Defender'interfaccia client**. 

5. Fare doppio clic **su Elimina tutte le notifiche** e impostare l'opzione su **Abilitato.** 

6. Selezionare **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>Usare Criteri di gruppo per nascondere le notifiche di riavvio

1. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica.**

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti**  >    >  **Antivirus Microsoft Defender'interfaccia client**.

5. Fai doppio clic **su Elimina le notifiche di riavvio** e imposta l'opzione su **Abilitato.** 

5. Selezionare **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

