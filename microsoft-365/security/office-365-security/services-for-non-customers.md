---
title: Servizi per i non clienti che inviano la posta a Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/2/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Per mantenere la fiducia degli utenti nell'utilizzo della posta elettronica, Microsoft ha messo a punto vari criteri e tecnologie che consentono di proteggere gli utenti.
ms.openlocfilehash: 2d8de601fd24f30c342768b8b27e44248f05b5fe
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638393"
---
# <a name="services-for-non-customers-sending-mail-to-office-365"></a>Servizi per i non clienti che inviano la posta a Office 365

Abuso di posta elettronica, posta indesiderata e messaggi di posta elettronica fraudolenti (phishing) continuano a gravare sull'intero sistema di posta elettronica. Per mantenere la fiducia degli utenti nell'utilizzo della posta elettronica, Microsoft ha messo a punto vari criteri e tecnologie che consentono di proteggere gli utenti. Tuttavia, Microsoft capisce che la posta elettronica legittima non dovrebbe essere influenzata negativamente. Pertanto, è stata configurata una serie di servizi per consentire ai mittenti di migliorare la possibilità di inviare messaggi di posta elettronica agli utenti di Microsoft 365 gestendo attivamente la propria reputazione di invio.

In questa panoramica vengono fornite informazioni sui vantaggi forniti all'organizzazione anche se non si è clienti.

## <a name="sender-solutions"></a>Soluzioni del mittente

|**Servizio**|**Vantaggi**|
|:-----|:-----|
|Contenuto della Guida in linea| Fornisce  <br/>  Punto di partenza per qualsiasi problema relativo alla distribuzione di comunicazioni agli utenti di EOP  <br/>  Include una semplice guida online con i criteri e i requisiti necessari  <br/>  Una panoramica dei filtri per la posta indesiderata e delle tecnologie di autenticazione impiegate da Microsoft|
|[Supporto tecnico Microsoft](#microsoft-support)|Fornisce supporto per l'escalation e la self-service per i problemi di recapito.|
|[Portale di delist IP di protezione da posta indesiderata](#anti-spam-ip-delist-portal)|Strumento per inviare la richiesta di esclusione di indirizzi IP. Prima di inoltrare la richiesta, è responsabilità del mittente garantire che qualsiasi ulteriore messaggio di posta proveniente dall'IP in questione non sia abusivo o dannoso.|
|[Segnalazione di abusi e posta indesiderata per posta indesiderata proveniente da Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Consente di mantenere la posta indesiderata e gli altri messaggi non voluti inviati da Exchange Online e ingombrare Internet e il sistema di posta elettronica.|

## <a name="microsoft-support"></a>Supporto tecnico Microsoft

Microsoft offre diverse opzioni di supporto per gli utenti che hanno problemi a inviare posta elettronica alle cassette postali di Microsoft 365. È consigliabile:

- Seguire le istruzioni riportate in qualsiasi rapporto di mancato recapito ricevuto.

- Consultare i problemi più comuni riscontrati dai non clienti nella [risoluzione dei problemi relativi alla posta inviata a Office 365](troubleshooting-mail-sent-to-office-365.md).

- Utilizzare il portale di rimozione della [lista di Microsoft 365](https://sender.office.com) per inviare una richiesta affinché l'IP sia stato rimosso dall'elenco dei mittenti bloccati.

- Leggere i [Forum della community Microsoft](https://community.office365.com/f/).

- Contattare il cliente che si sta tentando di inviare tramite posta elettronica utilizzando un altro metodo e chiedergli di contattare il supporto tecnico Microsoft e di aprire un ticket di supporto per conto dell'utente. In alcuni casi, per motivi legali, il supporto tecnico Microsoft deve comunicare direttamente con il mittente che possiede lo spazio IP che viene bloccato. Tuttavia, i non clienti in genere non sono in grado di aprire ticket di supporto.

  Per ulteriori informazioni sul supporto tecnico Microsoft per Office 365, vedere [support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Portale di delist IP di protezione da posta indesiderata

Si tratta di un portale self-service che è possibile utilizzare per rimuovere se stessi dall'elenco dei mittenti bloccati di Microsoft 365. Utilizzare questo portale se si riceve un messaggio di errore quando si tenta di inviare una posta elettronica a un destinatario il cui indirizzo di posta elettronica è in Microsoft 365 e non si ritiene di dover essere. Per ulteriori informazioni, vedere [use the delist Portal to Remove yourself from the Blocked Senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Segnalazione di abusi e posta indesiderata per posta indesiderata proveniente da Exchange Online

A volte Microsoft365 viene utilizzato da terze parti per inviare messaggi di posta indesiderata, in violazione dei termini di utilizzo e criteri. Se si riceve un messaggio di posta indesiderata da Office 365, è possibile segnalarli a Microsoft. Per istruzioni, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).
