---
title: Attivare la protezione basata sul cloud in Microsoft Defender Antivirus
description: Attivare la protezione basata sul cloud per usufruire di funzionalità di protezione avanzate e veloci.
keywords: Microsoft Defender Antivirus, antimalware, sicurezza, cloud, blocco al primo sguardo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9f949a4cb54ca5dd64a2648bb05a5cb9ad50e44d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764964"
---
# <a name="turn-on-cloud-delivered-protection"></a>Attivare la protezione basata sul cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Il servizio cloud Microsoft Defender Antivirus è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Sebbene sia denominato servizio cloud, non è semplicemente protezione per i file archiviati nel cloud. usa invece risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di Security intelligence.

Microsoft Defender Antivirus usa più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente. [Informazioni sulle tecnologie avanzate alla base di Microsoft Defender for Endpoint di nuova generazione.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)
![Elenco dei motori Microsoft Defender AV](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Puoi attivare o disattivare la protezione con distribuzione cloud di Microsoft Defender Antivirus in diversi modi:

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- Criteri di gruppo
- Cmdlet di PowerShell.

 Puoi anche attivarlo o disattivarlo nei singoli client con l'app Sicurezza di Windows.

Vedi [Usare la protezione fornita dal cloud Microsoft](cloud-protection-microsoft-defender-antivirus.md) per una panoramica della protezione fornita dal cloud di Microsoft Defender Antivirus.

Per ulteriori informazioni sui requisiti di connettività di rete specifici per garantire che gli endpoint possano connettersi al servizio di protezione fornito dal cloud, vedere [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> In Windows 10, non esiste alcuna differenza tra le **opzioni** di creazione di report di base **e** avanzate descritte in questo argomento. Si tratta di una distinzione legacy e la scelta di entrambe le impostazioni determina lo stesso livello di protezione fornito dal cloud. Non esiste alcuna differenza nel tipo o nella quantità di informazioni condivise. Per altre informazioni sui dati raccolti, vedi l'Informativa [sulla privacy di Microsoft.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Usare Intune per attivare la protezione con distribuzione cloud

1. Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.
2. Nel riquadro **Home** selezionare **Configurazione dispositivo > Profili**.
3. Selezionare il **tipo di profilo** Restrizioni dispositivo che si desidera configurare. Se devi creare un nuovo tipo di profilo Restrizioni **dispositivo,** vedi [Configurare le impostazioni di restrizione dei dispositivi in Microsoft Intune.](/intune/device-restrictions-configure)
4. Selezionare **Proprietà**  >  **Impostazioni di configurazione: Modifica** Microsoft Defender  >  **Antivirus.**
5. **Nell'opzione Protezione con recapito cloud** selezionare **Abilita**.
6. **Nell'elenco a discesa Richiedi conferma agli utenti prima dell'invio** di esempio seleziona **Invia automaticamente tutti i dati.**

Per altre informazioni sui profili dei dispositivi Intune, incluso come creare e configurare le impostazioni, vedere Che cosa sono i profili di [dispositivo di Microsoft Intune?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Usare Microsoft Endpoint Manager per attivare la protezione con distribuzione cloud

1. Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.
2. Scegliere **Endpoint security**  >  **Antivirus**.
3. Selezionare un profilo antivirus. Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune.](/intune/device-restrictions-configure)
4. Selezionare **Proprietà**. Quindi, accanto a **Impostazioni di configurazione** scegliere **Modifica.**
5. Espandere **Protezione cloud** e  quindi selezionare una delle opzioni seguenti nell'elenco Livello di protezione fornito dal cloud:
    1. **High**: applica un livello elevato di rilevamento.
    2. **High plus**: usa **il livello High** e applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client).
    3. **Tolleranza zero:** blocca tutti i file eseguibili sconosciuti.
6. Seleziona **Rivedi e salva,** quindi scegli **Salva.**

Per ulteriori informazioni sulla configurazione di Microsoft Endpoint Configuration Manager, vedere [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Usare Criteri di gruppo per attivare la protezione con distribuzione cloud

1. Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Selezionare **Modelli amministrativi**.

4. Espandere l'albero fino **ai componenti di Windows > Microsoft Defender Antivirus > MAPS**

5. Fare doppio clic su **Partecipa a Microsoft MAPS.** Assicurati che l'opzione sia attivata e impostata su **MAPPE di base** o MAPPE **avanzate.** Selezionare **OK**.

6. Fare doppio clic su **Invia esempi di file quando è necessaria un'ulteriore analisi.** Verificare che la prima opzione sia impostata su **Abilitato** e che le altre opzioni siano impostate su:

    1. **Inviare campioni sicuri** (1)
    2. **Inviare tutti gli esempi** (3)

        >[!NOTE]
        > **L'opzione Invia campioni sicuri** (1) indica che la maggior parte dei campioni verrà inviata automaticamente. I file che probabilmente contengono informazioni personali verranno comunque richiesti e richiederanno ulteriore conferma.

        > [!WARNING]
        > Se si imposta **l'opzione su Chiedi** sempre conferma (0), lo stato di protezione del dispositivo verrà abbassato. L'impostazione su **Non inviare** mai (2) significa che la [funzionalità](configure-block-at-first-sight-microsoft-defender-antivirus.md) Blocca al primo sguardo di Microsoft Defender per Endpoint non funzionerà.

7. Selezionare **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Usare i cmdlet di PowerShell per attivare la protezione recapitata nel cloud

I cmdlet seguenti possono attivare la protezione recapitata nel cloud:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Per ulteriori informazioni su come usare PowerShell con Microsoft Defender Antivirus, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/) [CSP criteri - Defender](/windows/client-management/mdm/policy-csp-defender) include anche altre informazioni specifiche su [-SubmitSamplesConsent.](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)

>[!NOTE]
> Puoi anche impostare **-SubmitSamplesConsent** `SendSafeSamples` su (impostazione predefinita), `NeverSend` o `AlwaysPrompt` . `SendSafeSamples`L'impostazione indica che la maggior parte dei campioni verrà inviata automaticamente. I file che probabilmente contengono informazioni personali verranno comunque richiesti e richiederanno ulteriore conferma.

>[!WARNING]
> Se **si imposta -SubmitSamplesConsent** su o si riduce il livello `NeverSend` di protezione del `AlwaysPrompt` dispositivo. Inoltre, impostandola su significa che la funzionalità Blocca al primo sguardo `NeverSend` di Microsoft Defender per Endpoint non funzionerà. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Usare Windows Management Instruction (WMI) per attivare la protezione basata sul cloud

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) per le proprietà seguenti:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Per altre informazioni sui parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Attivare la protezione basata sul cloud su singoli client con l'app Sicurezza di Windows

