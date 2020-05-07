---
title: GDPR per Project Server
description: Informazioni su come gestire i requisiti del GDPR in Project Server locale.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3a7eb291d0da72adf171594aac307ec0ad91829d
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036239"
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
