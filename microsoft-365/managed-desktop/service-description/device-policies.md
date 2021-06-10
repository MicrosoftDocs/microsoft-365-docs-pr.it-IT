---
title: Configurazione delle periferiche
description: Informazioni sui criteri predefiniti applicati Microsoft Managed Desktop dispositivi.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920493"
---
# <a name="device-configuration"></a>Configurazione delle periferiche


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

Quando viene configurato Microsoft Managed Desktop nuovo dispositivo, ci assicuriamo che abbia la configurazione giusta ottimizzata per Microsoft Managed Desktop. Tale configurazione include un set di criteri predefiniti impostati come parte del processo di onboarding. Questi criteri vengono recapitati con Gestione dispositivi mobili (MDM, Mobile Device Management) quando possibile. Per altre informazioni, vedi [Gestione dei dispositivi mobili.](/windows/client-management/mdm/) 

>[!NOTE]
>Per evitare conflitti, non modificare questi criteri.

I dispositivi arriveranno con un'immagine della firma e quindi verranno Azure Active Directory dominio quando il primo utente esegue l'accesso. Il dispositivo installerà automaticamente le applicazioni e i criteri necessari senza alcun intervento da parte del personale IT.

## <a name="default-policies"></a>Criteri predefiniti

Questa tabella evidenzia i criteri predefiniti applicati a tutti i dispositivi Microsoft Managed Desktop durante il provisioning dei dispositivi. Tutte le modifiche rilevate non approvate dal Microsoft Managed Desktop Operations Team sugli oggetti gestiti Microsoft Managed Desktop verranno ripristinate.

Criterio | Descrizione
--- | ---
Baseline di sicurezza | [Microsoft security baseline](/windows/device-security/windows-security-baselines) for MDM è configurato per tutti i Microsoft Managed Desktop mobili. Questa linea di base è la configurazione standard del settore. Viene rilasciato pubblicamente, ben testato ed è stato esaminato dagli esperti di sicurezza Microsoft per mantenere sicuri i dispositivi e le app Microsoft Managed Desktop nell'ambiente di lavoro moderno. <br><br>Per ridurre le minacce nel panorama delle minacce alla sicurezza in continua evoluzione, la linea di base della sicurezza Microsoft verrà aggiornata e distribuita nei dispositivi Microsoft Managed Desktop con ogni aggiornamento delle funzionalità Windows 10 sicurezza.<br><br>Per ulteriori informazioni, vedere [Windows di sicurezza](/windows/security/threat-protection/windows-security-baselines).
Microsoft Managed Desktop di sicurezza consigliato | Un set di modifiche consigliate alla linea di base della sicurezza che ottimizzano l'esperienza utente.  Queste modifiche sono documentate nel [Security Addendum.](#security-addendum) Gli aggiornamenti al criterio addendum vengono eseguiti in base alle esigenze.  
Distribuzione degli aggiornamenti | Utilizzare Windows Update for Business per eseguire la distribuzione graduale degli aggiornamenti software. Gli amministratori IT non possono modificare le impostazioni per i criteri di gruppo di distribuzione. Per ulteriori informazioni sulla distribuzione basata su gruppi, vedere [Come vengono gestiti](updates.md)gli aggiornamenti in Microsoft Managed Desktop .
Connessioni a consumo | Per impostazione predefinita, gli aggiornamenti su connessioni a consumo ,ad esempio le reti LTE, sono disattivati, anche se ogni utente può attivare in modo indipendente questa funzionalità in Impostazioni > **Aggiornamenti > Opzioni avanzate**. Se vuoi consentire a tutti gli utenti di abilitare gli aggiornamenti su connessioni [a](../working-with-managed-desktop/admin-support.md)consumo, invia una richiesta di modifica che attiverà questa impostazione per tutti i dispositivi.
| Conformità dispositivo | Questi criteri sono configurati per tutti Microsoft Managed Desktop dispositivi. Un dispositivo viene segnalato come non conforme quando deriva dalla configurazione di sicurezza necessaria.

## <a name="windows-diagnostic-data"></a>Windows di diagnostica

 I dispositivi verranno impostati per fornire dati di diagnostica avanzata a Microsoft in base a un identificatore commerciale noto. Nell'ambito di Microsoft Managed Desktop, gli amministratori IT non possono modificare queste impostazioni. Per i clienti nelle aree del Regolamento generale sulla protezione dei dati (GDPR), gli utenti possono ridurre il livello di dati di diagnostica forniti, ma si ridurrà il servizio. Ad esempio, Microsoft Managed Desktop non sarà in grado di raccogliere i dati necessari per eseguire un'iterazione delle impostazioni e dei criteri per soddisfare al meglio le esigenze di prestazioni e sicurezza. Per ulteriori informazioni, vedere [Configure Windows diagnostic data in your organization.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Addendum per la sicurezza

 In questa sezione vengono descritti i criteri che verranno distribuiti oltre ai criteri Microsoft Managed Desktop standard elencati in [Criteri predefiniti.](#default-policies) Questa configurazione è progettata tenendo conto dei servizi finanziari e dei settori altamente regolamentati, ottimizzando al tempo stesso la massima sicurezza, mantenendo al contempo la produttività degli utenti.

 ### <a name="additional-security-policies"></a>Criteri di sicurezza aggiuntivi

 Questi criteri vengono aggiunti per aumentare la sicurezza per i settori altamente regolamentati. 
 - **Monitoraggio della sicurezza:** Microsoft monitorerà i dispositivi [con Microsoft Defender for Endpoint.](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Se viene rilevata una minaccia, Microsoft invierà una notifica al cliente, isola il dispositivo e correggerà il problema in remoto. 
 - **Disabilitare PowerShell V2:** Microsoft ha rimosso PowerShell V2 nell'agosto 2017. Questa funzionalità è stata disabilitata in tutti Microsoft Managed Desktop dispositivi. Per ulteriori informazioni su questa modifica, vedere [Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).