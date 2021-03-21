---
title: Configurazione delle periferiche
description: Informazioni sui criteri predefiniti applicati ai dispositivi Microsoft Managed Desktop.
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

Quando viene configurato un nuovo dispositivo Microsoft Managed Desktop, si garantisce che abbia la configurazione giusta ottimizzata per Microsoft Managed Desktop. Tale configurazione include un set di criteri predefiniti impostati come parte del processo di onboarding. Questi criteri vengono recapitati con Gestione dispositivi mobili (MDM, Mobile Device Management) quando possibile. Per altre informazioni, vedi [Gestione dei dispositivi mobili.](/windows/client-management/mdm/) 

>[!NOTE]
>Per evitare conflitti, non modificare questi criteri.

I dispositivi arriveranno con un'immagine della firma e quindi si aggiungeranno al dominio di Azure Active Directory quando il primo utente accede. Il dispositivo installerà automaticamente le applicazioni e i criteri necessari senza alcun intervento da parte del personale IT.

## <a name="default-policies"></a>Criteri predefiniti

Questa tabella evidenzia i criteri predefiniti applicati a tutti i dispositivi Microsoft Managed Desktop durante il provisioning dei dispositivi. Tutte le modifiche rilevate non approvate da Microsoft Managed Desktop Operations Team per gli oggetti gestiti da Microsoft Managed Desktop verranno ripristinate.

Criteri | Descrizione
--- | ---
Baseline di sicurezza | [La baseline di sicurezza Microsoft](/windows/device-security/windows-security-baselines) per MDM è configurata per tutti i dispositivi Microsoft Managed Desktop. Questa linea di base è la configurazione standard del settore. Viene rilasciato pubblicamente, ben testato ed è stato esaminato dagli esperti di sicurezza Microsoft per mantenere sicuri i dispositivi e le app di Microsoft Managed Desktop nell'ambiente di lavoro moderno. <br><br>Per ridurre le minacce nel panorama delle minacce alla sicurezza in continua evoluzione, la linea di base per la sicurezza Microsoft verrà aggiornata e distribuita nei dispositivi Desktop gestiti Microsoft con ogni aggiornamento delle funzionalità di Windows 10.<br><br>Per altre informazioni, vedi Linee [di base per la sicurezza di Windows.](/windows/security/threat-protection/windows-security-baselines)
Modello di sicurezza consigliato per Microsoft Managed Desktop | Un set di modifiche consigliate alla linea di base della sicurezza che ottimizzano l'esperienza utente.  Queste modifiche sono documentate nel [Security Addendum.](#security-addendum) Gli aggiornamenti al criterio addendum vengono eseguiti in base alle esigenze.  
Distribuzione degli aggiornamenti | Usa Windows Update for Business per eseguire la distribuzione graduale degli aggiornamenti software. Gli amministratori IT non possono modificare le impostazioni per i criteri di gruppo di distribuzione. Per ulteriori informazioni sulla distribuzione basata su gruppi, vedere Come vengono gestiti gli aggiornamenti [in Microsoft Managed Desktop.](updates.md)
Connessioni a consumo | Per impostazione predefinita, gli aggiornamenti su connessioni a consumo (ad esempio reti LTE) sono disattivati, anche se ogni utente può attivare in modo indipendente questa funzionalità in Impostazioni **> Aggiornamenti > Opzioni avanzate.** Se vuoi consentire a tutti gli utenti di abilitare gli aggiornamenti su connessioni [a](../working-with-managed-desktop/admin-support.md)consumo, invia una richiesta di modifica che attiverà questa impostazione per tutti i dispositivi.
| Conformità dispositivo | Questi criteri sono configurati per tutti i dispositivi Microsoft Managed Desktop. Un dispositivo viene segnalato come non conforme quando deriva dalla configurazione di sicurezza necessaria.

## <a name="windows-diagnostic-data"></a>Dati di diagnostica di Windows

 I dispositivi verranno impostati per fornire dati di diagnostica avanzata a Microsoft in base a un identificatore commerciale noto. Come parte di Microsoft Managed Desktop, gli amministratori IT non possono modificare queste impostazioni. Per i clienti nelle aree del Regolamento generale sulla protezione dei dati (GDPR), gli utenti possono ridurre il livello di dati di diagnostica forniti, ma si ridurrà il servizio. Ad esempio, Microsoft Managed Desktop non sarà in grado di raccogliere i dati necessari per eseguire un'iterazione delle impostazioni e dei criteri per soddisfare al meglio le esigenze di prestazioni e sicurezza. Per altre informazioni, vedi [Configurare i dati di diagnostica di Windows nell'organizzazione.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>Addendum per la sicurezza

 In questa sezione vengono descritti i criteri che verranno distribuiti oltre ai criteri standard di Microsoft Managed Desktop elencati in [Criteri predefiniti.](#default-policies) Questa configurazione è progettata tenendo conto dei servizi finanziari e dei settori altamente regolamentati, ottimizzando al tempo stesso la massima sicurezza, mantenendo al contempo la produttività degli utenti.

 ### <a name="additional-security-policies"></a>Criteri di sicurezza aggiuntivi

 Questi criteri vengono aggiunti per aumentare la sicurezza per i settori altamente regolamentati. 
 - **Monitoraggio della sicurezza:** Microsoft monitorerà i dispositivi [con Microsoft Defender for Endpoint.](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) Se viene rilevata una minaccia, Microsoft invierà una notifica al cliente, isola il dispositivo e correggerà il problema in remoto. 
 - **Disabilitare PowerShell V2:** Microsoft ha rimosso PowerShell V2 nell'agosto 2017. Questa funzionalità è stata disabilitata in tutti i dispositivi Microsoft Managed Desktop. Per ulteriori informazioni su questa modifica, vedere [Windows PowerShell 2.0 Deprecation](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/).