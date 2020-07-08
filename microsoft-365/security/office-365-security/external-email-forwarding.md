---
title: Configurazione e controllo dell'inoltro della posta elettronica esterno, inoltro automatico, accesso negato per 5.7.520, disabilitazione dell'inoltro esterno, l'amministratore ha disabilitato l'inoltro esterno, i criteri di protezione dalla posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080114"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="91def-103">Configurazione dell'inoltro della posta elettronica esterno in Office 365</span><span class="sxs-lookup"><span data-stu-id="91def-103">Configuring external email forwarding in Office 365</span></span>

<span data-ttu-id="91def-104">L'inoltro esterno è controllato dal *criterio di protezione dalla posta indesiderata in uscita* e dall'ambito agli utenti in base all'impostazione configurata.</span><span class="sxs-lookup"><span data-stu-id="91def-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="91def-105">Attualmente sono supportate tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="91def-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="91def-106">**Automatico** – in questa modalità, il sistema è responsabile di decidere se un messaggio inoltrato è consentito o meno.</span><span class="sxs-lookup"><span data-stu-id="91def-106">**Automatic** – In this mode the system is responsible for deciding if a forwarded message is allowed or not.</span></span>  <span data-ttu-id="91def-107">Questa è la modalità predefinita e in questa modalità il sistema bloccherà l'inoltro esterno automatico.</span><span class="sxs-lookup"><span data-stu-id="91def-107">This is the default mode and in this mode the system will block automatic external forwarding.</span></span>

- <span data-ttu-id="91def-108">**On** – l'inoltro automatico esterno è consentito e non è limitato.</span><span class="sxs-lookup"><span data-stu-id="91def-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="91def-109">**Off** – l'inoltro automatico esterno è disabilitato e si verificherà un rapporto di mancato recapito (NDR) all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="91def-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="91def-110">Per ulteriori informazioni su come configurare queste impostazioni, vedere Configurare il filtro per la [posta indesiderata in uscita in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="91def-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide) for more information on how to configure these settings.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="91def-111">Controllo dell'inoltro della posta elettronica esterno</span><span class="sxs-lookup"><span data-stu-id="91def-111">Controlling external email forwarding</span></span>

<span data-ttu-id="91def-112">L'amministratore di un'organizzazione può avere i requisiti aziendali per limitare o controllare chi è in grado di inoltrare automaticamente i messaggi di posta elettronica utilizzando le regole Inbox o l'inoltro SMTP all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="91def-112">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="91def-113">L'inoltro della posta elettronica può essere una funzionalità utile, ma può anche rappresentare un rischio tramite la divulgazione di informazioni, anche fornendo informazioni agli aggressori che possono essere utilizzati per attaccare l'organizzazione o i suoi partner.</span><span class="sxs-lookup"><span data-stu-id="91def-113">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="91def-114">Office 365 non consente l'inoltro automatico esterno tramite le regole di posta in arrivo o la configurazione della casella di posta, che fornisce un criterio predefinito sicuro.</span><span class="sxs-lookup"><span data-stu-id="91def-114">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="91def-115">Tuttavia, l'amministratore può modificare queste impostazioni per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="91def-115">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="91def-116">L'inoltro dei messaggi tra utenti interni non è influenzato da tale modifica.</span><span class="sxs-lookup"><span data-stu-id="91def-116">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="91def-117">La disattivazione dell'inoltro automatico agli indirizzi esterni in Office 365 viene distribuita in fasi con i dettagli comunicati tramite i post del [centro messaggi](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) .</span><span class="sxs-lookup"><span data-stu-id="91def-117">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="91def-118">Per aiutare gli amministratori a prepararsi per queste modifiche, è necessario che modifichino i criteri in anticipo per garantire che non vi siano interruzioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="91def-118">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="91def-119">Ulteriori informazioni sugli utenti che utilizzano l'inoltro automatico (regole di posta in arrivo o inoltro SMTP) nell'organizzazione possono essere trovate nel [rapporto messaggi auto-inoltrati](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="91def-119">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide).</span></span>

## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="91def-120">Il messaggio di inoltro della posta elettronica bloccato</span><span class="sxs-lookup"><span data-stu-id="91def-120">The blocked email forwarding message</span></span>

<span data-ttu-id="91def-121">Quando un messaggio viene rilevato come inoltrato automaticamente e il criterio dell'organizzazione *blocca* tale attività, verrà generato un **rapporto di mancato recapito (NDR, non-delivery report)** all'utente finale.</span><span class="sxs-lookup"><span data-stu-id="91def-121">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="91def-122">Il rapporto indicherà che il messaggio non è stato recapitato.</span><span class="sxs-lookup"><span data-stu-id="91def-122">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="91def-123">Il rapporto di mancato recapito avrà il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="91def-123">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
