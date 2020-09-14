---
title: RGDP per Office Online Server e Server Office Web Apps
description: In questo articolo vengono fornite informazioni su come gestire i requisiti del GDPR per Office Online Server e Office Web Apps Server.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 84ea370f513ade134df75b2ee4e0912d6a623227
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547342"
---
# <a name="gdpr-for-office-web-apps-server-and-office-online-server"></a><span data-ttu-id="ad2e3-103">GDPR per Server Office Web Apps e Office Online Server</span><span class="sxs-lookup"><span data-stu-id="ad2e3-103">GDPR for Office Web Apps Server and Office Online Server</span></span>

<span data-ttu-id="ad2e3-p101">I dati di telemetria di Office Online Server e Server Office Web Apps sono archiviati come log ULS. È possibile utilizzare il [Visualizzatore Servizio di registrazione unificato](https://www.microsoft.com/download/details.aspx?id=44020) per visualizzare i log di Servizio di registrazione unificato dal tenant locale.</span><span class="sxs-lookup"><span data-stu-id="ad2e3-p101">Office Online Server and Office Web Apps Server telemetry data is stored in the form of ULS logs. You can use [ULS Viewer](https://www.microsoft.com/download/details.aspx?id=44020) to view ULS logs from your on-premises tenant.</span></span>

<span data-ttu-id="ad2e3-p102">Ogni riga di log contiene un CorrelationID. Righe di log correlate condividono lo stesso CorrelationID. Ogni CorrelationID è vincolato a un solo SessionID e un SessionID può riguardare più CorrelationID. Ogni SessionID può riguardare un solo UserID, anche se alcune sessioni possono essere anonime e pertanto possono non essere associate ad alcun UserID. Per determinare quali dati sono associati a un determinato utente, è quindi possibile eseguire il mapping da un unico UserID ai SessionID associati all'utente, da questi SessionID ai CorrelationID associati e dai CorrelationID a tutti i log in queste correlazioni. Vedere il seguente diagramma per la relazione tra i diversi ID.</span><span class="sxs-lookup"><span data-stu-id="ad2e3-p102">Every log line contains a CorrelationID. Related log lines share the same CorrelationID. Each CorrelationID is tied to a single SessionID, and one SessionID may be related to many CorrelationIDs. Each SessionID may be related to a single UserID, although some sessions can be anonymous and therefore not have an associated UserID. In order to determine what data is associated with a particular user, it is therefore possible to map from a single UserID to the SessionIDs associated with that user, from those SessionIDs to the associated CorrelationIDs, and from those CorrelationIDs to all the logs in those correlations. See the below diagram for the relationship between the different IDs.</span></span>

![Diagramma di flusso che mostra la relazione tra SessionID e CorrelationIds](../media/gdpr-for-office-online-server-image1.jpg)

## <a name="gathering-logs"></a><span data-ttu-id="ad2e3-113">Raccolta dei log</span><span class="sxs-lookup"><span data-stu-id="ad2e3-113">Gathering Logs</span></span>

<span data-ttu-id="ad2e3-p103">Per raccogliere tutti i log associati a UserID 1, ad esempio, il primo passaggio consiste nel raccogliere tutte le sessioni associate a UserID 1 (ad esempio, SessionID 1 e SessionID2). Il passaggio successivo consiste nel raccogliere tutte le correlazioni associate a SessionID 1 (ad esempio, CorrelationIDs 1, 2 e 3) e a SessionID 2 (ad esempio, CorrelationID 4). Infine, raccogliere tutti i log associati a ognuna delle correlazioni dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ad2e3-p103">In order to gather all logs associated with UserID 1, for example, the first step would be to gather all sessions associated with UserID 1 (i.e. SessionID 1 and SessionID2). The next step would be to gather all correlations associated with SessionID 1 (i.e. CorrelationIDs 1, 2, and 3) and with SessionID 2 (i.e. CorrelationID 4). Finally, gather all logs associated with each of the correlations in the list.</span></span>

1. <span data-ttu-id="ad2e3-117">Avvio di UlsViewer</span><span class="sxs-lookup"><span data-stu-id="ad2e3-117">Launch UlsViewer</span></span>

2. <span data-ttu-id="ad2e3-118">Aprire il log di Servizio di registrazione unificato corrispondente all'intervallo di tempo desiderato; i log di Servizio di registrazione unificato vengono archiviati in %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span><span class="sxs-lookup"><span data-stu-id="ad2e3-118">Open up the uls log corresponding to the intended timeframe; ULS logs are stored in %PROGRAMDATA%\\Microsoft\\OfficeWebApps\\Data\\Logs\\ULS</span></span>

3. <span data-ttu-id="ad2e3-119">Modifica | Modifica filtro</span><span class="sxs-lookup"><span data-stu-id="ad2e3-119">Edit | Modify Filter</span></span>

4. <span data-ttu-id="ad2e3-120">Applicare il filtro:</span><span class="sxs-lookup"><span data-stu-id="ad2e3-120">Apply a filter that is:</span></span>

    - <span data-ttu-id="ad2e3-121">EventID è uguale a apr3y</span><span class="sxs-lookup"><span data-stu-id="ad2e3-121">EventID equals apr3y</span></span>

      <span data-ttu-id="ad2e3-122">Oppure</span><span class="sxs-lookup"><span data-stu-id="ad2e3-122">Or</span></span>

    - <span data-ttu-id="ad2e3-123">EventID è uguale a bp2d6</span><span class="sxs-lookup"><span data-stu-id="ad2e3-123">EventID equals bp2d6</span></span>

5. <span data-ttu-id="ad2e3-124">UserId con hash saranno presenti nel Messaggio di uno o due eventi</span><span class="sxs-lookup"><span data-stu-id="ad2e3-124">Hashed UserIds will be in the Message of either one of these two events</span></span>

6. <span data-ttu-id="ad2e3-125">Per apr3y, il Messaggio conterrà un valore UserID e un valore PUID</span><span class="sxs-lookup"><span data-stu-id="ad2e3-125">For apr3y, the Message will contain a UserID value and a PUID value</span></span>

7. <span data-ttu-id="ad2e3-p104">Per bp2d6, il Messaggio conterrà gran parte delle informazioni. Il campo valore LoggableUserId è l'ID utente con hash.</span><span class="sxs-lookup"><span data-stu-id="ad2e3-p104">For bp2d6, the Message will contain quite a bit of information. The LoggableUserId Value field is the hashed UserID.</span></span>

8. <span data-ttu-id="ad2e3-128">Dopo aver ottenuto UserId con hash da uno di questi due tag, il valore WacSessionId della riga corrispondente in ULSViewer conterrà il valore WacSessionId associato a quell'utente</span><span class="sxs-lookup"><span data-stu-id="ad2e3-128">Once the hashed UserId is obtained from either of these two tags, the WacSessionId value of that row in ULSViewer will contain the WacSessionId associated with that user</span></span>

9. <span data-ttu-id="ad2e3-129">Raccogliere tutti i valori WacSessionId associati all'utente in questione</span><span class="sxs-lookup"><span data-stu-id="ad2e3-129">Collect all of the WacSessionId values associated with the user in question</span></span>

10. <span data-ttu-id="ad2e3-130">Filtrare per tutti gli EventId uguali a "xmnv", messaggio uguale a "UserSessionId=\<WacSessionId\>" per il primo WacSessionId nell'elenco (sostituendo la parte \<WacSessionId\> del filtro con WacSessionId)</span><span class="sxs-lookup"><span data-stu-id="ad2e3-130">Filter for all EventId equals "xmnv", Message equals "UserSessionId=\<WacSessionId\>" for the first WacSessionId in the list (replacing the \<WacSessionId\> part of the filter with your WacSessionId)</span></span>

11. <span data-ttu-id="ad2e3-131">Raccogliere tutti i valori di Correlation corrispondenti a tale WacSessionId</span><span class="sxs-lookup"><span data-stu-id="ad2e3-131">Collect all values of Correlation that match that WacSessionId</span></span>

12. <span data-ttu-id="ad2e3-132">Ripetere i passaggi 10 e 11 per tutti i valori di WacSessionId nell'elenco per l'utente in questione</span><span class="sxs-lookup"><span data-stu-id="ad2e3-132">Repeat steps 10-11 for all values of WacSessionId in your list for the user in question</span></span>

13. <span data-ttu-id="ad2e3-133">Filtrare per tutti i valori di Correlation uguali alla prima Correlation nell'elenco</span><span class="sxs-lookup"><span data-stu-id="ad2e3-133">Filter for all Correlation equals the first Correlation in your list</span></span>

14. <span data-ttu-id="ad2e3-134">Raccogliere tutti i log corrispondenti a tale Correlation</span><span class="sxs-lookup"><span data-stu-id="ad2e3-134">Collect all logs matching that Correlation</span></span>

15. <span data-ttu-id="ad2e3-135">Ripetere i passaggi 13 e 14 per tutti i valori di Correlation nell'elenco per l'utente in questione</span><span class="sxs-lookup"><span data-stu-id="ad2e3-135">Repeat steps 13-14 for all values of Correlation in your list for the user in question</span></span>

## <a name="types-of-data"></a><span data-ttu-id="ad2e3-136">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="ad2e3-136">Types of Data</span></span>

<span data-ttu-id="ad2e3-p105">I log di Office contengono un'ampia varietà di tipi di dati. Di seguito sono riportati alcuni esempi di dati che potrebbero essere contenuti dai log di Servizio di registrazione unificato:</span><span class="sxs-lookup"><span data-stu-id="ad2e3-p105">Office logs contain a variety of different types of data. The following are examples of the data that ULS logs may contain:</span></span>

- <span data-ttu-id="ad2e3-139">Codici di errore per problemi riscontrati durante l'utilizzano del prodotto</span><span class="sxs-lookup"><span data-stu-id="ad2e3-139">Error codes for issues encountered during use of the product</span></span>

- <span data-ttu-id="ad2e3-140">Pulsanti e altre parti dei dati sull'utilizzo delle app</span><span class="sxs-lookup"><span data-stu-id="ad2e3-140">Button clicks and other pieces of data about app usage</span></span>

- <span data-ttu-id="ad2e3-141">Dati sulle prestazioni dell'applicazione e/o funzionalità particolari all'interno dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="ad2e3-141">Performance data about the app and/or particular features within the app</span></span>

- <span data-ttu-id="ad2e3-142">Informazioni generali sulla posizione del computer dell'utente (ad esempio paese/area geografica, provincia e città, derivate dall'indirizzo IP), ma non la precisa posizione geografica.</span><span class="sxs-lookup"><span data-stu-id="ad2e3-142">General location information about where the user’s computer is (e.g. country / region, state, and city, derived from the IP address), but not precise geo location.</span></span>

- <span data-ttu-id="ad2e3-143">I metadati di base sul browser, ad esempio la versione e il nome del browser e del computer, ad esempio il tipo di sistema operativo e la versione</span><span class="sxs-lookup"><span data-stu-id="ad2e3-143">Basic metadata about the browser, e.g. browser name and version, and the computer, e.g. OS type and version</span></span>

- <span data-ttu-id="ad2e3-144">Messaggi di errore dall'host del documento (ad esempio OneDrive, SharePoint, Exchange)</span><span class="sxs-lookup"><span data-stu-id="ad2e3-144">Error messages from the document host (e.g. OneDrive, SharePoint, Exchange)</span></span>

- <span data-ttu-id="ad2e3-145">Informazioni sui processi interni all'applicazione, non correlate a operazioni che effettuate dall'utente</span><span class="sxs-lookup"><span data-stu-id="ad2e3-145">Information about processes internal to the app, unrelated to any action the user has taken</span></span>
