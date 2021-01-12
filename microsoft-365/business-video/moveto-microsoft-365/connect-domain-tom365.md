---
title: Connettere il proprio dominio a Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come connettere il dominio a Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794643"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="7a4d2-103">Connettere il dominio a Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="7a4d2-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="7a4d2-104">Dopo aver configurato Microsoft 365 e aver spostato i dati della posta elettronica da Google Workspace, è possibile connettere il dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="7a4d2-105">Per prima cosa, è necessario eliminare i record DNS esistenti da Google, quindi è possibile aggiungere nuovi record DNS da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="7a4d2-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="7a4d2-106">Try it!</span></span>

1. <span data-ttu-id="7a4d2-107">Accedere alla console di amministrazione di Google Workspace all' [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="7a4d2-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="7a4d2-108">Selezionare **domini**, **Gestisci domini**, **Visualizza dettagli**, **Gestisci dominio** e quindi **DNS** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="7a4d2-109">Scorrere verso il basso fino a **record sintetici**, aprire **Google Workspace**, selezionare **Elimina**, quindi **eliminare** di nuovo.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="7a4d2-110">Scorrere verso il basso fino a **record di risorse personalizzati** ed eliminare tutti i record DNS esistenti che vengono visualizzati, compresi quelli eventualmente creati in precedenza per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="7a4d2-111">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7a4d2-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="7a4d2-112">Nella barra di spostamento a sinistra, scegliere, **mostrare tutto**, **Impostazioni**, **domini**.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="7a4d2-113">Scegliere quindi il dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="7a4d2-114">Selezionare **Continua installazione**, quindi, per connettere il dominio, scegliere  **continue**.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="7a4d2-115">Scorrere verso il basso per visualizzare i record DNS che devono essere copiati su Google.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="7a4d2-116">Aprire i **record MX** e in **punti a indirizzo o valore**, copiare il record.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="7a4d2-117">Torna a Google e nella sezione **Custom Resource Records** Apri il menu a discesa tipo di record e seleziona **MX**.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="7a4d2-118">Nel campo **dati** incollare il record copiato.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="7a4d2-119">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-119">Then select **Add**.</span></span>
1. <span data-ttu-id="7a4d2-120">Ripetere il processo per i record CNAME e TXT e aggiungere i valori nella pagina Gestione DNS di Google.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="7a4d2-121">Tornare all'interfaccia di amministrazione di Microsoft 365 e selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="7a4d2-122">La configurazione del dominio è stata completata.</span><span class="sxs-lookup"><span data-stu-id="7a4d2-122">Your domain setup is complete.</span></span>