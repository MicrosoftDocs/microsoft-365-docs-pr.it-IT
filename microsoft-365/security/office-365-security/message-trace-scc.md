---
title: Traccia messaggi nel portale Microsoft 365 Defender messaggi
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono usare il collegamento di traccia dei messaggi nel portale Microsoft 365 Defender per scoprire cosa è successo ai messaggi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108128"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="5bb54-103">Traccia messaggi nel portale Microsoft 365 Defender messaggi</span><span class="sxs-lookup"><span data-stu-id="5bb54-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5bb54-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5bb54-104">**Applies to**</span></span>
- [<span data-ttu-id="5bb54-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5bb54-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5bb54-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5bb54-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5bb54-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bb54-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5bb54-108">La traccia dei messaggi nel portale Microsoft 365 Defender segue i messaggi di posta elettronica mentre viaggiano nell'Exchange Online aziendale.</span><span class="sxs-lookup"><span data-stu-id="5bb54-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="5bb54-109">È possibile determinare se un messaggio è stato ricevuto, rifiutato, rinviato o recapitato dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5bb54-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="5bb54-110">Mostra inoltre quali azioni sono state eseguite sul messaggio prima del raggiungimento dello stato finale.</span><span class="sxs-lookup"><span data-stu-id="5bb54-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="5bb54-111">È possibile utilizzare le informazioni dalla traccia dei messaggi per rispondere in modo efficiente alle domande degli utenti su cosa è successo ai messaggi, risolvere i problemi relativi al flusso di posta e convalidare le modifiche ai criteri.</span><span class="sxs-lookup"><span data-stu-id="5bb54-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="5bb54-112">La traccia dei messaggi nel portale Microsoft 365 Defender è solo un passaggio alla traccia dei messaggi nell'Exchange di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="5bb54-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="5bb54-113">Per ulteriori informazioni, vedere [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span><span class="sxs-lookup"><span data-stu-id="5bb54-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5bb54-114">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5bb54-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5bb54-115">È necessario essere membri dei gruppi di ruoli **Gestione** **organizzazione,** Gestione conformità o Help **Desk** **Exchange Online** utilizzare la traccia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="5bb54-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="5bb54-116">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="5bb54-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="5bb54-117">**Note:** l'appartenenza al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce  agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5bb54-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5bb54-118">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5bb54-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="5bb54-119">Il numero massimo di messaggi visualizzati nei risultati di una traccia dei messaggi dipende dal tipo di rapporto selezionato (per informazioni dettagliate, vedere la sezione [Scegliere](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) il tipo di report).</span><span class="sxs-lookup"><span data-stu-id="5bb54-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="5bb54-120">Il cmdlet [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell o PowerShell EOP autonomo restituisce tutti i messaggi nei risultati.</span><span class="sxs-lookup"><span data-stu-id="5bb54-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="5bb54-121">Apri traccia messaggio</span><span class="sxs-lookup"><span data-stu-id="5bb54-121">Open message trace</span></span>

<span data-ttu-id="5bb54-122">Nel portale Microsoft 365 Defender ( ), passare a Posta <https://security.microsoft.com> elettronica & collaborazione **Exchange** traccia \> **dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="5bb54-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="5bb54-123">In caso contrario, per passare direttamente alla pagina di traccia dei messaggi, utilizzare <https://admin.exchange.microsoft.com/#/messagetrace> .</span><span class="sxs-lookup"><span data-stu-id="5bb54-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="5bb54-124">A questo punto, viene aperta la traccia dei messaggi nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="5bb54-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="5bb54-125">Per ulteriori informazioni, vedere [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span><span class="sxs-lookup"><span data-stu-id="5bb54-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
