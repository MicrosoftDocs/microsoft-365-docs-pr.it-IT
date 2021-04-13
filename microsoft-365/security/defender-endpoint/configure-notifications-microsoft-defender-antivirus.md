---
title: Configurare le notifiche di Microsoft Defender Antivirus
description: Scopri come configurare e personalizzare le notifiche standard e aggiuntive di Microsoft Defender Antivirus sugli endpoint.
keywords: notifiche, defender, antivirus, endpoint, gestione, amministratore
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82ca54e383943f4994f9647ce1e110a6621b1327
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691414"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configurare le notifiche visualizzate sugli endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In Windows 10, le notifiche delle applicazioni relative al rilevamento e alla correzione di malware sono più affidabili, coerenti e concise.

Le notifiche vengono visualizzate sugli endpoint quando vengono completate analisi attivate manualmente e pianificate e vengono rilevate minacce. Queste notifiche vengono visualizzate anche nel **Centro notifiche** e un riepilogo delle analisi e dei rilevamenti delle minacce viene visualizzato a intervalli di tempo regolari.

Puoi anche configurare la modalità di visualizzazione delle notifiche standard sugli endpoint, ad esempio le notifiche per il riavvio o quando è stata rilevata e corretti una minaccia.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configurare le notifiche aggiuntive visualizzate sugli endpoint

Puoi configurare la visualizzazione di notifiche aggiuntive, ad esempio riepiloghi di rilevamento delle minacce recenti, [nell'app Sicurezza](microsoft-defender-security-center-antivirus.md) di Windows e con Criteri di gruppo.

> [!NOTE]
> In Windows 10 versione 1607  la funzionalità era denominata Notifiche avanzate e poteva essere configurata in Impostazioni di **Windows** Aggiornamento &  >  **sicurezza**  >  **Windows Defender**. Nelle impostazioni di Criteri di gruppo in tutte le versioni di Windows 10, si chiama **Notifiche avanzate.**

> [!IMPORTANT]
> La disabilitazione di notifiche aggiuntive non disabiliterà le notifiche critiche, come il rilevamento delle minacce e gli avvisi di correzione.

**Usa l'app Sicurezza di Windows per disabilitare notifiche aggiuntive:**

1. Apri l'app Sicurezza di Windows facendo clic sull'icona scudo nella barra delle applicazioni o cercando **Defender** nel menu Start.

2. Fai clic **sul riquadro Protezione** da & virus (o sull'icona scudo sulla barra dei menu sinistra) e quindi sull'etichetta **Impostazioni** protezione da & virus:

    ![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Scorrere fino alla **sezione Notifiche** e fare clic su Modifica **impostazioni notifica.**

4. Fai scorrere **l'interruttore su Disattivato** o **Attivato** per disabilitare o abilitare notifiche aggiuntive.

**Utilizzare Criteri di gruppo per disabilitare notifiche aggiuntive:**

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus > Reporting**.

5. Fai doppio clic **su Disattiva notifiche avanzate** e imposta l'opzione su **Abilitato.** Fare clic su **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

## <a name="configure-standard-notifications-on-endpoints"></a>Configurare le notifiche standard sugli endpoint

È possibile utilizzare Criteri di gruppo per:

- Visualizzare testo aggiuntivo personalizzato sugli endpoint quando l'utente deve eseguire un'azione
- Nascondere tutte le notifiche sugli endpoint
- Nascondere le notifiche di riavvio sugli endpoint

Nascondere le notifiche può essere utile in situazioni in cui non è possibile nascondere l'intera interfaccia di Microsoft Defender Antivirus. Per [altre informazioni, vedi Impedire](prevent-end-user-interaction-microsoft-defender-antivirus.md) agli utenti di visualizzare o interagire con l'interfaccia utente di Microsoft Defender Antivirus. 

> [!NOTE]
> Le notifiche nascoste verranno eseguite solo sugli endpoint in cui è stato distribuito il criterio. Le notifiche relative alle azioni che devono essere eseguite (ad esempio un riavvio) verranno comunque visualizzate nel dashboard e nei report di monitoraggio di [Endpoint Protection di Microsoft Endpoint Manager.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Per istruzioni su come aggiungere informazioni di contatto personalizzate alle notifiche visualizzate dagli utenti nei computer, vedi Personalizzare [l'app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) Sicurezza di Windows per l'organizzazione.

**Usare Criteri di gruppo per nascondere le notifiche:**

1. Nel computer di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandi l'albero **fino a visualizzare i componenti di Windows >'interfaccia > Client di Microsoft Defender Antivirus.** 

4. Fare doppio clic **su Elimina tutte le notifiche** e impostare l'opzione su **Abilitato.** Fare clic su **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

**Usare Criteri di gruppo per nascondere le notifiche di riavvio:**

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandi l'albero **fino a visualizzare i componenti di Windows >'interfaccia > Client di Microsoft Defender Antivirus.**

5. Fai doppio clic **su Elimina le notifiche di riavvio** e imposta l'opzione su **Abilitato.** Fare clic su **OK**. In questo modo si impedirà la visualizzazione di notifiche aggiuntive.

## <a name="related-topics"></a>Argomenti correlati

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurare l'interazione dell'utente finale con Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)