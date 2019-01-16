---
title: Preparazione di App per Microsoft gestiti Desktop
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868482"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparazione di App per Microsoft gestiti Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
I clienti Microsoft e Desktop gestiti Microsoft hanno ugualmente critiche e altro ancora responsabilità attorno applicazioni utilizzate con Microsoft Desktop gestiti.

## <a name="microsoft-responsibilities"></a>Responsabilità di Microsoft
**Applicazioni di Office 365** Microsoft fornirà servizi completi per la distribuzione, aggiornamento e il supporto di App specifiche di Office 365. Tutti gli utenti riceveranno il gruppo di fare clic su Office 365 per l'esecuzione, versione a 64 bit di applicazioni incluse nell'immagine del dispositivo in modo che un utente può risultare di produttività di base. Le applicazioni di Project e Visio in della famiglia di prodotti Office 365 vengono concessi in licenza separatamente.  Microsoft Desktop gestiti fornirà gruppi di distribuzione che consente all'amministratore IT di gestire le licenze e distribuire le applicazioni in modo appropriato per la propria organizzazione. Microsoft dovranno supportare gli utenti finali di queste applicazioni tramite i canali di supporto Desktop gestiti Microsoft.

**Applicazioni line-of-business** Microsoft offre gli strumenti per amministratori IT di gestire e distribuire applicazioni line-of-business (LOB) per gli utenti finali come parte del prodotto Intune. Microsoft supporterà problemi relativi alla distribuzione di applicazioni come descritto in [applicazioni Line-of-business](#line-of-business-applications) 

**Eseguire la distribuzione con Intune** Intune verrà collegato all' **Archivio di Microsoft per le aziende** durante onboarding Desktop gestiti Microsoft che consente di App ottenuti da distribuire tramite Intune. Microsoft verrà inoltre distribuire la versione del portale aziendale basata sul web per utenti finali in modo che gli amministratori IT possono offrire un'esperienza self-service per gli utenti finali.

**Gestione App** Microsoft può identificare le applicazioni con restrizioni che non sono appropriate per il luogo di lavoro moderno causa l'impatto del sistema. Quando viene identificata di un'applicazione Microsoft provvederà a darne comunicazione cliente e sarà necessario tale applicazione da rimuovere dal tenant. 

Per ulteriori informazioni su comportamenti di app con restrizioni e app requisiti, vedere [requisiti di app Desktop gestiti Microsoft](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Responsabilità del cliente
La famiglia di prodotti Office 365 core per le offerte di produttività di Microsoft e incluso nella licenza 365 Microsoft per tutti gli utenti di Desktop gestiti Microsoft. Mentre Microsoft distribuisce, aggiornamenti e supporta le applicazioni di Office per i dispositivi Desktop gestiti Microsoft esistono alcune aree per cui il cliente è responsabile.
- **Assegnare licenze** - sono responsabili dell'assegnazione di licenze appropriate per gli utenti finali per Office 365. 
- **Aggiungere utenti ai gruppi di sicurezza** - per i clienti con gli utenti hanno bisogno di progetto o Visio, è necessario l'amministratore IT aggiungere gli utenti ai gruppi di distribuzione appropriata. Gli amministratori IT sono anche responsabili della gestione del ciclo di vita per gli utenti finali. 
- **Distribuzione di Office 365 componenti aggiuntivi** - sono responsabili della distribuzione di un plug-in per la famiglia di prodotti Office 365 che vengono considerate necessarie. 

Poiché le applicazioni line-of-business (LOB) sono univoche per ogni cliente, i clienti sono responsabili della gestione di tutte le applicazioni all'interno dell'organizzazione non distribuito da Microsoft. Includono:
- Per decidere quali App necessarie e chi deve
- Assegnazione di App per gli utenti
- Creare e gestire gruppi di Azure Active Directory (AD) per la gestione delle assegnazioni di app 

Il cliente deve caricare applicazioni LOB Intune. Sono quindi responsabile della distribuzione, l'aggiornamento e rimozione delle autorizzazioni per le applicazioni tramite i rispettivi cicli di vita, nonché gestire il supporto per le App per gli utenti.

## <a name="office-applications"></a>Applicazioni di Office
Come parte di licenza Microsoft 365 E5, Office 365 Standard Suite (64 Bit) è distribuito da Microsoft. 

Per ulteriori informazioni, vedere [le tecnologie Microsoft Desktop gestiti](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Applicazioni line-of-business
In questa tabella sono riepilogate le responsabilità in fasi diverse per le applicazioni line-of-business (LOB). 

Elementi di lavoro di applicazione |    Cliente    | Microsoft
--- | --- | ---
**Onboarding App** |  |
Identificare le applicazioni necessari per gruppi di utenti di destinazione   | ![sì](images/checkmark.png)  |
Creare e gestire gruppi di Azure Active Directory per la distribuzione di applicazioni | ![sì](images/checkmark.png) |   
**Creazione del pacchetto App** |  |
Pacchetto App per soddisfare Intune distribuzione standard |  ![sì](images/checkmark.png) |  
Caricare apps Intune | ![sì](images/checkmark.png)     |
Test App nell'ambiente Desktop gestito Microsoft |    ![sì](images/checkmark.png) |  
Applicazioni di test con gli utenti finali    | ![sì](images/checkmark.png) |    
**Distribuzione** | |
Gestire e assegnare gli utenti alle applicazioni  | ![sì](images/checkmark.png)  |
Strumenti di distribuzione Intune consente di eseguire applicazioni ai client remoti| |   ![sì](images/checkmark.png)
Identificare e distribuire gli aggiornamenti delle applicazioni tramite Intune | ![sì](images/checkmark.png)    |
Applicazioni procedere alla disinstallazione e remove quando sono stato ritirati    | ![sì](images/checkmark.png) |    
**Gestione** | |
Procurarsi e assegnare licenze |   ![sì](images/checkmark.png)     |
Fornire il supporto degli utenti finali per le applicazioni line-of-business  | ![sì](images/checkmark.png) |
Gestire le impostazioni delle applicazioni in remoto    | ![sì](images/checkmark.png) |

Per informazioni su requisiti delle applicazioni LOB, vedere [requisiti per le applicazioni Desktop gestiti Microsoft](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Distribuzione delle applicazioni Intune
Gestione delle applicazioni può essere gestita tramite il portale di amministrazione di Desktop gestiti Microsoft o tramite il portale Intune. Portale di gestione app dell'Intune Mostra le applicazioni distribuite per Windows, Android e iOS. Portale di amministrazione di Desktop gestiti Microsoft limita la visualizzazione per le applicazioni di Windows 10. Entrambi sono disponibili tramite il portale di Azure. 
* [Nozioni fondamentali di gestione app Intune](https://docs.microsoft.com/intune/app-management)
* [Aggiungere applicazioni al Intune](https://docs.microsoft.com/intune/app-management)
   * [Aggiungere un'applicazione line-of-business](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Aggiungere applicazioni Win32 al Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Aggiungere applicazioni web](https://docs.microsoft.com/intune/web-app)
* [Distribuzione di App](https://docs.microsoft.com/intune/apps-deploy)
   * [Distribuzione di applicazioni per Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Portale della società
   * [Distribuire il portale aziendale](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configurare l'applicazione del portale aziendale](https://docs.microsoft.com/intune/company-portal-app)
