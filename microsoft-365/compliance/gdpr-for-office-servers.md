---
title: RGPD per server di Office
description: Informazioni su come gestire i requisiti RGPD nei server locali di Office.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: b50722d7f37b54b38bac259b7c42d3bd782dfb3d
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557956"
---
# <a name="gdpr-for-office-on-premises-servers"></a>RGDP per server locali di Office

L'RGDP presenta i requisiti delle organizzazioni per proteggere i dati personali e rispondere in modo appropriato alle richieste del soggetto dei dati. Questa serie di articoli fornisce i metodi consigliati per i carichi di lavoro locali:

-   [SharePoint Server](gdpr-for-sharepoint-server.md)

-   [Exchange Server](gdpr-for-exchange-server.md)

-   [Skype for Business Server](gdpr-for-skype-for-business-server.md)

-   [Project Server](gdpr-for-project-server.md)

-   [Server Office Web Apps e Office Online Server](gdpr-for-office-online-server.md)

-   [Condivisioni file locali](gdpr-for-on-premises-file-shares.md)

Per ulteriori informazioni sull'RGDP e su come Microsoft può essere di aiuto, vedere [Centro protezione Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview
).

Prima di iniziare una qualsiasi operazione con i dati locali, consultare il team di conformità e il team legale per cercare informazioni sugli schemi di classificazione esistenti e sugli approcci all'utilizzo dei dati personali. Microsoft fornisce suggerimenti per lo sviluppo e per l'estensione degli schemi di classificazione nel Microsoft GDPR Data Discovery Toolkit in [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). Il toolkit descrive anche metodi per trasferire dati locali nel cloud, dove è possibile utilizzare funzionalità di gestione dati più complesse, se necessario. Gli articoli di questa sezione contengono suggerimenti per i dati che devono rimanere in locale.

Di seguito sono elencate funzionalità consigliate per ognuno di questi carichi di lavoro per individuare, classificare, proteggere e monitorare i dati personali. Vedere gli articoli in questa sezione per ulteriori informazioni.

![](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a>Descrizione dell'illustrazione

Ai fini dell'accessibilità, la seguente tabella fornisce le stesse informazioni dell'illustrazione.

|             |Condivisioni file di Windows Server|SharePoint Server|Exchange Server|Skype for Business|Project Server|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|Individuare|Scanner di Azure Information Protection|Centro ricerche o eDiscovery (dopo la classificazione dei dati); scanner di Azure Information Protection*|Portale eDiscovery di Exchange|Portale eDiscovery di Exchange|Script SQL per l'individuazione e l'esportazione|
|Classificare|Scanner di Azure Information Protection*; tipi di informazioni riservate di Office 365|Scanner di Azure Information Protection*; tipi di informazioni riservate di Office 365|Tag e criteri di conservazione di Exchange|Tag e criteri di conservazione di Exchange||
|Proteggere||Regole di prevenzione della perdita dei dati di Exchange Server; autorizzazioni, protezione IRM per le raccolte|Regole di prevenzione della perdita dei dati di Exchange Server; integrazione IRM con Exchange Server|||
|Monitorare|Integrazione di log con strumenti SIEM|Integrazione di log con strumenti SIEM|Integrazione di log con strumenti SIEM|Integrazione di log con strumenti SIEM|Integrazione di log con strumenti SIEM|

*Si noti che la protezione crittografa il file, di conseguenza, SharePoint Server non riesce a individuare tipi di informazioni riservate nei file protetti.
