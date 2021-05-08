---
title: Configurare Microsoft Defender per le funzionalità di Endpoint in iOS
description: Descrive come distribuire Microsoft Defender for Endpoint in funzionalità iOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configurare, funzionalità, ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dab72da02927c3fff6025eb2d0fa9ed0fdf1d0d7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245277"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a>Configurare Microsoft Defender per le funzionalità di Endpoint in iOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> Defender for Endpoint in iOS userebbe una VPN per fornire la funzionalità di protezione Web. Non si tratta di una NORMALE VPN ed è una VPN locale/con looping che non porta traffico all'esterno del dispositivo.

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a>Accesso condizionale con Defender per Endpoint in iOS  
Microsoft Defender for Endpoint su iOS insieme a Microsoft Intune e Azure Active Directory consente di far rispettare la conformità dei dispositivi e i criteri di accesso condizionale in base al punteggio di rischio del dispositivo. Defender for Endpoint è una soluzione Mobile Threat Defense (MTD) che puoi distribuire per sfruttare questa funzionalità tramite Intune.

Per altre informazioni su come configurare l'accesso condizionale con Defender per Endpoint in iOS, vedi [Defender per Endpoint e Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)

> [!NOTE]
> **Il rilevamento jailbreak di Microsoft Defender per Endpoint su iOS è attualmente in anteprima.** Se un dispositivo viene rilevato come jailbroken da Microsoft Defender for Endpoint, verrà segnalato al Centro sicurezza e se l'accesso condizionale viene installato in base al punteggio di rischio del dispositivo, al dispositivo verrà impedito l'accesso ai dati aziendali.

## <a name="web-protection-and-vpn"></a>Protezione Web e VPN

Per impostazione predefinita, Defender per Endpoint in iOS include e abilita la funzionalità di protezione Web. [La protezione Web](web-protection-overview.md) consente di proteggere i dispositivi dalle minacce Web e proteggere gli utenti dagli attacchi di phishing. Defender for Endpoint su iOS usa una VPN per fornire questa protezione. Tieni presente che si tratta di una VPN locale e, a differenza della VPN tradizionale, il traffico di rete non viene inviato all'esterno del dispositivo.

Anche se abilitata per impostazione predefinita, in alcuni casi potrebbe essere necessario disabilitare vpn. Ad esempio, vuoi eseguire alcune app che non funzionano quando è configurata una VPN. In questi casi, puoi scegliere di disabilitare vpn dall'app nel dispositivo seguendo la procedura seguente:

1. Nel dispositivo iOS, apri l'app **Impostazioni,** tocca o fai clic su **Generale** e **quindi su VPN.**
1. Tocca o fai clic sul pulsante "i" per Microsoft Defender for Endpoint.
1. Disattiva la **Connessione su richiesta per** disabilitare la VPN.

    > [!div class="mx-imgBorder"]
    > ![Connessione a richiesta della configurazione VPN](images/ios-vpn-config.png)

> [!NOTE]
> Protezione Web non sarà disponibile quando LA VPN è disabilitata. Per abilitare di nuovo Web Protection, apri l'app Microsoft Defender for Endpoint nel dispositivo e tocca o fai clic su **Avvia VPN.**

## <a name="co-existence-of-multiple-vpn-profiles"></a>Coesistenza di più profili VPN

Apple iOS non supporta più VPN a livello di dispositivo per essere attive contemporaneamente. Anche se nel dispositivo possono esistere più profili VPN, può essere attiva una sola VPN alla volta.


## <a name="configure-compliance-policy-against-jailbroken-devices"></a>Configurare i criteri di conformità per i dispositivi jailbroken

Per proteggere l'accesso ai dati aziendali nei dispositivi iOS jailbroken, è consigliabile configurare i criteri di conformità seguenti in Intune.

> [!NOTE]
> Al momento il rilevamento del jailbreak da parte di Microsoft Defender per Endpoint su iOS è in anteprima. Ti consigliamo di configurare questo criterio come ulteriore livello di difesa contro gli scenari di jailbreak.

Segui i passaggi seguenti per creare un criterio di conformità per i dispositivi jailbroken.

1. In [Microsoft Endpoint Manager di amministrazione,](https://go.microsoft.com/fwlink/?linkid=2109431)vai a **Criteri** di  ->  **conformità dispositivi** Crea  ->  **criterio.** Seleziona "iOS/iPadOS" come piattaforma e fai clic su **Crea.**

    > [!div class="mx-imgBorder"]
    > ![Creare criteri](images/ios-jb-policy.png)

2. Specificare un nome del criterio, ad esempio "Criteri di conformità per Jailbreak".
3. Nella pagina impostazioni di conformità fai clic per espandere la sezione **Integrità** dispositivo e fai clic **su Blocca** per il campo **Dispositivi Jailbroken.**

    > [!div class="mx-imgBorder"]
    > ![Criteri Impostazioni](images/ios-jb-settings.png)

4. Nella sezione *Azione per la non conformità* selezionare le azioni in base ai requisiti e selezionare **Avanti**.

    > [!div class="mx-imgBorder"]
    > ![Azioni dei criteri](images/ios-jb-actions.png)

5. Nella sezione *Assegnazioni* selezionare i gruppi di utenti che si desidera includere per questo criterio e quindi selezionare **Avanti.**
6. Nella sezione **Revisione e creazione** verificare che tutte le informazioni immesse siano corrette e quindi selezionare **Crea**.

## <a name="configure-custom-indicators"></a>Configurare indicatori personalizzati

Defender for Endpoint su iOS consente agli amministratori di configurare indicatori personalizzati anche nei dispositivi iOS. Per ulteriori informazioni su come configurare gli indicatori personalizzati, vedere [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).

> [!NOTE]
> Defender for Endpoint in iOS supporta la creazione di indicatori personalizzati solo per indirizzi IP e URL/domini.

## <a name="report-unsafe-site"></a>Segnala sito non sicuro

I siti Web di phishing rappresentano siti Web attendibili allo scopo di ottenere informazioni personali o finanziarie. Visitare la [pagina Fornire commenti e](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) suggerimenti sulla protezione di rete se si desidera segnalare un sito Web che potrebbe essere un sito di phishing.

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a>Problemi di consumo della batteria in iOS quando è installato Microsoft Defender for Endpoint

L'utilizzo della batteria da parte di un'app viene calcolato da Apple in base a numerosi fattori, tra cui l'utilizzo della CPU e della rete. Microsoft Defender for Endpoint usa una VPN locale/loop-back in background per controllare il traffico Web per eventuali siti Web o connessioni dannose. I pacchetti di rete da qualsiasi app passano attraverso questo controllo e questo causa il calcolo impreciso dell'utilizzo della batteria di Microsoft Defender per Endpoint. Questo dà una falsa impressione all'utente. Il consumo effettivo della batteria di Microsoft Defender for Endpoint è inferiore a quello visualizzato nella pagina Batteria Impostazioni nel dispositivo. Si basa sui test eseguiti nell'app Microsoft Defender for Endpoint per comprendere il consumo della batteria.

Anche la VPN utilizzata è una VPN locale e, a differenza delle VPN tradizionali, il traffico di rete non viene inviato all'esterno del dispositivo.
