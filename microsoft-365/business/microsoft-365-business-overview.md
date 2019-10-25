---
title: Informazioni generali su Microsoft 365 business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come configurare Microsoft 365 business.
ms.openlocfilehash: 0c717271da17ff4bf28d8d3546df3a9da427dba5
ms.sourcegitcommit: 53148fc3663bdcfa9605684317785cb19f37e141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "37697766"
---
# <a name="overview-of-microsoft-365-business"></a>Panoramica di Microsoft 365 business

## <a name="what-is-microsoft-365-business"></a>Che cos'è Microsoft 365 business

Microsoft 365 Business è un set completo di strumenti per la produttività e la collaborazione aziendali sempre aggiornati, tra cui Outlook, Word, Excel e altri prodotti di Office. È possibile proteggere i file di lavoro in tutti i dispositivi iOS, Android e Windows 10 con sicurezza di livello aziendale semplice da gestire.
  
Microsoft 365 business è destinato a un massimo di 300 licenze, per ulteriori informazioni, vedere [microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) Documentation.

Vedere [Descrizione servizio Microsoft 365 business](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description) per l'intero elenco delle caratteristiche.
  
## <a name="small-business-security-needs"></a>Requisiti di sicurezza per le aziende di piccole dimensioni

I dati aziendali possono essere compromessi in molti modi. L'utente e gli utenti possono compromettere la sicurezza dell'organizzazione quando si accede con credenziali compromesse o si visualizzano i dati dell'organizzazione su diversi dispositivi e applicazioni. In particolare, l'organizzazione è a rischio:

1. Credenziali di accesso compromesse o deboli.
2. Dispositivo compromesso con un pin debole o un dispositivo di proprietà di un utente.
3. Utenti che possono copiare/incollare/salvare i dati dell'organizzazione in app personali.
4. Utenti che installano e utilizzano app<sup>di terze</sup> parti con protezione debole.
5. Vulnerabilità della posta elettronica, tra cui la condivisione di dati sensibili, tentativi di phishing, malware e così via.
6. Quando le persone che non dovrebbero, possono accedere ai documenti con informazioni riservate.

Microsoft 365 business contribuisce alla salvaguardia dei dati in ognuna di queste istanze. Le funzionalità di sicurezza che proteggono i dati business sono descritte nella figura seguente.

![Figura che illustra il modo in cui M365B protegge la propria azienda.](media/m365businessvalueadd.png)

## <a name="how-your-data-and-devices-are-protected"></a>Come proteggere i dati e i dispositivi

Microsoft 365 business aiuta a **difendersi dalle minacce** :

Scansione di qualsiasi collegamento nei messaggi di posta elettronica e nei documenti in tempo reale per bloccare siti Web non sicuri (collegamenti sicuri di ATP).

- Esecuzione di analisi avanzate degli allegati di posta elettronica in un ambiente sandbox per rilevare malware di recente sviluppo (allegati sicuri di ATP). 

- Abilitazione dei criteri di anti-phishing che utilizzano modelli di apprendimento automatico e rilevamento della rappresentazione per garantire la protezione da attacchi avanzati (ATP anti-phishing Intelligence). 

- Impostazione di criteri avanzati che consentono di disabilitare l'accesso da posizioni non attendibili o di ignorare l'autenticazione a più fattori da luoghi attendibili, ad esempio la rete di Office (Azure AMF, compresi gli indirizzi IP attendibili e l'accesso condizionale). 

- Applicazione della protezione antimalware in tutti i dispositivi Windows 10 dell'azienda e protezione dei file in cartelle di sistema chiave dalle modifiche apportate da ransomware (Windows Defender)

I **dati dell'azienda sono protetti** da:

- Utilizzo del rilevamento automatico per evitare che informazioni sensibili, come i numeri di previdenza sociale o le carte di credito, fuoriescano dalla propria azienda (prevenzione della perdita di dati). 

- Crittografia dei messaggi di posta elettronica sensibili per poter comunicare in modo sicuro con i clienti o con altre persone esterne all'azienda, assicurando che solo il destinatario possa leggere il messaggio (Office 365 Message Encryption).

- Controllare chi ha accesso alle informazioni dell'azienda applicando restrizioni quali non **copiare** e non **inoltrare** messaggi di posta elettronica e documenti (Azure Information Protection, piano 1).

- Abilitazione dell'archiviazione cloud illimitata in modo da poter mantenere la posta elettronica di tutte le aziende, incluse le cassette postali degli ex dipendenti (archiviazione Exchange Online).

I **dispositivi sono protetti** da:

- Controllo dei dispositivi e degli utenti che possono accedere ai dati di Office 365; con le opzioni che impediscono agli utenti di eseguire l'accesso da computer di casa, app non approvate o al di fuori dell'orario di lavoro (accesso condizionale).

- Applicazione di criteri di sicurezza per la protezione dei dati aziendali nei dispositivi iOS e Android.  Ad esempio, è possibile richiedere agli utenti di fornire un PIN o un'impronta digitale per accedere ai dati business e crittografare i dati nei dispositivi mobili (app Protection for Office Mobile Apps).

- Mantenere i documenti aziendali, i messaggi di posta elettronica e altri dati all'interno delle app di Office per dispositivi mobili approvati e impedire ai dipendenti di salvarli nelle app e nelle posizioni non autorizzate (app Protection for Office Mobile Apps).

- Cancellare in remoto i dati aziendali dai dispositivi smarriti o rubati senza influire sulle informazioni personali (wipe selettivo di Intune).

- Utilizzo di controlli semplificati per la gestione dei criteri per tutti i PC Windows 10 nella propria azienda, l'applicazione della crittografia BitLocker e l'installazione automatica di aggiornamenti critici di Windows (applicazione dei criteri di Windows Update).

Per visualizzare l'elenco completo delle funzionalità di sicurezza, vedere [Microsoft 365 Business Security features](security-features.md). Dopo aver [configurato Microsoft 365 business](set-up.md), vedere [configurare i criteri di sicurezza avanzati](set-up-advanced-security.md) per iniziare a utilizzare le funzionalità di sicurezza non incluse nell'installazione guidata. Leggere anche i [primi 10 modi per proteggere i piani aziendali di Office 365 e Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) per una buona panoramica su come configurare le protezioni contro i criminali informatici e gli hacker.

## <a name="get-microsoft-365-business"></a>Ottenere Microsoft 365 Business

- I partner riceveranno Microsoft 365 Business: [Ottenere Microsoft 365 Business dal Centro per i partner Microsoft](get-microsoft-365-business.md#get-microsoft-365-business-from-microsoft-partner-center).

- Se non si dispone di un partner e si desidera ottenere Microsoft 365 business, è possibile [acquistarlo qui](https://www.microsoft.com/microsoft-365/business) e seguire le istruzioni di [iscrizione](sign-up.md) .

- È inoltre possibile accedere a un [Microsoft Store](https://www.microsoft.com/en-us/store/locations/find-a-store?icid=en-us_UF_FAS) per acquistare Microsoft 365 business e ottenere assistenza per la configurazione.
