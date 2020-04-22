---
title: Crittografia dei dati in OneDrive for Business e SharePoint Online
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Informazioni sugli elementi di base della crittografia per la sicurezza dati in OneDrive for Business e SharePoint Online.
ms.openlocfilehash: e882bf3bf633c821fe50246316b5b1065cfa4693
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633341"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>Crittografia dei dati in OneDrive for Business e SharePoint Online

Informazioni sugli elementi di base della crittografia per la sicurezza dati in OneDrive for Business e SharePoint Online.
  
## <a name="overview"></a>Panoramica

Microsoft 365 è un ambiente altamente sicuro che offre una protezione estesa in più livelli: protezione dei data center fisici, sicurezza della rete, sicurezza dell'accesso, sicurezza delle applicazioni e sicurezza dei dati. In questo articolo viene illustrato il lato della crittografia in transito e inattiva della sicurezza dati di OneDrive for Business e SharePoint Online.
  
Per una descrizione della sicurezza di Microsoft 365 nel suo complesso, vedere [white paper sulla sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=270895).
  
Nel seguente video è possibile vedere in che modo funziona la crittografia dei dati.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>Crittografia dei dati in transito

In OneDrive for Business e SharePoint Online, esistono due scenari in cui i dati entrano ed escono dai data center.
  
- **Comunicazione client con il server** La comunicazione con OneDrive for Business tramite Internet utilizza connessioni SSL/TLS. Tutte le connessioni SSL vengono stabilite mediante chiavi a 2048 bit.

- **Spostamento dei dati tra data center** Il motivo principale dello spostamento di dati tra data center è la replica geografica per abilitare il ripristino di emergenza. Ad esempio, i registri transazioni di SQL Server e le differenze dell'archiviazione BLOB viaggiano lungo questa pipe. Mentre questi dati vengono già trasmessi utilizzando una rete privata, sono ulteriormente protetti mediante la migliore crittografia. 

## <a name="encryption-of-data-at-rest"></a>Crittografia dei dati statici

La crittografia inattiva include due componenti: Crittografia a livello di disco BitLocker e crittografia per file del contenuto cliente.
  
BitLocker viene distribuito per OneDrive for Business e SharePoint Online attraverso il servizio. La crittografia per file è anche in OneDrive for business e SharePoint online in Microsoft 365 multi-tenant e nuovi ambienti dedicati che sono basati su una tecnologia multi-tenant.
  
Mentre BitLocker esegue la crittografia di tutti i dati su un disco, la crittografia per file è ancora più approfondita includendo un'unica chiave di crittografia per ogni file. Inoltre, ogni aggiornamento di ogni file viene crittografata mediante la relativa chiave di crittografia. Prima di essere archiviate, le chiavi del contenuto crittografato vengono archiviate in una posizione fisica separata dal contenuto. Ogni passaggio di questo tipo di crittografia utilizza Advanced Encryption Standard (AES) con chiavi a 256 bit ed è conforme ai criteri FIPS (Federal Information Processing Standard) 140-2. Il contenuto crittografato viene distribuito in una serie di contenitori in tutto il data center ed ogni contenitore ha credenziali univoche. Queste credenziali vengono archiviate in una posizione fisica separata dal contenuto o dalle chiavi del contenuto.
  
Per ulteriori informazioni sulla conformità FIPS 140-2, vedere [Compliance fips 140-2](https://go.microsoft.com/fwlink/?LinkId=517625).
  
La crittografia a livello di file inattiva sfrutta l'archiviazione BLOB per fornire una crescita di archiviazione praticamente illimitata e per consentire una protezione senza precedenti. Tutti i contenuti dei clienti in OneDrive for Business e SharePoint Online verranno migrati nell'archiviazione BLOB. Ecco come vengono protetti i dati:
  
1. Tutto il contenuto viene crittografato, potenzialmente con più chiavi e distribuito in tutto il data center. Ogni file da archiviare viene suddiviso in uno o più blocchi, a seconda delle dimensioni. Successivamente, ogni blocco viene crittografato mediante la relativa chiave univoca. Gli aggiornamenti vengono gestiti in modo analogo: il set di modifiche o delta inviato da un utente viene suddiviso in blocchi e ognuno di questi blocchi viene crittografato con la sua chiave.

2. Tutti questi blocchi, ovvero file, blocchi di file e aggiornamento delta, verranno archiviati come BLOB nell'archiviazione BLOB. Inoltre vengono casualmente distribuiti in più contenitori BLOB.

3. La "mappa" utilizzata per riassemblare il file è memorizzata nel database del contenuto.

4. Ogni contenitore BLOB ha credenziali univoche per ogni tipo di accesso (lettura, scrittura, enumerazione ed eliminazione). Ogni set di credenziali è conservato nell'archivio chiavi protetto e viene regolarmente aggiornato.

In altre parole, sono disponibili tre tipi diversi di archivi necessari per la crittografia per file inattiva, ognuna con una funzione distinta:
  
- Il contenuto viene archiviato come BLOB crittografati nell'archiviazione BLOB. La chiave di ogni blocco di contenuto è crittografata e conservata separatamente nel database del contenuto. Il contenuto stesso non contiene alcuna indicazione su come può essere decrittografato.

- Il database del contenuto è un database SQL Server. Contiene la mappa necessaria per individuare e riunire tutti i contenuti BLOB contenuti nell'archiviazione BLOB, nonché le chiavi necessarie per decrittografare tali BLOB.

Ognuno di questi tre componenti di archiviazione, ovvero l'archiviazione BLOB, il database del contenuto e l'archivio chiavi, è separato fisicamente. Le informazioni contenute in uno dei componenti sono inutilizzabili da sole. Questa funzionalità offre un livello di sicurezza senza precedenti. Senza accesso a tutti e tre non è possibile recuperare le chiavi dei blocchi, decrittografare le chiavi per renderli utilizzabili, associare le chiavi ai blocchi corrispondenti, decrittografare i blocchi né ricostruire un documento dai blocchi che lo compongono.
