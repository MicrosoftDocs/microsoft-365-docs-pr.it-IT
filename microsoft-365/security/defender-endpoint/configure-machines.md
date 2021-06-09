---
title: Verificare che i dispositivi siano configurati correttamente
description: Configurare correttamente i dispositivi per aumentare la resilienza generale contro le minacce e migliorare la capacità di rilevare e rispondere agli attacchi.
keywords: onboard, gestione di Intune, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, riduzione della superficie di attacco, ASR, baseline di sicurezza
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dccc623bfa6c3f5e8fe4d88ccfafd66d3e53482a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840899"
---
# <a name="ensure-your-devices-are-configured-properly"></a>Verificare che i dispositivi siano configurati correttamente

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Con i dispositivi configurati correttamente, è possibile aumentare la resilienza generale contro le minacce e migliorare la capacità di rilevare e rispondere agli attacchi. La gestione della configurazione della sicurezza garantisce che i dispositivi:

- Onboard to Microsoft Defender for Endpoint
- Soddisfare o superare la configurazione di base di Defender for Endpoint security
- Disporre di mitigazioni strategiche della superficie di attacco

Fai **clic su Gestione** configurazione dal menu di spostamento per aprire la pagina Gestione configurazione dispositivi.

![Pagina Gestione della configurazione della sicurezza](images/secconmgmt_main.png)<br>
*Pagina Gestione configurazione dispositivi*

È possibile tenere traccia dello stato di configurazione a livello di organizzazione e intervenire rapidamente in risposta a una copertura di onboarding scarsa, a problemi di conformità e a mitigazioni della superficie di attacco scarsamente ottimizzate tramite collegamenti diretti e diretti alle pagine di gestione dei dispositivi nel centro sicurezza Microsoft Intune e Microsoft 365.

In questo modo, si trarranno vantaggio da:
- Visibilità completa degli eventi nei dispositivi
- Una solida intelligence sulle minacce e potenti tecnologie di apprendimento dei dispositivi per l'elaborazione di eventi non elaborati e l'identificazione dell'attività di violazione e degli indicatori di minaccia
- Una pila completa di funzionalità di sicurezza configurate per arrestare in modo efficiente l'installazione di installazioni dannose, dirottamento di file di sistema e processo, esfiltrazione dei dati e altre attività di minaccia
- Mitigazioni ottimizzate della superficie di attacco, massimizzando le difese strategiche contro l'attività delle minacce riducendo al minimo l'impatto sulla produttività

## <a name="enroll-devices-to-intune-management"></a>Registrare i dispositivi nella gestione di Intune

La gestione della configurazione dei dispositivi funziona a stretto contatto con la gestione dei dispositivi di Intune per stabilire l'inventario dei dispositivi nell'organizzazione e la configurazione di sicurezza di base. Sarà possibile tenere traccia e gestire i problemi di configurazione nei dispositivi Windows 10 Intune.

Prima di poter verificare che i dispositivi siano configurati correttamente, registrarli nella gestione di Intune. La registrazione di Intune è affidabile e include diverse opzioni di registrazione per Windows 10 dispositivi. Per altre informazioni sulle opzioni di registrazione di Intune, leggi informazioni sulla configurazione della registrazione [per Windows dispositivi](/intune/windows-enroll).

>[!NOTE]
>Per registrare Windows dispositivi in Intune, agli amministratori devono essere già state assegnate licenze. [Per informazioni sull'assegnazione delle licenze per la registrazione dei dispositivi, vedere](/intune/licenses-assign).

>[!TIP] 
>Per ottimizzare la gestione dei dispositivi tramite Intune, [connetti Intune a Defender per Endpoint.](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)

## <a name="obtain-required-permissions"></a>Ottenere le autorizzazioni necessarie
Per impostazione predefinita, solo gli utenti a cui è stato assegnato il ruolo Amministratore globale o Amministratore servizio Intune in Azure AD possono gestire e assegnare i profili di configurazione dei dispositivi necessari per l'onboarding dei dispositivi e la distribuzione della linea di base di sicurezza.

Se sono stati assegnati altri ruoli, verificare di disporre delle autorizzazioni necessarie:

- Autorizzazioni complete per le configurazioni dei dispositivi
- Autorizzazioni complete per le linee di base della sicurezza
- Autorizzazioni di lettura per i criteri di conformità dei dispositivi
- Autorizzazioni di lettura per l'organizzazione

![Autorizzazioni necessarie in Intune](images/secconmgmt_intune_permissions.png)<br>
*Autorizzazioni di configurazione dei dispositivi in Intune*

>[!TIP] 
>Per ulteriori informazioni sull'assegnazione delle autorizzazioni in Intune, [vedere creazione di ruoli personalizzati.](/intune/create-custom-role#to-create-a-custom-role)

## <a name="in-this-section"></a>Contenuto della sezione
Argomento | Descrizione
:---|:---
[Eseguire l'onboarded dei dispositivi in Defender for Endpoint](configure-machines-onboarding.md)| Tenere traccia dello stato di onboarding dei dispositivi gestiti da Intune e dell'onboarding di altri dispositivi tramite Intune. 
[Aumentare la conformità alla linea di base di sicurezza di Defender for Endpoint](configure-machines-security-baseline.md) | Tenere traccia della conformità di base e della non conformità. Distribuire la linea di base per la sicurezza in più dispositivi gestiti da Intune.
[Ottimizzare la distribuzione e i rilevamenti delle regole asr](configure-machines-asr.md) | Esaminare la distribuzione delle regole e ottimizzare i rilevamenti usando gli strumenti di analisi dell'impatto nel centro sicurezza Microsoft 365 sicurezza.

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
