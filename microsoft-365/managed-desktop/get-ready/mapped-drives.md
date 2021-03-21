---
title: Preparare unità mappate per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922909"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparare unità mappate per Microsoft Managed Desktop

Molti ambienti aziendali hanno requisiti legacy per le unità mappate per consentire agli utenti o ai team di condividere e archiviare file o per le applicazioni locali. Microsoft non consiglia l'uso di unità mappate con Microsoft Managed Desktop. È invece consigliabile modernizzare le soluzioni di accesso ai file nel modo seguente:
  
- Eseguire la migrazione delle unità mappate usate dai singoli utenti a OneDrive for Business. 
- Eseguire la migrazione delle unità mappate utilizzate dai team per condividere file in SharePoint Online. 
- Modernizzare o sostituire tutte le applicazioni che utilizzano condivisioni file locali per rimuovere tale requisito.
  
La modernizzazione di questi servizi consentirà la migliore esperienza utente con Microsoft Managed Desktop. Microsoft FastTrack Services consente di modernizzare l'ambiente utilizzando i servizi cloud Microsoft. Puoi verificare se sei idoneo per i servizi FastTrack in [Piani](/fasttrack/m365-eligible-services-and-plans) e servizi idonei e quindi contattarli direttamente per prepararti per Microsoft Managed Desktop. Per informazioni di base sulla migrazione di FastTrack OneDrive for Business o SharePoint Online, vedere [Migrazione dei dati.](/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unità mappate in Microsoft Managed Desktop
 
Se non è possibile rimuovere o sostituire le unità mappate per alcuni casi di utilizzo, è consigliabile inviare una richiesta di supporto nel portale di amministrazione di Microsoft Managed Desktop per inviare tali unità agli utenti di Microsoft Managed Desktop.
    
Per una richiesta di questo tipo, dovrai fornire i dettagli seguenti nella richiesta di supporto: 

- Tutti i percorsi UNC ai percorsi di condivisione file che dovranno essere mappati per i dispositivi Desktop gestito Microsoft 
- Gruppi di utenti che richiedono l'accesso a questi percorsi di condivisione file 
- Qualsiasi lettera di unità specifica che deve essere assegnata (se necessario)

Ad esempio:

| Lettera di unità | Percorso UNC | Gruppo utenti |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

È interamente responsabilità dell'utente assicurarsi che gli utenti e i gruppi dispongono e mantengano le autorizzazioni appropriate per accedere ai percorsi di condivisione file e che i servizi file locali rimangano accessibili. Inoltre, è consigliabile rimuovere i requisiti per tali condivisioni file il prima possibile.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Per distribuire unità mappate in Microsoft Managed Desktop
 
Assicurarsi che le unità mappate non siano evitate e che i requisiti siano stati esaminati attentamente prima di inviare qualsiasi richiesta di servizio. Eseguire quindi la procedura seguente:

1. Passa a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e seleziona "Risoluzione dei problemi e supporto", quindi cerca "Richieste di servizio" nella sezione Microsoft Managed Desktop.  
2. Inviare una richiesta di supporto intitolata "Distribuzione di unità mappate" e fornire tutti i dettagli necessari sulla condivisione file.  
3. Microsoft Managed Desktop IT Operations avvisa, utilizzando gli aggiornamenti delle richieste di supporto, quando la richiesta è stata completata. Inizialmente questa configurazione verrà distribuita solo ai dispositivi nel gruppo di distribuzione Test.  
4. È necessario verificare e verificare se la configurazione distribuita da Microsoft Managed Desktop IT Operations funziona come previsto. Rispondi usando la scheda Discussione nei dettagli della stessa richiesta di supporto per inviare una notifica a Microsoft Managed Desktop IT Operations dopo aver completato il test.  
5. Il team Microsoft Managed Desktop IT Operations distribuirà quindi la configurazione agli altri gruppi di distribuzione.