---
title: Preparare unità mappate per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che gli utenti possano accedere ai dati nelle unità mappate
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: f770f5083fe9193660b03e7971b09a127f2dae16
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574560"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Preparare unità mappate per Microsoft Managed Desktop

Molti ambienti aziendali hanno requisiti legacy per le unità mappate per consentire agli utenti o ai team di condividere e archiviare file o per le applicazioni locali. Microsoft non consiglia l'uso di unità mappate con il Microsoft Managed Desktop. È invece consigliabile modernizzare le soluzioni di accesso ai file nel modo seguente:
  
- Eseguire la migrazione delle unità mappate utilizzate dai singoli utenti OneDrive for Business. 
- Eseguire la migrazione delle unità mappate utilizzate dai team per condividere file SharePoint Online. 
- Modernizzare o sostituire tutte le applicazioni che utilizzano condivisioni file locali per rimuovere tale requisito.
  
La modernizzazione di questi servizi consentirà all'utente di ottenere la migliore esperienza Microsoft Managed Desktop. Microsoft FastTrack Services consente di modernizzare l'ambiente utilizzando i servizi cloud Microsoft. Puoi verificare se sei idoneo per i servizi FastTrack in [Piani](/fasttrack/m365-eligible-services-and-plans) e servizi idonei e quindi contattarli direttamente per prepararti per Microsoft Managed Desktop. Per informazioni di base su FastTrack OneDrive for Business o SharePoint online, vedere [Migrazione dei dati](/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Unità mappate in Microsoft Managed Desktop
 
Se non è possibile rimuovere o sostituire le unità mappate per alcuni casi d'uso, è consigliabile inviare una richiesta di supporto nel portale di amministrazione di Microsoft Managed Desktop per inviare tali unità Microsoft Managed Desktop utenti.
    
Per una richiesta di questo tipo, dovrai fornire i dettagli seguenti nella richiesta di supporto: 

- Tutti i percorsi UNC ai percorsi di condivisione file che dovranno essere mappati per Microsoft Managed Desktop dispositivi 
- Gruppi di utenti che richiedono l'accesso a questi percorsi di condivisione file 
- Qualsiasi lettera di unità specifica che deve essere assegnata (se necessario)

Ad esempio:

| Lettera di unità | Percorso UNC | Gruppo utenti |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

È interamente responsabilità dell'utente assicurarsi che gli utenti e i gruppi dispongono e mantengano le autorizzazioni appropriate per accedere ai percorsi di condivisione file e che i servizi file locali rimangano accessibili. Inoltre, è consigliabile rimuovere i requisiti per tali condivisioni file il prima possibile.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>Per distribuire unità mappate in Microsoft Managed Desktop
 
Assicurarsi che le unità mappate non siano evitate e che i requisiti siano stati esaminati attentamente prima di inviare qualsiasi richiesta di servizio. Eseguire quindi la procedura seguente:

1. Passa a [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) e seleziona "Risoluzione dei problemi e supporto", quindi cerca "Richieste di servizio" nella sezione Microsoft Managed Desktop assistenza.  
2. Inviare una richiesta di supporto intitolata "Distribuzione di unità mappate" e fornire tutti i dettagli necessari sulla condivisione file.  
3. Microsoft Managed Desktop Le operazioni IT avvisano, utilizzando gli aggiornamenti delle richieste di supporto, quando la richiesta è stata completata. Inizialmente questa configurazione verrà distribuita solo ai dispositivi nel gruppo di distribuzione Test.  
4. È necessario verificare e verificare se la configurazione distribuita dal Microsoft Managed Desktop it operations funziona come previsto. Rispondi usando la scheda Discussione nei dettagli della stessa richiesta di supporto per inviare Microsoft Managed Desktop operazioni IT dopo aver completato il test.  
5. Microsoft Managed Desktop Il team it operations distribuirà quindi la configurazione agli altri gruppi di distribuzione. 

## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).
2. [Utilizzare gli strumenti di valutazione della conformità](readiness-assessment-tool.md).
3. [Prerequisiti per gli account Guest](guest-accounts.md)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Preparare l'accesso alle risorse locali per Microsoft Managed Desktop](authentication.md)
7. [App in Microsoft Managed Desktop](apps.md)
8. [Preparare le unità mappate per Microsoft Managed Desktop](mapped-drives.md) (questo articolo)
9. [Preparare risorse di stampa per Microsoft Managed Desktop](printing.md)
