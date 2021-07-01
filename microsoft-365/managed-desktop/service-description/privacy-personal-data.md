---
title: Privacy e dati personali
description: Dettagli sui dati raccolti, archiviati e utilizzati dal servizio
keywords: GDPR, conservazione, eliminazione, archiviazione, conservazione, elaborazione, sicurezza, controllo
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 0ee214cf7ff5d5998a7fa35688574a23f8b082f0
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229600"
---
# <a name="overview"></a>Panoramica

Microsoft Managed Desktop è un servizio IT-as-a-Service (ITaaS) per i clienti cloud aziendali progettato per mantenere distribuiti e aggiornati i dispositivi Windows dipendenti. Fornisce inoltre la gestione e le operazioni dei servizi IT, monitora la sicurezza e la risposta agli incidenti, oltre a fornire supporto agli utenti. Questa documentazione fornisce ulteriori dettagli sulla piattaforma dati e sulla conformità alla privacy per Microsoft Managed Desktop.

## <a name="microsoft-managed-desktop-data-sources-and-purpose"></a>Microsoft Managed Desktop origini dati e scopo

Microsoft Managed Desktop fornisce il proprio servizio ai clienti aziendali e gestisce correttamente i dispositivi registrati dei clienti utilizzando dati provenienti da diverse origini. Queste origini, tra cui Azure Active Directory, Microsoft Intune, Microsoft Windows 10 e Microsoft Defender for Endpoint, offrono una visualizzazione completa dei dispositivi che Microsoft Managed Desktop gestire. Il servizio usa anche questi servizi Microsoft per abilitare Microsoft Managed Desktop fornire funzionalità ITaaS:

- [Microsoft Windows 10 Enterprise-](/windows/windows-10/) per la gestione dell'esperienza di configurazione dei dispositivi, la gestione delle connessioni ad altri servizi e il supporto operativo per i professionisti IT.
- [Windows Update for Business:](/windows/deployment/update/waas-manage-updates-wufb) usa Windows 10 Enterprise dati di diagnostica per fornire ulteriori informazioni sull Windows 10 aggiornamento. 
- [Microsoft Endpoint Manager:](/mem/endpoint-manager-overview) per la gestione dei dispositivi e per proteggere i dati.
  - [Microsoft Azure Active Directory](/azure/active-directory/) - per l'autenticazione e l'identificazione di tutti gli account utente. 
  - [Microsoft Intune:](/mem/intune/) per la distribuzione delle configurazioni dei dispositivi, la gestione dei dispositivi e la gestione delle applicazioni.
  - [Endpoint Analytics:](/mem/analytics/overview) per informazioni analitiche sull'utilizzo di dispositivi e app.
  - [Windows Autopilot](/microsoft-365/windows/windows-autopilot) : per il provisioning e la distribuzione dei dispositivi.
  - [Microsoft Defender for Endpoint:](/microsoft-365/security/defender-endpoint/) fornisce servizi di sicurezza come il monitoraggio della sicurezza dei dispositivi e i dati di intelligence per la sicurezza.
