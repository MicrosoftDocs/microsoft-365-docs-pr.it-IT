---
title: Ruoli e responsabilità Microsoft Managed Desktop
description: Questo articolo descrive i ruoli e le responsabilità forniti da Microsoft per Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 94389fbb9a13b9a880b0c4dcaf67d8adcaff0f98
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841316"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Ruoli e responsabilità Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Quando l'organizzazione è iscritta a Microsoft Managed Desktop, cosa fa Microsoft? Quali sono le responsabilità dell'organizzazione?

## <a name="microsofts-roles-and-responsibilities"></a>Ruoli e responsabilità di Microsoft

Microsoft fornisce questi ruoli e responsabilità chiave:

Ruolo o responsabilità | Descrizione
--- | ---
Gestione dei criteri MDM | Microsoft applierà i criteri MDM in base alle procedure consigliate e considererà le richieste di modifica dei criteri. Modificheremo anche il tenant come prescritto nei [criteri dei dispositivi.](../service-description/device-policies.md)
supporto per gli utenti | Microsoft fornisce supporto per gli utenti per dispositivi, Windows e la famiglia di prodotti Microsoft 365 Apps for enterprise per tutti gli utenti registrati tramite l'app Guida preinstallata in tutti i dispositivi Microsoft Managed Desktop. 
Supporto del servizio Microsoft Managed Desktop | Microsoft fornirà supporto al reparto IT tramite un team Microsoft Managed Desktop Operations. Questo team supporterà la risoluzione dei problemi tecnici, le richieste di modifica e la gestione degli eventi imprevisti per l'ambiente Microsoft Managed Desktop del cliente. Per ulteriori informazioni, vedere [Supporto per gli amministratori per Microsoft Managed Desktop.](../working-with-managed-desktop/admin-support.md)
Monitoraggio della sicurezza | Microsoft monitorerà i dispositivi Microsoft Managed Desktop usando Microsoft Defender for Endpoint. Se Microsoft Managed Desktop Security Operations Center (SOC) rileva una minaccia, microsoft informerà l'utente, isola il dispositivo e correggerà il problema in remoto. Per ulteriori informazioni, vedere [Sicurezza.](../service-description/security.md)
Monitoraggio e gestione degli aggiornamenti | Microsoft monitora attivamente i dispositivi Microsoft Managed Desktop per garantire che gli aggiornamenti qualitativi e delle funzionalità più recenti siano installati per Microsoft Windows e Microsoft Office. Per ulteriori informazioni, vedere [Come vengono gestiti gli aggiornamenti.](../service-description/updates.md)
Raggruppamento di utenti e dispositivi | Il team operativo Microsoft Managed Desktop creerà e gestirà i gruppi di dispositivi e utenti necessari nell'ambito delle operazioni IT. A questi gruppi non sono consentite modifiche di appartenenza o configurazione. La modifica di questi gruppi può comportare una configurazione imprevista dei dispositivi e la perdita di funzionalità. Per eventuali problemi o domande su questi gruppi una volta stabiliti, gli amministratori IT possono contattare le operazioni di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Supporto per gli amministratori per Microsoft Managed Desktop.](../working-with-managed-desktop/admin-support.md)

## <a name="your-roles-and-responsibilities"></a>Ruoli e responsabilità

Questo set di ruoli e responsabilità comuni è necessario per la distribuzione, ma non è fornito da Microsoft. Non è esaustivo, ma è applicabile alla maggior parte delle organizzazioni. Esistono alcuni elementi di cui l'utente e Microsoft condividono la responsabilità. 

