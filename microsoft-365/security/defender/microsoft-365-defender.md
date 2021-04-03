---
title: Microsoft 365 Defender
description: Microsoft 365 Defender è una soluzione di protezione dalle minacce coordinata progettata per proteggere dispositivi, identità, dati e applicazioni
keywords: introduzione a Microsoft Threat Protection, sicurezza informatica, minacce persistenti avanzate, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, indagini e correzioni automatizzate, ricerca avanzata
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 687077b1c9ff2449d9994875419a97cf0c503c2f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581083"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Vuoi provare Microsoft 365 Defender? Puoi [valutarlo in un ambiente lab](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [eseguire il progetto pilota in produzione](m365d-pilot.md?ocid=cx-evalpilot).
>

Microsoft 365 Defender è una famiglia di prodotti unificata di difesa aziendale pre e post-violazione che consente di coordinare in modo nativo rilevazione, prevenzione, indagini e risposta tra endpoint, identità, posta elettronica e applicazioni per offrire una protezione integrata dagli attacchi più sofisticati.

Con la soluzione integrata Microsoft 365 Defender, i professionisti della sicurezza possono unire i segnali di minaccia che ognuno di questi prodotti riceve e determinare l'ambito e l'impatto completi della minaccia; come è entrato nell'ambiente, su cosa ne è interessato e su come attualmente influisce sull'organizzazione. Microsoft 365 Defender adotta un'azione automatica per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati.  


<center><h2>Servizi di Microsoft 365 Defender</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender per Endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender per Office 365</b></center></a></td>
<td><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Guida interattiva a Microsoft 365 Defender

In questa guida interattiva imparerai a proteggere l'organizzazione con Microsoft 365 Defender. Vedrai come Microsoft 365 Defender può aiutarti a rilevare i rischi per la sicurezza, analizzare gli attacchi all'organizzazione e prevenire automaticamente le attività dannose.

[Consultare la guida interattiva](https://aka.ms/M365Defender-InteractiveGuide)



La famiglia di prodotti Microsoft 365 Defender protegge quanto segue: 
- **Endpoint con Microsoft Defender for Endpoint** - Microsoft Defender for Endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. 
- Posta elettronica e collaborazione con **Microsoft Defender per Office 365** - Defender per Office 365 protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. 
- Identità con Microsoft Defender per l'identità e **Azure AD Identity Protection** - Microsoft Defender for Identity usa i segnali di Active Directory per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni insider dannose indirizzate all'organizzazione. 
- **Applicazioni con sicurezza di Microsoft Cloud App** - La sicurezza di Microsoft Cloud App è una soluzione saaS completa che offre visibilità profonda, controlli dei dati forti e protezione avanzata dalle minacce per le tue app cloud. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

L'esclusivo livello cross-product di Microsoft 365 Defender aumenta i singoli componenti della famiglia di prodotti per:
- Proteggere dagli attacchi e coordinare le risposte difensive in tutta la famiglia di prodotti tramite la condivisione dei segnali e azioni automatizzate
- Narra la storia completa dell'attacco tra avvisi di prodotto, comportamenti e contesto per i team di sicurezza unendo i dati sugli avvisi, gli eventi sospetti e gli asset influenzati a "incidenti"
- Automatizzare la risposta alla compromissione attivando l'auto-riparazione per gli asset influenzati tramite correzione automatica
- Consentire ai team di sicurezza di eseguire una ricerca dettagliata ed efficace delle minacce tra endpoint e dati di Office

![Immagine della pagina di panoramica dell'evento imprevisto](../../media/overview-incident.png) <br>
Evento imprevisto tra prodotti (panoramica)

![Immagine della coda degli avvisi](../../media/incident-list.png)<br>
Tutti gli avvisi correlati tra i prodotti della famiglia di prodotti sono correlati in un singolo evento imprevisto (visualizzazione avvisi)

![Immagine della coda degli eventi imprevisti](../../media/advanced-hunting.png)<br>
Ricerca basata su query sulla posta elettronica e sui dati non elaborati dell'endpoint


Le funzionalità cross-product di Microsoft 365 Defender includono: 
- **Riquadro singolo** di vetro tra prodotti : consente di visualizzare centralmente tutte le informazioni relative a rilevamenti, asset influenzati, azioni automatizzate eseguite e prove correlate in una singola coda e in un singolo riquadro [in security.microsoft.com](https://security.microsoft.com). 
- **Coda degli** eventi imprevisti combinati: per aiutare i professionisti della sicurezza a concentrarsi su ciò che è fondamentale garantendo l'ambito di attacco completo, gli asset influenzati e le azioni di correzione automatizzate vengono raggruppati e visualizzati in modo appropriato. 
- **Risposta automatica alle** minacce: le informazioni sulle minacce critiche vengono condivise in tempo reale tra i prodotti Microsoft 365 Defender per impedire la progressione di un attacco. Ad esempio, se viene rilevato un file dannoso in un endpoint protetto da Microsoft Defender for Endpoint, verrà indicato a Defender per Office 365 di analizzare e rimuovere il file da tutti i messaggi di posta elettronica. Il file verrà bloccato a vista dall'intera famiglia di prodotti di sicurezza di Microsoft 365.
- Correzione automatica per i dispositivi **compromessi,** le identità utente e le cassette postali- Microsoft 365 Defender usa le azioni automatiche e i playbook basati su IA per correggere gli asset danneggiati di nuovo allo stato sicuro. Microsoft 365 Defender si avvale delle funzionalità di correzione automatica dei prodotti della famiglia di prodotti per garantire che tutte le risorse a impatto correlato a un evento imprevisto siano corretti automaticamente, se possibile.
- **Ricerca delle minacce** tra prodotti - I team di sicurezza possono sfruttare le proprie conoscenze organizzative uniche per cercare segni di compromissione creando query personalizzate sui dati non elaborati raccolti dai vari prodotti di protezione. Microsoft 365 Defender fornisce l'accesso basato su query a 30 giorni di segnali non elaborati storici e dati di avviso tra endpoint e dati di Microsoft Defender per Office 365. 


## <a name="get-started"></a>Informazioni di base
I requisiti di licenza di Microsoft 365 Defender devono essere soddisfatti prima di poter abilitare il servizio nel Centro sicurezza Microsoft 365 [in security.microsoft.com](https://security.microsoft.com). Per ulteriori informazioni, leggere:
- [Requisiti relativi alle licenze](prerequisites.md#licensing-requirements)
- [Attivare Microsoft 365 Defender](m365d-enable.md)
