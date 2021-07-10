---
title: Ruoli e responsabilità Microsoft Managed Desktop
description: In questo articolo vengono descritti i ruoli e le responsabilità forniti da Microsoft per Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7b9efe1a52c108e3de46429d64f9a5535ad13e4e
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362751"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Ruoli e responsabilità Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Quando l'organizzazione è iscritta a Microsoft Managed Desktop, cosa fa Microsoft? Quali sono le responsabilità dell'organizzazione?

## <a name="microsofts-roles-and-responsibilities"></a>Ruoli e responsabilità di Microsoft

Microsoft fornisce questi ruoli e responsabilità chiave:

Ruolo o responsabilità | Descrizione
--- | ---
Gestione dei criteri MDM | Microsoft applierà i criteri MDM in base alle procedure consigliate e considererà le richieste di modifica dei criteri. Verranno inoltre apportate modifiche al tenant come prescritto in [Criteri dispositivo.](../service-description/device-policies.md)
Supporto agli utenti | Forniamo un meccanismo per l'accesso elevato ai dispositivi e per i problemi da inoltrare se necessario. Per ulteriori informazioni, vedere [Supporto per gli utenti.](../service-description/user-support.md)
Microsoft Managed Desktop servizio di supporto | Microsoft fornirà supporto al reparto IT tramite un team Microsoft Managed Desktop operations. Questo team supporterà la risoluzione dei problemi tecnici, le richieste di modifica e la gestione degli incidenti per l'ambiente Microsoft Managed Desktop cliente. Per ulteriori informazioni, vedere [Supporto dell'amministratore per Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Monitoraggio della sicurezza | Microsoft monitorerà i dispositivi Microsoft Managed Desktop usando Microsoft Defender for Endpoint. Se il Microsoft Managed Desktop Security Operations Center (SOC) rileva una minaccia, microsoft informerà l'utente, isola il dispositivo e correggerà il problema in remoto. Per ulteriori informazioni, vedere [Sicurezza](../service-description/security.md).
Monitoraggio e gestione degli aggiornamenti | Monitoriamo attivamente i dispositivi Microsoft Managed Desktop per garantire che gli aggiornamenti qualitativi e delle funzionalità più recenti siano installati per Microsoft Windows e Microsoft Office. Per ulteriori informazioni, vedere [Come vengono gestiti gli aggiornamenti](../service-description/updates.md).
Raggruppamento di utenti e dispositivi | Microsoft Managed Desktop team operativo creerà e gestirà i gruppi di dispositivi e utenti necessari nell'ambito delle operazioni IT. A questi gruppi non sono consentite modifiche di appartenenza o configurazione. La modifica di questi gruppi può causare una configurazione imprevista dei dispositivi e la perdita di funzionalità. Per eventuali problemi o domande su questi gruppi una volta stabiliti, gli amministratori IT possono contattare Microsoft Managed Desktop operazioni. Per ulteriori informazioni, vedere [Supporto dell'amministratore per Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Ruoli e responsabilità

Questo set di ruoli e responsabilità comuni è necessario per la distribuzione, ma non viene fornito da Microsoft. Non è esaustivo, ma è applicabile per la maggior parte delle organizzazioni. Ci sono alcuni elementi di cui l'utente e Microsoft condividono la responsabilità. 

