---
title: Record DNS necessari per Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Riepilogo: record DNS per Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691156"
---
# <a name="dns-records-for-office-365-gcc-high"></a>Record DNS necessari per Office 365 GCC High

*Questo articolo si applica a Office 365 GCC High e Microsoft 365 GCC High*

Come parte dell'onboarding di Office 365 GCC High, sarà necessario aggiungere i domini SMTP e SIP al tenant dei servizi online.  Per eseguire questa operazione, utilizzare il cmdlet New-MsolDomain in Azure AD PowerShell o utilizzare il [portale di amministrazione di Azure](https://portal.azure.us) per iniziare il processo di aggiunta del dominio e la proprietà di prova.

Dopo aver aggiunto i domini al tenant e convalidati, utilizzare le linee guida seguenti per aggiungere i record DNS corretti per i servizi riportati di seguito.  Potrebbe essere necessario modificare la tabella seguente per adattare le esigenze dell'organizzazione in relazione ai record MX in ingresso e a qualsiasi record di individuazione automatica di Exchange esistente.  È consigliabile coordinare questi record DNS con il team di messaggistica per evitare interruzioni o mancato recapito del messaggio di posta elettronica.

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | Nome host | Punta all'indirizzo o al valore | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*. mail.Protection.office365.US (vedere di seguito per ulteriori informazioni) | 1 Hour |
| TXT | - | @ | v = spf1 include: SPF. Protection. office365. us-all | 1 ora |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Record di individuazione automatica di Exchange

Se si dispone di Exchange Server locale, è consigliabile lasciare il record esistente durante la migrazione a Exchange Online e aggiornare tale record dopo aver completato la migrazione. 

### <a name="exchange-online-mx-record"></a>Record MX di Exchange Online

Il valore del record MX per i domini accettati segue un formato standard, come indicato in alto: *tenant*. mail.Protection.office365.US, sostituendo *tenant* con la prima parte del nome predefinito del tenant.

Ad esempio, se il nome del tenant è contoso.onmicrosoft.us, è necessario utilizzare **contoso.mail.Protection.office365.US** come valore per il record MX.

## <a name="skype-for-business-online"></a>Skype for Business online

### <a name="cname-records"></a>Record CNAME

| Tipo | Nome host | Punta all'indirizzo o al valore | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 ora |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 Hour |

### <a name="srv-records"></a>Record SRV

| Tipo | Servizio | Protocollo | Porta | Peso | Priority | Nome | Destinazione | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_TLS | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 ora |
| SRV | \_sipfederationtls | \_TCP | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Record DNS aggiuntivi

> [!IMPORTANT]
> Se si dispone di un record CNAME di *msoID* esistente nella propria area DNS, è necessario **rimuovere** il record da DNS in questo momento.  Il record msoID non è compatibile con le app di Microsoft 365 Enterprise *(in precedenza Office 365 ProPlus)* e impedirà l'attivazione.
