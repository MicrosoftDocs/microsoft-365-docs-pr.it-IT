---
title: Infrastruttura di base di Microsoft 365 per le aziende
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere le fasi principali della distribuzione dell'infrastruttura di base per Microsoft 365 per le aziende all'interno dell'organizzazione, nota anche come la distribuzione di base.
ms.openlocfilehash: 26f95b9e7fb951910b983defb8b80162f39c37a2
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633614"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure"></a>Infrastruttura di base di Microsoft 365 per le aziende

Se si esegue la distribuzione end-to-end di Microsoft 365 per le aziende autonomamente, è necessario innanzitutto creare una base fissa sulla quale le applicazioni e i servizi possano sbloccare creatività e collaborazione in un ambiente protetto. Questa base è chiamata anche *distribuzione di base*.

Per un percorso definito end-to-end per la distribuzione, è possibile utilizzare queste fasi per pianificare e distribuire l'infrastruttura di base di Microsoft 365 per le aziende:

| | Fase | Risultati |
|:-------|:-----|:-----|
|![Fase 1: collegamento in rete](../media/deploy-foundation-infrastructure/networking_icon-small.png)|[Fase 1: Funzionalità di rete](networking-infrastructure.md)| La rete è ottimizzata per l'accesso ai servizi basati sul cloud di Microsoft 365. |
|![Fase 2: identità](../media/deploy-foundation-infrastructure/identity_icon-small.png)|[Fase 2: identità](identity-infrastructure.md)| Gli account di amministratore sono protetti, gli utenti e gruppi sono sincronizzati e l'autenticazione degli utenti è sicura. |
|![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[Fase 3: Windows 10 Enterprise](windows10-infrastructure.md)| I computer esistenti basati su Windows possono eseguire l'aggiornamento a Windows 10 Enterprise e vengono installati nuovi dispositivi con Windows 10 Enterprise. |
|![Fase 4: Office 365 ProPlus](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md)| Gli utenti di Microsoft Office esistenti possono eseguire l'aggiornamento a Office 365 ProPlus. |
|![Fase 5: gestione dei dispositivi mobili](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[Fase 5: gestione dei dispositivi mobili](mobility-infrastructure.md)| I dispositivi possono essere registrati e gestiti. |
|![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[Fase 6: protezione delle informazioni](infoprotect-infrastructure.md)| Le funzionalità di sicurezza di Office 365 sono abilitate e sono pronti etichette e criteri per proteggere i documenti e i messaggi di posta elettronica. |

Le fasi iniziano con le più fondamentali (rete e identità) e quindi creano livelli di impostazioni dell'infrastruttura e gruppi per:

- Installare la versione più sicura e aggiornata di Windows nei dispositivi e mantenerla attuale.
- Installare la versione più aggiornata di Microsoft Office nei dispositivi e mantenerla attuale.
- Gestione dei dispositivi dell'organizzazione e accesso alle app.
- Proteggere le informazioni in tali dispositivi e nel cloud.

Tuttavia, c’è flessibilità nel configurare e nell’implementare fasi o passaggi nelle fasi per soddisfare le necessità di risorse IT e business.

- **Organizzazioni di dimensioni inferiori o nuove**, se necessario, possono seguire le fasi per creare l’infrastruttura in modo metodico. Per una distribuzione semplificata per le organizzazioni non, fare clic [qui](deploy-foundation-infrastructure-non-enterprises.md).

-  **Se si ha un'organizzazione aziendale**, visualizzare le fasi come livelli dell'infrastruttura IT invece di un percorso definito, e determinare la strategia migliore per ottenere una finale conformità ai requisiti per ogni livello all'interno dell'organizzazione.

Al termine di ogni fase, è necessario esaminare i *criteri di uscita*, comprese le condizioni necessarie che è necessario soddisfare e le condizioni facoltative da prendere in considerazione. I criteri di uscita per ogni fase assicurano che la risultante configurazione end-to-end e l’infrastruttura cloud e locale soddisfino i requisiti per una distribuzione di Microsoft 365 per le aziende.

Per visualizzare la struttura del contenuto, vedere questo breve video.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

Ecco l'infrastruttura di base della Guida alla distribuzione generale di Microsoft 365 per le aziende:

![Infrastruttura di base della Guida alla distribuzione generale di Microsoft 365 per le aziende](../media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a>In breve

Il [poster Infrastruttura di base di Microsoft 365 per le aziende](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf) rappresenta una posizione centrale da visualizzare, per ogni fase:

- Obiettivi generali della fase per amministratori e utenti
- Servizi, funzionalità e strumenti
- Decisioni chiave per la progettazione
- Risultati della configurazione
- Processo di onboarding di un nuovo utente
- Monitoraggio e aggiornamento

[![Immagine per il poster dell'infrastruttura di base di Microsoft 365 per le aziende](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)](../media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)

Per scaricare una copia del poster, fare clic [qui](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).


## <a name="infrastructure-configuration-vs-user-rollout"></a>Configurazione dell'infrastruttura vs. implementazione dell’utente

L'infrastruttura di base è un set di configurazione di software e servizi configurati che, se combinati insieme per un utente, consentono di sfruttare l'intera gamma di funzionalità e protezioni offerte da Microsoft 365 per le aziende. La destinazione finale del percorso di distribuzione end-to-end consiste nell'applicare questa infrastruttura a tutti gli utenti e i dispositivi basati su Windows. 

Tuttavia, è importante tenere presente che l'infrastruttura di base di Microsoft 365 per le aziende è indipendente dalla distribuzione di software e servizi agli utenti. ***È possibile configurare i livelli dell'infrastruttura di base senza la necessità di implementare i livelli per tutti gli utenti.***

È possibile configurare, testare e provare a usare gli elementi dell'infrastruttura di base prima dell'implementazione di questi elementi per i numerosi utenti negli uffici, regioni o reparti dell'organizzazione.

Ad esempio, creare le impostazioni per:

| Fase | Risultati |
|:-------|:-----|
| Identità | Sincronizzazione di account e gruppi per i criteri di accesso condizionale basato sull'identità. |
| Windows 10 Enterprise | Gruppi per aggiornare automaticamente i computer che eseguono Windows 7 o Windows 8.1 a Windows 10 Enterprise. |
| Office 365 ProPlus | Gruppi per distribuire automaticamente Office 365 ProPlus agli utenti con Office 2010, Office 2013 o Office 2016. |
| Gestione dei dispositivi mobili | Gruppi per la registrazione di dispositivi e per i criteri di accesso condizionale basati sul dispositivo. |
| Protezione delle informazioni | Gruppi per le etichette di riservatezza di Office 365. |

Quando si è pronti a distribuire elementi di questa infrastruttura per gli utenti:

| Fase | Azione di distribuzione |
|:-------|:-----|
| Identità | Aggiungere account utenti ai gruppi per i criteri di accesso condizionale basato sull'identità. |
| Windows 10 Enterprise | Aggiungere account ai gruppi di distribuzione automaticamente di Windows 10 Enterprise utilizzata per gli utenti con Windows 7 o Windows 8.1. |
| Office 365 ProPlus | Aggiungere account utenti ai gruppi per distribuire automaticamente Office 365 ProPlus agli utenti con Office 2010, Office 2013 o Office 2016. |
| Gestione dei dispositivi mobili | Aggiungere account ai gruppi per la registrazione di dispositivi e per i criteri di accesso condizionale basati sul dispositivo. |
| Protezione delle informazioni | Aggiungere account utente ai gruppi per le etichette di riservatezza. |

Dopo che le fasi o gli elementi dell'infrastruttura di base sono completati, testati e sperimentati, è possibile distribuire a tutti gli utenti il software installato, ad esempio Windows 10 Enterprise e Office 365 ProPlus, e i servizi e le protezioni basati su cloud, ad esempio la registrazione di dispositivi e i criteri di accesso condizionale, nel modo più idoneo rispetto alle risorse IT e agli obiettivi aziendali.

## <a name="deployment-and-project-management-strategies"></a>Strategie di distribuzione e di gestione progetti

Per farsi un'idea di come affrontare la gestione dei progetti delle diverse fasi dell'infrastruttura di base per utenti pilota e per il resto dell'organizzazione, vedere [strategie di distribuzione](deployment-strategies-microsoft-365-enterprise.md).

## <a name="deployment-for-non-enterprises"></a>Distribuzione per gli scenari non aziendali

Se l'organizzazione è di piccole dimensioni e Microsoft 365 Business non è idoneo, vedere l'articolo sulla [distribuzione per organizzazioni non aziendali](deploy-foundation-infrastructure-non-enterprises.md) per un metodo di distribuzione semplificato.


## <a name="next-step"></a>Passaggio successivo

| Dove sono | Dove devo andare |
|:-------|:-----|
| Ho l'infrastruttura esistente di Office 365, Enterprise Mobility + Security (EMS) o Windows 10 Enterprise | Iniziare con [Distribuire un'infrastruttura esistente](deploy-with-existing-infrastructure.md), che illustra i criteri di uscita per ogni fase. |
| Inizio da zero come azienda | Iniziare il percorso di distribuzione end-to-end con [Fase 1: Funzionalità di rete](networking-infrastructure.md). |
| Inizio da zero in scenari non appartenenti alle organizzazioni | Iniziare il percorso di distribuzione end-to-end con [Distribuzione per gli scenari non appartenenti alle organizzazioni](deploy-foundation-infrastructure-non-enterprises.md). |
