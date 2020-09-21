---
title: Preparare unità mappate per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: fc216adadea8dd774901d42a754fb288412318a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104595"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparare unità mappate per Microsoft Managed Desktop

Molti ambienti aziendali presentano requisiti legacy per le unità mappate per consentire agli utenti o ai team di condividere e archiviare file oppure per le applicazioni locali. Microsoft non consiglia l'utilizzo di unità mappate con Microsoft Managed Desktop. È consigliabile invece modernizzare le soluzioni di accesso ai file come indicato di seguito:
  
- Eseguire la migrazione delle unità mappate utilizzate dai singoli utenti a OneDrive for business. 
- Eseguire la migrazione delle unità mappate utilizzate dai team per condividere i file in SharePoint Online. 
- Modernizzare o sostituire le applicazioni che utilizzano condivisioni di file locali per rimuovere tale requisito.
  
Modernizzare questi servizi consentirà la migliore esperienza utente con Microsoft Managed Desktop. I servizi di Microsoft FastTrack consentono di modernizzare l'ambiente utilizzando i servizi cloud Microsoft. È possibile verificare se si è idonei per i servizi di FastTrack a [Servizi e piani idonei](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) e quindi contattarli direttamente per prepararsi per Microsoft Managed Desktop. Per informazioni generali su FastTrack OneDrive for business o sulla migrazione di SharePoint Online, vedere [Data Migration](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unità mappate su Microsoft Managed Desktop
 
Se non è possibile rimuovere o sostituire unità mappate per alcuni casi di utilizzo, è necessario inviare una richiesta di supporto nel portale di amministrazione di Microsoft Managed Desktop per farli distribuire agli utenti di Microsoft Managed Desktop.
    
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

1. Passare a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e selezionare "risoluzione dei problemi + supporto", quindi cercare "richieste di servizio" nella sezione Microsoft Managed deskop.  
2. Inviare una richiesta di supporto intitolata "distribuzione di unità mappate" e fornire tutti i dettagli di condivisione file necessari.  
3. Operazioni IT di Microsoft Managed Desktop consiglierà, utilizzando gli aggiornamenti delle richieste di supporto, quando la richiesta è stata completata. Inizialmente questa configurazione verrà distribuita solo ai dispositivi del gruppo di distribuzione di test.  
4. È necessario verificare e verificare se la configurazione distribuita dalle operazioni IT di Microsoft Managed Desktop funziona come previsto. Rispondere utilizzando la scheda discussione nei dettagli della stessa richiesta di supporto per inviare una notifica alle operazioni IT di Microsoft Managed Desktop dopo aver completato il testing.  
5. Il team delle operazioni IT di Microsoft Managed Desktop IT distribuirà quindi la configurazione agli altri gruppi di distribuzione. 