> [!NOTE]
> Se **l'impostazione** di Criteri di gruppo Configura impostazioni locali per la segnalazione di Microsoft MAPS è impostata su **Disabilitato,** l'impostazione di protezione basata su **cloud** in Impostazioni di Windows sarà disattivata e non disponibile. Le modifiche apportate tramite un oggetto Criteri di gruppo devono prima essere distribuite a singoli endpoint prima che l'impostazione venga aggiornata in Impostazioni di Windows.

1. Apri l'app Sicurezza di Windows selezionando l'icona scudo nella barra delle applicazioni o cercando Defender **nel** menu Start.

2. Seleziona il **riquadro Protezione** da & virus (o l'icona scudo sulla barra dei menu sinistra) e quindi l'etichetta **Impostazioni** protezione da & virus:

    ![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Verificare che **Protezione basata su cloud e** **Invio** automatico di esempio siano stati commutati su **On.**

> [!NOTE]
> Se l'invio automatico di esempio è stato configurato con Criteri di gruppo, l'impostazione sarà disattivata e non disponibile.

## <a name="related-articles"></a>Articoli correlati

- [Configurare il periodo di timeout del blocco cloud](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Configurare il blocco al primo avvistamento](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Utilizzare i cmdlet di PowerShell per gestire Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Proteggere i PC Windows con Endpoint Protection per Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlet defender](/powershell/module/defender/)
- [Usare la protezione microsoft basata sul cloud in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)
- [Come creare e distribuire criteri antimalware: servizio di protezione cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)