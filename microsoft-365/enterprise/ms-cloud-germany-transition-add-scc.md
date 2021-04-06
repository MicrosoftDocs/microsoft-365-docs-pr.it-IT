---
title: Informazioni sull'esperienza di eDiscovery durante la migrazione da Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Riepilogo: passaggi di migrazione di eDiscovery per la migrazione da Microsoft Cloud Deutschland.'
ms.openlocfilehash: 16da6e6d1994ae107b62ff1f915454568a35344d
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592136"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>Informazioni sull'esperienza di eDiscovery durante la migrazione da Microsoft Cloud Deutschland
Nelle sezioni seguenti vengono fornite ulteriori informazioni sull'esperienza di eDiscovery durante il passaggio da Microsoft Cloud Germania (Microsoft Cloud Deutschland) ai servizi di Office 365 nella nuova area data center tedesca.

## <a name="ediscovery-administration-until-phase-4"></a>Amministrazione di eDiscovery fino alla fase 4
Fino alla fase 4, il Centro sicurezza e conformità sarà completamente disponibile. Tutto il contenuto rimane ancora in Microsoft Cloud Germania ed è gestibile dal Centro sicurezza e conformità di Microsoft Cloud Germania ( https://protection.office.de/) .

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>Esperienza di eDiscovery tra la fase 4 e la fine della fase 9
Dall'inizio della fase 4 fino al completamento della fase 9, le ricerche eDiscovery avranno esito negativo o restituiranno 0 risultati per i percorsi di SharePoint Online, OneDrive for Business ed Exchange Online migrati.

> [!NOTE]
> Durante la migrazione, i clienti possono continuare a creare casi, blocchi, ricerche ed esportazioni nel [Centro sicurezza & conformità,](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)inclusa [ricerca contenuto.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) Tuttavia, le ricerche nei percorsi di SharePoint Online, OneDrive for Business ed Exchange Online di cui è stata eseguita la migrazione restituiranno 0 risultati o genereranno un errore.

Nel caso in cui una ricerca restituisca zero risultati o un errore durante la migrazione, eseguire l'azione seguente per SharePoint Online: 
- Scaricare i siti direttamente dal sito di SharePoint Online o OneDrive for Business seguendo le istruzioni in Scaricare file e cartelle [da OneDrive o SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Questo metodo richiede autorizzazioni di amministratore di SharePoint Online o autorizzazioni di sola lettura per il sito.
- Se vengono superati i limiti, come illustrato in Scaricare file e cartelle da OneDrive o [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)i clienti possono utilizzare il client di sincronizzazione di OneDrive for Business seguendo le indicazioni in Sincronizzare i file di SharePoint e Teams con il [computer.](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)

- Per ulteriori informazioni, vedere  [eDiscovery sul posto in Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery).


## <a name="ediscovery-administration-after-phase-9"></a>Amministrazione di eDiscovery dopo la fase 9

**Si applica a:** Tutti i clienti che utilizzano eDiscovery

Nella fase 9 verranno completati i passaggi finali per il passaggio alla nuova area data center tedesca. In questa fase verrà eseguita la migrazione di tutti i componenti del servizio rimanenti. Dopo la fase 9, l'uso del Centro sicurezza e conformità in Microsoft Cloud Germania (protection.office.de) non è più supportato. Usa invece il nuovo [Centro sicurezza](https://security.microsoft.com/) o [Centro](https://compliance.microsoft.com/) conformità. Tutti i dati sono stati migrati nei nuovi portali di amministrazione. 

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
|  Tutte le posizioni di SharePoint Online, OneDrive for Business ed Exchange Online sono state migrate insieme al Centro sicurezza e conformità (SCC). | Tutte le attività di eDiscovery devono essere eseguite dal tenant globale. Le ricerche avranno ora esito positivo al 100%. Eventuali errori o errori devono seguire i normali canali di supporto. | Nessuno |
||||

### <a name="ediscovery-retention-policy"></a>Criteri di conservazione di eDiscovery
**Si applica a:**  Tutti i clienti che hanno applicato un criterio di conservazione nell'ambito della procedura di pre-migrazione

| Step(s) | Descrizione | Impatto |
|:-------|:-------|:-------|
| Rimuovere i criteri di conservazione a livello di organizzazione creati durante la procedura di pre-migrazione | I clienti possono rimuovere i criteri di conservazione a livello di organizzazione creati durante le attività di pre-migrazione dei clienti. | Nessuno |
||||
