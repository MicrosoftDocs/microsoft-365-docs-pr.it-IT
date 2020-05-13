---
title: Pool di recapito ad alto rischio per i messaggi in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Informazioni sul modo in cui il pool di recapito ad alto rischio viene utilizzato per proteggere la reputazione dei server di posta elettronica nei datacenter Microsoft 365.
ms.openlocfilehash: 190dc3bd7ed2a6cddb23c8bc7c117dee30fd4f13
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209188"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="16021-103">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="16021-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="16021-104">I server di posta elettronica nei datacenter Microsoft 365 potrebbero essere temporaneamente colpevoli di inviare messaggi di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="16021-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="16021-105">Ad esempio, un attacco di posta indesiderata o malware in un'organizzazione di posta elettronica locale che invia la posta in uscita tramite Microsoft 365 o ha compromesso gli account di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="16021-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="16021-106">Questi scenari possono comportare l'indirizzo IP dei server del datacenter Microsoft 365 interessato che appaiono negli elenchi di blocco di terze parti.</span><span class="sxs-lookup"><span data-stu-id="16021-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="16021-107">Le organizzazioni di posta elettronica di destinazione che utilizzano questi elenchi di blocco rifiuteranno la posta elettronica dalle origini dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="16021-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="16021-108">Per evitare questo, tutti i messaggi in uscita dai server di datacenter Microsoft 365 che sono determinati come posta indesiderata o che superano i limiti di invio del [servizio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o i [criteri di posta indesiderata in uscita](configure-the-outbound-spam-policy.md) vengono inviati attraverso il _pool di recapito ad alto rischio_.</span><span class="sxs-lookup"><span data-stu-id="16021-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="16021-109">Il pool di recapito ad alto rischio è un pool di indirizzi IP secondario per la posta elettronica in uscita utilizzata solo per l'invio di messaggi di "bassa qualità" (ad esempio, posta indesiderata e [backscattering](backscatter-messages-and-eop.md)).</span><span class="sxs-lookup"><span data-stu-id="16021-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="16021-110">L'utilizzo del pool di recapito ad alto rischio impedisce che il pool di indirizzi IP normale per la posta elettronica in uscita invii la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="16021-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="16021-111">Il pool di indirizzi IP normale per la posta elettronica in uscita mantiene la reputazione che invia messaggi "di alta qualità", che riduce la probabilità che questi indirizzi IP vengano visualizzati negli elenchi di blocco IP.</span><span class="sxs-lookup"><span data-stu-id="16021-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="16021-112">La possibilità reale che gli indirizzi IP in un pool di recapito ad alto rischio venga disposta sugli elenchi di blocco IP rimane, ma è in base alla progettazione.</span><span class="sxs-lookup"><span data-stu-id="16021-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="16021-113">Il recapito ai destinatari previsti non è garantito, perché molte organizzazioni di posta elettronica non accettano messaggi dal pool di recapito ad alto rischio.</span><span class="sxs-lookup"><span data-stu-id="16021-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="16021-114">Per ulteriori informazioni, vedere [controllare la posta indesiderata in uscita](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="16021-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="16021-115">Messaggi in cui il dominio di posta elettronica di origine non ha un record e nessun record MX definito in DNS pubblico vengono sempre instradati attraverso il pool di recapito ad alto rischio, indipendentemente dalla posta indesiderata o dall'invio dei limiti.</span><span class="sxs-lookup"><span data-stu-id="16021-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="16021-116">Messaggi di rimbalzo</span><span class="sxs-lookup"><span data-stu-id="16021-116">Bounce messages</span></span>

<span data-ttu-id="16021-117">Il pool di recapito ad alto rischio in uscita gestisce il recapito per tutti i rapporti di mancato recapito (noti anche come NDR, messaggi di rimbalzo, notifiche sullo stato del recapito o DSN).</span><span class="sxs-lookup"><span data-stu-id="16021-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="16021-118">Le possibili cause di un aumento dei rapporti di mancato recapito includono:</span><span class="sxs-lookup"><span data-stu-id="16021-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="16021-119">Una campagna di spoofing che influisce su uno dei clienti che utilizzano il servizio.</span><span class="sxs-lookup"><span data-stu-id="16021-119">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="16021-120">Un attacco di raccolta directory.</span><span class="sxs-lookup"><span data-stu-id="16021-120">A directory harvest attack.</span></span>
- <span data-ttu-id="16021-121">Un attacco di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="16021-121">A spam attack.</span></span>
- <span data-ttu-id="16021-122">Un server di posta elettronica canaglia.</span><span class="sxs-lookup"><span data-stu-id="16021-122">A rogue email server.</span></span>

<span data-ttu-id="16021-123">Tutti questi problemi possono portare a un improvviso aumento del numero di rapporti di mancato recapito elaborati dal servizio.</span><span class="sxs-lookup"><span data-stu-id="16021-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="16021-124">Molte volte, questi rapporti di mancato recapito sembrano essere posta indesiderata ad altri server e servizi di posta elettronica (noti anche come _[backscatter](backscatter-messages-and-eop.md)_).</span><span class="sxs-lookup"><span data-stu-id="16021-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
