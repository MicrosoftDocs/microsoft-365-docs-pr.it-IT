---
title: Passaggio 5. Gestione di dispositivi e app per i tenant di Microsoft 365 per le aziende
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuire l'opzione corretta per la gestione di dispositivi e app per i tenant di Microsoft 365.
ms.openlocfilehash: 96412cb52540e87341fa67e20382951db7becfbe
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406373"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 5. Gestione di dispositivi e app per i tenant di Microsoft 365 per le aziende

Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e l'uso delle app in tali dispositivi all'interno dell'organizzazione con gestione di dispositivi mobili (MDM) e gestione di applicazioni mobili (MAM). Puoi gestire i dispositivi iOS, Android, macOS e Windows per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati. Ad esempio, è possibile impedire l'invio di messaggi di posta elettronica a persone esterne all'organizzazione o isolare i dati dell'organizzazione dai dati personali nei dispositivi personali dei lavoratori.

Ecco un esempio di convalida e gestione degli utenti, dei loro dispositivi e dell'uso di app di produttività locali e cloud come Microsoft Teams.

![Convalida e gestione di utenti, dispositivi e app](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Per proteggere e proteggere le risorse dell'organizzazione, Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e il loro accesso alle app. Esistono due opzioni per la gestione dei dispositivi:

- Microsoft Intune, una soluzione completa per la gestione di dispositivi e app per le aziende.
- Sicurezza e mobilità di base, che è un sottoinsieme dei servizi intune inclusi in tutti i prodotti Microsoft 365 per la gestione dei dispositivi nell'organizzazione. Per ulteriori informazioni, vedere [Capabilities of Basic Mobility and Security.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)

Se si dispone di Microsoft 365 E3 o E5, è consigliabile usare Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Si usa [Microsoft Intune per](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) gestire l'accesso all'organizzazione tramite MDM o MAM. MDM si verifica quando gli utenti "registrano" i propri dispositivi in Intune. Dopo la registrazione, un dispositivo è gestito e può ricevere i criteri, le regole e le impostazioni dell'organizzazione. Ad esempio, puoi installare app specifiche, creare criteri password, installare una connessione VPN e altro ancora.

Gli utenti con i propri dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione. È comunque necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, puoi proteggere le tue app usando MAM. Ad esempio, è possibile utilizzare un criterio MAM che richiede a un utente di immettere un PIN quando accede a SharePoint nel dispositivo.

Potrai anche determinare come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione. Potresti voler trattare i dispositivi in modo diverso, a seconda del loro uso.

## <a name="identity-and-device-access-configurations"></a>Configurazioni di identità e accesso dei dispositivi

Microsoft fornisce un set di configurazioni per [l'identità e l'accesso](../security/office-365-security/microsoft-365-policies-configurations.md) ai dispositivi per garantire una forza lavoro sicura e produttiva. Queste configurazioni includono l'uso di:

- Criteri di Accesso condizionale di Azure AD
- Criteri di conformità dei dispositivi e di protezione delle app di Microsoft Intune
- Criteri di rischio utente di Azure AD Identity Protection
- Criteri aggiuntivi delle app cloud

Ecco un esempio dell'applicazione di queste impostazioni e criteri per convalidare e limitare gli utenti, i loro dispositivi e l'uso di app di produttività locali e cloud come Microsoft Teams.

![Configurazioni di identità e accesso ai dispositivi per i requisiti e le restrizioni per gli utenti, i dispositivi e l'uso delle app](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Per l'accesso ai dispositivi e la gestione delle app, usa le configurazioni negli articoli seguenti:

- [Prerequisiti](../security/office-365-security/identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Risultati del passaggio 5

Per la gestione di dispositivi e app per il tenant di Microsoft 365, sono stati determinati le impostazioni e i criteri di Intune per convalidare e limitare gli utenti, i dispositivi e l'uso delle app di produttività locale e cloud.

Ecco un esempio di tenant con gestione di app e dispositivi Intune con i nuovi elementi evidenziati.

![Esempio di tenant con gestione di app e dispositivi Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

In questa figura, il tenant ha:

- Dispositivi di proprietà dell'organizzazione registrati in Intune.
- Criteri di dispositivi e app intune per i dispositivi registrati e personali.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Manutenzione continua per la gestione di dispositivi e app

Su base continuativa, potrebbe essere necessario: 

- Gestire la registrazione del dispositivo.
- Rivedere le impostazioni e i criteri per altre app, dispositivi e requisiti di sicurezza.
