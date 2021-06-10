---
title: Introduzione alla prevenzione della perdita di dati degli endpoint di Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
ms.openlocfilehash: bf607890fcae34e95da15954349e7190bdbb19ac
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878101"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>Introduzione alla prevenzione della perdita di dati degli endpoint

Microsoft Endpoint Data Loss Prevention (Endpoint DLP) fa parte della famiglia di funzionalità di prevenzione della perdita dei dati (DLP) di Microsoft 365 che è possibile usare per individuare e proteggere gli elementi sensibili nei servizi di Microsoft 365. Per altre informazioni su tutte le offerte DLP di Microsoft, vedere [Panoramica sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md). Per altre informazioni sulla perdita dei dati degli endpoint, vedere [Informazioni sulla prevenzione della perdita di dati degli endpoint ](endpoint-dlp-learn-about.md)

Microsoft Endpoint DLP consente di monitorare i dispositivi Windows 10 e rilevare l'uso e la condivisione di elementi sensibili. In questo modo si ottengono la visibilità e il controllo necessari per assicurarsi che vengano usati e protetti correttamente e per evitare comportamenti rischiosi che potrebbero comprometterli.

## <a name="before-you-begin"></a>Informazioni preliminari

### <a name="skusubscriptions-licensing"></a>Licenze per SKU/abbonamenti

Prima di iniziare a usare Endpoint DLP, è necessario confermare l'[abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi. Per accedere e usare le funzionalità di Endpoint DLP, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi.

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

I dati provenienti da Endpoint DLP possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md). Sono disponibili quattro ruoli che concedono l'autorizzazione per Esplora attività, l'account usato per accedere ai dati deve essere membro di uno di essi.

- Amministratore globale
- Amministratore di conformità
- Amministratore della sicurezza
- Amministratore dati di conformità
- Ruolo con autorizzazioni di lettura globali
- Amministratore che legge i dati di sicurezza
- Amministratore che legge i report

### <a name="prepare-your-endpoints"></a>Preparare gli endpoint

Verificare che i dispositivi Windows 10 in cui si prevede di distribuire Endpoint DLP soddisfino questi requisiti.

1. Devono eseguire Windows 10 x 64, build 1809 o successiva.

2. La versione del client antimalware deve essere 4.18.2009.7 o successiva. Controllare la versione corrente aprendo l'app Sicurezza di Windows e facendo clic sull'icona impostazioni e quindi su Informazioni. Il numero di versione è elencato in Versione client antimalware. Eseguire l'aggiornamento all'ultima versione del client antimalware installando l'aggiornamento di Windows KB4052623. 

   > [!NOTE]
   > Nessun componente di Sicurezza di Windows deve essere attivo ed è possibile eseguire Endpoint DLP indipendentemente dallo stato di Sicurezza di Windows, ma il [Controllo in tempo reale della protezione e del comportamento](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) deve essere abilitato. 
 
3. Devono essere installati gli aggiornamenti seguenti di Windows. 
 
   > [!NOTE]
   > Questi aggiornamenti non sono prerequisiti per l'onboarding di un dispositivo in Endpoint DLP, ma contengono correzioni per problemi importanti, pertanto vanno installati prima di usare il prodotto.

    - Per Windows 10 1809 - KB4559003, KB4577069, KB4580390
    - Per Windows 10 1903 o 1909 - KB4559004, KB4577062, KB4580386
    - Per Windows 10 2004 - KB4568831, KB4577063
    - Per i dispositivi che eseguono Office 2016 (e non qualsiasi altra versione di Office) - KB4577063 

4. Tutti i dispositivi devono essere uno dei seguenti:
- [Aggiunto ad Azure Active Directory (Azure AD)](/azure/active-directory/devices/concept-azure-ad-join)
- [Aggiunto ad Azure AD ibrido](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
- [Registrato ad Azure AD](/azure/active-directory/user-help/user-help-register-device-on-network)

5. Installare il browser Microsoft Edge Chromium nel dispositivo endpoint per applicare azioni dei criteri per l'attività di caricamento nel cloud. Vedere [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

6. Se si usa il Canale Enterprise mensile di Microsoft 365 Apps versioni 2004-2008, esiste un problema noto con Endpoint DLP che classifica il contenuto di Office ed è necessario eseguire l'aggiornamento alla versione 2009 o successiva. Vedere [Cronologia degli aggiornamenti per Microsoft 365 Apps (elencati in ordine cronologico)](/officeupdates/update-history-microsoft365-apps-by-date) per le versioni correnti. Per altre informazioni su questo problema, vedere la sezione relativa alle famiglia di prodotti di Office di [Note sulla versione del Canale corrente nel 2020](/officeupdates/current-channel#version-2010-october-27).

7. Se sono presenti endpoint che usano un proxy per la connessione a Internet, seguire le procedure in [Configurare il proxy del dispositivo e le impostazioni di connessione Internet per la Prevenzione della perdita dei dati degli endpoint](endpoint-dlp-configure-proxy.md).

## <a name="onboarding-devices-into-device-management"></a>Onboarding di dispositivi nella gestione dei dispositivi

Per poter monitorare e proteggere gli elementi sensibili in un dispositivo, è necessario abilitare il monitoraggio dei dispositivi ed eseguire l'onboarding degli endpoint. Entrambe le azioni vengono eseguite nel portale Conformità Microsoft 365.

Quando si vuole eseguire l'onboarding di nuovi dispositivi, si scarica lo script appropriato e lo si distribuisce in questi dispositivi. Seguire la [procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).

Se i dispositivi sono già presenti in [Microsoft Defender per endpoint](/windows/security/threat-protection/), verranno visualizzati nell'elenco dei dispositivi gestiti. Seguire la [Procedura con dispositivi già presenti in Microsoft Defender per endpoint](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).

### <a name="onboarding-devices"></a>Onboarding dei dispositivi

In questo scenario di distribuzione si esegue l'onboarding di dispositivi non ancora caricati e si vogliono soltanto monitorare e proteggere gli elementi sensibili dalla condivisione involontaria nei dispositivi Windows 10.

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).

