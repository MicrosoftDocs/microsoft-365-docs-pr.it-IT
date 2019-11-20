---
title: GDPR per Skype for Business Server
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Informazioni su come gestire i requisiti GDPR nell'ambiente Skype for Business Server e Lync Server locale.
ms.openlocfilehash: fb3789a6835a367d415e5c32eeec043add150724
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "38749811"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a><span data-ttu-id="a6c9b-103">GDPR per Skype for Business Server e Lync Server</span><span class="sxs-lookup"><span data-stu-id="a6c9b-103">GDPR for Skype for Business Server and Lync Server</span></span>

<span data-ttu-id="a6c9b-p101">La maggior parte dei dati di Skype for Business Server e Lync Server è archiviata in Exchange Server. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a6c9b-p101">Most Skype for Business Server and Lync Server data is stored in Exchange Server. This includes:</span></span>

-   <span data-ttu-id="a6c9b-106">Cronologia conversazioni</span><span class="sxs-lookup"><span data-stu-id="a6c9b-106">Conversation history</span></span>

-   <span data-ttu-id="a6c9b-107">Trascrizioni e notifiche di segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="a6c9b-107">Voicemail notifications and transcriptions</span></span>

-   <span data-ttu-id="a6c9b-108">Inviti alle riunioni</span><span class="sxs-lookup"><span data-stu-id="a6c9b-108">Meeting invites</span></span>

<span data-ttu-id="a6c9b-109">Seguire le procedure descritte per [GDPR per Exchange Server](gdpr-for-exchange-server.md) per trovare, esportare o eliminare questi tipi di dati per le richieste GDPR.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-109">Use the procedures outlined for [GDPR for Exchange Server](gdpr-for-exchange-server.md) to find, export, or delete these types of data for GDPR requests.</span></span>

<span data-ttu-id="a6c9b-p102">Gli elenchi contatti sono archiviati nel database di SQL Server. Possono essere esportati nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a6c9b-p102">Contact lists are stored in the SQL Server database. They can be exported in the following ways:</span></span>

-   <span data-ttu-id="a6c9b-p103">Gli utenti finali possono esportare autonomamente i contatti direttamente facendo clic sull’intestazione del gruppo e scegliendo Copia. Tutti i contatti in tale gruppo verranno copiati negli Appunti, per poi essere incollati in qualsiasi applicazione.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-p103">End users themselves can export the contacts by right clicking the group header and selecting Copy. This will copy all the contacts in that group into the clipboard, which can then be pasted into any app.</span></span>

-   <span data-ttu-id="a6c9b-114">È possibile usare il cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) per esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-114">You can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>

<span data-ttu-id="a6c9b-p104">Il contenuto caricato in una riunione, come file di PowerPoint o gli stampati, o il contenuto generato durante una riunione, come lavagna, sondaggi e domande e risposte, viene archiviato nel filtro. Può essere esportato anche se gli utenti finali accedono di nuovo a una riunione che non sia scaduta e scaricano il contenuto aggiornato o memorizzano screenshot nel caso di contenuto generato.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-p104">Content uploaded into meetings (such as PowerPoint files or handouts) or content generated in a meeting (such as whiteboard, polls, or Q/A) is stored in the filer. This can also be exported if end users log back into any meeting that has not expired and download any uploaded content or take screenshots in the case of generated content.</span></span>

<span data-ttu-id="a6c9b-p105">Le riunioni MeetNow che non si trovano nel Calendario e nella lista contatti e diritti di contatto (familiari, colleghi e così via) di Exchange sono nel database dell’utente. In Lync Server 2013 e versioni successive, è possibile usare il cmdlet [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) per esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="a6c9b-p105">MeetNow meetings that are not in the Exchange Calendar and Contact List and contact rights (family, co-worker, etc.) are in the User Database. In Lync Server 2013 and later, you can use the [Export-CsUserData](https://docs.microsoft.com/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>
