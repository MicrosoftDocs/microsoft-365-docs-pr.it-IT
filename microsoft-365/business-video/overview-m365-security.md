---
title: Panoramica di Microsoft 365 Business Premium Security
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni sulle funzionalità di sicurezza incluse in Microsoft 365 per le aziende.
ms.openlocfilehash: c0890f097177848ef5a75c7c139c7dbc69e4eba1
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007094"
---
# <a name="overview-of-security"></a>Panoramica della sicurezza

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Business Premium offre funzionalità di protezione dalle minacce, protezione dei dati e gestione dei dispositivi per proteggere l'azienda da minacce online e accessi non autorizzati, oltre a proteggere e gestire i dati aziendali su telefoni, tablet e computer.

|![Protezione dalle minacce](../media/m365-business-security-threat-protection.png)<br/>[Protezione dalle minacce](#threat-protection)|![Collaborare con un client](../media/m365-business-security-data-protection.png) <br/>[Protezione dei dati](#data-protection) | ![Gestione dei dispositivi](../media/m365-business-security-device-management.png) <br/>[Gestione dispositivi](#device-management) |
|--|--|--|

## <a name="threat-protection"></a>Protezione dalle minacce

Microsoft 365 Business Premium include [Office 365 Advanced Threat Protection (ATP),](safe-links.md)un servizio di filtro della posta elettronica basato su cloud che protegge da malware, ransomware, collegamenti dannosi e altro ancora. I collegamenti sicuri di ATP proteggono l'utente da URL dannosi nei messaggi di posta elettronica o nei documenti di Office. Gli allegati sicuri di ATP proteggono l'utente da malware e virus allegati a messaggi o documenti.

L'autenticazione a più fattori [(MFA)](turn-on-mfa.md)o la verifica in due passaggi richiede la presentazione di una seconda forma di autenticazione, ad esempio un codice di verifica, per confermare l'identità prima di poter accedere alle risorse.

[Windows Defender](/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10) fornisce una protezione completa per il sistema, i file e le attività online da virus, malware, spyware e altre minacce.

## <a name="data-protection"></a>Protezione dei dati

Le funzionalità di protezione dei dati in Microsoft 365 Business Premium assicurano che i dati importanti rimangano sicuri e che solo le persone autorizzate vi hanno accesso.

È possibile utilizzare i criteri di prevenzione della perdita dei dati [(DLP)](set-up-dlp.md) per identificare e gestire le informazioni riservate, ad esempio i numeri di previdenza sociale o di carta di credito, in modo che non vengono erroneamente condivise.

[La crittografia dei messaggi di Office 365](/microsoft-365/compliance/ome) combina le funzionalità di crittografia e diritti di accesso per garantire che solo i destinatari previsti possano visualizzare il contenuto dei messaggi. La crittografia dei messaggi di Office 365 funziona con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica.

[Archiviazione Exchange Online](/office365/servicedescriptions/exchange-online-archiving-service-description/exchange-online-archiving-service-description) è una soluzione di archiviazione basata su cloud che funziona con Microsoft Exchange o Exchange Online per fornire funzionalità di archiviazione avanzate, tra cui blocchi e ridondanza dei dati. È possibile utilizzare i criteri di conservazione per aiutare l'organizzazione a ridurre le responsabilità associate alla posta elettronica e ad altre comunicazioni. Se l'azienda deve conservare le comunicazioni relative a controversie legali, è possibile utilizzare i blocchi In-Place e le esenzioni per controversia legale per conservare la posta elettronica correlata.

## <a name="device-management"></a>Gestione dei dispositivi

Le funzionalità avanzate di gestione dei dispositivi di Microsoft 365 Business Premium consentono di monitorare e controllare le attività che gli utenti possono eseguire con i dispositivi registrati. Queste funzionalità includono l'accesso condizionale, [Gestione dispositivi mobili (MDM),](/microsoft-365/admin/basic-mobility-security/manage-enrolled-devices)BitLocker e gli aggiornamenti automatici.

È possibile utilizzare i criteri di accesso condizionale per richiedere misure di sicurezza aggiuntive per determinati utenti e attività. Ad esempio, è possibile richiedere l'autenticazione a più fattori [(MFA)](/microsoft-365/business-video/turn-on-mfa) o bloccare i client che non supportano l'accesso condizionale.

Con MDM, puoi proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e telefoni Windows. Puoi creare e gestire i criteri di sicurezza dei dispositivi, cancellare in remoto un dispositivo per rimuovere tutti i dati aziendali, ripristinare le impostazioni di fabbrica di un dispositivo e visualizzare report dettagliati sul dispositivo.

Puoi abilitare la crittografia BitLocker per proteggere i dati in caso di perdita o furto di un dispositivo e abilitare Windows Exploit Guard per fornire una protezione avanzata contro i ransomware.

È possibile configurare gli aggiornamenti automatici in modo che le funzionalità e gli aggiornamenti di sicurezza più recenti siano applicati a tutti i dispositivi utente.

## <a name="recommended-security-guidance"></a>Indicazioni consigliate per la sicurezza

Se si ha Microsoft Business Premium, il modo più rapido per configurare la sicurezza e iniziare a collaborare in modo sicuro consiste nel seguire le indicazioni fornite in questa raccolta: [Microsoft 365 per piccole imprese e campagne](../campaigns/index.md). Queste indicazioni sono state sviluppate in collaborazione con il team Microsoft Defending Democracy per proteggere tutti i clienti delle piccole imprese dalle minacce informatiche lanciate da hacker sofisticati.
