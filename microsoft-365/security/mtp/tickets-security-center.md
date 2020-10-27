---
title: Creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365
description: Informazioni su come creare e monitorare i ticket in ServiceNow dal centro sicurezza Microsoft 365.
keywords: sicurezza, Microsoft 365, M365, Secure score, Centro sicurezza, ServiceNow, ticket, attività
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769676"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Creare e monitorare i ticket di ServiceNow nel centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
>**Il periodo di anteprima per il connettore ServiceNow termina**<br>
>Questa funzionalità non sarà più disponibile entro la fine del 2020 novembre. La ringrazio per i commenti e il supporto continuo, mentre si determinano i passaggi successivi.

Il [Centro sicurezza di Microsoft 365](overview-security-center.md) è stato migliorato grazie alla possibilità di creare e registrare in modo nativo i ticket in ServiceNow. [Altre informazioni su ServiceNow](https://www.servicenow.com/)

Nel centro sicurezza, gli amministratori della sicurezza possono inviare un'azione di miglioramento di [Microsoft Secure Score](microsoft-secure-score.md) direttamente a ServiceNow e creare un ticket. È possibile creare sia la gestione degli incidenti che i ticket di gestione delle modifiche. Registrare i ticket nella Home page del Centro sicurezza e ServiceNow.

- [**Informazioni sui prerequisiti, lo scambio di dati e la risoluzione dei problemi**](tickets.md)
- **Gestire i ticket di ServiceNow nel centro conformità** (non disponibile)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Connettere il Centro sicurezza di Microsoft 365 a ServiceNow

Passare alla Home page del Centro sicurezza Microsoft 365 per visualizzare la scheda di connessione ServiceNow.

![Si utilizza ServiceNow](../../media/do-you-use-servicenow-250.png)

Selezionare "Connetti a ServiceNow" per accedere alla pagina di installazione di ServiceNow. Seguire le istruzioni per autorizzare l'app del connettore Microsoft 365.

> [!NOTE]
> Prima di autorizzare la connessione tra Microsoft 365 Security Center e ServiceNow, assicurarsi di utilizzare l'account di accesso e la password dell'utente di integrazione creati nei passaggi di installazione. Non utilizzare le credenziali personali.

Dopo aver seguito le istruzioni e aver autorizzato la connessione, visualizzare lo stato della connessione nella pagina connessione al centro sicurezza di Microsoft 365 e nell'app ServiceNow di ticketing Connector di Microsoft 365. Ora è tutto pronto per iniziare a creare attività.

### <a name="troubleshooting"></a>Risoluzione dei problemi

Informazioni sugli errori comuni che è possibile incontrare nel processo di connessione e su come attenuarli, nella [sezione risoluzione dei problemi](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Creare un'attività e condividerla con ServiceNow

Una volta configurata l'integrazione, creare attività di ServiceNow in base a specifiche azioni di miglioramento del [Punteggio Microsoft sicuro](microsoft-secure-score.md) . Passare a qualsiasi azione di miglioramento del Punteggio sicuro nel centro sicurezza Microsoft 365 e selezionare **Condividi** . Una delle opzioni di menu a discesa è ServiceNow.

Viene generata un'attività in cui è possibile impostare la priorità e modificare il nome, la descrizione o la data di scadenza. Una volta che tutti i campi richiesti sono stati riempiti, inviare l'attività a ServiceNow.

L'attività è visibile in ServiceNow come richiesta di modifica della sicurezza e della configurazione di Microsoft 365.

## <a name="track-tickets"></a>Registrare i ticket

Dopo aver creato i ticket per la gestione delle modifiche e la gestione degli incidenti di ServiceNow, vengono visualizzati su schede nella Home page del Centro sicurezza Microsoft 365. Da queste schede, è possibile creare un ticket, visualizzare tutti i ticket o gestire la configurazione di ServiceNow.

![Ticket di gestione delle modifiche di ServiceNow](../../media/change-management-375.png)  ![Ticket per la gestione degli incidenti di ServiceNow](../../media/incident-management-375.png)

Per eseguire il provisioning o la gestione dell'integrazione di ServiceNow nel centro sicurezza Microsoft 365, selezionare **Gestisci configurazione ServiceNow** su una delle schede. Da qui, rimuovere la connessione ServiceNow corrente e personalizzare i nomi degli Stati dei ticket.

Con i ticket di ServiceNow visibili nel centro sicurezza Microsoft 365, le attività vengono riportate in un luogo in cui possono essere monitorate e applicate insieme agli altri elementi del dashboard di sicurezza.

## <a name="resources"></a>Risorse

- [Informazioni sui prerequisiti, lo scambio di dati e la risoluzione dei problemi](tickets.md)
- [Microsoft Secure Score](microsoft-secure-score.md)
