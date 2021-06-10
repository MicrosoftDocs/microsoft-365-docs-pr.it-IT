---
title: Servizi per non clienti che inviano posta a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Per mantenere la fiducia degli utenti nell'uso della posta elettronica, Microsoft ha messo in atto diversi criteri e tecnologie per proteggere i nostri utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206513"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Servizi per non clienti che inviano posta a Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


L'abuso della posta elettronica, la posta indesiderata e le e-mail fraudolente (phishing) continuano a gravare sull'intero ecosistema di posta elettronica. Per mantenere la fiducia degli utenti nell'uso della posta elettronica, Microsoft ha messo in atto diversi criteri e tecnologie per proteggere i nostri utenti. Tuttavia, Microsoft è a conoscenza del fatto che la posta elettronica legittima non deve essere influenzata negativamente. Di conseguenza, abbiamo creato una famiglia di servizi per aiutare i mittenti a migliorare la loro capacità di recapitare la posta elettronica agli utenti Microsoft 365 gestendo in modo proattivo la reputazione di invio.

Questa panoramica fornisce informazioni sui vantaggi offerti all'organizzazione anche se non si è un cliente.

## <a name="sender-solutions"></a>Soluzioni mittente

****

|Servizio|Vantaggi|
|---|---|
|Contenuto della Guida online|Fornisce: <ul><li>Un punto di partenza per tutte le domande relative al recapito delle comunicazioni agli utenti di EOP.</li><li>Include una semplice guida online con i criteri e i requisiti.</li><li>Panoramica dei filtri per la posta indesiderata e delle tecnologie di autenticazione utilizzate da Microsoft.</li><ul>|
|[Supporto Tecnico Microsoft](#microsoft-support)|Fornisce supporto self-help e escalation per i problemi di recapito.|
|[Portale antispam IP Delist](#anti-spam-ip-delist-portal)|Uno strumento per inviare la richiesta di delist ip. Prima di inviare questa richiesta, è responsabilità del mittente assicurarsi che qualsiasi ulteriore posta proveniente dall'IP in questione non sia offensiva o dannosa.|
|[Segnalazione di abuso e posta indesiderata per la posta indesiderata proveniente da Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Impedisce l'invio di posta indesiderata e altri messaggi indesiderati da Exchange Online e l'ingombro di Internet e del sistema di posta.|
|

## <a name="microsoft-support"></a>Supporto Tecnico Microsoft

Microsoft offre diverse opzioni di supporto per gli utenti che hanno problemi a inviare posta Microsoft 365 destinatari. È consigliabile:

- Seguire le istruzioni contenute in qualsiasi rapporto di mancato recapito ricevuto.

- Vedere i problemi più comuni riscontrati dai non clienti in Risoluzione dei problemi relativi alla posta [inviata Office 365](troubleshooting-mail-sent-to-office-365.md).

- Usa il [Microsoft 365 delist per](https://sender.office.com) inviare una richiesta di rimozione dell'IP dall'elenco dei mittenti bloccati.

- Leggere i [forum della community Microsoft](https://community.office365.com/f/).

- Contattare il cliente che si sta tentando di inviare tramite posta elettronica utilizzando un altro metodo e chiedere loro di contattare il Supporto Tecnico Microsoft e aprire un ticket di supporto per conto dell'utente. In alcuni casi, per motivi legali, il supporto Tecnico Microsoft deve comunicare direttamente con il mittente proprietario dello spazio IP bloccato. Tuttavia, i non clienti in genere non possono aprire ticket di supporto.

  Per ulteriori informazioni sul supporto tecnico Microsoft per Office 365, vedere [Support](/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Portale antispam IP Delist

Si tratta di un portale self-service che è possibile utilizzare per rimuovere se stessi dall'Microsoft 365 dei mittenti bloccati. Utilizzare questo portale se si riceve un messaggio di errore quando si tenta di inviare un messaggio di posta elettronica a un destinatario il cui indirizzo di posta elettronica si trova in Microsoft 365 e non si pensa di doverlo fare. Per altre informazioni, vedere [Usare il portale per l'esclusione di indirizzi IP dal filtro della posta indesiderata per rimuoversi dall'elenco di mittenti bloccati](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Segnalazione di abuso e posta indesiderata per la posta indesiderata proveniente da Exchange Online

A volte Microsoft365 viene utilizzato da terze parti per inviare posta indesiderata, in violazione delle condizioni per l'utilizzo e i criteri. Se si riceve posta indesiderata da Office 365, è possibile segnalare questi messaggi a Microsoft. Per istruzioni, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).