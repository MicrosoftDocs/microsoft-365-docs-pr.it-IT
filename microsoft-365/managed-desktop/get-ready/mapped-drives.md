---
title: Preparare unità mappate per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3fc4a4ed82c01188f348d2e494a0dbf7effc77a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34079271"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparare unità mappate per Microsoft Managed Desktop

Molti ambienti aziendali presentano requisiti legacy per le unità mappate per consentire agli utenti o ai team di condividere e archiviare file oppure per le applicazioni locali. Microsoft non consiglia l'utilizzo di unità mappate con Microsoft Managed Desktop. È consigliabile invece modernizzare le soluzioni di accesso ai file di Yor nel modo seguente:
  
- Eseguire la migrazione delle unità mappate utilizzate dai singoli utenti a OneDrive for business. 
- Eseguire la migrazione delle unità mappate utilizzate dai team per condividere i file in SharePoint Online. 
- Modernizzare o sostituire le applicazioni che utilizzano condivisioni di file locali per rimuovere tale requisito.
  
Modernizzare questi servizi consentirà la migliore esperienza degli utenti finali con Microsoft Managed Desktop. I servizi di Microsoft FastTrack consentono di modernizzare l'ambiente utilizzando i servizi cloud Microsoft. È possibile verificare se si è idonei per i servizi di FastTrack a [Servizi e piani idonei](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) e quindi contattarli direttamente per prepararsi per Microsoft Managed Desktop. Per informazioni generali su FastTrack OneDrive for business o sulla migrazione di SharePoint Online, vedere [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unità mappate su Microsoft Managed Desktop
 
Se non è possibile rimuovere o sostituire unità mappate per alcuni casi di utilizzo, è necessario inviare una richiesta di supporto nel portale Microsoft Managed Desktop per farli distribuire agli utenti di Microsoft Managed Desktop.
    
Per una richiesta di questo tipo, è necessario fornire i seguenti dettagli nella richiesta di supporto: 

- Tutti i percorsi UNC per le posizioni di condivisione file che dovranno essere mappate per i dispositivi Microsoft Managed Desktop 
- Gruppi di utenti che richiedono l'accesso a questi percorsi di condivisione file 
- Qualsiasi lettera di unità specifica che deve essere assegnata (se necessario)

Ad esempio:

| Lettera di unità | Percorso UNC | Gruppo di utenti |
|--------------|----------|------------|
| X  | \\\server\share\Marketing | ContosoMarketing |

È responsabilità del tutto garantire che gli utenti e i gruppi dispongano e mantengano le autorizzazioni appropriate per accedere ai percorsi di condivisione file e che i servizi di file locali siano accessibili. È inoltre necessario rimuovere i requisiti per tali condivisioni di file il più presto possibile.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Per disporre di unità mappate distribuite in Microsoft Managed Desktop
 
Verificare che le unità mappate non possano essere evitate e che siano stati esaminati accuratamente i requisiti prima di inviare qualsiasi richiesta di servizio. Eseguire quindi la procedura seguente:

1. Passare al [portale Microsoft Managed Desktop](https://aka.ms/mmdportal).  
2. Inviare una richiesta di supporto intitolata "distribuzione di unità mappate" tramite la sezione supporto **richieste di supporto di >** e fornire tutti i dettagli di condivisione file necessari.  
3. Le operazioni di Microsoft Managed Desktop consigliano, utilizzando gli aggiornamenti delle richieste di supporto, quando la richiesta è stata completata. Inizialmente questa configurazione verrà distribuita solo ai dispositivi del gruppo di distribuzione di test.  
4. È necessario verificare e verificare se la configurazione distribuita dal team di operazioni di Microsoft Managed Desktop funziona come previsto. Utilizzare la richiesta di supporto per aggiornare le operazioni di Microsoft Managed Desktop dopo aver completato il testing.  
5. Il team di Microsoft Managed Desktop Operations distribuirà la configurazione agli altri gruppi di distribuzione. 