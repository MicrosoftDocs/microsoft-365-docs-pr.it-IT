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
# <a name="gdpr-for-project-server"></a><span data-ttu-id="762de-103">GDPR per Project Server</span><span class="sxs-lookup"><span data-stu-id="762de-103">GDPR for Project Server</span></span>

<span data-ttu-id="762de-p101">Project Server utilizza gli script personalizzati per esportare e redigere dati utente in Project Web App. Il processo di base è il seguente:</span><span class="sxs-lookup"><span data-stu-id="762de-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="762de-106">Trovare i siti di Project Web App della farm.</span><span class="sxs-lookup"><span data-stu-id="762de-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="762de-107">Trovare i progetti in ogni sito che contiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="762de-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="762de-108">Esportare ed esaminare i tipi di dati da esaminare.</span><span class="sxs-lookup"><span data-stu-id="762de-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="762de-109">Redigere i dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="762de-109">Redact data as needed.</span></span>

<span data-ttu-id="762de-110">Questi passaggi sono descritti dettagliatamente negli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="762de-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="762de-111">Esportare i dati degli utenti da Project Server</span><span class="sxs-lookup"><span data-stu-id="762de-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="762de-112">Eliminare i dati degli utenti da Project Server</span><span class="sxs-lookup"><span data-stu-id="762de-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="762de-p102">Tenere presente che Project Server è basato su SharePoint Server e registra gli eventi nei registri del Servizio di registrazione unificato e su database servizio di utilizzo. Per ulteriori informazioni, vedere [GDPR per SharePoint Server](gdpr-for-sharepoint-server.md).</span><span class="sxs-lookup"><span data-stu-id="762de-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
