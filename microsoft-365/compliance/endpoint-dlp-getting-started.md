---
title: Introduzione alla prevenzione della perdita di dati degli endpoint di Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Configurare la prevenzione della perdita di dati degli endpoint di Microsoft 365 per monitorare le attività dei file e implementare azioni di protezione per questi file negli endpoint.
ms.openlocfilehash: 8211ffbe3a84c0ee9fb4cb4c22d4dcea7f906a78
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371602"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>Introduzione alla prevenzione della perdita di dati degli endpoint

La prevenzione della perdita di dati degli endpoint di Microsoft 365 (Endpoint DLP) fa parte della famiglia di funzionalità di prevenzione della perdita dei dati (DLP) di Microsoft 365 che è possibile usare per individuare e proteggere gli elementi sensibili nei servizi di Microsoft 365. Per altre informazioni su tutte le offerte DLP Microsoft, vedere [Panoramica della prevenzione della perdita dei dati](data-loss-prevention-policies.md). Per altre informazioni sulla perdita dei dati degli endpoint, vedere [Informazioni sulla prevenzione della perdita di dati degli endpoint ](endpoint-dlp-learn-about.md)

La prevenzione della perdita di dati degli endpoint di Microsoft consente di monitorare i dispositivi Windows 10 e rilevare quando vengono usati e condivisi elementi sensibili. Questo fornisce la visibilità e il controllo necessari per garantire che vengano usati e protetti in modo appropriato e per prevenire comportamenti rischiosi che potrebbero comprometterli.

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="skusubscriptions-licensing"></a>Licenze per SKU/sottoscrizioni

Prima di iniziare a usare Endpoint DLP, è necessario confermare [la sottoscrizione a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e a qualsiasi componente aggiuntivo. Per accedere a e usare la funzionalità Endpoint DLP, è necessario disporre di una delle seguenti sottoscrizioni o dei seguenti componenti aggiuntivi.

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 Compliance
- Microsoft 365 A5 Compliance
- Microsoft 365 E5 Information Protection and Governance
- Microsoft 365 A5 Information Protection and Governance


### <a name="permissions"></a>Autorizzazioni

Per abilitare la gestione dei dispositivi, l'account in uso deve essere membro di uno di questi ruoli:

- Amministratore globale
- Amministratore della sicurezza
- Amministratore di conformità

Se si vuole usare un account personalizzato per vedere le impostazioni di gestione dei dispositivi, deve essere in uno dei ruoli seguenti:

- Amministratore globale
- Amministratore di conformità
- Amministratore dati di conformità
- Ruolo con autorizzazioni di lettura globali

Se si vuole usare un account personalizzato per accedere alla pagina di onboarding/offboarding, deve essere in uno dei ruoli seguenti:

- Amministratore globale
- Amministratore di conformità

Se si vuole usare un account personalizzato per attivare o disattivare il monitoraggio dei dispositivi, deve essere in uno dei ruoli seguenti:

- Amministratore globale
- Amministratore di conformità

I dati da Endpoint DLP possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md). Sono disponibili quattro ruoli che concedono l'autorizzazione per Esplora attività e l'account usato per accedere ai dati deve essere membro di uno di essi.

- Amministratore globale
- Amministratore di conformità
- Amministratore della sicurezza
- Amministratore dati di conformità

### <a name="prepare-your-endpoints"></a>Preparare gli endpoint

Verificare che i dispositivi Windows 10 in cui si prevede di distribuire Endpoint DLP soddisfino questi requisiti.

1. Devono eseguire Windows 10 x 64, build 1809 o successiva.

2. La versione del client antimalware è 4.18.2009.7 o più recente. Verificare la versione corrente aprendo l'app Sicurezza di Windows, selezionare l'icona Impostazioni, quindi Informazioni. Il numero versione compare sotto Versione client antimalware. Eseguira l'aggiornamento all'ultima versione del client antimalware installando Windows Update KB4052623. Not: nessun componente di Sicurezza di Windows deve essere attivo, è possibile eseguire Endpoint DLP a prescindere dallo stato di Sicurezza di Windows.

3. I seguenti aggiornamenti di Windows sono installati. Nota: questi aggiornamenti non costituiscono un prerequisito per eseguire l'onboarding di un dispositivo a Endpoint DLP, ma contengono correzioni per errori importanti, pertanto devono essere installati prima di usare il prodotto.

    - Per Windows 10 1809 - KB4559003, KB4577069, KB4580390
    - Per Windows 10 1903 o 1909 - KB4559004, KB4577062, KB4580386
    - Per Windows 10 2004 - KB4568831, KB4577063
    - Per i dispositivi che eseguono Office 2016 (e non qualsiasi altra versione di Office) - KB4577063 

4. Tutti i dispositivi devono essere [aggiunti ad Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) o aggiunti ad Azure AD ibrido.

5. Installare il browser Microsoft Chromium Edge sul dispositivo endpoint per applicare le azioni dei criteri per l'attività di caricamento nel cloud. Vedere [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

