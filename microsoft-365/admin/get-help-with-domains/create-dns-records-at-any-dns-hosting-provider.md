---
title: Aggiungere record DNS per connettere il dominio
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
description: Connettere un dominio di qualsiasi provider di hosting DNS a Microsoft 365 verificando il dominio e aggiornando i record DNS nell'account del proprio registrar.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 62b6793dd97e146b703c82e0ba23f4d7414025b6
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623978"
---
# <a name="add-dns-records-to-connect-your-domain"></a>Aggiungere record DNS per connettere il dominio

Se è stato acquistato un dominio presso un provider di hosting di terze parti, è possibile connetterlo a Microsoft 365 aggiornando i record DNS nell'account del registrar.

Alla fine di questa procedura, il dominio rimarrà registrato con l'host da cui è stato acquistato, ma Microsoft 365 potrà usarlo per gli indirizzi di posta elettronica, ad esempio utente@dominio.com, e altri servizi.

Finché non verrà aggiunto un dominio, gli utenti dell'organizzazione useranno onmicrosoft.com per gli indirizzi di posta elettronica. È importante aggiungere il dominio prima di aggiungere utenti, per evitare una doppia configurazione.

Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml).

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>Passaggio 1: Aggiungere un record TXT o MX per verificare la proprietà del dominio

### <a name="recommended-verify-with-a-txt-record"></a>Consigliato: Verificare con un record TXT

Prima di tutto, è necessario dimostrare di essere proprietari del dominio che si vuole aggiungere a Microsoft 365.

1. Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) e selezionare **Mostra tutto** > **Impostazioni** > **Domini**.
2. In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).
3. Passare alla pagina Gestore DNS del provider e aggiungere il record TXT indicato nell'interfaccia di amministrazione al dominio.

L'aggiunta di questo record non influirà sulla posta elettronica o su altri servizi esistenti, inoltre il record potrà essere rimosso una volta connesso il dominio a Microsoft 365.

Esempio:
- Nome TXT: `@`
- Valore TXT: MS=ms######## (ID univoco dall'interfaccia di amministrazione)
- TTL: `3600‎` (o il provider predefinito)

4. Salvare il record, tornare nell'interfaccia di amministrazione, quindi selezionare **Verifica**. In genere occorrono circa 15 minuti prima che le modifiche apportate al record vengano registrate, ma a volte può essere necessario più tempo. Attendere il tempo richiesto ed effettuare i tentativi necessari per rilevare la modifica.

Quando Microsoft trova il record TXT corretto, il dominio è verificato.

### <a name="verify-with-an-mx-record"></a>Verificare con un record MX

Se il registrar non supporta l'aggiunta di record TXT, è possibile verificare aggiungendo un record MX.

1. Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) e selezionare **Mostra tutto** > **Impostazioni** > **Domini**.
2. In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).
3. Passare alla pagina Gestore DNS del provider e aggiungere il record MX indicato nell'interfaccia di amministrazione al dominio.

La **Priorità** di questo record MX deve essere più elevata di tutti i record MX esistenti per il dominio. In caso contrario, può interferire con l'invio e la ricezione di posta elettronica. È necessario eliminare questo record non appena la verifica del dominio viene completata.

Verificare che i campi siano impostati sui valori seguenti:

- Tipo di record: `MX`
- Priorità: impostare sul valore massimo disponibile, in genere `0`.
- Nome host: `@`
- Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- TTL: `3600‎` (o il provider predefinito)

Quando Microsoft trova il record MX corretto, il dominio è verificato.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>Passaggio 2: Aggiungere record DNS per connettere servizi Microsoft

In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).

Verranno aggiunti diversi tipi di record DNS in base ai servizi da abilitare. 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>Aggiungere un record MX per la posta elettronica (Outlook, Exchange Online)
**Prima di iniziare:** se gli utenti hanno già un'e-mail con il proprio dominio (ad esempio utente@dominio.com), creare gli account nell'interfaccia di amministrazione prima di configurare i record MX. In questo modo potranno continuare a ricevere messaggi di posta elettronica. Quando si aggiorna il record MX del dominio, tutti i nuovi messaggi di posta elettronica indirizzati a chiunque usi il dominio verranno recapitati in Microsoft 365. I messaggi già disponibili rimarranno nell'attuale host di posta elettronica, a meno che non si decida di [eseguire la migrazione di posta elettronica e contatti](../setup/migrate-email-and-contacts-admin.md) a Microsoft 365.

