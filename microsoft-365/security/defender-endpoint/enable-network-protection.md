---
title: Attivare la protezione di rete
description: Abilitare la protezione di rete con Criteri di gruppo, PowerShell o Gestione dispositivi mobili e Configuration Manager.
keywords: Protezione ANetwork, exploit, sito Web dannoso, ip, dominio, domini, abilitare, attivare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b62659360e990467524ec632968dfea313d0b164
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861672"
---
# <a name="turn-on-network-protection"></a>Attivare la protezione di rete

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[La protezione di](network-protection.md) rete consente di impedire ai dipendenti di utilizzare qualsiasi applicazione per accedere a domini pericolosi che potrebbero ospitare tentativi di phishing, exploit e altri contenuti dannosi su Internet. Puoi controllare [la protezione di rete](evaluate-network-protection.md) in un ambiente di testing per visualizzare quali app verrebbero bloccate prima di abilitarla.

[Ulteriori informazioni sulle opzioni di configurazione del filtro di rete](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Verificare se la protezione di rete è abilitata

Controlla se la protezione di rete è stata abilitata in un dispositivo locale usando l'editor del Registro di sistema.

1. Seleziona il **pulsante Start** nella barra delle applicazioni e digita **regedit** per aprire l'editor del Registro di sistema

2. Scegli **HKEY_LOCAL_MACHINE** dal menu laterale

3. Spostarsi tra i menu annidati fino **a SOFTWARE**  >  **Microsoft**  >  **Windows Defender** Windows Defender Protezione di  >  **rete di Exploit**  >  **Guard**

4. Seleziona **EnableNetworkProtection** per visualizzare lo stato corrente della protezione di rete nel dispositivo

    * 0 o **Disattivato**
    * 1 o **Su**
    * 2 o **Modalità di** controllo
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Abilitare la protezione di rete

Abilitare la protezione di rete utilizzando uno dei metodi seguenti:

* [PowerShell](#powershell)
* [Gestione di dispositivi mobili (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager / Intune](#microsoft-endpoint-manager-formerly-intune)
* [Criteri di gruppo](#group-policy)

### <a name="powershell"></a>PowerShell

1. Digita **powershell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore**
2. Immettere il cmdlet seguente:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Facoltativo: abilitare la funzionalità in modalità di controllo utilizzando il cmdlet seguente:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Utilizzare `Disabled` invece di o per `AuditMode` `Enabled` disattivare la funzionalità.

### <a name="mobile-device-management-mdm"></a>Gestione di dispositivi mobili (MDM)

Usa [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) per abilitare o disabilitare la protezione di rete o abilitare la modalità di controllo.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (in precedenza Intune)

1. Accedere all'Microsoft Endpoint Manager di amministrazione (https://endpoint.microsoft.com)

2. Creare o modificare un profilo di [configurazione di Endpoint Protection](/mem/intune/protect/endpoint-protection-configure)

3. In **Configurazione Impostazioni** nel flusso del profilo, andare a Microsoft Defender Exploit Guard   >  **Filtro** di rete Protezione di  >  **rete**  >  **Abilita** o Controlla **solo**

### <a name="group-policy"></a>Criteri di gruppo

Utilizzare la procedura seguente per abilitare la protezione di rete nei computer aggiunti a un dominio o in un computer autonomo.

1. In un computer autonomo, andare a **Start** e quindi digitare e selezionare **Modifica Criteri di gruppo.**

    *-Or-*

    In un computer di gestione di Criteri di gruppo aggiunto al dominio, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.

3. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **Windows Defender Protezione di rete di Exploit Guard**  >  .

> [!NOTE]
> Nelle versioni precedenti di Windows, il percorso di Criteri di gruppo potrebbe essere "Windows Defender Antivirus" anziché "Antivirus Microsoft Defender".

4. Fai doppio clic **sull'impostazione Impedisci** a utenti e app di accedere a siti Web pericolosi e imposta l'opzione su **Abilitato.** Nella sezione opzioni è necessario specificare una delle opzioni seguenti:
    * **Blocca** - Gli utenti non possono accedere a indirizzi IP e domini dannosi
    * **Disabilita (impostazione predefinita):** la funzionalità Protezione di rete non funziona. Agli utenti non verrà impedito di accedere a domini dannosi
    * **Modalità di** controllo: se un utente visita un dominio o un indirizzo IP dannoso, un evento verrà registrato nel Windows eventi. Tuttavia, all'utente non verrà impedito di visitare l'indirizzo.

> [!IMPORTANT]
> Per abilitare completamente la protezione di rete, devi impostare l'opzione Criteri di gruppo su **Abilitato** e anche selezionare **Blocca** nel menu a discesa delle opzioni.

Verificare che la protezione di rete sia abilitata in un computer locale utilizzando l'editor del Registro di sistema:

1. Selezionare **Start e** digitare **regedit** per aprire l'editor **del Registro di sistema.**

2. Passare a **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. Selezionare **EnableNetworkProtection e** confermare il valore:
   * 0=Off
   * 1=On
   * 2=Controllo

## <a name="see-also"></a>Vedere anche

* [Protezione di rete](network-protection.md)
* [Valutare la protezione di rete](evaluate-network-protection.md)
* [Risolvere i problemi di protezione di rete](troubleshoot-np.md)
