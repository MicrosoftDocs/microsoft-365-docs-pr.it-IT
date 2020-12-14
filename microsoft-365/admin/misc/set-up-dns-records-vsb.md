---
title: Connettere il proprio dominio a Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come verificare il dominio e creare record DNS con Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658204"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Connettere il proprio dominio a Microsoft 365

> [!NOTE]
> Finché non verrà aggiunto un dominio, gli utenti dell'organizzazione useranno onmicrosoft.com per gli indirizzi di posta elettronica. È importante aggiungere il dominio prima di aggiungere utenti, per evitare una doppia configurazione.

Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft

Le informazioni per il record MX saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.

Nel sito Web del provider di hosting, aggiungere un nuovo record MX.
Verificare che i campi siano impostati sui valori seguenti:

- Tipo di record: `MX`
- Priorità: impostare sul valore massimo disponibile, in genere `0`.
- Nome host: `@`
- Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- TTL: `3600‎` (o il provider predefinito)

Salvare il record, quindi rimuovere qualsiasi altro record MX.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>Aggiungere un record CNAME per connettere gli utenti alle rispettive cassette postali
Le informazioni per i record CNAME saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.

Nel sito Web del provider di hosting, aggiungere il record CNAME seguente. Verificare che i campi siano impostati sui valori seguenti per ciascun:

- Tipo di record: `CNAME (Alias)`
- Host: incollare qui i valori copiati dall'interfaccia di amministrazione.
- Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- TTL: `3600‎` (o il provider predefinito)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>Aggiungere un record TXT per evitare di ricevere posta indesiderata
**Prima di iniziare:** se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365. Aggiungere invece i valori di Microsoft 365 necessari al record corrente nel sito Web del provider di hosting, in modo da ottenere un *unico* record SPF che includa entrambi i set di valori.

Nel sito Web del provider di hosting, creare un record SPF o modificarne uno esistente.
Verificare che i campi siano impostati sui valori seguenti:

- Tipo di record: `TXT (Text)`
- Host: `@`
- Valore TXT: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (o il provider predefinito)

Salvare il record.

Convalidare il record SPF usando uno di questi [strumenti di convalida SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile impostare anche DKIM e DMARC per Microsoft 365.

Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) e [Usare DKIM per convalidare la posta elettronica in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Infine, tornare configurazione dominio guidata dell'interfaccia di amministrazione per completare la configurazione.
