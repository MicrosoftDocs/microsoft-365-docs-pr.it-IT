---
title: Preparazione di App per Microsoft gestiti Desktop
description: ''
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868482"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparazione di App per Microsoft gestiti Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
I clienti Microsoft e Desktop gestiti Microsoft hanno ugualmente critiche e altro ancora responsabilità attorno applicazioni utilizzate con Microsoft Desktop gestiti.

## <a name="microsoft-responsibilites"></a>Microsoft responsibilites
**Applicazioni di Office 365** Microsoft fornirà servizi completi per la distribuzione, aggiornamento e il supporto di App specifiche di Office 365. Tutti gli utenti riceveranno il gruppo di fare clic su Office 365 per l'esecuzione, versione a 64 bit di applicazioni incluse nell'immagine del dispositivo in modo che un utente può risultare di produttività di base. Le applicazioni di Project e Visio in della famiglia di prodotti Office 365 vengono concessi in licenza separatamente.  Microsoft Desktop gestiti fornirà gruppi di distribuzione che consente all'amministratore IT di gestire le licenze e distribuire le applicazioni in modo appropriato per la propria organizzazione. Microsoft dovranno supportare gli utenti finali di queste applicazioni tramite i canali di supporto Desktop gestiti Microsoft.

**Applicazioni line-of-business** Microsoft offre gli strumenti per amministratori IT di gestire e distribuire le applicazioni Line-of-Business per gli utenti finali come parte del prodotto Intune. Microsoft supporterà problemi relativi alla distribuzione di applicazioni come descritto in [applicazioni Line-of-business](#line-of-business-applications) 

**Eseguire la distribuzione con Intune** Intune verrà collegato all' **Archivio di Microsoft per le aziende** durante onboarding Desktop gestiti Microsoft che consente di App ottenuti da distribuire tramite Intune. Microsoft verrà inoltre distribuire la versione del portale aziendale basata sul web per utenti finali in modo che gli amministratori IT possono offrire un'esperienza self-service per gli utenti finali.

**Gestione App** Microsoft può identificare le applicazioni con restrizioni che non sono appropriate per il luogo di lavoro moderno causa l'impatto del sistema. Quando viene identificata di un'applicazione Microsoft provvederà a darne comunicazione cliente e sarà necessario tale applicazione da rimuovere dal tenant. 

## <a name="customer-responsibilities"></a>Responsabilità del cliente
La famiglia di prodotti Office 365 core per le offerte di produttività di Microsoft e incluso nella licenza 365 Microsoft per tutti gli utenti di Desktop gestiti Microsoft. Mentre Microsoft distribuisce, aggiornamenti e supporta le applicazioni di Office per i dispositivi Desktop gestiti Microsoft esistono alcune aree per cui il cliente è responsabile.
- **Assegnare licenze** - sono responsabili dell'assegnazione di licenze appropriate per gli utenti finali per Office 365. 
- **Aggiungere utenti ai gruppi di sicurezza** - per i clienti con gli utenti hanno bisogno di progetto o Visio, è necessario l'amministratore IT aggiungere gli utenti ai gruppi di distribuzione appropriata. Gli amministratori IT sono anche responsabili della gestione del ciclo di vita per gli utenti finali. 
- **Distribuzione di Office 365 componenti aggiuntivi** - sono responsabili della distribuzione di un plug-in per la famiglia di prodotti Office 365 che vengono considerate necessarie. 

Poiché le applicazioni line-of-business (LOB) sono univoche per ogni cliente, i clienti sono responsabili della gestione di tutte le applicazioni all'interno dell'organizzazione non distribuito da Microsoft. Includono:
- Per decidere quali App necessarie e chi deve
- Assegnazione di App per gli utenti
- Creare e gestire gruppi di Azure Active Directory (AD) per la gestione delle assegnazioni di app 

Dopo aver individuato il set di componenti di base delle applicazioni LOB cliente verrà procurarsi, assegnare una licenza, creazione del pacchetto e testare tali applicazioni nell'ambiente Desktop gestito Microsoft. Il cliente deve caricare e distribuire le applicazioni Intune per distribuire l'aggiornamento e rimuovere le autorizzazioni delle applicazioni LOB. I clienti che sono responsabili della gestione di supporto per applicazioni LOB per gli utenti.
 

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

## <a name="resources"></a>Risorse
Mentre molti servizi rientrano nell'ambito di operazioni di Desktop gestiti Microsoft sono disponibili i servizi che offre Microsoft che possono risultare utili per il cliente gestiscono le applicazioni.

### <a name="windows-upgrade-readiness"></a>Preparazione dell'aggiornamento di Windows
Una parte essenziale dell'impostazione di nuovi dispositivi Microsoft gestito è di memorizzazione quali App sono necessari per gli utenti di dispositivi. Preparazione tecnica dell'aggiornamento di Windows è uno strumento Microsoft che consente alle organizzazioni di comprendere il panorama applicazione all'interno della propria azienda e consente di esaminare dati della chiave su tali applicazioni, ad esempio:

- **Utilizzo dell'applicazione** - dati di telemetria viene utilizzato per monitorare l'utilizzo dell'applicazione.
- **Compatibilità delle applicazioni** - aggiornamento Readiness esamina ogni applicazione e Visualizza come in generale è stato distribuito nella versione più recente di Windows 10 e valuta come identificare se è "Pronto per Windows". Questi dati contribuiscono di testare gli sforzi per applicazioni che non sono già ampiamente adottate lo stato attivo.

### <a name="intune-application-deployment"></a>Distribuzione delle applicazioni Intune
Gestione delle applicazioni può essere gestita tramite il portale di amministrazione di Desktop gestiti Microsoft o tramite il portale Intune. Portale di gestione app dell'Intune Mostra le applicazioni distribuite per Windows, Android e iOS. Portale di amministrazione di Desktop gestiti Microsoft limita la visualizzazione per le applicazioni di Windows 10. Entrambi sono disponibili tramite il portale di Azure. 
- [Nozioni fondamentali di gestione app Intune](https://docs.microsoft.com/intune/app-management)
- [Aggiungere un'applicazione Windows a 32](https://docs.microsoft.com/intune/lob-apps-windows)
- [Aggiungere applicazioni web](https://docs.microsoft.com/intune/web-app)
- [Assegnare e distribuire applicazioni ai gruppi](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a>Standard di creazione di pacchetti applicativi
Per distribuire le applicazioni di Windows a 32 tramite Intune devono essere incluse in pacchetti come un unico. MSI, un portali o. MSIX. Il tipo di pacchetto più comune per Intune è attualmente. MSI.
