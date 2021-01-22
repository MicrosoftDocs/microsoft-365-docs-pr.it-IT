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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come connettere il dominio a Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925111"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="bed4b-103">Connettere il dominio a Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="bed4b-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="bed4b-104">Dopo aver configurato Microsoft 365 e spostato i dati di posta elettronica da Google Workspace, è possibile connettere il dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bed4b-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="bed4b-105">Prima di tutto sarà necessario eliminare i record DNS esistenti da Google, quindi possiamo aggiungere nuovi record DNS da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bed4b-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="bed4b-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="bed4b-106">Try it!</span></span>

1. <span data-ttu-id="bed4b-107">Accedere alla console di amministrazione di Google Workspace [all'indirizzo admin.google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="bed4b-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="bed4b-108">Seleziona **Domini,** **Gestisci domini,** **Visualizza dettagli,** **Gestisci dominio,** **quindi DNS** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="bed4b-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="bed4b-109">Scorrere verso il basso **fino a Record sintetici,** aprire **Google Workspace,** selezionare **Elimina** e quindi **eliminare di** nuovo.</span><span class="sxs-lookup"><span data-stu-id="bed4b-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="bed4b-110">Scorrere verso il **basso fino a Record** di risorse personalizzati ed eliminare eventuali record DNS esistenti visualizzati, inclusi quelli creati in precedenza per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bed4b-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="bed4b-111">Passare all'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="bed4b-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="bed4b-112">In the left nav, choose, **Show all**, **Settings**, **Domains.**</span><span class="sxs-lookup"><span data-stu-id="bed4b-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="bed4b-113">Scegliere quindi il dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="bed4b-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="bed4b-114">Selezionare **Continua l'installazione,** quindi, per connettere il dominio, scegliere **Continua.**</span><span class="sxs-lookup"><span data-stu-id="bed4b-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="bed4b-115">Scorrere verso il basso per visualizzare i record DNS che devono essere copiati su Google.</span><span class="sxs-lookup"><span data-stu-id="bed4b-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="bed4b-116">Aprire **i record MX** e, in Indirizzo o valore di **puntamento,** copiare il record.</span><span class="sxs-lookup"><span data-stu-id="bed4b-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="bed4b-117">Tornare a Google e nella sezione **Custom resource records** aprire l'elenco a discesa del tipo di record e selezionare **MX.**</span><span class="sxs-lookup"><span data-stu-id="bed4b-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="bed4b-118">Nel campo **Dati** incollare il record copiato.</span><span class="sxs-lookup"><span data-stu-id="bed4b-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="bed4b-119">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bed4b-119">Then select **Add**.</span></span>
1. <span data-ttu-id="bed4b-120">Ripetere il processo per i record CNAME e TXT e aggiungere i valori nella pagina di gestione DNS di Google.</span><span class="sxs-lookup"><span data-stu-id="bed4b-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="bed4b-121">Tornare all'interfaccia di amministrazione di Microsoft 365 e selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="bed4b-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="bed4b-122">La configurazione del dominio è stata completata.</span><span class="sxs-lookup"><span data-stu-id="bed4b-122">Your domain setup is complete.</span></span>