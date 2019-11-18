---
title: Crittografia di Office 365 per i dati in transito
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: 'Sintesi: breve descrizione del modo in cui Microsoft crittografa i dati in transito.'
ms.openlocfilehash: 571a0e28386539058a9998f703d7b4537e1a155a
ms.sourcegitcommit: 93cef4906c5495ae293450ceb52d6cc336f52b53
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690631"
---
# <a name="office-365-encryption-for-data-in-transit"></a>Crittografia di Office 365 per i dati in transito

Oltre a proteggere i dati dei clienti a riposo, Microsoft utilizza le tecnologie di crittografia per proteggere i dati dei clienti di Office 365 in transito. 

I dati sono in transito:

- Quando un computer client comunica con un server di Office 365;
- Quando un server di Office 365 comunica con un altro server di Office 365; e
- Quando un server di Office 365 comunica con un server non Office 365 (ad esempio, Exchange Online recapitare la posta elettronica a un server di posta elettronica esterno).

Le comunicazioni tra i datacenter tra i server di Office 365 si verificano su TLS o IPsec e tutti i server rivolti ai clienti negoziano una sessione sicura tramite TLS con i computer client (ad esempio, Exchange Online utilizza TLS 1,2 con la forza di crittografia a 256 bit (FIPS 140-2 livello 2-convalidato). Per un elenco dei gruppi di crittografia TLS supportati da Office 365, vedere [informazioni di riferimento tecnico sulla crittografia in office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) . Questo vale per i protocolli utilizzati da client quali Outlook, Skype for business e Outlook sul Web (ad esempio, HTTP, POP3 e così via).

I certificati pubblici vengono emessi da Microsoft IT SSL tramite SSLAdmin, uno strumento interno di Microsoft per proteggere la riservatezza delle informazioni trasmesse. Tutti i certificati emessi da Microsoft hanno una lunghezza minima di 2048 bit e la conformità di WebTrust richiede SSLAdmin per assicurarsi che i certificati vengano emessi solo per gli indirizzi IP pubblici di proprietà di Microsoft. Tutti gli indirizzi IP che non rispondono a questo criterio vengono instradati tramite un processo di eccezione.

Tutti i dettagli sull'implementazione, ad esempio la versione di TLS utilizzata, l'abilitazione del segreto di inoltro (FS), l'ordine delle suite di crittografia e così via, sono disponibili pubblicamente. Un modo per visualizzare questi dettagli consiste nell'utilizzare un sito Web di terze parti, ad esempio [Qualys SSL Labs](https://www.ssllabs.com). Di seguito sono riportati i collegamenti alle pagine di test automatizzate di Qualys che visualizzano le informazioni relative ai servizi seguenti:

- [Portale di Office 365](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for business (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for business (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Per Exchange Online Protection, gli URL variano in base ai nomi dei tenant; Tuttavia, tutti i clienti possono testare Office 365 utilizzando **Microsoft-com.mail.Protection.Outlook.com**.
