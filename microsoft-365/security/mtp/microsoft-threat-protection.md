---
title: Microsoft 365 Defender
description: Microsoft 365 Defender è una soluzione coordinata per la protezione dalle minacce, progettata per proteggere dispositivi, identità, dati e applicazioni
keywords: Introduzione a Microsoft Threat Protection, Cyber Security, Advanced Persistent Threat, sicurezza dell'organizzazione, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi automatizzata e correzione, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 1884f0dae87bf068d134430ada78e44d713fd4d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780521"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Vuoi provare Microsoft 365 Defender? È possibile [valutarla in un ambiente lab](https://aka.ms/mtp-trial-lab) o [eseguire il progetto pilota in produzione](https://aka.ms/m365d-pilotplaybook).
>

Microsoft 365 Defender è una famiglia di prodotti di difesa aziendale unificata che coordina in modo nativo il rilevamento, la prevenzione, l'analisi e la risposta tra endpoint, identità, posta elettronica e applicazioni per garantire la protezione integrata da attacchi sofisticati.

Con la soluzione integrata Microsoft 365 Defender, i professionisti della sicurezza possono unire i segnali di minaccia che ognuno di questi prodotti riceve e determina l'intero ambito e l'impatto della minaccia; come è entrata nell'ambiente, cosa ne è interessata e come sta attualmente influenzando l'organizzazione. Microsoft 365 Defender esegue un'azione automatica per impedire o arrestare le cassette postali, gli endpoint e le identità degli utenti coinvolti.  


<center><h2>Servizi Microsoft 365 Defender</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender per endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender per Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender per l'identità</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Sicurezza delle app di Microsoft Cloud</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Guida interattiva Microsoft 365 Defender

In questa guida interattiva, vengono fornite informazioni su come proteggere l'organizzazione con Microsoft 365 Defender. Vedrai come Microsoft 365 Defender può aiutare a rilevare i rischi per la sicurezza, indagare sugli attacchi alla propria organizzazione e prevenire automaticamente le attività dannose.

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender Suite protegge: 
- **Endpoint con Microsoft Defender per endpoint** -Microsoft Defender per endpoint è una piattaforma endpoint unificata per la protezione preventiva, il rilevamento post-violazione, l'analisi automatizzata e la risposta. 
- La **posta elettronica e la collaborazione con Microsoft Defender per office 365** -Defender per Office 365 salvaguarda la propria organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. 
- **Identità con Microsoft Defender per Identity e Azure ad Identity Protection** -Microsoft Defender for Identity utilizza segnali di Active Directory per identificare, rilevare ed esaminare le minacce avanzate, le identità compromesse e le azioni Insider dannose indirizzate alla propria organizzazione. 
- **Applicazioni con Microsoft cloud app Security** -Microsoft cloud app Security è una soluzione cross-SaaS completa che introduce una visibilità profonda, forti controlli dati e una protezione avanzata dalle minacce per le app cloud. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender ' s Unique cross-product layer aumenta i singoli componenti della famiglia per:
- Contribuire alla protezione contro gli attacchi e coordinare le risposte difensive attraverso la famiglia attraverso la condivisione dei segnali e le azioni automatiche
- Raccontare la storia completa dell'attacco tra avvisi di prodotto, comportamenti e contesto per i team di sicurezza unendo i dati su avvisi, eventi sospetti e risorse interessate a' incidenti '
- Automatizzare la risposta al compromesso mediante l'attivazione della correzione automatica per le risorse interessate tramite la correzione automatica
- Consentire ai team di sicurezza di eseguire la ricerca di minacce dettagliate ed effettive tra endpoint e dati di Office

![Immagine della pagina Panoramica sugli incidenti](../../media/overview-incident.png) <br>
Evento incrociato tra i prodotti (panoramica)

![Immagine della coda di avvisi](../../media/incident-list.png)<br>
Tutti gli avvisi correlati tra i prodotti della suite correlati tra loro in un singolo incidente (visualizzazione avvisi)

![Immagine della coda degli incidenti](../../media/advanced-hunting.png)<br>
Caccia basata su query in cima alla posta elettronica e ai dati non elaborati dell'endpoint


Le funzionalità di Microsoft 365 Defender sono: 
- **Riquadro singolo tra prodotti di vetro** -centrale visualizzare tutte le informazioni per i rilevamenti, le risorse interessate, le azioni automatizzate eseguite e le evidenze correlate in una singola coda e in un unico riquadro in [Security.Microsoft.com](https://security.microsoft.com). 
- **Coda degli incidenti combinati** -per aiutare i professionisti della sicurezza a concentrarsi su ciò che è critico, assicurando che l'ambito di attacco completo, le risorse interessate e le azioni di correzione automatizzate vengano raggruppate e riemerse in modo tempestivo. 
- **Risposta automatica alle minacce** : le informazioni di minacce critiche sono condivise in tempo reale tra i prodotti Microsoft 365 Defender per impedire la progressione di un attacco. Ad esempio, se un file dannoso viene rilevato su un endpoint protetto da Microsoft Defender per endpoint, incaricherà Defender per Office 365 di analizzare e rimuovere il file da tutti i messaggi di posta elettronica. Il file verrà bloccato a vista dall'intera famiglia di prodotti Microsoft 365 Security.
- **Auto-guarigione per i dispositivi compromessi, le identità degli utenti e le cassette postali** -Microsoft 365 Defender utilizza le azioni automatiche ai e i PlayBook per correggere le risorse interessate di nuovo in uno stato sicuro. Microsoft 365 Defender utilizza le funzionalità di correzione automatica dei prodotti della famiglia per garantire che tutte le risorse interessate a un evento imprevisto vengano automaticamente rimediate laddove possibile.
- **Cross-product Threat Hunting** -i team di sicurezza possono sfruttare le proprie conoscenze organizzative esclusive per cercare segni di compromesso creando query personalizzate sui dati non elaborati raccolti dai vari prodotti di protezione. Microsoft 365 Defender fornisce l'accesso basato su query a 30 giorni di segnali RAW e dati di avviso cronologici tra endpoint e Microsoft Defender per i dati di Office 365. 


## <a name="get-started"></a>Per iniziare
I requisiti di licenza di Microsoft 365 Defender devono essere soddisfatti prima di poter abilitare il servizio nel centro sicurezza di Microsoft 365 all' [Security.Microsoft.com](https://security.microsoft.com). Per ulteriori informazioni, vedere:
- [Requisiti relativi alle licenze](prerequisites.md#licensing-requirements)
- [Attiva Microsoft 365 Defender](mtp-enable.md)
