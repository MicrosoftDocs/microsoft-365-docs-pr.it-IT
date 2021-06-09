---
title: Passaggio 5. Gestione di dispositivi e app per i Microsoft 365 per i tenant aziendali
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
description: Distribuisci l'opzione corretta per la gestione di dispositivi e app per Microsoft 365 tenant.
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050995"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 5. Gestione di dispositivi e app per i Microsoft 365 per i tenant aziendali

Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e l'uso di app in tali dispositivi all'interno dell'organizzazione con gestione dei dispositivi mobili (MDM) e gestione delle applicazioni mobili (MAM). Puoi gestire dispositivi iOS, Android, macOS e Windows per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati. Ad esempio, è possibile impedire l'invio di messaggi di posta elettronica a persone esterne all'organizzazione o isolare i dati dell'organizzazione dai dati personali nei dispositivi personali del lavoratore.

Ecco un esempio di convalida e gestione degli utenti, dei loro dispositivi e dell'uso di app per la produttività locale e cloud come Microsoft Teams.

![Convalida e gestione di utenti, dispositivi e app](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Per proteggere e proteggere le risorse dell'organizzazione, Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e il relativo accesso alle app. Esistono due opzioni per la gestione dei dispositivi:

- Microsoft Intune, una soluzione completa per la gestione di dispositivi e app per le aziende.
- Dispositivi mobili e sicurezza di base, che è un sottoinsieme dei servizi intune inclusi in tutti i prodotti Microsoft 365 per la gestione dei dispositivi nell'organizzazione. Per ulteriori informazioni, vedere [Capabilities of Basic Mobility and Security.](../admin/basic-mobility-security/capabilities.md)

Se si dispone di Microsoft 365 E3 o E5, è consigliabile usare Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Puoi usare [Microsoft Intune](/mem/intune/fundamentals/planning-guide) per gestire l'accesso all'organizzazione usando MDM o MAM. MDM è quando gli utenti "registrano" i propri dispositivi in Intune. Dopo la registrazione, un dispositivo gestito può ricevere i criteri, le regole e le impostazioni dell'organizzazione. Ad esempio, puoi installare app specifiche, creare criteri password, installare una connessione VPN e altro ancora.

Gli utenti con i propri dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione. È comunque necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, puoi proteggere le tue app usando MAM. Ad esempio, puoi usare un criterio MAM che richiede a un utente di immettere un PIN quando accede a un SharePoint nel dispositivo.

Determinerai anche come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione. Potresti voler trattare i dispositivi in modo diverso, a seconda del loro utilizzo.

## <a name="identity-and-device-access-configurations"></a>Configurazioni di identità e accesso dei dispositivi

Microsoft fornisce una serie di configurazioni per [l'accesso a identità](../security/defender-365-security/microsoft-365-policies-configurations.md) e dispositivi per garantire una forza lavoro sicura e produttiva. Queste configurazioni includono l'uso di:

- Criteri di Accesso condizionale di Azure AD
- Microsoft Intune conformità dei dispositivi e criteri di protezione delle app
- Criteri di rischio utente di Azure AD Identity Protection
- Criteri aggiuntivi delle app cloud

Ecco un esempio dell'applicazione di queste impostazioni e criteri per convalidare e limitare gli utenti, i loro dispositivi e l'uso di app per la produttività locale e cloud come Microsoft Teams.

![Configurazioni di identità e accesso ai dispositivi per requisiti e restrizioni per gli utenti, i dispositivi e l'uso delle app](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Per l'accesso ai dispositivi e la gestione delle app, usa le configurazioni in questi articoli:

- [Prerequisiti](../security/defender-365-security/identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Risultati del passaggio 5

Per la gestione di dispositivi e app per il tenant di Microsoft 365, hai determinato le impostazioni e i criteri di Intune per convalidare e limitare gli utenti, i loro dispositivi e il loro uso di app di produttività locali e cloud.

Ecco un esempio di tenant con gestione di app e dispositivi Intune con i nuovi elementi evidenziati.

![Esempio di tenant con gestione di app e dispositivi Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

In questa illustrazione, il tenant ha:

- Dispositivi di proprietà dell'organizzazione registrati in Intune.
- Criteri dei dispositivi e delle app di Intune per i dispositivi registrati e personali.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Manutenzione continua per la gestione di dispositivi e app

Su base continuativa, potrebbe essere necessario: 

- Gestire la registrazione dei dispositivi.
- Rivedi le impostazioni e i criteri per altre app, dispositivi e requisiti di sicurezza.