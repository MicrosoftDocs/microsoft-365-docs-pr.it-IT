---
title: Attivare la protezione basata sul cloud in Antivirus Microsoft Defender
description: Attivare la protezione basata sul cloud per usufruire di funzionalità di protezione avanzate e veloci.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, cloud, blocco al primo sguardo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 694c09c5136f874550fa4a47586f3268ee2d0833
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007184"
---
# <a name="turn-on-cloud-delivered-protection"></a>Attivare la protezione fornita dal cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Sebbene sia denominato servizio cloud, non è semplicemente protezione per i file archiviati nel cloud. usa invece risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di Security intelligence.

Antivirus Microsoft Defender più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente. [Informazioni sulle tecnologie avanzate alla base di Microsoft Defender for Endpoint di nuova generazione.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

È possibile attivare o Antivirus Microsoft Defender la protezione basata sul cloud in diversi modi:

- Microsoft Intune
- Microsoft Endpoint Manager
- Criteri di gruppo
- Cmdlet di PowerShell.

 Puoi anche attivarlo o disattivarlo nei singoli client con l Sicurezza di Windows app.

Vedi Usare la protezione fornita [dal cloud Microsoft](cloud-protection-microsoft-defender-antivirus.md) per una panoramica Antivirus Microsoft Defender protezione fornita dal cloud.

Per ulteriori informazioni sui requisiti di connettività di rete specifici per garantire che gli endpoint possano connettersi al servizio di protezione fornito dal cloud, vedere [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> In Windows 10, non esiste alcuna differenza tra le **opzioni** di creazione di **report** di base e avanzate descritte in questo argomento. Si tratta di una distinzione legacy e la scelta di entrambe le impostazioni determina lo stesso livello di protezione fornito dal cloud. Non esiste alcuna differenza nel tipo o nella quantità di informazioni condivise. Per altre informazioni sui dati raccolti, vedi l'Informativa [sulla privacy di Microsoft.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Usare Intune per attivare la protezione con distribuzione cloud

1. Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.

2. Nel riquadro **Home** selezionare **Configurazione dispositivo > Profili**.

3. Selezionare il **tipo di profilo** Restrizioni dispositivo che si desidera configurare. Se devi creare un  nuovo tipo di profilo Restrizioni dispositivo, vedi Configurare le impostazioni di [restrizione dei](/intune/device-restrictions-configure)dispositivi in Microsoft Intune .

4. Selezionare **Proprietà**  >  **Impostazioni di configurazione: Modifica**  >  **Antivirus Microsoft Defender**.

5. **Nell'opzione Protezione con recapito cloud** selezionare **Abilita**.

6. **Nell'elenco a discesa Richiedi conferma agli utenti prima dell'invio** di esempio seleziona **Invia automaticamente tutti i dati.**

Per altre informazioni sui profili dei dispositivi Intune, incluso come creare e configurare le impostazioni, vedere Che cosa sono i profili Microsoft Intune [dispositivo?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Usare Microsoft Endpoint Manager per attivare la protezione con distribuzione cloud

1. Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.

2. Scegliere **Endpoint security**  >  **Antivirus**.

3. Selezionare un profilo antivirus. Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune](/intune/device-restrictions-configure).

4. Selezionare **Proprietà**. Quindi, accanto a **Impostazioni di configurazione** scegliere **Modifica.**

5. Espandere **Protezione cloud** e  quindi selezionare una delle opzioni seguenti nell'elenco Livello di protezione fornito dal cloud:
   - **High**: applica un livello elevato di rilevamento.
   - **High plus**: usa **il livello High** e applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client).
   - **Tolleranza zero:** blocca tutti i file eseguibili sconosciuti.

6. Seleziona **Rivedi e salva,** quindi scegli **Salva.**

Per ulteriori informazioni sulla configurazione Microsoft Endpoint Configuration Manager, vedere [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Usare Criteri di gruppo per attivare la protezione con distribuzione cloud

1. Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Selezionare **Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > MAPS**

5. Fare doppio clic su **Partecipa a Microsoft MAPS.** Assicurati che l'opzione sia attivata e impostata su **MAPPE di base** o MAPPE **avanzate.** Selezionare **OK**.

6. Fare doppio clic su **Invia esempi di file quando è necessaria un'ulteriore analisi.** Verificare che la prima opzione sia impostata su **Abilitato** e che le altre opzioni siano impostate su:

    1. **Inviare campioni sicuri** (1)
    2. **Inviare tutti gli esempi** (3)

        >[!NOTE]
        > **L'opzione Invia campioni sicuri** (1) indica che la maggior parte dei campioni verrà inviata automaticamente. I file che probabilmente contengono informazioni personali verranno comunque richiesti e richiederanno ulteriore conferma.
        > Se si imposta **l'opzione su Chiedi** sempre conferma (0), lo stato di protezione del dispositivo verrà abbassato. L'impostazione su **Non inviare** mai (2) significa che la [funzionalità](configure-block-at-first-sight-microsoft-defender-antivirus.md) Blocca al primo sguardo di Microsoft Defender per Endpoint non funzionerà.

7. Selezionare **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Usare i cmdlet di PowerShell per attivare la protezione recapitata nel cloud

I cmdlet seguenti possono attivare la protezione recapitata nel cloud:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/) [CSP criteri - Defender](/windows/client-management/mdm/policy-csp-defender) include anche altre informazioni specifiche su [-SubmitSamplesConsent.](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)

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

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Attivare la protezione basata sul cloud su singoli client con l'app Sicurezza di Windows cloud

> [!NOTE]
> Se l'impostazione configura **l'override** dell'impostazione locale per la segnalazione di Criteri di gruppo di Microsoft MAPS è impostata su **Disabilitato,** l'impostazione di protezione basata su **cloud** in Windows Impostazioni sarà disattivata e non disponibile. Le modifiche apportate tramite un oggetto Criteri di gruppo devono essere distribuite nei singoli endpoint prima che l'impostazione venga aggiornata nelle impostazioni di Windows.

1. Apri l Sicurezza di Windows app selezionando l'icona scudo nella barra delle applicazioni o cercando Defender nel menu **Start.**

2. Seleziona il **riquadro Protezione** da & virus (o l'icona scudo sulla barra dei menu sinistra) e quindi l'etichetta **Impostazioni** protezione da & virus:

    :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Screenshot delle impostazioni di Protezione da & virus":::

3. Verificare che **Protezione basata su cloud e** **Invio** automatico di esempio siano stati commutati su **On.**

> [!NOTE]
> Se l'invio automatico di esempio è stato configurato con Criteri di gruppo, l'impostazione sarà disattivata e non disponibile.

## <a name="related-articles"></a>Articoli correlati

- [Configurare il periodo di timeout del blocco cloud](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Configurare il blocco al primo avvistamento](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Usare PowerShell cmdlets per gestire Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Proteggere i WINDOWS pc con Endpoint Protection per Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlet defender](/powershell/module/defender/)
- [Usare la protezione microsoft basata su cloud in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)
- [Come creare e distribuire criteri antimalware: servizio di protezione cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
