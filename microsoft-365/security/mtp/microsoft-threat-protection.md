---
title: Microsoft 365 Defender
description: Microsoft 365 Defender è una soluzione coordinata per la protezione dalle minacce progettata per proteggere dispositivi, identità, dati e applicazioni
keywords: introduzione a Microsoft Threat Protection, cyber security, minacce persistenti avanzate, sicurezza aziendale, dispositivi, dispositivo, identità, utenti, dati, applicazioni, incidenti, analisi e correzione automatizzate, ricerca avanzata
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e80a3d094ac8f5724bbe7daf72a0ded7d30091ba
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930571"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

> Si vuole provare Microsoft 365 Defender? È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)
>

Microsoft 365 Defender è una famiglia di prodotti di difesa aziendale pre e post-violazione unificata che coordina in modo nativo il rilevamento, la prevenzione, l'indagine e la risposta tra endpoint, identità, posta elettronica e applicazioni per fornire protezione integrata da attacchi sofisticati.

Con la soluzione microsoft 365 Defender integrata, i professionisti della sicurezza possono unire i segnali di minaccia che ognuno di questi prodotti riceve e determinare l'ambito e l'impatto della minaccia; come è entrato nell'ambiente, su cosa ne è interessato e su come influisce attualmente sull'organizzazione. Microsoft 365 Defender adotta un'azione automatica per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati.  


<center><h2>Servizi di Microsoft 365 Defender</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender per endpoint</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender per Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Guida interattiva di Microsoft 365 Defender

In questa guida interattiva scoprirai come proteggere l'organizzazione con Microsoft 365 Defender. Verrà illustrato in che modo Microsoft 365 Defender consente di rilevare i rischi per la sicurezza, analizzare gli attacchi all'organizzazione e impedire automaticamente attività dannose.

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



La famiglia di prodotti Microsoft 365 Defender protegge quanto segue: 
- **Endpoint con Microsoft Defender per endpoint:** Microsoft Defender for Endpoint è una piattaforma unificata per la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. 
- Posta elettronica e collaborazione con Microsoft Defender per **Office 365:** Defender per Office 365 protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. 
- Identità con Microsoft Defender for Identity e **Azure AD Identity Protection:** Microsoft Defender for Identity usa i segnali di Active Directory per identificare, rilevare e analizzare le minacce avanzate, le identità compromesse e le azioni insider dannose indirizzate all'organizzazione. 
- **Applicazioni con Microsoft Cloud App Security:** Microsoft Cloud App Security è una soluzione saaS completa che offre visibilità approfondita, controlli dei dati forti e protezione avanzata dalle minacce nelle app cloud. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

L'esclusivo livello di cross-product di Microsoft 365 Defender aumenta i singoli componenti della famiglia di prodotti per:
- Proteggiti dagli attacchi e coordina le risposte di difesa in tutta la famiglia di prodotti tramite la condivisione dei segnali e le azioni automatizzate
- Narrare la storia completa dell'attacco tra avvisi di prodotto, comportamenti e contesto per i team di sicurezza unendo i dati sugli avvisi, gli eventi sospetti e le risorse influenzate agli "incidenti"
- Automatizzare la risposta alla compromissione attivando la riparazione automatica per le risorse danneggiate tramite la correzione automatica
- Consentire ai team di sicurezza di eseguire una ricerca dettagliata ed efficace delle minacce tra endpoint e dati di Office

![Immagine della pagina di panoramica dell'incidente](../../media/overview-incident.png) <br>
Incidente tra prodotti (panoramica)

![Immagine della coda degli avvisi](../../media/incident-list.png)<br>
Tutti gli avvisi correlati tra i prodotti della famiglia di prodotti sono correlati in un singolo evento imprevisto (visualizzazione avvisi)

![Immagine della coda degli eventi imprevisti](../../media/advanced-hunting.png)<br>
Ricerca basata su query sulla posta elettronica e sui dati non elaborati dell'endpoint


Le funzionalità per il cross-product di Microsoft 365 Defender includono: 
- **Riquadro singolo** di vetro tra prodotti: consente di visualizzare centralmente tutte le informazioni relative a rilevamenti, risorse influenzate, azioni automatizzate eseguite e prove correlate in una singola coda e in un singolo riquadro in [security.microsoft.com](https://security.microsoft.com). 
- **Coda** degli eventi imprevisti combinati: per aiutare i professionisti della sicurezza a concentrarsi su ciò che è fondamentale garantendo l'ambito completo degli attacchi, le risorse influenzate e le azioni di correzione automatizzate vengono raggruppate e visualizzate in modo corretto. 
- **Risposta automatica alle** minacce: le informazioni critiche sulle minacce vengono condivise in tempo reale tra i prodotti Microsoft 365 Defender per arrestare la progressione di un attacco. Ad esempio, se viene rilevato un file dannoso in un endpoint protetto da Microsoft Defender for Endpoint, defender for Office 365 dovrà analizzare e rimuovere il file da tutti i messaggi di posta elettronica. Il file verrà bloccato a vista dall'intera famiglia di prodotti di sicurezza di Microsoft 365.
- Riparazione automatica per dispositivi **compromessi,** identità utente e cassette postali: Microsoft 365 Defender usa le azioni automatiche e i playbook basati sull'intelligenza artificiale per correggere gli asset danneggiati di nuovo in uno stato sicuro. Microsoft 365 Defender sfrutta le funzionalità di correzione automatica dei prodotti della famiglia di prodotti per garantire che tutte le risorse influenzate correlate a un evento imprevisto siano automaticamente corretti quando possibile.
- **Ricerca delle minacce** tra prodotti: i team di sicurezza possono sfruttare le proprie conoscenze organizzative uniche per cercare segni di compromissione creando query personalizzate sui dati non elaborati raccolti dai vari prodotti di protezione. Microsoft 365 Defender fornisce l'accesso basato su query a 30 giorni di segnali non elaborati e dati di avviso storici tra endpoint e dati di Microsoft Defender per Office 365. 


## <a name="get-started"></a>Per iniziare
I requisiti di licenza di Microsoft 365 Defender devono essere soddisfatti prima di poter abilitare il servizio nel Centro sicurezza Microsoft 365 [in security.microsoft.com](https://security.microsoft.com). Per ulteriori informazioni, leggere:
- [Requisiti relativi alle licenze](prerequisites.md#licensing-requirements)
- [Attivare Microsoft 365 Defender](mtp-enable.md)
