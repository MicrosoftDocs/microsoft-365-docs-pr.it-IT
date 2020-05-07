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
# <a name="gdpr-for-project-server"></a><span data-ttu-id="3fc22-103">GDPR per Project Server</span><span class="sxs-lookup"><span data-stu-id="3fc22-103">GDPR for Project Server</span></span>

<span data-ttu-id="3fc22-p101">Project Server utilizza gli script personalizzati per esportare e redigere dati utente in Project Web App. Il processo di base è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3fc22-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="3fc22-106">Trovare i siti di Project Web App della farm.</span><span class="sxs-lookup"><span data-stu-id="3fc22-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="3fc22-107">Trovare i progetti in ogni sito che contiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="3fc22-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="3fc22-108">Esportare ed esaminare i tipi di dati da esaminare.</span><span class="sxs-lookup"><span data-stu-id="3fc22-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="3fc22-109">Redigere i dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="3fc22-109">Redact data as needed.</span></span>

<span data-ttu-id="3fc22-110">Questi passaggi sono descritti dettagliatamente negli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3fc22-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="3fc22-111">Esportare i dati degli utenti da Project Server</span><span class="sxs-lookup"><span data-stu-id="3fc22-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="3fc22-112">Eliminare i dati degli utenti da Project Server</span><span class="sxs-lookup"><span data-stu-id="3fc22-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="3fc22-p102">Tenere presente che Project Server è basato su SharePoint Server e registra gli eventi nei registri del Servizio di registrazione unificato e su database servizio di utilizzo. Per ulteriori informazioni, vedere [GDPR per SharePoint Server](gdpr-for-sharepoint-server.md).</span><span class="sxs-lookup"><span data-stu-id="3fc22-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