Ruolo o responsabilità | Descrizione
--- | ---
Gestione delle modifiche | Microsoft informerà i clienti, in anticipo, quando è necessario apportare modifiche all'ambiente Microsoft Managed Desktop. Per ulteriori informazioni, vedere Service [Changes and Communication .](../service-description/servicechanges.md)<br><br>È necessario disporre di un proprio processo di gestione delle modifiche e avere un contatto stabilito con il team Microsoft Managed Desktop Operations. È inoltre necessario disporre di risorse per rivedere e approvare queste modifiche. Per ulteriori informazioni, vedere [Operazioni e monitoraggio.](../service-description/operations-and-monitoring.md)  
Gestione delle identità | L'utente è responsabile della creazione di account utente, dell'assegnazione degli utenti ai gruppi e della conservazione dei metadati aggiornati. 
Configurazione e gestione di Microsoft 365 Apps for enterprise | Microsoft è responsabile della distribuzione delle applicazioni di Office agli utenti e di mantenere aggiornate tali applicazioni. <br><br> L'utente è responsabile della gestione dei servizi e dei criteri di Microsoft 365, incluse le responsabilità di amministrazione di Exchange Online:<br>- Amministrazione della posta elettronica<br>- Configurazione delle cassette postali e delle regole<br>- Gestione locale di Exchange<br><br>L'utente è inoltre responsabile degli strumenti di collaborazione, dell'amministrazione del server di SharePoint, della gestione dei domini e dei criteri di sicurezza e informazioni impostati nell'interfaccia di amministrazione di Microsoft 365. 
Supporto agli utenti | È necessario fornire supporto per gli utenti per: <br>- Infrastruttura locale: tutta la connettività di rete e Internet, l'infrastruttura VPN e la configurazione client, le apparecchiature della sala riunioni locali, le stampanti, il server proxy e la configurazione e i firewall.<br><br>- Risorse cloud a livello aziendale: posta elettronica, SharePoint, servizi di collaborazione e altre infrastrutture cloud correlate al footprint tecnologico a livello aziendale.<br><br>- Line-of-business e qualsiasi altra applicazione specifica della società.
App | I ruoli e le responsabilità variano in qualche modo per le app fornite come parte di Microsoft Managed Desktop rispetto alle app fornite. <br><br>Per le app fornite da Microsoft (Microsoft 365 Apps for enterprise che comprendono Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, Teams e OneNote), **Microsoft** fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto. **Devi** ottenere e assegnare licenze per queste app, aggiungere utenti ai gruppi di sicurezza e gestire la fine del ciclo di vita e distribuire i componenti aggiuntivi necessari.<br><br>Per le app fornite (ad esempio le app line-of-business), indipendentemente dal fatto che tu le metta in pacchetto o che coinvolgi un fornitore non **Microsoft,** sei responsabile di queste azioni: <br><br>- Identificazione delle applicazioni necessarie per i gruppi di utenti di destinazione<br>- Creazione e gestione dei gruppi di Azure AD per la distribuzione di app<br>- Creazione di pacchetti di app per soddisfare gli standard di distribuzione di Microsoft Intune<br>- Caricamento di app in Microsoft Intune<br>- Test delle app nell'ambiente Microsoft Managed Desktop<br>- Test delle app con gli utenti<br>- Gestione e assegnazione di utenti alle applicazioni<br>- Identificare e distribuire gli aggiornamenti delle applicazioni tramite Microsoft Intune<br>- Disinstallazione e rimozione delle applicazioni dopo il ritiro<br>- Procurarsi e assegnare licenze<br>- Fornire supporto per gli utenti per le app line-of-business<br>- Gestione delle impostazioni dell'app in remoto<br><br>**Microsoft** fornirà gli strumenti di distribuzione di Microsoft Intune per distribuire le applicazioni ai client remoti.<br><br>Per altre informazioni, vedi [App.](../get-ready/apps.md)
Monitoraggio sicurezza e risposta | L'utente è responsabile dell'analisi e della risoluzione degli eventi imprevisti per i dispositivi che non sono dispositivi Microsoft Managed Desktop e di garantire che il team microsoft managed desktop operations sia informato di eventuali problemi che potrebbero influire sul servizio.
Supporto delle operazioni | È necessario fornire un elenco di contatti preferiti ed esperti in materia nell'organizzazione. Questi contatti sono necessari se si verifica un incidente operativo non correlato a Microsoft Managed Desktop. <br><br>L'utente è inoltre responsabile dell'analisi e della risoluzione degli eventi imprevisti per dispositivi e servizi non presenti in Microsoft Managed Desktop e per garantire che microsoft Managed Desktop Operations Team sia sempre informato.
Infrastruttura di rete, inclusa la VPN | L'utente è responsabile dell'installazione, della configurazione e della gestione (inclusi la risoluzione dei problemi e il debug) di tutte le infrastrutture e servizi correlati alla rete, tra cui connettività Internet, controlli di rete, configurazione proxy e infrastruttura di connettività remota.<br><br>Se è configurato un proxy (in hardware o software), esiste una raccolta di URL che devono essere consentiti dal proxy. L'utente è responsabile della risoluzione di eventuali conflitti o incompatibilità dovuti a più proxy. È possibile aggiungere proxy di rete specifici per l'organizzazione utilizzando impostazioni configurabili. Per ulteriori informazioni, vedere [Configurable settings.](../working-with-managed-desktop/config-setting-ref.md#proxy)<br><br>Per ulteriori informazioni, vedere [Configurazione proxy.](../get-ready/network.md)
Stampa | L'utente è responsabile dell'installazione, della gestione e dell'amministrazione di stampanti e code di stampa. La stampa cloud è una soluzione consigliata, ma non è necessaria. 




