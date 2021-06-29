---
title: Novità di Microsoft Defender per Office 365
description: Informazioni sulle nuove funzionalità e funzionalità disponibili nella versione più recente di Microsoft Defender per Office 365.
keywords: novità di Microsoft Defender per Office 365, ga, generalmente disponibili, funzionalità, disponibili, nuove
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0a9eb63ed4508ff875324cf6fb0b4a8ad59cb29f
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177550"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Novità di Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Questo articolo elenca le nuove funzionalità della versione più recente di Microsoft Defender per Office 365. Le funzionalità attualmente in anteprima sono denotata **con (anteprima).**

Scopri di più guardando [questo video](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3).
> [!TIP]
> Non hai ancora Microsoft Defender per Office 365? [Contattare le vendite per avviare una versione di valutazione.](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="june-2021"></a>Giugno 2021

- Nuovo primo contatto suggerimento per la sicurezza all'interno dei criteri anti-phishing. Questa suggerimento per la sicurezza viene visualizzata quando i destinatari ricevono per la prima volta un messaggio di posta elettronica da un mittente o non ricevono spesso messaggi di posta elettronica da un mittente. Per ulteriori informazioni su questa impostazione e su come configurarla, vedere gli articoli seguenti:

- [Primo contatto suggerimento per la sicurezza](set-up-anti-phishing-policies.md#first-contact-safety-tip)
- [Configurare i criteri anti-phishing in Exchange Online Protection](configure-anti-phishing-policies-eop.md)
- [Configurare i criteri anti-phishing in Microsoft Defender per Office 365](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>Aprile/maggio 2021

- [Pagina](mdo-email-entity-page.md)entità di posta elettronica : visualizzazione unificata a 360 gradi di un messaggio di posta elettronica con informazioni avanzate su minacce, autenticazione e rilevamenti, dettagli di detonazione e un'esperienza di anteprima della posta elettronica nuova.
- [Office 365 Management API](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events): Aggiornamenti a EmailEvents (RecordType 28) per aggiungere l'azione di recapito, i percorsi di recapito originali e più recenti e i dettagli di rilevamento aggiornati.
- [Threat Analytics for Defender for Office 365](/microsoft-365/security/defender/threat-analytics): visualizzare gli attori delle minacce attive, le tecniche più popolari e le superfici di attacco, insieme a report approfonditi da parte dei ricercatori Microsoft sulle campagne in corso.

## <a name="februarymarch-2021"></a>Febbraio/marzo 2021

- Integrazione dell'ID avviso (ricerca con ID avviso e Alert-Explorer navigazione) nelle [esperienze di ricerca](threat-explorer.md)
- Aumento dei limiti per l'esportazione di record da 9990 a 200.000 in esperienze [di ricerca](threat-explorer.md)
- Estensione del limite di conservazione e ricerca dei dati di Explorer (e rilevamento in tempo [reale)](threat-explorer.md) per i tenant di prova da 7 (limite precedente) a 30 giorni nelle esperienze di ricerca
- Nuovi pivot di ricerca **denominati** dominio rappresentato e utente rappresentato all'interno di Esplora risorse (e rilevamenti in tempo reale) per cercare gli attacchi di rappresentazione contro utenti o domini protetti.  Per ulteriori informazioni, vedere [details](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains). (Microsoft Defender per Office 365 Piano 1 o Piano 2)

## <a name="december-2020"></a>Dicembre 2020

- [Protezione per impostazione predefinita in Office 365](secure-by-default.md)
- Miglioramenti delle indagini automatizzate a: avvisi generali per indagini di posta elettronica attivate manualmente, considerare le modifiche delle cassette postali come una categoria di entità separata, rimuovere le azioni di blocco url ridondanti e creare cluster di posta elettronica in uscita per indagini compromesse dall'utente.

## <a name="november-2020"></a>Novembre 2020

- Limiti di esportazione aggiornati in Review > Action Center > Remediation from Mail Submission and Action Log (Defender for Office 365 Plan 2)

## <a name="septemberoctober-2020"></a>Settembre/Ottobre 2020

- Nuovo primo contatto suggerimento per la sicurezza quando i destinatari ricevono per la prima volta un messaggio di posta elettronica da un mittente o non ricevono spesso messaggi di posta elettronica da un mittente. Per ulteriori informazioni su questa impostazione e su come configurarla Exchange regole del flusso di posta (note anche come regole di trasporto), vedere [First contact suggerimento per la sicurezza](set-up-anti-phishing-policies.md#first-contact-safety-tip).
- [Controllare i criteri con Configuration Analyzer](configuration-analyzer-for-security-policies.md)
- Funzionalità estese [in Threat Explorer,](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) inclusi gli utenti principali, le regole di trasporto e i connettori (informazioni su Defender per Office 365 in [Threat Explorer](threat-explorer.md) (la posta elettronica è stata consentita/bloccata dai criteri tenant/utente) (Defender per Office 365 Piano 2)
- Navigare le minacce URL in [Threat Explorer](threat-explorer.md#threats-in-urls) (malware, phish, spam o nessuno) (Defender per Office 365 Piano 2)
- [Miglioramenti a Hunting Experience Threat Explorer](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) con aggiornamenti relativi a minacce, azioni aggiuntive, posizioni di recapito e visualizzazione cronologia aggiornata (Defender per Office 365 Piano 2)

## <a name="julyaugust-2020"></a>Luglio/agosto 2020

- [Miglioramenti dell'esperienza di ricerca](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender per Office 365 Piano 1 o Piano 2)
- [Applicare facilmente le impostazioni consigliate usando criteri di sicurezza preimpostati](preset-security-policies.md)

## <a name="marchapril-2020"></a>Marzo/aprile 2020

- La possibilità di [gestire gli account utente compromessi con analisi](address-compromised-users-quickly.md) e risposte automatizzate è ora disponibile in genere. (Microsoft Defender per Office 365 Piano 2)

## <a name="januaryfebruary-2020"></a>Gennaio/febbraio 2020

- [Disponibilità generale delle visualizzazioni campagna in Microsoft Defender per Office 365](campaigns.md) (Microsoft Defender per Office 365 Piano 2)
- Miglioramenti a [Threat Explorer per](threat-explorer.md) consentire ai team delle operazioni di sicurezza di cercare e filtrare in base a più campi durante l'analisi della posta elettronica : (Microsoft Defender per Office 365 Piano 2) [](investigate-malicious-email-that-was-delivered.md)
  - Luogo di recapito e azioni speciali
  - Direzionalità (in ingresso, in uscita o all'interno dell'organizzazione)
  - Filtri NOT avanzati (si tratta di opzioni di filtro avanzate che includono non contiene, non include e così via)
  - Filtri tempo granulari (giorno, ora, mezz'ora)

- Il widget **Eventi** imprevisti è ora il widget **Centro** notifiche. Per visualizzare i widget di sicurezza nel Centro sicurezza & conformità, passare a **Gestione delle minacce** \> **Revisione**.) (Microsoft Defender per Office 365 Piano 2)

- [Cassaforte documenti in Microsoft 365](safe-docs.md) **(anteprima)**

## <a name="december-2019"></a>Dicembre 2019

- [Esportare i dati dei clic url per](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) l'analisi offline (Microsoft Defender per Office 365 Piano 1 o Piano 2)

- [Usare visualizzazioni campagna in Microsoft Defender per Office 365 (**anteprima**)](campaigns.md) (Microsoft Defender per Office 365 Piano 2)

## <a name="november-2019"></a>Novembre 2019

- [Scopri le nuove funzionalità di rilevamento e risposta](address-compromised-users-quickly.md) degli utenti compromesse (**anteprima**) (Microsoft Defender per Office 365 Piano 2)

## <a name="september-2019"></a>Settembre 2019

- [Utilizzare funzionalità di indagine e risposta automatizzate](automated-investigation-response-office.md) (Microsoft Defender per Office 365 Piano 2)

- [Integrazione con Microsoft Defender per Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) eventi di indagine e risposta automatizzati tramite l'API di Office 365 Management Activity (Defender per Office 365 Piano 2)

- [Visualizzare le intestazioni di posta elettronica e scaricare il corpo del messaggio](investigate-malicious-email-that-was-delivered.md) di posta elettronica (Microsoft Defender per Office 365 Piano 1 o Piano 2)

## <a name="august-2019"></a>Agosto 2019

- [Visualizzare la sequenza temporale della posta](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) elettronica (Microsoft Defender per Office 365 Piano 1 o Piano 2)

## <a name="july-2019"></a>Luglio 2019

- [Controllare l'azione di recapito e la posizione dei](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) messaggi di posta elettronica (Microsoft Defender per Office 365 Piano 1 o 2)

## <a name="june-2019"></a>Giugno 2019

- [Visualizzare gli URL di phishing e fare clic su Dati](threat-explorer.md#view-phishing-url-and-click-verdict-data) verdetto (Microsoft Defender per Office 365 Piano 1 o Piano 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender per Office 365 Piano 1 e Piano 2

Lo sai che Microsoft Defender per Office 365 è disponibile in due piani? [Ulteriori informazioni su ciò che include ogni piano](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2).

## <a name="see-also"></a>Vedere anche

[Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender for Office 365 Service Description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
