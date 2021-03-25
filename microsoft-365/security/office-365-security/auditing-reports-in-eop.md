---
title: Report di controllo in Exchange Online Protection autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Gli amministratori possono ottenere informazioni sui report di controllo dell'amministratore disponibili in Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08432f97d196df8b661d63a5d4cdf3680b78e070
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205545"
---
# <a name="auditing-reports-in-standalone-eop"></a><span data-ttu-id="8f38e-103">Report di controllo in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="8f38e-103">Auditing reports in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8f38e-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="8f38e-104">**Applies to**</span></span>
-  [<span data-ttu-id="8f38e-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="8f38e-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="8f38e-106">Nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i report di controllo consentono di soddisfare i requisiti normativi, di conformità e di controversia legale per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f38e-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, auditing reports can help you meet regulatory, compliance, and litigation requirements for your organization.</span></span> <span data-ttu-id="8f38e-107">È possibile ottenere report di controllo in qualsiasi momento per determinare le modifiche apportate alla configurazione di Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="8f38e-107">You can obtain auditing reports at any time to determine the changes that have been made to your EOP configuration.</span></span> <span data-ttu-id="8f38e-108">Questi report consentono di risolvere problemi di configurazione o individuare la causa di problemi relativi alla sicurezza o alla conformità.</span><span class="sxs-lookup"><span data-stu-id="8f38e-108">These reports can help you troubleshoot configuration issues or find the cause of security-related or compliance-related problems.</span></span>

<span data-ttu-id="8f38e-109">In EOP autonomo sono disponibili due report di controllo:</span><span class="sxs-lookup"><span data-stu-id="8f38e-109">There are two auditing reports available in standalone EOP:</span></span>

- <span data-ttu-id="8f38e-110">**Rapporto gruppo di ruoli amministratore:** il report del gruppo di ruoli amministratore consente di visualizzare quando un utente viene aggiunto o rimosso dall'appartenenza a un gruppo di ruoli amministratore.</span><span class="sxs-lookup"><span data-stu-id="8f38e-110">**Administrator role group report**: The administrator role group report lets you view when a user is added to or removed from membership in an administrator role group.</span></span> <span data-ttu-id="8f38e-111">È possibile usare questo report per monitorare le modifiche apportate alle autorizzazioni amministrative assegnate agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f38e-111">You can use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span> <span data-ttu-id="8f38e-112">Per ulteriori informazioni, vedere [Run an administrator role group report in standalone EOP.](run-an-administrator-role-group-report-in-eop-eop.md)</span><span class="sxs-lookup"><span data-stu-id="8f38e-112">For more information, see [Run an administrator role group report in standalone EOP](run-an-administrator-role-group-report-in-eop-eop.md).</span></span>

- <span data-ttu-id="8f38e-113">**Log di controllo** dell'amministratore: il log di controllo dell'amministratore registra qualsiasi azione (basata sui cmdlet di PowerShell EOP autonomi) da parte di un amministratore o di un utente con privilegi amministrativi.</span><span class="sxs-lookup"><span data-stu-id="8f38e-113">**Administrator audit log**: The administrator audit log records any action (based on standalone EOP PowerShell cmdlets) by an admin or a user with administrative privileges.</span></span> <span data-ttu-id="8f38e-114">Per ulteriori informazioni, vedere [View the Administrator Audit Log in Exchange Online.](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log)</span><span class="sxs-lookup"><span data-stu-id="8f38e-114">For more information, see [View the Administrator Audit Log in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log).</span></span>