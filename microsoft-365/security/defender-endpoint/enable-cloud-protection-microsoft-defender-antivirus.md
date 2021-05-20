---
title: Attivare la protezione fornita dal cloud in Antivirus Microsoft Defender
description: Attiva la protezione fornita dal cloud per beneficiare di funzionalità di protezione veloci e avanzate.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, cloud, blocco a prima vista
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572058"
---
# <a name="turn-on-cloud-delivered-protection"></a>Attivare la protezione fornita dal cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e agli endpoint. Sebbene sia chiamato servizio cloud, non è semplicemente protezione per i file archiviati nel cloud; piuttosto, utilizza risorse distribuite e machine learning per fornire protezione agli endpoint a una velocità molto più veloce rispetto ai tradizionali aggiornamenti di intelligence sulla sicurezza.

Antivirus Microsoft Defender utilizza più tecnologie di rilevamento e prevenzione per fornire una protezione accurata, in tempo reale e intelligente. [Conoscere le tecnologie avanzate al centro della protezione di nuova generazione di Microsoft Defender for Endpoint](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

È possibile attivare o disattivare Antivirus Microsoft Defender protezione fornita dal cloud in diversi modi:

- Microsoft Intune
- Microsoft Endpoint Manager
- Criteri di gruppo
- Cmdlet di PowerShell.

 Puoi anche attivarlo o disattivarlo nei singoli client con l'app Sicurezza di Windows.

Per una panoramica della protezione fornita dal cloud Microsoft, vedere Antivirus Microsoft Defender Use [Microsoft cloud-delivered](cloud-protection-microsoft-defender-antivirus.md) protection.

Per ulteriori informazioni sui requisiti specifici di connettività di rete per garantire che gli endpoint possano connettersi al servizio di protezione fornito dal cloud, vedere [Configurare e convalidare le connessioni di rete](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> In Windows 10 non vi è alcuna differenza tra le opzioni **di** reporting **di base** e avanzate descritte in questo argomento. Si tratta di una distinzione legacy e la scelta di entrambe le impostazioni comporterà lo stesso livello di protezione fornita dal cloud. Non vi è alcuna differenza nel tipo o nella quantità di informazioni condivise. Per ulteriori informazioni su ciò che raccogliamo, vedere l'Informativa [sulla privacy di Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Utilizzare Intune per attivare la protezione fornita dal cloud

1. Passare all'interfaccia Microsoft Endpoint Manager'interfaccia di [https://endpoint.microsoft.com](https://endpoint.microsoft.com) amministrazione di Amministrazione ( ) e accedere.

2. Nel riquadro **Home** selezionare Configurazione **dispositivo > profili**.

3. Selezionare il **tipo di profilo** Restrizioni dispositivo da configurare. Se è necessario creare un nuovo tipo di profilo **restrizioni dispositivo,** vedere [Configurare le impostazioni di restrizione del dispositivo in Microsoft Intune](/intune/device-restrictions-configure).

4. Selezionare **Impostazioni**  >  **di configurazione proprietà: Modifica**  >  **Antivirus Microsoft Defender**.

5. **Nell'opzione di protezione recapitata dal** cloud selezionare **Abilita**.

6. **Nell'elenco a discesa Richiedi utenti prima dell'invio** di esempio selezionare Invia **automaticamente tutti i dati**.

Per ulteriori informazioni sui profili dei dispositivi Intune, incluso come creare e configurare le impostazioni, [vedere Cosa sono i Microsoft Intune dei dispositivi?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Utilizzare Microsoft Endpoint Manager per attivare la protezione fornita dal cloud

1. Passare all'interfaccia Microsoft Endpoint Manager'interfaccia di [https://endpoint.microsoft.com](https://endpoint.microsoft.com) amministrazione di Amministrazione ( ) e accedere.

2. Scegliere **Endpoint security**  >  **Antivirus**.

3. Selezionare un profilo antivirus. Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le [impostazioni di restrizione del dispositivo in Microsoft Intune](/intune/device-restrictions-configure).

4. Selezionare **Proprietà**. Accanto alle impostazioni **di configurazione scegliere** **Modifica**.

5. Espandere **Protezione cloud** e quindi nell'elenco Livello di protezione **recapitato nel** cloud selezionare una delle opzioni seguenti:
   - **Alto:** applica un forte livello di rilevamento.
   - **Alto plus:** utilizza il **livello Alto e** applica ulteriori misure di protezione (può influire sulle prestazioni del client).
   - **Tolleranza zero:** blocca tutti gli eseguibili sconosciuti.

6. Selezionare **Revisione + salva**, quindi Scegliere **Salva**.

Per ulteriori informazioni sulla configurazione Microsoft Endpoint Configuration Manager, vedere [Come creare e distribuire criteri antimalware: Servizio di protezione cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Usare Criteri di gruppo per attivare la protezione fornita dal cloud

1. Nel dispositivo di gestione Criteri di gruppo aprire Console Gestione Criteri di gruppo , [fare clic con](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e selezionare **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Selezionare **Modelli amministrativi**.

4. Espandere l'albero **per Windows componenti > Antivirus Microsoft Defender > MAPS**

5. Fare doppio clic **su Partecipa a Microsoft MAPS**. Assicurarsi che l'opzione sia attivata e impostata **su Basic MAPS** o Advanced **MAPS**. Selezionare **OK**.

6. Fare doppio clic su **Invia esempi di file quando è necessaria un'ulteriore analisi**. Verificare che la prima opzione sia impostata **su Abilitato** e che le altre opzioni siano impostate su:

    1. **Invia campioni sicuri** (1)
    2. **Invia tutti i campioni** (3)

        >[!NOTE]
        > **L'opzione Invia campioni sicuri** (1) significa che la maggior parte dei campioni verrà inviata automaticamente. I file che potrebbero contenere informazioni personali richiederanno comunque una conferma aggiuntiva.
        > L'impostazione **dell'opzione su Richiedi** sempre (0) riducerà lo stato di protezione del dispositivo. Impostarlo su **Mai inviare** (2) significa che [la funzionalità Blocca a prima](configure-block-at-first-sight-microsoft-defender-antivirus.md) vista di Microsoft Defender per endpoint non funzionerà.

7. Selezionare **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Utilizzare i cmdlet di PowerShell per attivare la protezione fornita dal cloud

I cmdlet seguenti possono attivare la protezione fornita dal cloud:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Per ulteriori informazioni sull'utilizzo di PowerShell con Antivirus Microsoft Defender, vedere [Utilizzare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) cmdlet di [Defender](/powershell/module/defender/). [Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) dispone inoltre di ulteriori informazioni specifiche su [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> È inoltre possibile impostare **-SubmitSamplesConsent** `SendSafeSamples` su (impostazione predefinita), `NeverSend` o `AlwaysPrompt` . `SendSafeSamples`L'impostazione significa che la maggior parte dei campioni verrà inviata automaticamente. I file che potrebbero contenere informazioni personali richiederanno comunque una conferma aggiuntiva.

>[!WARNING]
> Impostazione **di -SubmitSamplesConsent** `NeverSend` su o si riduce il livello di protezione del `AlwaysPrompt` dispositivo. Inoltre, impostarlo su `NeverSend` significa che la funzionalità Blocca a [prima](configure-block-at-first-sight-microsoft-defender-antivirus.md) vista di Microsoft Defender per endpoint non funzionerà.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Utilizzare Windows di gestione dei dati (WMI) per attivare la protezione fornita dal cloud

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) per le proprietà seguenti:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Per ulteriori informazioni sui parametri consentiti, [vedere Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Attivare la protezione fornita dal cloud sui singoli client con l'app Sicurezza di Windows

> [!NOTE]
> Se **l'impostazione Configura override delle impostazioni locali per la segnalazione** di Criteri di gruppo di Microsoft MAPS è **disabilitata**, **l'impostazione di** protezione basata su cloud in Windows Impostazioni verrà disattivata e non disponibile. Le modifiche apportate tramite un oggetto Criteri di gruppo devono essere distribuite nei singoli endpoint prima che l'impostazione venga aggiornata nelle impostazioni di Windows.

1. Aprire l Sicurezza di Windows applicazione selezionando l'icona scudo nella barra delle applicazioni o cercando Defender nel menu di **avvio**.

2. Selezionare il **riquadro & protezione da virus** (o l'icona scudo sulla barra dei menu sinistra) e quindi **l'etichetta & protezione dalle minacce** di Virus:

    ![Screenshot dell'etichetta Impostazioni di Protezione da virus e minacce nell'app Sicurezza di Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Verificare che **la protezione basata sul cloud e l'invio** **automatico dell'esempio** siano accesi . 

> [!NOTE]
> Se l'invio automatico dell'esempio è stato configurato con Criteri di gruppo, l'impostazione verrà disattivata e non disponibile.

## <a name="related-articles"></a>Articoli correlati

- [Configurare il periodo di timeout del blocco cloud](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Configurare il blocco a prima vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Usare PowerShell cmdlets per gestire Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Proteggere i Windows pc con Endpoint Protection per Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Cmdlet di Defender](/powershell/module/defender/)
- [Utilizzare la protezione fornita dal cloud Microsoft in Antivirus Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)
- [Come creare e distribuire criteri antimalware: servizio di protezione del cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