6. Se si è in un Canale Enterprise mensile di Microsoft 365 Apps, versioni 2004-2008, è presente un problema noto relativo alla classificazione dei contenuti di Office da parte di Endpoint DLP ed è necessaria la versione 2009 o successiva. Vedere [Aggiornare la cronologia per Microsoft 365 Apps (per data)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) per le versioni correnti. Per ulteriori informazioni in merito a questo problema, vedere la sezione della famiglia di prodotti Office di [Note sulla versione per i rilasci del canale corrente nel 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).

## <a name="onboarding-devices-into-device-management"></a>Onboarding di dispositivi nella gestione dei dispositivi

Per poter monitorare e proteggere gli elementi riservati in un dispositivo, è necessario abilitare il monitoraggio dei dispositivi ed eseguire l'onboarding degli endpoint. Entrambe queste azioni vengono eseguite nel portale per la conformità di Microsoft 365.

Quando si desidera eseguire l'onboarding di nuovi dispositivi, si scarica lo script appropriato e lo si distribuisce in questi dispositivi. Seguire la [Procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).

Se si dispone già di dispositivi per cui è stato eseguito l'onboarding in [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/), compariranno già nell'elenco dei dispositivi gestiti. Seguire la [Procedura con i dispositivi per cui è stato eseguito l'onboarding in Microsoft ATP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).

### <a name="onboarding-devices"></a>Onboarding dei dispositivi

In questo scenario di distribuzione si esegue l'onboarding di dispositivi non ancora caricati e si vogliono soltanto monitorare e proteggere gli elementi sensibili dalla condivisione involontaria nei dispositivi Windows 10.

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).

2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Onboarding di dispositivi**. 

   > [!div class="mx-imgBorder"]
   > ![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > Anche se in genere sono necessari circa 60 secondi perché l'onboarding dei dispositivi sia abilitato, attendere fino a 30 minuti prima di contattare il supporto tecnico Microsoft.

3. Scegliere **Gestione dispositivi** per aprire l'elenco dei **Dispositivi**. L'elenco sarà vuoto fino all'onboarding dei dispositivi.

4. Scegliere **Onboarding** per avviare il processo di onboarding.

5. Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **scaricare il pacchetto**.

   > [!div class="mx-imgBorder"]
   > ![metodo di distribuzione](../media/endpoint-dlp-getting-started-3-deployment-method.png)
   
6. Seguire le procedure appropriate in [Strumenti per l'onboarding e metodi per i computer Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta alla pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender ATP che corrispondono al pacchetto di distribuzione selezionato al passaggio 5:

    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.

Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco dei dispositivi e inizierà anche a inviare log audit delle attività a Esplora attività.

> [!NOTE]
> Questa esperienza richiede l'applicazione di una licenza. Senza la licenza richiesta, i dati non saranno visibili o accessibili.

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Con dispositivi già presenti in Microsoft Defender per endpoint

In questo scenario, Microsoft Defender ATP è già stato distribuito e sono presenti endpoint che inviano report a esso. Tutti questi endpoint compariranno nell'elenco dei dispositivi gestiti. È possibile continuare a eseguire l'onboarding di nuovi dispositivi in Endpoint DLP per espandere la copertura tramite la [Procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).

2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Abilita monitoraggio dispositivi**.

3. Scegliere **Gestione dispositivi** per aprire l'elenco dei **Dispositivi**. Dovrebbe essere visualizzato l'elenco dei dispositivi che inviano già report a Microsoft Defender ATP.

   > [!div class="mx-imgBorder"]
   > ![gestione dispositivi](../media/endpoint-dlp-getting-started-2-device-management.png)
   
4. Scegliere **Onboarding** se è necessario aggiungere altri dispositivi.

5. Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **Scarica pacchetto**.

6. Seguire le procedure appropriate in [Strumenti per l'onboarding e metodi per i computer Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta alla pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender ATP che corrispondono al pacchetto di distribuzione selezionato al passaggio 5:

    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.

Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco **Dispositivi** e inizierà anche a inviare log di controllo a **Esplora attività**.

> [!NOTE]
>Questa esperienza richiede l'applicazione di una licenza. Senza la licenza richiesta, i dati non saranno visibili o accessibili.

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>Visualizzazione degli avvisi di Endpoint DLP nel dashboard di gestione degli avvisi DLP

1. Aprire la pagina Prevenzione della perdita dei dati nel centro conformità Microsoft 365 e scegliere Avvisi.

2. Fare riferimento alle procedure in [Come configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati](dlp-configure-view-alerts-policies.md) per visualizzare gli avvisi per i criteri di Endpoint DLP.


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Visualizzazione dei dati di Endpoint DLP in Esplora attività

1. Aprire la pagina [Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il dominio nel Centro conformità Microsoft 365 e scegliere Esplora attività.

2. Vedere le procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi ai dispositivi endpoint e filtrarli.

   > [!div class="mx-imgBorder"]
   > ![filtro di Esplora attività per i dispositivi endpoint](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>Passaggi successivi
Ora che si è eseguito l'onboarding dei dispositivi e che è possibile visualizzare i dati sulle attività in Esplora attività, è possibile procedere con il passaggio successivo, in cui si creano criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.

- [Uso della prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-using.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni sulla prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-learn-about.md)
- [Uso della prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-using.md)
- [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/)
- [Strumenti e metodi di onboarding per i dispositivi Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivi aggiunti ad Azure AD](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
