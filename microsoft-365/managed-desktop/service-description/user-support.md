---
title: Supporto agli utenti
description: Illustra le opzioni per il supporto guidato dal cliente e dal partner.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8063e1b0e76241df946a29ef2c5115bc0dc39aad
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363768"
---
# <a name="user-support"></a>Supporto agli utenti

Gli Microsoft Managed Desktop possono ricevere supporto dall'organizzazione (questo supporto è "guidato dal cliente") o da un partner selezionato ("supporto guidato dal partner"). Il nostro obiettivo è offrire agli utenti un'esperienza coerente mantenendo al contempo sicuri i dispositivi con entrambe le opzioni di supporto. Indipendentemente dall'opzione scelta, si applicano gli stessi principi: 

- Integrazione flessibile dei Microsoft Managed Desktop con i processi di supporto esistenti. 
- Ruoli e responsabilità chiari tra il provider di supporto, gli amministratori IT e Microsoft Managed Desktop 
- [Percorsi di escalation definiti](#workflow-for-support-providers)
- Documentazione fornita da Microsoft Managed Desktop, insieme a un portale in cui è possibile richiedere l'accesso ai dispositivi con privilegi elevati e l'escalation al personale di supporto, se necessario.
- Monitoraggio e mitigazione delle minacce fornite Microsoft Managed Desktop tutti i giorni

## <a name="roles-and-responsibilities"></a>Ruoli e responsabilità

Per garantire la qualità del servizio senza compromettere la sicurezza, il provider di supporto, gli amministratori IT e i Microsoft Managed Desktop hanno ruoli e responsabilità diversi.

### <a name="support-provider"></a>Provider di supporto

Chiunque fornisce supporto (per il supporto guidato dal cliente o un partner per partner) è responsabile di questi elementi:

- Fornire tutto il supporto e l'assistenza tecnica dell'utente dal primo contatto alla risoluzione per l'utente
- Adempimento di tutti i contratti di servizio per il supporto degli utenti stabilito dall'organizzazione o in collaborazione con il provider di supporto scelto
- Esecuzione di azioni di risoluzione dei problemi specifiche, ad esempio la richiesta di privilegi di dispositivo elevati, come descritto in [Ottenere assistenza per gli utenti](../working-with-managed-desktop/end-user-support.md)
- Risoluzione e correzione dei problemi degli utenti, tra cui:
    - Sistema operativo (Windows)
    - Microsoft Apps per le aziende
    - Funzionalità del browser
    - Problemi del dispositivo
    - Problemi relativi all'infrastruttura, ad esempio stampanti, driver e VPN
    - Applicazioni line-of-business

### <a name="it-admin"></a>Amministratore IT

L'amministratore IT è responsabile di questi elementi:

- Collaborazione con il provider di supporto per impostare e gestire i contratti di servizio per il supporto degli utenti
- Gestione dei privilegi di accesso elevati per il personale di supporto approvato. Per ulteriori informazioni, vedere [Enable user support features](../get-started/enable-support.md)
- Se si verificano problemi con i dispositivi che interessano più utenti, è necessario eseguire l'escalation di tali dispositivi usando il processo di supporto Microsoft Managed Desktop amministratore. Per ulteriori informazioni, vedere [Supporto dell'amministratore per Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
- Instradare i problemi relativi all'hardware al fornitore o al fornitore appropriato
- Mantenere e proteggere le impostazioni dei criteri di sicurezza dei dispositivi Microsoft Managed Desktop dispositivi impedendo la modifica dei criteri impostati.

### <a name="microsoft-managed-desktop"></a>Microsoft Managed Desktop

In qualità di provider di servizi, siamo responsabili di questi elementi:

- Fornire i mezzi per l'accesso ai dispositivi con privilegi elevati e l'escalation dei problemi, inclusa la documentazione
- Mantenere aggiornate queste informazioni sui ruoli e sulle responsabilità
- Rispondere alle richieste di supporto dell'amministratore in base alle definizioni di gravità
- Fornire il monitoraggio e la mitigazione delle minacce per tutti i dispositivi registrati tutti i giorni ogni giorno

## <a name="workflow-for-support-providers"></a>Flusso di lavoro per i provider di supporto

Se il supporto è guidato dal cliente o dal partner, il flusso di attività per una richiesta di supporto utente segue questo percorso:

:::image type="content" source="../../media/mmd-support-flow.png" alt-text="Quando un utente contatta il supporto, funzionerà nel sistema del personale a più livelli come hai progettato. È importante designare un gruppo di personale di supporto a cui verranno fornite le capacità per l'elevazione e l'escalation, noto come team di escalation del supporto. Per problemi Microsoft Managed Desktop specifici, possono essere inoltrati al team operativo. O per altri problemi Microsoft, possono instradare al canale di supporto esistente, Unified o Premier. I problemi hardware devono sempre essere instradati al provider o al fornitore stabilito":::

L'integrazione dei processi esistenti con questo flusso di lavoro per Microsoft Managed Desktop dispositivi è flessibile, quindi i dettagli potrebbero essere diversi. In genere, il provider di supporto segue un approccio basato su livelli o handoff esistente, designando utenti specifici che hanno la possibilità di elevare le autorizzazioni o inoltrare i problemi a Microsoft Managed Desktop Operations. È meglio mantenere questo gruppo più piccolo rispetto al team di supporto più ampio.

Se un problema dell'utente deve essere inoltrato a Microsoft Managed Desktop, è utile identificare il team a cui deve essere indirizzato il problema. Possiamo trasferire i casi in modo appropriato, ma risparmia tempo per instradare i casi nel punto giusto dall'inizio.

- I problemi specifici Microsoft Managed Desktop (ad esempio, un criterio o un'impostazione distribuita dal servizio stesso): inoltrare direttamente al team operations. Per altre info, vedi [Ottenere assistenza per gli utenti.](../working-with-managed-desktop/end-user-support.md)
- Problemi hardware: direttamente al fornitore o al fornitore dell'hardware
- Altri problemi: passare attraverso i canali di supporto esistenti, che si tratta di un abbonamento Unified o Premier.

## <a name="provided-support-framework"></a>Framework di supporto fornito


### <a name="elevation-portal"></a>Portale di elevazione 

Poiché Microsoft Managed Desktop dispositivi vengono eseguiti sull'utente standard per impostazione predefinita, alcune attività richiedono l'elevazione dei privilegi. Per ulteriori informazioni sul controllo dell'account utente, vedere [Controllo dell'account utente](/windows/security/identity-protection/user-account-control/user-account-control-overview). Per consentire al personale di [](../working-with-managed-desktop/end-user-support.md#elevation-requests) supporto di eseguire attività durante la risoluzione dei problemi per gli utenti, viene fornito l'accesso "just-in-time" a un account amministratore. Questa password è accessibile in modo sicuro solo dagli utenti designati e ruota ogni due ore.  

Per la procedura per configurare gli utenti per l'accesso a questo portale, vedere [Enable user support features](../get-started/enable-support.md).

Per la procedura per l'invio di una richiesta di elevazione, vedere [Richieste di elevazione](../working-with-managed-desktop/end-user-support.md#elevation-requests).

### <a name="escalation-portal"></a>Portale di escalation 

Se un problema richiede un'escalation al team Microsoft Managed Desktop Operations, il personale di supporto designato potrebbe indirizzare in modo simile a una richiesta di supporto dell'amministratore IT.  

> [!NOTE]
> Solo le richieste di supporto Sev C possono essere inviate in questo modo. Per un problema corrispondente alla descrizione di altre gravità, è consigliabile contattare l'amministratore IT appropriato per il file. Per altre info, vedi [Definizioni di gravità delle richieste di supporto.](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions)

Per la procedura per configurare gli utenti per l'accesso a questo portale, vedere [Enable user support features](../get-started/enable-support.md).

Per la procedura per l'invio di una richiesta di escalation, vedere [Richieste di escalation.](../working-with-managed-desktop/end-user-support.md#escalation-requests)
