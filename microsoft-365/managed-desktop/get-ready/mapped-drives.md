---
title: Preparare unità mappate per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 34b2186ea3f9129ae7bb602aee879d7d23424136
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841065"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparare unità mappate per Microsoft Managed Desktop

Molti ambienti aziendali hanno requisiti legacy per le unità mappate per consentire agli utenti o ai team di condividere e archiviare file o per le applicazioni locali. Microsoft non consiglia l'uso di unità mappate con Microsoft Managed Desktop. È invece consigliabile modernizzare le soluzioni di accesso ai file nel modo seguente:
  
- Eseguire la migrazione delle unità mappate utilizzate dai singoli utenti a OneDrive for Business. 
- Eseguire la migrazione delle unità mappate utilizzate dai team per condividere file in SharePoint Online. 
- Modernizzare o sostituire le applicazioni che usano condivisioni file locali per rimuovere tale requisito.
  
La modernizzazione di questi servizi consentirà la migliore esperienza utente con Microsoft Managed Desktop. I servizi Microsoft FastTrack possono essere utili per modernizzare l'ambiente tramite Servizi cloud Microsoft. È possibile verificare se si è idonei per i servizi FastTrack in [Piani](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) e servizi idonei e quindi contattarli direttamente per prepararsi per Microsoft Managed Desktop. Per informazioni di base sulla migrazione di FastTrack OneDrive for Business o SharePoint Online, vedere [Migrazione dei dati.](https://docs.microsoft.com/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unità mappate in Microsoft Managed Desktop
 
Se non è possibile rimuovere o sostituire le unità mappate per alcuni casi d'uso, è necessario inviare una richiesta di supporto nel portale di amministrazione di Microsoft Managed Desktop per inviare loro la distribuzione agli utenti di Microsoft Managed Desktop.
    
Per una richiesta di questo tipo, dovrai fornire i dettagli seguenti nella richiesta di supporto: 

- Tutti i percorsi UNC ai percorsi di condivisione file che dovranno essere mappati per i dispositivi Microsoft Managed Desktop 
- Gruppi di utenti che richiedono l'accesso a questi percorsi di condivisione file 
- Qualsiasi lettera di unità specifica che deve essere assegnata (se necessario)

Ad esempio:

| Lettera di unità | Percorso UNC | Gruppo di utenti |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

È interamente responsabilità dell'utente assicurarsi che gli utenti e i gruppi dispongono e mantengano le autorizzazioni appropriate per accedere ai percorsi di condivisione file e che i servizi file locali rimangano accessibili. Inoltre, è consigliabile rimuovere i requisiti per tali condivisioni file il prima possibile.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Per distribuire unità mappate in Microsoft Managed Desktop
 
Assicurarsi che le unità mappate non siano evitate e di aver esaminato attentamente i requisiti prima di inviare qualsiasi richiesta di servizio. Eseguire quindi la procedura seguente:

1. Passare a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e selezionare "Risoluzione dei problemi e supporto" e quindi cercare "Richieste di servizio" nella sezione Microsoft Managed Desktop.  
2. Invia una richiesta di supporto intitolata "Distribuzione di unità mappate" e fornisci tutti i dettagli della condivisione file necessaria.  
3. Microsoft Managed Desktop IT Operations consiglia, utilizzando gli aggiornamenti delle richieste di supporto, quando la richiesta è stata completata. Inizialmente questa configurazione verrà distribuita solo ai dispositivi nel gruppo di distribuzione Test.  
4. È necessario verificare e verificare se la configurazione distribuita da Microsoft Managed Desktop IT Operations funziona come previsto. Rispondere utilizzando la scheda Discussione nei dettagli della stessa richiesta di supporto per inviare una notifica alle operazioni IT di Microsoft Managed Desktop dopo aver completato i test.  
5. Il team Microsoft Managed Desktop IT Operations distribuirà quindi la configurazione agli altri gruppi di distribuzione. 
