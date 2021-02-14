---
title: Record DNS per Office 365 DoD
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
description: 'Riepilogo: record DNS per Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691167"
---
# <a name="dns-records-for-office-365-dod"></a>Record DNS per Office 365 DoD

*Questo articolo si applica a Office 365 DoD e Microsoft 365 DoD*

Come parte dell'onboarding in Office 365 DoD, è necessario aggiungere i domini SMTP e SIP al tenant dei Servizi online.  A tale scopo, puoi usare il cmdlet New-MsolDomain in Azure AD PowerShell o usare il portale azure [per](https://portal.azure.us) enti pubblici per avviare il processo di aggiunta del dominio e dimostrare la proprietà.

Dopo aver aggiunto i domini al tenant e convalidato, utilizzare le indicazioni seguenti per aggiungere i record DNS appropriati per i servizi riportati di seguito.  Potrebbe essere necessario modificare la tabella seguente in base alle esigenze dell'organizzazione in relazione ai record MX in ingresso e ai record di individuazione automatica di Exchange esistenti.  È consigliabile coordinare questi record DNS con il team di messaggistica per evitare interruzioni o mancato recapito della posta elettronica.

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | Nome host | Indirizzo o valore di puntamento | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (vedere di seguito per ulteriori dettagli) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 ora |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Record di individuazione automatica di Exchange

Se si dispone Exchange Server locale, è consigliabile lasciare il record esistente sul posto durante la migrazione a Exchange Online e aggiornare tale record dopo aver completato la migrazione.

### <a name="exchange-online-mx-record"></a>Exchange Online MX Record

Il valore del record MX per i domini accettati segue un formato standard come indicato in precedenza: *tenant*.mail.protection.office365.us, sostituendo *il tenant* con la prima parte del nome del tenant predefinito.

Ad esempio, se il nome del tenant è contoso.onmicrosoft.us, è necessario utilizzare contoso.mail.protection.office365.us **come** valore per il record MX.

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>Record CNAME

| Tipo | Nome host | Indirizzo o valore di puntamento | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 ora |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>Record SRV

| Tipo | Servizio | Protocollo | Porta | Peso | Priority | Nome | Destinazione | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1  | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 ora |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1  | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Record DNS aggiuntivi

> [!IMPORTANT]
> Se nella zona DNS è presente un record CNAME *msoid* esistente, è necessario **rimuovere** il record dal DNS in questo momento.  Il record msoid non è compatibile con Microsoft 365 Enterprise Apps (in precedenza *Office 365 ProPlus)* e impedirà il successo dell'attivazione.
