---
title: Configurazione del dispositivo
description: Informazioni sui criteri predefiniti applicati ai dispositivi Desktop gestiti Microsoft.
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868726"
---
# <a name="device-configuration"></a>Configurazione del dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando un nuovo dispositivo Desktop gestiti Microsoft provisioning, è verificare che la configurazione corretta, ottimizzata per Microsoft Desktop gestiti, sul posto. Include un set di criteri predefiniti che sono impostati come parte del processo di on-boarding. Per evitare conflitti, questi criteri non devono essere modificati. 

Dispositivi aggiunti con un'immagine della firma e quindi aggiungerlo al dominio di Azure Active Directory quando il primo utente effettua l'accesso. Il dispositivo installerà automaticamente i criteri necessari e le applicazioni senza l'intervento IT necessario.

## <a name="why-mdm-over-group-policy"></a>Perché MDM tramite criteri di gruppo

Esistono alcuni motivi per utilizzare la gestione dei dispositivi mobili (MDM) invece di criteri di gruppo:

- Sicurezza - MDM criteri sono più sicuri il mondo moderno. Criteri di gruppo sono progettato per l'utilizzo con identità locale mentre MDM progettato per l'utilizzo con la gestione delle identità cloud (Azure Active Directory).
- Affidabilità - MDM criteri offrono più affidabile distribuzione dei criteri. Inoltre, le impostazioni di MDM sovrascrivono criteri oggetto Criteri di gruppo (GPO). A partire da Windows 10, versione 1803, impostazioni MDM assegnare la priorità sui valori dei criteri di gruppo, che supporta i clienti che passano alla gestione moderno. 
- Allineati con la visione del Desktop gestiti Microsoft - fornisce più completo monitoring nella distribuzione di criteri e supporta basata sui gruppi approccio alla gradualmente modifiche ai criteri implementazione con capacità di Sospendi / Riprendi distribuzione quando necessario.

Per ulteriori informazioni, vedere [Gestione dei dispositivi mobili](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Criteri predefiniti

In questa tabella vengono evidenziati i criteri predefiniti che vengono applicati a tutti i dispositivi Desktop gestiti Microsoft durante il provisioning di dispositivi. Tutti i rilevate le modifiche non approvate dal Team di operazioni di Desktop gestiti Microsoft per gli oggetti gestiti da Desktop gestiti Microsoft verranno ripristinate.

Criterio | Descrizione
--- | ---
Base per la sicurezza | [Base per la sicurezza Microsoft](https://docs.microsoft.com/windows/device-security/windows-security-baselines) per MDM è configurato per tutti i dispositivi Desktop gestiti Microsoft. Questa linea di base è la configurazione standard del settore. Viene rilasciata pubblicamente, testato ed è stata controllata da esperti di protezione di Microsoft per mantenere i dispositivi Desktop gestiti Microsoft e la protezione di applicazioni nell'area di lavoro moderno.<br><br>Per attenuare le minacce in continua evoluzione scenario dei rischi di protezione, la base per la sicurezza Microsoft sarà aggiornati e distribuiti nei dispositivi Desktop gestiti Microsoft con l'aggiornamento ogni caratteristica Windows 10.<br><br>Per ulteriori informazioni, vedere [Security baseline per Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Desktop gestiti Microsoft consiglia di modello di sicurezza | Un insieme di modifiche alla linea di base della protezione consigliate ottimizzare l'esperienza utente.  Queste modifiche sono documentate negli [Security Addendum](#security-addendum). In informazioni aggiuntive al criterio vengono aggiornate in base alle necessità.  
Conformità di dispositivo | Questi criteri sono configurati per impostazione predefinita per tutti i dispositivi Desktop gestiti Microsoft. Un dispositivo viene indicato come non conforme quando viene soddisfatta non una delle condizioni di sicurezza seguenti:<br>-BitLocker crittografia del dispositivo abilitato per proteggere i dati nei dispositivi. Per ulteriori informazioni, vedere [Panoramica dei dispositivi crittografia BitLocker in Windows 10.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-Avvio protetta attivata e applicata, per convalidare le immagini del firmware nei dispositivi prima che possono essere eseguite. Per ulteriori informazioni, vedere [Panoramica della crittografia Secure avvio e il dispositivo.](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-Dispositivo Desktop gestiti Microsoft richiede la password per l'accesso.
Distribuzione degli aggiornamenti | Utilizzare Windows Update per le aziende (WUfB) per eseguire la graduale distribuzione degli aggiornamenti software. Gli amministratori IT non possono modificare le impostazioni per i criteri di gruppo di distribuzione. Per ulteriori informazioni sulla distribuzione basata su gruppo, vedere [modalità di gestione degli aggiornamenti](../working-with-managed-desktop/updates.md).
Telemetria | Dispositivi impostano inviare dati di diagnostica avanzati a Microsoft in un identificatore commerciale noto. Come parte di Microsoft Desktop gestito, gli amministratori IT non possono modificare queste impostazioni. Per i clienti in genere aree di protezione dei dati nella regolazione (PILR), gli utenti finali possono ridurre il livello di dati di diagnostica fornito, ma vi sarà una riduzione del servizio. Desktop gestiti Microsoft, ad esempio, sarà possibile raccogliere i dati necessari per eseguire un'iterazione su criteri e impostazioni per adattarlo alle esigenze di protezione e le prestazioni. Per ulteriori informazioni, vedere [dati di diagnostica configurare Windows nella propria organizzazione.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Supplemento di sicurezza

 In questa sezione vengono descritti i criteri che verranno distribuiti come aggiuntive per i criteri di Desktop gestiti Microsoft standard. In [criteri predefiniti](#default-policies)sono elencati i criteri standard. Questa configurazione è progettata con servizi finanziari e altamente regolamentato settori presente: ottimizzazione per l'orientamento più sicuro, mantenendo la produttività degli utenti.

 ### <a name="additional-security-policies"></a>Criteri di sicurezza aggiuntive

 Questi criteri vengono aggiunte per aumentare la protezione per altamente regolamentato settori. 
 - **Elenco Consenti applicazioni**: app deve essere considerato attendibile dall'organizzazione per l'esecuzione su dispositivi Desktop gestiti Microsoft. In questo modo un ambiente bloccato. Le applicazioni che devono essere onboarded devono essere comunicate al Team di operazioni di Desktop gestiti Microsoft. Per ulteriori informazioni, vedere [Windows Defender dispositivo Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Monitoraggio della protezione**: Microsoft dovrà monitorare dispositivi mediante [La protezione di Windows Defender avanzate rischio](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Se è possibile rilevare una minaccia, Microsoft provvederà a darne comunicazione del cliente, isolare il dispositivo e risolvere il problema in modalità remota. 

