---
title: Crittografia per i dati in transito
f1.keywords:
- NOCSH
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
description: In questo articolo, trovare una breve spiegazione del modo in cui Microsoft crittografa i dati dei clienti di Microsoft 365 in transito.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7ee869308549398a9df00ed42975b4aeedb666a4
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033604"
---
# <a name="encryption-for-data-in-transit"></a>Crittografia per i dati in transito

Oltre a proteggere i dati dei clienti a riposo, Microsoft utilizza le tecnologie di crittografia per proteggere i dati dei clienti in transito. 

I dati sono in transito:

- Quando un computer client comunica con un server Microsoft;
- Quando un server Microsoft comunica con un altro server Microsoft; e
- Quando un server Microsoft comunica con un server non Microsoft (ad esempio, Exchange Online recapitare la posta elettronica a un server di posta elettronica di terze parti).

Le comunicazioni tra i datacenter tra i server Microsoft si verificano su TLS o IPsec e tutti i server con accesso client negoziano una sessione sicura tramite TLS con i propri computer (ad esempio, Exchange Online utilizza TLS 1,2 con il valore di crittografia a 256 bit (FIPS 140-2 Level 2-convalidato). (Vedere [informazioni di riferimento tecnico sulla crittografia](technical-reference-details-about-encryption.md) per un elenco dei gruppi di crittografia TLS supportati da Office 365). Questo vale per i protocolli utilizzati da client quali Outlook, Skype for business, Microsoft teams e Outlook sul Web (ad esempio, HTTP, POP3 e così via).

I certificati pubblici vengono emessi da Microsoft IT SSL tramite SSLAdmin, uno strumento interno di Microsoft per proteggere la riservatezza delle informazioni trasmesse. Tutti i certificati emessi da Microsoft hanno una lunghezza minima di 2048 bit e la conformità di WebTrust richiede SSLAdmin per assicurarsi che i certificati vengano emessi solo per gli indirizzi IP pubblici di proprietà di Microsoft. Tutti gli indirizzi IP che non rispondono a questo criterio vengono instradati tramite un processo di eccezione.

Tutti i dettagli sull'implementazione, ad esempio la versione di TLS utilizzata, l'abilitazione del segreto di inoltro (FS), l'ordine delle suite di crittografia e così via, sono disponibili pubblicamente. Un modo per visualizzare questi dettagli consiste nell'utilizzare un sito Web di terze parti, ad esempio [Qualys SSL Labs](https://www.ssllabs.com). Di seguito sono riportati i collegamenti alle pagine di test automatizzate di Qualys che visualizzano le informazioni relative ai servizi seguenti:

- [Portale di Office 365](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for business (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for business (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Per Exchange Online Protection, gli URL variano in base ai nomi dei tenant; Tuttavia, tutti i clienti possono testare Microsoft 365 utilizzando **Microsoft-com.mail.Protection.Outlook.com**.
