---
title: Ruoli e responsabilità Microsoft Managed Desktop
description: In questo argomento vengono descritti i ruoli e le responsabilità forniti da Microsoft per Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8cec5a99d2275e451ceac9004a922820e4b3e726
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289746"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Ruoli e responsabilità Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Quando l'organizzazione è stata eseguita in Microsoft Managed Desktop, cosa può fare Microsoft per l'utente? Quali sono le responsabilità dell'organizzazione?

## <a name="microsofts-roles-and-responsibilities"></a>Ruoli e responsabilità di Microsoft

Di seguito sono riportati alcuni ruoli e responsabilità principali che verranno forniti dall'utente Microsoft.

Ruolo o responsabilità | Descrizione
--- | ---
Gestione dei criteri MDM | Microsoft applica i criteri MDM secondo le procedure consigliate e prende in considerazione le richieste di modifiche ai criteri. Verranno inoltre apportate modifiche al tenant come prescritto nei [criteri dei dispositivi](../service-description/device-policies.md).
supporto per gli utenti | Microsoft fornirà supporto utente per dispositivi, finestre e prodotti Office per tutti gli utenti registrati tramite l'app ottenere la guida preinstallata su tutti i dispositivi desktop Microsoft gestiti. 
Supporto per Microsoft Managed Desktop Service | Microsoft fornirà supporto ai reparti IT dei clienti tramite un team di Operations desktop Microsoft gestito. Questo team sosterrà la risoluzione dei problemi tecnici, le richieste di modifica e la gestione degli incidenti per l'ambiente desktop Microsoft gestito del cliente. Per ulteriori informazioni, vedere [supporto di amministrazione per Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Monitoraggio della sicurezza | Microsoft controllerà i dispositivi desktop Microsoft gestiti tramite Microsoft Defender ATP. Se viene rilevata una minaccia da Microsoft Managed Desktop Security Operations Center (SOC), Microsoft invierà una notifica al cliente, isolerà il dispositivo e rettificherà il problema in remoto. Per ulteriori informazioni, vedere [sicurezza](../service-description/security.md).
Aggiornare il monitoraggio e la gestione | Microsoft monitorerà attivamente i dispositivi Microsoft Managed Desktop dei clienti per garantire che siano installati gli aggiornamenti di qualità e funzionalità più recenti per Microsoft Windows e Microsoft Office. Per ulteriori informazioni, vedere [la modalità](../service-description/updates.md)di gestione degli aggiornamenti.
Raggruppamento di utenti e dispositivi | Il team di Microsoft Managed Desktop Operations creerà e gestirà i gruppi di utenti e dispositivi necessari come parte delle operazioni IT. Non sono consentite modifiche alla configurazione o all'appartenenza a questi gruppi. L'alterazione di questi gruppi può comportare una configurazione imprevista dei dispositivi e la perdita di funzionalità. Per eventuali problemi o domande su questi gruppi una volta stabiliti, gli amministratori IT possono contattare le operazioni di Microsoft Managed Desktop. Per ulteriori informazioni, vedere [supporto di amministrazione per Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Ruoli e responsabilità

Di seguito è riportato un ulteriore gruppo di ruoli e responsabilità comuni che non sono forniti da Microsoft, ma che sono necessari per una distribuzione corretta. Non è esaustivo, ma è applicabile per la maggior parte delle organizzazioni. Di seguito sono riportati alcuni elementi che sia Microsoft che il cliente condividono le responsabilità. 

Ruolo o responsabilità | Descrizione
--- | ---
Gestione delle modifiche | Microsoft invierà una notifica ai clienti, in anticipo, quando dovranno essere apportate modifiche all'ambiente desktop Microsoft gestito. Per ulteriori informazioni, vedere [modifiche e comunicazioni del servizio](../service-description/servicechanges.md)<br><br>Il cliente deve disporre di un processo di gestione delle modifiche e di un contatto stabilito con Microsoft Managed Desktop Operations team. È inoltre necessario che il cliente disponga di risorse per la revisione e l'approvazione di tali modifiche. Per ulteriori informazioni, vedere [Operations and Monitoring](../service-description/operations-and-monitoring.md).  
Gestione delle identità | Il cliente è responsabile della creazione degli account utente, dell'assegnazione degli utenti ai gruppi e dell'aggiornamento dei metadati. 
Microsoft 365 Apps per la configurazione e la gestione dell'organizzazione | Microsoft è responsabile della distribuzione di applicazioni di Office per gli utenti e tali applicazioni vengono mantenute aggiornate. <br><br> Il cliente ha la responsabilità di gestire i criteri e i servizi di Microsoft 365, incluse le responsabilità di amministrazione di Exchange Online:<br>-Amministrazione della posta elettronica<br>-Configurazione della cassetta postale e della regola<br>-Gestione in locale di Exchange<br><br>Il cliente è responsabile anche degli strumenti di collaborazione, dell'amministrazione di SharePoint Server, della gestione del dominio, dei criteri di sicurezza e delle informazioni impostati nell'interfaccia di amministrazione di Microsoft 365. 
Supporto agli utenti | Il cliente è responsabile della fornitura del supporto utente per: <br>-Sull'infrastruttura del sito: tutte le connessioni di rete e Internet, l'infrastruttura VPN e la configurazione dei client, le apparecchiature locali per conferenze, stampanti, server proxy e configurazione, firewall.<br><br>-Risorse cloud a livello di azienda: posta elettronica, SharePoint, servizi di collaborazione e altre infrastrutture cloud che si riferiscono all'impronta tecnologica a livello aziendale.<br><br>-Line of business e qualsiasi altra applicazione specifica della società.
App | I ruoli e le responsabilità variano un po' per le app fornite come parte di Microsoft Managed Desktop rispetto a quelle da te fornite. <br><br>Per le app fornite da Microsoft (Microsoft 365 Apps for Enterprise composto da Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for business, teams e OneNote), **Microsoft** fornirà servizi completi per la distribuzione, l'aggiornamento e il supporto. **È** necessario ottenere e assegnare licenze per queste app, aggiungere utenti ai gruppi di sicurezza e gestire la fine della vita e distribuire i componenti aggiuntivi necessari.<br><br>Per le app che fornisci (ad esempio le app line-of-business), sia che si tratti di un pacchetto da soli o che coinvolga un fornitore non Microsoft, **è** responsabile di queste azioni: <br><br>-Identificare le applicazioni necessarie per i gruppi di utenti di destinazione<br>-Creazione e gestione dei gruppi di Azure AD per la distribuzione di app<br>-Pacchetti di app per rispondere agli standard di distribuzione di Microsoft Intune<br>-Caricamento delle app in Microsoft Intune<br>-Testare le app nell'ambiente desktop Microsoft gestito<br>-Testare le app con gli utenti<br>-Gestione e assegnazione degli utenti alle applicazioni<br>-Identificare e distribuire gli aggiornamenti delle applicazioni tramite Microsoft Intune<br>-Disinstallazione e rimozione di applicazioni quando sono stati ritirati<br>-Procurare e assegnare licenze<br>-Fornire supporto agli utenti per le app line-of-business<br>-Gestione delle impostazioni delle app in remoto<br><br>**Microsoft** fornirà gli strumenti di distribuzione di Microsoft Intune per distribuire le applicazioni ai client remoti.<br><br>Per ulteriori informazioni, vedere [app](../get-ready/apps.md)
Monitoraggio sicurezza e risposta | Il cliente è responsabile per l'analisi e la risoluzione degli incidenti per i dispositivi desktop non Microsoft gestiti e per garantire che il team Microsoft Managed Desktop Operations sia informato di eventuali problemi che potrebbero influire sul servizio.
Supporto per le operazioni | Il cliente è responsabile della fornitura di un elenco di contatti dei clienti preferiti e di esperti in materia. Microsoft ha bisogno di questi casi, in caso di un incidente operativo desktop non gestito da Microsoft. <br><br>Il cliente è anche responsabile dell'analisi e della risoluzione degli incidenti per dispositivi e servizi desktop non gestiti da Microsoft e per garantire che il team delle operazioni di Microsoft Managed Desktop sia sempre informato.
Infrastruttura di rete, inclusa la VPN | Il cliente è responsabile dell'installazione, della configurazione e della gestione (inclusi la risoluzione dei problemi e il debug) di tutti i servizi e infrastruttura connessi alla rete, tra cui la connettività Internet, i controlli di rete, la configurazione del proxy e l'infrastruttura di connettività remota.<br><br>Se un proxy è configurato (in hardware o software), è presente un insieme di URL che devono essere consentiti dal proxy. Il cliente è responsabile della risoluzione di eventuali conflitti o incompatibilità dovuti a più proxy. È possibile aggiungere proxy di rete specifici per l'organizzazione utilizzando impostazioni configurabili. Per ulteriori informazioni, vedere [impostazioni configurabili](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Per ulteriori informazioni, vedere [configurazione del proxy](../get-ready/network.md).
Stampa | Il cliente è responsabile per l'installazione, la manutenzione e l'amministrazione di stampanti e code di stampa. La stampa cloud è una soluzione consigliata, ma non è necessaria. 




