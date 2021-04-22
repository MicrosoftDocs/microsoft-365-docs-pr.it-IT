---
title: Onboarding di dispositivi Windows 10 con uno script locale
description: Usa uno script locale per distribuire il pacchetto di configurazione nei dispositivi in modo che siano onboarded nel servizio.
keywords: configurare i dispositivi usando uno script locale, la gestione dei dispositivi, configurare Microsoft Defender per i dispositivi endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 056268ed093d371d39a6136dd0b272c12ab6f9d7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933914"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>Onboarding di dispositivi Windows 10 con uno script locale

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Puoi anche eseguire manualmente l'onboard di singoli dispositivi in Defender for Endpoint. È consigliabile eseguire questa operazione prima di testare il servizio prima di eseguire l'onboarding di tutti i dispositivi della rete.

> [!IMPORTANT]
> Questo script è stato ottimizzato per l'uso su un massimo di 10 dispositivi.
>
> Per eseguire la distribuzione su larga scala, [utilizzare altre opzioni di distribuzione.](configure-endpoints.md) Ad esempio, puoi distribuire uno script di onboarding a più di 10 dispositivi in produzione con lo script disponibile nei dispositivi [Windows 10](configure-endpoints-gp.md)con Criteri di gruppo.

## <a name="onboard-devices"></a>Dispositivi onboard 

[![Immagine del PDF che mostra i vari percorsi di distribuzione](images/onboard-script.png)](images/onboard-script.png#lightbox)


Consultare il [PDF o](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) per visualizzare i vari percorsi nella distribuzione di Defender per Endpoint. 


1.  Aprire il file ZIP del pacchetto di configurazione criteri *di gruppo*(WindowsDefenderATPOnboardingPackage.zip) scaricato dall'onboarding guidato del servizio. Puoi anche ottenere il pacchetto da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)

    1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Onboarding.**

    1. Seleziona Windows 10 come sistema operativo.

    1. Nel campo **Metodo di** distribuzione selezionare **Script locale**.

    1. Fai **clic su Scarica** pacchetto e salva il file ZIP.

  
2.  Estrai il contenuto del pacchetto di configurazione in una posizione nel dispositivo che vuoi eseguire l'onboard(ad esempio, desktop). Dovresti avere un file denominato *WindowsDefenderATPOnboardingScript.cmd.*

3.  Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:

    1.  Passare a **Start** e digitare **cmd**.

    1.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

        ![Menu Start finestra che punta a Esegui come amministratore](images/run-as-admin.png)

4.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

5.  Premere INVIO **o** fare clic su **OK.**

Per informazioni su come convalidare manualmente la conformità del dispositivo e la segnalazione corretta dei dati del sensore, vedi Risolvere i problemi di [onboarding](troubleshoot-onboarding.md)di Microsoft Defender for Endpoint.


>[!TIP]
> Dopo l'onboarding del dispositivo, puoi scegliere di eseguire un test di rilevamento per verificare che un dispositivo sia stato correttamente onboarding nel servizio. Per altre informazioni, vedi Eseguire un test di rilevamento su un endpoint [di Microsoft Defender for Endpoint appena onboarded.](run-detection-test.md)

## <a name="configure-sample-collection-settings"></a>Configurare le impostazioni della raccolta di esempio
Per ogni dispositivo, puoi impostare un valore di configurazione per indicare se è possibile raccogliere campioni dal dispositivo quando viene effettuata una richiesta tramite Microsoft Defender Security Center per inviare un file per l'analisi approfondita.

Puoi configurare manualmente l'impostazione di condivisione di esempio nel dispositivo usando *regedit* o creando ed eseguendo un file *REG.*  

La configurazione viene impostata tramite la voce della chiave del Registro di sistema seguente:

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Dove:<br>
Il tipo di nome è D-WORD. <br>
I valori possibili sono:
- 0 - Non consente la condivisione di esempi da questo dispositivo
- 1 - Consente la condivisione di tutti i tipi di file da questo dispositivo

Il valore predefinito nel caso in cui la chiave del Registro di sistema non esista è 1.


## <a name="offboard-devices-using-a-local-script"></a>Dispositivi offboard con uno script locale
Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download. I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati. Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.

> [!NOTE]
> I criteri di onboarding e offboarding non devono essere distribuiti nello stesso dispositivo contemporaneamente, altrimenti ciò causerà collisioni imprevedibili.

1. Ottenere il pacchetto di offboarding da [Microsoft Defender Security Center:](https://securitycenter.windows.com/)

    1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Offboarding.**

    1. Seleziona Windows 10 come sistema operativo.

    1. Nel campo **Metodo di** distribuzione selezionare **Script locale**.

    1. Fai **clic su Scarica** pacchetto e salva il file ZIP.

2. Estrarre il contenuto del file ZIP in un percorso condiviso di sola lettura accessibile dai dispositivi. Dovresti avere un file denominato *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3.  Apri un prompt della riga di comando con privilegi elevati nel dispositivo ed esegui lo script:

    1.  Passare a **Start** e digitare **cmd**.

    1.  Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

        ![Menu Start finestra che punta a Esegui come amministratore](images/run-as-admin.png)

4.  Digitare il percorso del file script. Se il file è stato copiato sul desktop, digitare: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5.  Premere INVIO **o** fare clic su **OK.**

> [!IMPORTANT]
> L'offboarding fa sì che il dispositivo interrompi l'invio dei dati del sensore al portale, ma i dati dal dispositivo, incluso il riferimento a eventuali avvisi che ha avuto, verranno conservati per un massimo di 6 mesi.


## <a name="monitor-device-configuration"></a>Monitorare la configurazione del dispositivo
È possibile seguire i diversi passaggi di verifica descritti in Risolvere i problemi di [onboarding](troubleshoot-onboarding.md) per verificare che lo script sia stato completato correttamente e che l'agente sia in esecuzione.

Il monitoraggio può essere eseguito anche direttamente nel portale o utilizzando i diversi strumenti di distribuzione.

### <a name="monitor-devices-using-the-portal"></a>Monitorare i dispositivi tramite il portale
1. Passare a Microsoft Defender Security Center.

2. Fare **clic su Elenco dispositivi**.

3. Verificare che i dispositivi siano visualizzati.


## <a name="related-topics"></a>Argomenti correlati
- [Onboardare dispositivi Windows 10 con Criteri di gruppo](configure-endpoints-gp.md)
- [Onboard dei dispositivi Windows 10 con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili](configure-endpoints-mdm.md)
- [Aggiungere dispositivi VDI (Virtual Desktop Infrastructure) non persistenti](configure-endpoints-vdi.md)
- [Eseguire un test di rilevamento in un dispositivo Microsoft Defender for Endpoint appena onboarded](run-detection-test.md)
- [Risolvere i problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
