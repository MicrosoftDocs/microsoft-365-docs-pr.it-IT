---
title: GDPR per Project Server
description: Informazioni su come gestire i requisiti GDPR nell'ambiente Project Server locale.
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
ms.openlocfilehash: a9fff9f085fd42f28801a82c3f83d6bdd1f74ff6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596413"
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
