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
# <a name="gdpr-for-project-server"></a><span data-ttu-id="5d6dd-103">GDPR per Project Server</span><span class="sxs-lookup"><span data-stu-id="5d6dd-103">GDPR for Project Server</span></span>

<span data-ttu-id="5d6dd-p101">Project Server utilizza gli script personalizzati per esportare e redigere dati utente in Project Web App. Il processo di base è il seguente:</span><span class="sxs-lookup"><span data-stu-id="5d6dd-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="5d6dd-106">Trovare i siti di Project Web App della farm.</span><span class="sxs-lookup"><span data-stu-id="5d6dd-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="5d6dd-107">Trovare i progetti in ogni sito che contiene l'utente.</span><span class="sxs-lookup"><span data-stu-id="5d6dd-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="5d6dd-108">Esportare ed esaminare i tipi di dati da esaminare.</span><span class="sxs-lookup"><span data-stu-id="5d6dd-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="5d6dd-109">Redigere i dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="5d6dd-109">Redact data as needed.</span></span>

<span data-ttu-id="5d6dd-110">Questi passaggi sono descritti dettagliatamente negli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="5d6dd-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="5d6dd-111">Esportare i dati degli utenti da Project Server</span><span class="sxs-lookup"><span data-stu-id="5d6dd-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="5d6dd-112">Eliminare i dati degli utenti da Project Server</span><span class="sxs-lookup"><span data-stu-id="5d6dd-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="5d6dd-p102">Tenere presente che Project Server è basato su SharePoint Server e registra gli eventi nei registri del Servizio di registrazione unificato e su database servizio di utilizzo. Per ulteriori informazioni, vedere [GDPR per SharePoint Server](gdpr-for-sharepoint-server.md).</span><span class="sxs-lookup"><span data-stu-id="5d6dd-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
