---
title: Preparazione delle app per Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289067"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparazione delle app per Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
I clienti Microsoft e Microsoft Managed Desktop presentano responsabilità altrettanto critiche e diverse rispetto alle applicazioni utilizzate con Microsoft Managed Desktop.

## <a name="microsoft-responsibilities"></a>Responsabilità di Microsoft
**App di Office 365** Microsoft fornirà servizi completi per la distribuzione, l'aggiornamento e il supporto di specifiche app di Office 365. Tutti gli utenti riceveranno il set di base di Office 365 fare clic per eseguire, versione a 64 bit delle applicazioni incluse nell'immagine del dispositivo in modo che un utente possa rapidamente diventare produttivo. Le applicazioni di Project e Visio nella famiglia di prodotti Office 365 sono concessi in licenza separatamente.  Microsoft Managed Desktop fornirà ai gruppi di distribuzione che consentono all'amministratore IT di gestire le licenze e distribuire queste applicazioni in modo appropriato per la propria organizzazione. Microsoft sosterrà gli utenti finali di queste applicazioni tramite i canali di supporto di Microsoft Managed Desktop.

**App line-of-business** Microsoft fornisce strumenti per gli amministratori IT per la gestione e la distribuzione di applicazioni line-of-business (LOB) per gli utenti finali come parte del prodotto Intune. Microsoft sosterrà i problemi di distribuzione delle applicazioni come descritto in [applicazioni line-of-business](#line-of-business-applications) 

**Distribuire con Intune** Intune verrà collegato a **Microsoft Store for business** durante l'onboardIng di Microsoft Managed Desktop, consentendo l'implementazione delle app procurate tramite Intune. Microsoft distribuirà anche l'applicazione portale aziendale da Microsoft Store agli utenti finali in modo che gli amministratori IT possano fornire un'esperienza self-service per gli utenti finali.

**Gestione delle app** Microsoft può identificare applicazioni limitate che non sono adatte per il luogo di lavoro moderno a causa dell'impatto del sistema. Quando una tale applicazione viene identificata, Microsoft notificherà il cliente e l'applicazione dovrà essere rimossa dal tenant. 

Per ulteriori informazioni sui comportamenti delle app con restrizioni e sui requisiti delle app, vedere requisiti delle app di [Microsoft managEd desktop](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Responsabilità dell'utente
La famiglia di prodotti Office 365 è essenziale per le offerte di produttività di Microsoft ed è inclusa nella licenza di Microsoft 365 per tutti gli utenti di Microsoft Managed Desktop. Mentre Microsoft distribuisce, aggiorna e supporta le applicazioni di Office per i dispositivi Microsoft Managed Desktop, esistono ancora alcune aree per cui il cliente è responsabile.
- **Assegnare le licenze** : i clienti sono responsabili dell'assegnazione delle licenze appropriate agli utenti finali per Office 365. 
- **Aggiungere utenti ai gruppi di sicurezza** : per i clienti con utenti che hanno bisogno di Project o Visio, l'amministratore IT deve aggiungere tali utenti ai gruppi di distribuzione corretti. Gli amministratori IT sono anche responsabili della gestione della fine della vita per gli utenti. 
- **Deploy office 365 Add ons** -i clienti sono responsabili della distribuzione di qualsiasi plug-in per la famiglia di prodotti Office 365 che sono considerati necessari. 

Poiché le app line-of-business (LOB) sono univoci per ogni cliente, i clienti sono responsabili della gestione di tutte le applicazioni all'interno dell'organizzazione non distribuite da Microsoft. Ciò include:
- Decidere quali app sono necessarie e chi ne ha bisogno
- Assegnazione di app a tali utenti
- Creare e gestire gruppi di Azure Active Directory (AD) per la gestione delle assegnazioni delle app 

Il cliente deve caricare le app LOB in Intune. Sono quindi responsabili per la distribuzione, l'aggiornamento e la rimozione delle autorizzazioni per le applicazioni nei rispettivi ciclo di vita, nonché la gestione del supporto per queste app per i propri utenti.

## <a name="office-applications"></a>Applicazioni di Office
Come parte della licenza Microsoft 365 E5, la famiglia di prodotti Office 365 standard (64 bit) è distribuita da Microsoft. 

Per informazioni dettagliate, vedere [Microsoft managEd Desktop Technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Applicazioni line-of-business
In questa tabella vengono riepilogate le responsabilità nelle diverse fasi per le applicazioni line-of-business (LOB). 

Elementi di lavoro dell'applicazione |    Cliente    | Microsoft
--- | --- | ---
**App onboarding** |  |
Identificare le applicazioni necessarie per i gruppi di utenti di destinazione   | ![sì](images/checkmark.png)  |
Creare e gestire gruppi di Azure AD per la distribuzione di app | ![sì](images/checkmark.png) |   
**Pacchetti app** |  |
App del pacchetto per rispondere agli standard di distribuzione di Intune |  ![sì](images/checkmark.png) |  
Caricare le app in Intune | ![sì](images/checkmark.png)     |
Testare le app nell'ambiente desktop Microsoft gestito |    ![sì](images/checkmark.png) |  
Testare le app con gli utenti finali    | ![sì](images/checkmark.png) |    
**Distribuzione** | |
Gestione e assegnazione degli utenti alle applicazioni  | ![sì](images/checkmark.png)  |
Gli strumenti di distribuzione di Intune offrono applicazione ai client remoti| |   ![sì](images/checkmark.png)
Identificare e distribuire gli aggiornamenti delle applicazioni tramite Intune | ![sì](images/checkmark.png)    |
Disinstallare e rimuovere le applicazioni quando sono state ritirate    | ![sì](images/checkmark.png) |    
**Gestione** | |
ProCurarsi e assegnare licenze |   ![sì](images/checkmark.png)     |
Fornire il supporto per gli utenti finali per le app line-of-business  | ![sì](images/checkmark.png) |
Gestire le impostazioni delle app in remoto    | ![sì](images/checkmark.png) |

Per informazioni sui requisiti delle applicazioni LOB, vedere [requisiti delle applicazioni di Microsoft managEd desktop](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Distribuzione di applicazioni di Intune
La gestione delle applicazioni può essere gestita tramite il portale di amministrazione di Microsoft Managed Desktop oppure tramite il portale di Intune. Il portale di gestione delle app di Intune Visualizza le applicazioni distribuite per Windows, Android e iOS. Il portale di amministrazione di Microsoft Managed Desktop limita la visualizzazione alle applicazioni Windows 10. Entrambi sono disponibili tramite il portale di Azure. 
* [Nozioni fondamentali sulla gestione delle app di Intune](https://docs.microsoft.com/intune/app-management)
* [Aggiungere app a Intune](https://docs.microsoft.com/intune/app-management)
   * [Aggiungere un'app line-of-business](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Aggiungere le app Win32 a Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Aggiungere applicazioni Web](https://docs.microsoft.com/intune/web-app)
* [Distribuire le app](https://docs.microsoft.com/intune/apps-deploy)
   * [Distribuire le app a Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Portale aziendale
   * [Distribuire il portale aziendale](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configurare l'app portale aziendale](https://docs.microsoft.com/intune/company-portal-app)