Ruolo o responsabilità | Descrizione
--- | ---
Gestione delle modifiche | Microsoft informerà i clienti, in anticipo, quando è necessario apportare modifiche all'ambiente Microsoft Managed Desktop locale. Per ulteriori informazioni, vedere [service changes and communication](../service-description/servicechanges.md).<br><br>È necessario disporre di un proprio processo di gestione delle modifiche e stabilire un contatto con il team Microsoft Managed Desktop Operations. È inoltre necessario disporre di risorse per rivedere e approvare queste modifiche. Per ulteriori informazioni, vedere [Operazioni e monitoraggio](../service-description/operations-and-monitoring.md).  
Gestione delle identità | L'utente è responsabile della creazione di account utente, dell'assegnazione degli utenti ai gruppi e della conservazione dei metadati aggiornati. 
Microsoft 365 Apps for enterprise di configurazione e gestione | Microsoft è responsabile della distribuzione Office agli utenti e tali applicazioni vengono mantenute aggiornate. <br><br> L'utente è responsabile della gestione dei Microsoft 365 e dei criteri, incluse le responsabilità Exchange Online'amministrazione:<br>- Amministrazione della posta elettronica<br>- Configurazione delle cassette postali e delle regole<br>- Exchange gestione locale<br><br>L'utente è inoltre responsabile degli strumenti di collaborazione, dell SharePoint di amministrazione del server, della gestione dei domini e dei criteri di sicurezza e informazioni impostati nella interfaccia di amministrazione di Microsoft 365. 
Supporto agli utenti | Fornire tutto il supporto e l'assistenza tecnica degli utenti dal primo contatto alla risoluzione per l'utente, da parte dell'utente o tramite un partner di supporto designato. È necessario fornire direttamente il supporto degli utenti o collaborare con un partner per fornire supporto per queste aree: <br><br>- Infrastruttura locale: tutta la connettività di rete e Internet, l'infrastruttura VPN e la configurazione client, le apparecchiature per sale conferenze locali, le stampanti, il server proxy e la configurazione e i firewall.<br><br>- Risorse cloud a livello aziendale: posta elettronica, SharePoint, servizi di collaborazione e altre infrastrutture cloud correlate al footprint tecnologico a livello aziendale.<br><br>- Line-of-business e qualsiasi altra applicazione specifica dell'azienda.
App | I ruoli e le responsabilità variano in qualche modo per le app fornite nell'ambito Microsoft Managed Desktop rispetto alle app fornite. <br><br>Per le app fornite da Microsoft (Microsoft 365 Apps for enterprise che comprendono Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams e OneNote), **Microsoft** fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto. **Devi** ottenere e assegnare licenze per queste app, aggiungere utenti ai gruppi di sicurezza e gestire la fine del ciclo di vita e distribuire i componenti aggiuntivi necessari.<br><br>Per le app fornite (ad esempio le app line-of-business), indipendentemente dal fatto che tu le metta in un pacchetto o che coinvolgi un fornitore non **Microsoft,** sei responsabile di queste azioni: <br><br>- Identificazione delle applicazioni necessarie per i gruppi di utenti di destinazione<br>- Creazione e gestione dei gruppi di Azure AD per la distribuzione delle app<br>- Creazione di pacchetti di app per soddisfare Microsoft Intune standard di distribuzione<br>- Caricamento di app in Microsoft Intune<br>- Test delle app in Microsoft Managed Desktop ambiente<br>- Test delle app con gli utenti<br>- Gestione e assegnazione di utenti alle applicazioni<br>- Identificare e distribuire gli aggiornamenti delle applicazioni tramite Microsoft Intune<br>- Disinstallazione e rimozione di applicazioni ritirate<br>- Procurare e assegnare licenze<br>- Fornire supporto per gli utenti per le app line-of-business<br>- Gestione remota delle impostazioni dell'app<br><br>**Microsoft** fornirà strumenti Microsoft Intune distribuzione per distribuire le applicazioni ai client remoti.<br><br>Per altre informazioni, vedi [App](../get-ready/apps.md).
Monitoraggio sicurezza e risposta | L'utente è responsabile dell'analisi e della risoluzione degli eventi imprevisti per i dispositivi che non sono Microsoft Managed Desktop e per assicurarsi che il team operativo di Microsoft Managed Desktop sia informato di eventuali problemi che potrebbero influire sul servizio.
Supporto delle operazioni | È necessario fornire un elenco dei contatti preferiti e degli esperti in materia nell'organizzazione. Questi contatti sono necessari se si verifica un incidente operativo non correlato Microsoft Managed Desktop. <br><br>Sei anche responsabile dell'analisi e della risoluzione di eventi imprevisti per dispositivi e servizi non Microsoft Managed Desktop e per garantire che il team Microsoft Managed Desktop Operations sia sempre informato.
Infrastruttura di rete, tra cui VPN | L'utente è responsabile dell'installazione, della configurazione e della gestione (inclusa la risoluzione dei problemi e il debug) di tutte le infrastrutture e servizi correlati alla rete, tra cui la connettività Internet, i controlli di rete, la configurazione proxy e l'infrastruttura di connettività remota.<br><br>Se è configurato un proxy (nell'hardware o nel software), esiste una raccolta di URL che devono essere consentiti dal proxy. L'utente è responsabile della risoluzione di eventuali conflitti o incompatibilità a causa di più proxy. È possibile aggiungere proxy di rete specifici per l'organizzazione utilizzando impostazioni configurabili. Per ulteriori informazioni, vedere [Configurable settings.](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>Per ulteriori informazioni, vedere [Configurazione proxy](../get-ready/network.md).
Stampa | L'utente è responsabile dell'installazione, della manutenzione e dell'amministrazione di stampanti e code di stampa. La stampa cloud è una soluzione consigliata, ma non è necessaria. 




