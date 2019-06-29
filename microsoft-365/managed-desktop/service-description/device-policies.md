---
title: Configurazione dispositivo
description: Informazioni sui criteri predefiniti applicati ai dispositivi Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4e41494e853b79d843c5365beea7f01c5ca41308
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390483"
---
# <a name="device-configuration"></a>Configurazione dispositivo


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando si esegue il provisioning di un nuovo dispositivo Microsoft Managed Desktop, è necessario garantire che la configurazione corretta, ottimizzata per Microsoft Managed Desktop, sia sul posto. Questo include un insieme di criteri predefiniti che vengono impostati come parte del processo di onboarding. Per evitare conflitti, questi criteri non devono essere modificati. 

I dispositivi arriveranno con un'immagine della firma, quindi aggiungeranno il dominio di Azure Active Directory quando il primo utente accede. Il dispositivo installerà automaticamente i criteri e le applicazioni necessari senza che sia necessario un intervento IT.

## <a name="why-mdm-over-group-policy"></a>Perché MDM su criteri di gruppo

Esistono alcuni motivi per utilizzare la gestione dei dispositivi mobili (MDM) anziché criteri di gruppo:

- Sicurezza-i criteri MDM sono più sicuri nel mondo moderno. Criteri di gruppo è stato creato per funzionare al meglio con l'identità locale, mentre MDM è stato disegnato per funzionare al meglio con Cloud Identity Management (Azure Active Directory).
- Affidabilità: i criteri MDM offrono una distribuzione di criteri più affidabile. Inoltre, le impostazioni MDM sovrascrivono i criteri oggetto Criteri di gruppo (GPO). A partire da Windows 10, versione 1803, le impostazioni MDM avranno la priorità sui valori di criteri di gruppo, che consentono ai clienti di passare alla gestione moderna. 
- Allinea con Microsoft Managed Desktop Vision-fornisce un monitoraggio più completo sulla distribuzione dei criteri e supporta l'approccio basato su gruppo per l'implementazione graduale delle modifiche dei criteri con la possibilità di sospendere/riprendere la distribuzione, se necessario.

Per ulteriori informazioni, vedere [gestione dei dispositivi mobili](https://docs.microsoft.com/windows/client-management/mdm/). 

## <a name="default-policies"></a>Criteri predefiniti

In questa tabella vengono evidenziati i criteri predefiniti applicati a tutti i dispositivi Microsoft Managed Desktop durante il provisioning dei dispositivi. Tutte le modifiche rilevate non approvate dal team Microsoft Managed Desktop Operations per gli oggetti gestiti da Microsoft Managed Desktop verranno ripristinate.

Criteri | Descrizione
--- | ---
Previsione di sicurezza | [Microsoft Security Baseline](https://docs.microsoft.com/windows/device-security/windows-security-baselines) for MDM è configurato per tutti i dispositivi Microsoft Managed Desktop. Questa linea di base è la configurazione standard del settore. È stato rilasciato pubblicamente, testato bene ed è stato recensito dagli esperti di sicurezza di Microsoft per mantenere i dispositivi e le app desktop gestiti da Microsoft protette nei luoghi di lavoro moderni. <br><br>Per attenuare le minacce nel panorama delle minacce di sicurezza in continua evoluzione, la baseline di Microsoft Security verrà aggiornata e distribuita nei dispositivi Microsoft Managed Desktop con ogni aggiornamento delle funzionalità di Windows 10.<br><br>Per ulteriori informazioni, vedere [baseline di sicurezza per Windows 10](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/).
Modello di sicurezza consigliato per Microsoft Managed Desktop | Un set di modifiche consigliate per la linea di base di sicurezza che consente di ottimizzare l'esperienza utente.  Tali modifiche sono documentate nell' [addendum alla sicurezza](#security-addendum). Gli aggiornamenti all'addendum dei criteri si verificano in base alle esigenze.  
Distribuzione degli aggiornamenti | Utilizzare Windows Update for business (WUfB) per eseguire la distribuzione graduale degli aggiornamenti software. Gli amministratori IT non possono modificare le impostazioni per i criteri di gruppo di distribuzione. Per ulteriori informazioni sulla distribuzione basata su gruppo, vedere [How updates are handled](../working-with-managed-desktop/updates.md).
Dati di diagnostica | I dispositivi verranno impostati per fornire dati diagnostici avanzati a Microsoft in base a un identificatore commerciale conosciuto. Come parte di Microsoft Managed Desktop, gli amministratori IT non possono modificare queste impostazioni. Per i clienti nelle aree di regolamentazione generale per la protezione dei dati (GDPR), gli utenti finali possono ridurre il livello di dati diagnostici forniti, ma ci sarà una riduzione del servizio. Ad esempio, Microsoft Managed Desktop non sarà in grado di raccogliere i dati necessari per eseguire un'iterazione su impostazioni e criteri per soddisfare al meglio le esigenze di prestazioni e sicurezza. Per ulteriori informazioni, vedere [configurare i dati di diagnostica di Windows nell'organizzazione.](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>Addendum alla sicurezza

 In questa sezione vengono illustrati i criteri che verranno distribuiti come aggiuntivi per i criteri standard di Microsoft Managed Desktop. I criteri standard sono elencati nei [criteri predefiniti](#default-policies). Questa configurazione è progettata con i servizi finanziari e le industrie altamente regolamentate in mente: ottimizzazione per la posizione più sicura, mantenendo la produttività degli utenti.

 ### <a name="additional-security-policies"></a>Criteri di sicurezza aggiuntivi

 Questi criteri vengono aggiunti per aumentare la sicurezza per le industrie altamente regolamentate. 
 - **Elenco delle app**consentite: le app devono essere considerate attendibili dall'organizzazione per l'esecuzione su dispositivi Microsoft Managed Desktop. In questo modo viene fornito un ambiente bloccato. Tutte le app che devono essere onboarded devono essere comunicate al team di Operations di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Windows Defender Device Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide).
 - **Monitoraggio della sicurezza**: Microsoft controllerà i dispositivi con [Windows Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection). Se viene rilevata una minaccia, Microsoft invierà una notifica al cliente, isolerà il dispositivo e rettificherà il problema in remoto. 
 - **Disabilitare PowerShell V2**: Microsoft è obsoleto PowerShell v2 nell'agosto 2017. Questa funzionalità è stata disattivata su tutti i dispositivi Microsoft Managed Desktop. Per ulteriori informazioni su questa modifica, vedere [Deprecation di Windows PowerShell 2,0](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).
