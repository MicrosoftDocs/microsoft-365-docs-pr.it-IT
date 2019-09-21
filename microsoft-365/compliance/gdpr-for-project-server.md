---
title: GDPR per Project Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Informazioni su come gestire i requisiti GDPR nell'ambiente Project Server locale.
ms.openlocfilehash: 8fb29c2d383c03c79d619d2c78df75cffb4eab27
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083591"
---
# <a name="gdpr-for-project-server"></a>GDPR per Project Server

Project Server utilizza gli script personalizzati per esportare e redigere dati utente in Project Web App. Il processo di base è il seguente:

1.  Trovare i siti di Project Web App della farm.

2.  Trovare i progetti in ogni sito che contiene l'utente.

3.  Esportare ed esaminare i tipi di dati da esaminare.

4.  Redigere i dati in base alle esigenze.

Questi passaggi sono descritti dettagliatamente negli articoli seguenti:

- [Esportare i dati degli utenti da Project Server](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Eliminare i dati degli utenti da Project Server](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Tenere presente che Project Server è basato su SharePoint Server e registra gli eventi nei registri del Servizio di registrazione unificato e su database servizio di utilizzo. Per ulteriori informazioni, vedere [GDPR per SharePoint Server](gdpr-for-sharepoint-server.md).