- [Microsoft Managed Desktop:](https://endpoint.microsoft.com/#home) dati forniti dal cliente o generati dal servizio durante l'esecuzione del servizio.
- [Microsoft 365 per le aziende](https://www.microsoft.com/en-us/microsoft-365/enterprise/compare-office-365-plans?rtc=1) – per la gestione di Microsoft 365 Apps.

## <a name="microsoft-managed-desktop-data-process-and-storage"></a>Microsoft Managed Desktop e archiviazione dei dati

Microsoft Managed Desktop si basa sui dati di più prodotti e servizi Microsoft per fornire il proprio servizio ai clienti aziendali. Per raggiungere l'obiettivo di proteggere e mantenere i dispositivi registrati, eelaborare e copiare i dati da questi servizi a Microsoft Managed Desktop. Quando eseguiamo i dati, seguiamo le indicazioni documentate fornite dall'utente, come indicato nelle Condizioni dei Servizi online e nell'Informativa sulla privacy Microsoft. Quando eseguiamo i dati, seguiamo le indicazioni documentate fornite dall'utente, come indicato nelle Condizioni dei Servizi [online](https://www.microsoft.com/licensing/product-licensing/products) e nell'Informativa [sulla privacy Microsoft.](https://privacy.microsoft.com/privacystatement) Microsoft Managed Desktop del processore includono la garanzia di riservatezza, sicurezza e resilienza appropriate. Microsoft Managed Desktop adotta ulteriori misure di privacy e sicurezza per garantire una corretta gestione dei dati personali identificabili. 


## <a name="microsoft-managed-desktop-data-storage-and-staff-location"></a>Microsoft Managed Desktop dell'archiviazione dei dati e della posizione del personale

Microsoft Managed Desktop i propri dati nei data center di Azure negli Stati Uniti. I dati personali ottenuti da Microsoft Managed Desktop e altri servizi sono necessari per mantenere operativo il servizio. Se un dispositivo viene rimosso da Microsoft Managed Desktop, microsoft conserva i dati personali per un massimo di 30 giorni ad eccezione dei dati di avviso raccolti da Microsoft Defender per Endpoint, che viene archiviato per 180 giorni per motivi di sicurezza. Per ulteriori informazioni sulla conservazione dei dati, vedere [Conservazione, eliminazione](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)e distruzione dei dati in Microsoft 365 .

Microsoft Managed Desktop I team di Engineering Operations e Security Operations si trovano negli Stati Uniti e in India. 

## <a name="microsoft-windows-10-diagnostic-data"></a>Dati di diagnostica Windows 10 Microsoft

Microsoft Managed Desktop utilizza [Windows 10 dati di diagnostica](/windows/privacy/windows-diagnostic-data) ottimizzati per mantenere Windows, aggiornati, risolvere i problemi e apportare miglioramenti al prodotto. L'impostazione dei dati di diagnostica avanzata include informazioni più dettagliate sui dispositivi registrati in Microsoft Managed Desktop e le relative impostazioni, funzionalità e integrità del dispositivo. Quando si selezionano dati di diagnostica avanzata, vengono raccolti i dati, inclusi i dati di diagnostica necessari. Vedi [Modifiche alla raccolta Windows dati di](/windows/privacy/changes-to-windows-diagnostic-data-collection) diagnostica per altre informazioni sull'impostazione Windows 10 dati di diagnostica e sulla raccolta dei dati.

La terminologia dei dati di diagnostica cambierà nelle versioni future di Windows. Microsoft Managed Desktop si impegna a elaborare solo i dati di cui ha bisogno il servizio. Anche se questo significa che il livello di diagnostica cambierà in Facoltativo, Microsoft Managed Desktop implementerà i criteri di diagnostica limitati per ottimizzare la raccolta dei dati di diagnostica necessaria per il servizio. Per ulteriori dettagli, vedere [Changes to Windows diagnostic data collection](/windows/privacy/changes-to-windows-diagnostic-data-collection).

Microsoft Managed Desktop elabora e archivia solo i dati a livello di sistema da Windows 10 dati di diagnostica facoltativi provenienti da dispositivi registrati, ad esempio l'affidabilità delle applicazioni e dei dispositivi e le informazioni sulle prestazioni. Microsoft Managed Desktop non elabora e archivia i dati personali dei clienti, ad esempio la cronologia di chat e browser, i dati vocali, di testo o vocali. 

Per ulteriori informazioni sulla raccolta dei dati di diagnostica [](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) di Microsoft Windows 10, vedere la sezione Dove archiviamo ed eseiamo i dati personali dell'Informativa sulla privacy Microsoft.

## <a name="microsoft-windows-update-for-business"></a>Microsoft Windows Update for Business
Microsoft Windows Update for Business usa i dati di Windows diagnostica per analizzare lo stato e gli errori degli aggiornamenti. Microsoft Managed Desktop sfrutta questi dati e lo usa per ridurre e risolvere i problemi per garantire che tutti i dispositivi registrati siano aggiornati in base a una cadenza di aggiornamento predefinita.

## <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory
L'identificazione dei dati utilizzati da Microsoft Managed Desktop viene archiviata da Azure Active Directory (Azure AD) in una posizione geografica in base alla posizione fornita dall'organizzazione durante la sottoscrizione ai servizi online Microsoft, ad esempio Microsoft Apps per le aziende e Azure. L'identificazione dei dati usati da Microsoft Managed Desktop viene archiviata da Azure AD in una posizione geografica in base alla posizione fornita dall'organizzazione durante la sottoscrizione ai servizi online Microsoft, ad esempio Microsoft Apps per le aziende e Azure. Per altre informazioni sulla posizione dei dati di Azure AD, [vedere Azure Active Directory - Dove si trovano i dati?](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)

## <a name="microsoft-intune"></a>Microsoft Intune
Microsoft Intune raccoglie, elabora e condivide i dati Microsoft Managed Desktop per supportare le operazioni e i servizi aziendali. Per [altre informazioni](/mem/intune/protect/privacy-data-collect) sui dati raccolti in Intune, vedere Raccolta di dati in Intune. 

Per ulteriori informazioni sulle posizioni Microsoft Intune dati, vedere [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations). Intune rispetta le selezioni della posizione di archiviazione effettuate dall'amministratore per i dati dei clienti.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender per endpoint
Microsoft Defender for Endpoint raccoglie e archivia le informazioni per i dispositivi registrati in Microsoft Managed Desktop per scopi di amministrazione, monitoraggio e creazione di report. Le informazioni raccolte includono dati di file (ad esempio nomi di file, dimensioni e hash), dati di processo (processi in esecuzione, hash), dati del Registro di sistema, dati di connessione di rete e dettagli del dispositivo (ad esempio identificatori di dispositivo, nomi di dispositivi e versione del sistema operativo). Vedi [Microsoft Defender per l'archiviazione e](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) la privacy dei dati degli endpoint per altre informazioni su Microsoft Defender per la raccolta e la posizione di archiviazione dei dati di Endpoint. 

## <a name="microsoft-365-apps-for-enterprise"></a>Microsoft 365 Apps for enterprise 
Microsoft 365 Apps for enterprise raccoglie e condivide i dati con Microsoft Managed Desktop per garantire che tali app siano aggiornate con la versione più recente in base ai canali di aggiornamento predefiniti gestiti da Microsoft Managed Desktop. Vedi [Microsoft Defender per l'archiviazione e](/microsoft-365/security/defender-endpoint/data-storage-privacy#what-data-does-microsoft-defender-atp-collect) la privacy dei dati degli endpoint per altre informazioni sulla raccolta dei Microsoft 365 Apps e sulle posizioni di archiviazione dei dati.

## <a name="major-data-change-notification"></a>Notifica di modifica dei dati principali
Microsoft Managed Desktop segue un processo di controllo delle modifiche come descritto nel framework di comunicazione dei servizi. Microsoft comunica ai clienti tramite il Microsoft 365 Message Center e Microsoft Managed Desktop admin portal degli incidenti di sicurezza e delle modifiche principali apportate al servizio. Le modifiche apportate ai tipi di dati raccolti e alla posizione in cui sono archiviati vengono considerate modifiche materiali. Microsoft fornirà un minimo di 30 giorni di notifica avanzata di questa modifica, come è la pratica standard per i prodotti Microsoft 365 e i servizi. Per ulteriori informazioni, vedere [Service changes and communication](/microsoft-365/managed-desktop/service-description/servicechanges).

## <a name="compliance"></a>Conformità
Microsoft Managed Desktop ha subito controlli esterni e ha ottenuto un set completo di offerte di conformità. Per ulteriori informazioni, vedere Microsoft Managed Desktop [conformità](/microsoft-365/managed-desktop/intro/compliance). I report di controllo sono disponibili per il download nel Portale microsoft [per](https://aka.ms/stp)l'attendibilità dei servizi, che funge da archivio centrale per Microsoft Enterprise Online Services. (Microsoft Managed Desktop è elencato all'interno di questi documenti nella categoria "Monitoraggio e gestione.") 

## <a name="legal"></a>Esigenze legali
Informativa sulla privacy di Microsoft agli utenti finali dei prodotti forniti dai clienti **dell'organizzazione - L'Informativa** sulla privacy [Microsoft](https://privacy.microsoft.com/privacystatement) notifica agli utenti finali che, quando accedono ai prodotti Microsoft con un account aziendale, a) l'organizzazione può controllare e amministrare il proprio account (incluso il controllo delle impostazioni relative alla privacy) e accedere ed elaborare i dati e b) Microsoft può raccogliere ed elaborare i dati per fornire il servizio all'organizzazione e agli utenti finali.
