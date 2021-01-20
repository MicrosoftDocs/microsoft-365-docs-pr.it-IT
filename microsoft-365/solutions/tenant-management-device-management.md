---
title: Passaggio 5. Gestione di dispositivi e app per i tenant di Microsoft 365 per Enterprise
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
ms.custom:
- Ent_Solutions
description: Distribuire l'opzione corretta per la gestione di dispositivi e app per i tenant Microsoft 365.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908584"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Passaggio 5. Gestione di dispositivi e app per i tenant di Microsoft 365 per Enterprise

Microsoft 365 for Enterprise include funzionalità che consentono di gestire i dispositivi e l'utilizzo di app su tali dispositivi all'interno dell'organizzazione con la gestione dei dispositivi mobili (MDM) e la gestione delle applicazioni mobili (MAM). È possibile gestire i dispositivi iOS, Android, macOS e Windows per proteggere l'accesso alle risorse dell'organizzazione, inclusi i dati. Ad esempio, è possibile impedire l'invio di messaggi di posta elettronica a persone esterne all'organizzazione o isolare i dati dell'organizzazione dai dati personali dei dispositivi personali del lavoratore.

Di seguito è riportato un esempio di convalida e gestione degli utenti, dei loro dispositivi e del loro utilizzo delle applicazioni locali e di produttività cloud come Microsoft teams.

![Convalida e gestione di utenti, dispositivi e app](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

Per garantire la sicurezza e la protezione delle risorse dell'organizzazione, Microsoft 365 for Enterprise include funzionalità che consentono di gestire i dispositivi e l'accesso alle app. Sono disponibili due opzioni per la gestione dei dispositivi:

- Microsoft Intune, che è una soluzione completa per la gestione di dispositivi e app per le aziende.
- Mobilità e sicurezza di base, un sottoinsieme di servizi di Intune incluso con tutti i prodotti Microsoft 365 per la gestione dei dispositivi nell'organizzazione. Per ulteriori informazioni, vedere [funzionalità di base per dispositivi mobili e sicurezza](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).

Se si dispone di Microsoft 365 E3 o E5, è consigliabile utilizzare Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

È possibile utilizzare [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) per gestire l'accesso all'organizzazione tramite MDM o mam. MDM è il momento in cui gli utenti "iscrivono" i propri dispositivi in Intune. Dopo la registrazione di un dispositivo, si tratta di un dispositivo gestito che può ricevere i criteri, le regole e le impostazioni dell'organizzazione. Ad esempio, è possibile installare app specifiche, creare un criterio password, installare una connessione VPN e altro ancora.

Gli utenti che dispongono di dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione. Tuttavia, è comunque necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, è possibile proteggere le app utilizzando MAM. Ad esempio, è possibile utilizzare un criterio MAM che richiede a un utente di immettere un PIN quando si accede a SharePoint nel dispositivo.

È inoltre possibile determinare come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione. Potrebbe essere opportuno trattare i dispositivi in modo diverso, a seconda dell'utilizzo.

## <a name="identity-and-device-access-configurations"></a>Configurazioni di identità e accesso dei dispositivi

Microsoft fornisce una serie di configurazioni per [l'accesso a identità e dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) per garantire una forza lavoro sicura e produttiva. Tali configurazioni includono l'utilizzo di:

- Criteri di Accesso condizionale di Azure AD
- Criteri di conformità del dispositivo e di protezione delle app di Microsoft Intune
- Criteri di rischio per gli utenti di Azure AD Identity Protection
- Criteri aggiuntivi delle app Cloud

Di seguito è riportato un esempio dell'applicazione di queste impostazioni e dei criteri per convalidare e limitare gli utenti, i propri dispositivi e l'utilizzo delle applicazioni locali e di produttività cloud come Microsoft teams.

![Configurazioni di accesso a identità e dispositivi per i requisiti e le restrizioni degli utenti, dei dispositivi e dell'utilizzo delle app](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Per l'accesso ai dispositivi e la gestione delle app, utilizzare le configurazioni disponibili in questi articoli:

- [Prerequisiti](../security/office-365-security/identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Risultati del passaggio 5

Per la gestione di dispositivi e app per il tenant Microsoft 365, sono state determinate le impostazioni e i criteri di Intune per convalidare e limitare gli utenti, i loro dispositivi e l'utilizzo delle app di produttività locali e cloud.

Di seguito è riportato un esempio di tenant con il dispositivo Intune e la gestione delle app con i nuovi elementi evidenziati.

![Esempio di tenant con dispositivo e gestione delle app di Intune](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

In questa figura, il tenant ha:

- I dispositivi di proprietà dell'organizzazione sono stati registrati in Intune.
- Criteri del dispositivo e delle app di Intune per i dispositivi registrati e personali.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Manutenzione continua per la gestione di dispositivi e app

Su base continuativa, potrebbe essere necessario eseguire le operazioni seguenti: 

- Gestire la registrazione del dispositivo.
- Rivedere le impostazioni e i criteri per le app, i dispositivi e i requisiti di sicurezza aggiuntivi.