Le informazioni per il record MX saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.

Nel sito Web del provider di hosting, aggiungere un nuovo record MX.
Verificare che i campi siano impostati sui valori seguenti:

- Tipo di record: `MX`
- Priorità: impostare sul valore massimo disponibile, in genere `0`.
- Nome host: `@`
- Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- TTL: `3600‎` (o il provider predefinito)

Salvare il record, quindi rimuovere qualsiasi altro record MX.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>Aggiungere record CNAME per connettere altri servizi (Teams, Exchange Online, AAD, MDM)
Le informazioni per i record CNAME saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.

Nel sito Web del provider di hosting, aggiungere i record CNAME per ogni servizio che si vuole connettere.
Verificare che i campi siano impostati sui valori seguenti per ciascun:

- Tipo di record: `CNAME (Alias)`
- Host: incollare qui i valori copiati dall'interfaccia di amministrazione.
- Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- TTL: `3600‎` (o il provider predefinito)


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>Aggiungere o modificare un record TXT SPF per evitare di ricevere posta indesiderata (Outlook, Exchange Online)
**Prima di iniziare:** se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365. Aggiungere invece i valori di Microsoft 365 necessari al record corrente nel sito Web del provider di hosting, in modo da ottenere un *unico* record SPF che includa entrambi i set di valori.

Nel sito Web del provider di hosting, creare un record SPF o modificarne uno esistente.
Verificare che i campi siano impostati sui valori seguenti:

- Tipo di record: `TXT (Text)`
- Host: `@`
- Valore TXT: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (o il provider predefinito)

Salvare il record.

Convalidare il record SPF usando uno di questi [strumenti di convalida SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare. Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile impostare anche DKIM e DMARC per Microsoft 365. 

Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) e [Usare DKIM per convalidare la posta elettronica in Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>Aggiungere record SRV per servizi di comunicazione (Teams, Skype for Business)

Nel sito Web del provider di hosting, aggiungere i record SRV per ogni servizio che si vuole connettere.
Verificare che i campi siano impostati sui valori seguenti per ciascun:

- Tipo di record: `SRV (Service)`
- Nome: `@`
- Destinazione: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- Protocollo: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- Servizio: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- Priorità: `100`
- Peso: `1`
- Porta: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.
- TTL: `3600‎` (o il provider predefinito)

Salvare il record.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>Restrizioni del campo SRV e soluzioni alternative
Alcuni provider di hosting impongono restrizioni sui valori dei campi all'interno dei record SRV. Di seguito sono riportate alcune soluzioni alternative comuni per queste restrizioni.

##### <a name="name"></a>Nome
Se il provider di hosting non consente di configurare questo campo per **@**, lasciarlo vuoto. Usare questo approccio *solo* quando il provider di hosting ha campi distinti per i valori Servizio e Protocollo. Altrimenti, vedere la nota sui valori Servizio e Protocollo di seguito.

##### <a name="service-and-protocol"></a>Servizio e Protocollo
Se presso il provider di hosting non sono disponibili questi campi per i record SRV, è necessario specificare i valori **Servizio** e **Protocollo** nel campo **Nome** del record. Nota: a seconda del provider di hosting, il campo **Nome** potrebbe avere una denominazione diversa, ad esempio **Host**, **Nome host** o **Sottodominio**. Per aggiungere questi valori, creare una singola stringa, separando i valori con un punto. 

Esempio: `_sip._tls`

##### <a name="priority-weight-and-port-br"></a>Priorità, Peso e Porta <br>
Se presso il provider di hosting non sono disponibili questi campi per i record SRV, è necessario specificarli nel campo **Destinazione** del record. Nota: a seconda del provider di hosting, il campo **Destinazione** potrebbe avere una denominazione diversa, ad esempio **Contenuto**, **Indirizzo IP** o **Host di destinazione**. 

Per aggiungere questi valori, creare una singola stringa, separando i valori con spazi e *a volte terminando con un punto* (rivolgersi al provider in caso di dubbi). I valori devono essere inclusi in questo ordine: Priorità, Peso, Porta, Destinazione. 

- Esempio 1: `100 1 443 sipdir.online.lync.com.`
- Esempio 2: `100 1 443 sipdir.online.lync.com`

## <a name="related-content"></a>Contenuto correlato

[Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar del dominio](change-nameservers-at-any-domain-registrar.md) (articolo)\
[Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](find-and-fix-issues.md) (articolo)\
[Gestire i domini](index.yml) (pagina di collegamento)