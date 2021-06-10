---
title: Distribuzione con un sistema MDM (Mobile Device Management) diverso per Microsoft Defender per Endpoint su Mac
description: Installare Microsoft Defender per Endpoint su Mac in altre soluzioni di gestione.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, distribuzione, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ca779fc4cc8c40adb25a0e95a9450f59954dc605
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933794"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>Distribuzione con un sistema MDM (Mobile Device Management) diverso per Microsoft Defender for Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>Prerequisiti e requisiti di sistema

Prima di iniziare, vedi la pagina principale di [Microsoft Defender per Endpoint su macOS](microsoft-defender-endpoint-mac.md) per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente.


## <a name="approach"></a>Approccio

> [!CAUTION]

> Attualmente, Microsoft supporta ufficialmente solo Intune e JAMF per la distribuzione e la gestione di Microsoft Defender per Endpoint in macOS. Microsoft non fa alcuna garanzia, espressa o implicita, rispetto alle informazioni fornite di seguito.

Se l'organizzazione usa una soluzione di gestione dei dispositivi mobili (MDM) non ufficialmente supportata, ciò non significa che non sei in grado di distribuire o eseguire Microsoft Defender for Endpoint in macOS.

Microsoft Defender per Endpoint in macOS non dipende da funzionalità specifiche del fornitore. Può essere usato con qualsiasi soluzione MDM che supporti le funzionalità seguenti:

- Distribuisci un file pkg macOS nei dispositivi gestiti.
- Distribuire i profili di configurazione del sistema macOS nei dispositivi gestiti.
- Eseguire uno strumento o uno script arbitrario configurato dall'amministratore nei dispositivi gestiti.

La maggior parte delle soluzioni MDM moderne include queste funzionalità, tuttavia, possono chiamarle in modo diverso.

Puoi tuttavia distribuire Defender senza l'ultimo requisito dell'elenco precedente:

- Non sarà possibile raccogliere lo stato in modo centralizzato
- Se decidi di disinstallare Defender, dovrai accedere al dispositivo client in locale come amministratore

## <a name="deployment"></a>Distribuzione

La maggior parte delle soluzioni MDM usa lo stesso modello per la gestione dei dispositivi macOS, con una terminologia simile. Usa [la distribuzione basata su JAMF](mac-install-with-jamf.md) come modello.

### <a name="package"></a>Pacchetto

Configurare la distribuzione di un [pacchetto dell'applicazione necessario](mac-install-with-jamf.md), con il pacchetto di installazione (wdav.pkg) scaricato [da Microsoft Defender Security Center](mac-install-with-jamf.md).

Per distribuire il pacchetto nell'organizzazione, usa le istruzioni associate alla soluzione MDM.

### <a name="license-settings"></a>Impostazioni delle licenze

Configurare un [profilo di configurazione del sistema](mac-install-with-jamf.md). 

La soluzione MDM può chiamarla come "Profilo Impostazioni personalizzato", poiché Microsoft Defender per Endpoint in macOS non fa parte di macOS.

Usa l'elenco delle proprietà jamf/WindowsDefenderATPOnboarding.plist, che può essere estratto da un pacchetto di onboarding scaricato [da Microsoft Defender Security Center](mac-install-with-jamf.md).
Il sistema potrebbe supportare un elenco di proprietà arbitrario in formato XML. Puoi caricare il file jamf/WindowsDefenderATPOnboarding.plist così come è in questo caso.
In alternativa, potrebbe essere necessario convertire prima l'elenco delle proprietà in un formato diverso.

In genere, il profilo personalizzato ha un ID, un nome o un attributo di dominio. È necessario utilizzare esattamente "com.microsoft.wdav.atp" per questo valore.
MDM lo usa per distribuire il file di impostazioni in **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** in un dispositivo client e Defender usa questo file per caricare le informazioni di onboarding.

### <a name="kernel-extension-policy"></a>Criteri di estensione kernel

Configurare un criterio di estensione KEXT o kernel. Usa l'identificatore del team **UBF8T346G9** per consentire le estensioni del kernel fornite da Microsoft.

> [!CAUTION]
> Se l'ambiente è costituito da dispositivi Apple Silicon (M1), questi computer non devono ricevere profili di configurazione con criteri KEXT.
> Apple non supporta KEXT su questi computer, la distribuzione di tale profilo non riesce nei computer M1.

### <a name="system-extension-policy"></a>Criteri di estensione di sistema

Configurare un criterio di estensione di sistema. Usa l'identificatore del team **UBF8T346G9** e approva gli identificatori bundle seguenti:

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>Criteri di accesso completo al disco

Concedere l'accesso completo al disco ai componenti seguenti:

- Microsoft Defender per endpoint
    - Identificatore: `com.microsoft.wdav`
    - Tipo di identificatore: ID bundle
    - Requisiti del codice: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- Estensione microsoft Defender for Endpoint Security
    - Identificatore: `com.microsoft.wdav.epsext`
    - Tipo di identificatore: ID bundle
    - Requisiti del codice: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>Criteri di estensione di rete

Come parte delle funzionalità di rilevamento e risposta degli endpoint, Microsoft Defender for Endpoint su macOS esamina il traffico socket e segnala queste informazioni al portale Microsoft Defender Security Center remoto. Il criterio seguente consente all'estensione di rete di eseguire questa funzionalità.

- Tipo di filtro: Plug-in
- Identificatore bundle plug-in: `com.microsoft.wdav`
- Identificatore bundle del provider di dati di filtro: `com.microsoft.wdav.netext`
- Requisito designato dal provider di dati di filtro: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- Socket di filtro: `true`

## <a name="check-installation-status"></a>Controllare lo stato di installazione

Eseguire [Microsoft Defender for Endpoint](mac-install-with-jamf.md) in un dispositivo client per controllare lo stato di onboarding.