2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Onboarding di dispositivi**. 

   > [!div class="mx-imgBorder"]
   > ![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > Anche se in genere sono necessari circa 60 secondi perché l'onboarding dei dispositivi sia abilitato, attendere fino a 30 minuti prima di contattare il supporto tecnico Microsoft.

3. Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**. L'elenco sarà vuoto finché non si caricano dispositivi.

4. Scegliere **Onboarding** per avviare il processo di onboarding.

5. Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **scaricare il pacchetto**.

   > [!div class="mx-imgBorder"]
   > ![metodo di distribuzione](../media/endpoint-dlp-getting-started-3-deployment-method.png)
   
6. Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:

    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti in scenari a sessione singola

Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco dei dispositivi e inizierà anche a inviare log di controllo delle attività a Esplora attività.

> [!NOTE]
> Questa esperienza richiede la licenza. Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Con dispositivi già presenti in Microsoft Defender per endpoint

In questo scenario, Microsoft Defender per endpoint è già distribuito e ci sono endpoint per cui vengono creati report. Tutti questi endpoint compariranno nell'elenco dei dispositivi gestiti. È possibile continuare a eseguire l'onboarding di nuovi dispositivi in Endpoint DLP per ampliare la copertura usando la [procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).

1. Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).

2. Aprire la pagina delle impostazioni del Centro conformità e scegliere **Abilita monitoraggio dispositivi**.

3. Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**. Dovrebbe essere visualizzato l'elenco dei dispositivi che già inviano report a Microsoft Defender per endpoint.

   > [!div class="mx-imgBorder"]
   > ![gestione dispositivi](../media/endpoint-dlp-getting-started-2-device-management.png)
   
4. Scegliere **Onboarding** se è necessario aggiungere altri dispositivi.

5. Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **Scarica pacchetto**.

6. Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:

    - Onboarding di dispositivi Windows 10 con Criteri di gruppo
    - Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager
    - Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili
    - Onboarding di dispositivi Windows 10 con uno script locale
    - Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.

Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco **Dispositivi** e inizierà anche a inviare log di controllo a **Esplora attività**.

> [!NOTE]
>Questa esperienza richiede la licenza. Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>Visualizzazione degli avvisi sulla perdita dei dati degli endpoint nel dashboard di gestione degli avvisi prevenzione della perdita dei dati

1. Aprire la pagina Prevenzione della perdita dei dati nel centro conformità Microsoft 365 e scegliere Avvisi.

2. Fare riferimento alle procedure in [Come configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati](dlp-configure-view-alerts-policies.md) per visualizzare gli avvisi per i criteri di Endpoint DLP.


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>Visualizzazione dei dati di Endpoint DLP in Esplora attività

1. Aprire la pagina [Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il dominio nel Centro conformità Microsoft 365 e scegliere Esplora attività.

2. Vedere le procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi ai dispositivi endpoint e filtrarli.

   > [!div class="mx-imgBorder"]
   > ![filtro di Esplora attività per i dispositivi endpoint](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>Passaggi successivi
Ora che si è eseguito l'onboarding dei dispositivi e che è possibile visualizzare i dati sulle attività in Esplora attività, è possibile procedere con il passaggio successivo, in cui si creano criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.

- [Uso di Prevenzione della perdita di dati degli endpoint](endpoint-dlp-using.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni sulla prevenzione della perdita di dati degli endpoint ](endpoint-dlp-learn-about.md)
- [Uso della Prevenzione della perdita di dati degli endpoint ](endpoint-dlp-using.md)
- [Informazioni sulla prevenzione della perdita di dati](dlp-learn-about-dlp.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)
- [Microsoft Defender ATP](/windows/security/threat-protection/)
- [Strumenti e metodi di onboarding per i dispositivi Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivi aggiunti ad Azure AD](/azure/active-directory/devices/concept-azure-ad-join)
- [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
