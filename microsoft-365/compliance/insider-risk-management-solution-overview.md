---
title: Gestione dei rischi Insider in Microsoft 365
description: Informazioni su come configurare la gestione dei rischi Insider in Microsoft 365.
keywords: Microsoft 365, rischio Insider, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: 644fe1894cddcfea5bd45fcbd68e168ea8a1dca8
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423577"
---
# <a name="insider-risk-management-in-microsoft-365"></a><span data-ttu-id="9027d-104">Gestione dei rischi Insider in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9027d-104">Insider risk management in Microsoft 365</span></span>

<span data-ttu-id="9027d-105">Sempre più spesso, i dipendenti hanno più accesso per creare, gestire e condividere dati in un'ampia gamma di piattaforme e servizi.</span><span class="sxs-lookup"><span data-stu-id="9027d-105">Increasingly, employees have more access to create, manage, and share data across a broad spectrum of platforms and services.</span></span> <span data-ttu-id="9027d-106">Nella maggior parte dei casi, le organizzazioni dispongono di risorse e strumenti limitati per identificare e mitigare i rischi a livello di organizzazione, oltre a soddisfare i requisiti di conformità e gli standard di privacy dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="9027d-106">In most cases, organizations have limited resources and tools to identify and mitigate organization-wide risks while also meeting compliance requirements and employee privacy standards.</span></span> <span data-ttu-id="9027d-107">Questi rischi possono includere il furto di dati allontanando i dipendenti e la perdita di dati di informazioni all'esterno dell'organizzazione per oversharing accidentale o intento dannoso.</span><span class="sxs-lookup"><span data-stu-id="9027d-107">These risks may include data theft by departing employees and data leaks of information outside your organization by accidental oversharing or malicious intent.</span></span>

<span data-ttu-id="9027d-108">La gestione dei rischi Insider in Microsoft 365 usa l'intera gamma di indicatori di servizio e di terze parti per identificare, valutarne e agire rapidamente sulle attività degli utenti rischiose.</span><span class="sxs-lookup"><span data-stu-id="9027d-108">Insider risk management in Microsoft 365 uses the full breadth of service and 3rd-party indicators to help you quickly identify, triage, and act on risky user activity.</span></span> <span data-ttu-id="9027d-109">Utilizzando i log di Microsoft 365 e Microsoft Graph, la gestione dei rischi Insider consente di definire criteri specifici per identificare gli indicatori di rischio e di intervenire per attenuare questi rischi.</span><span class="sxs-lookup"><span data-stu-id="9027d-109">By using logs from Microsoft 365 and Microsoft Graph, insider risk management allows you to define specific policies to identify risk indicators and to take action to mitigate these risks.</span></span>

## <a name="configure-insider-risk-management-for-microsoft-365"></a><span data-ttu-id="9027d-110">Configurare la gestione dei rischi Insider per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9027d-110">Configure insider risk management for Microsoft 365</span></span>

<span data-ttu-id="9027d-111">Utilizzare la procedura seguente per configurare la gestione dei rischi Insider per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="9027d-111">Use the following steps to configure insider risk management for your organization:</span></span>

![Passaggi per la gestione dei rischi Insider della soluzione di rischio Insider](../media/ir-solution-ir-steps.png)

1. <span data-ttu-id="9027d-113">Informazioni sulla [gestione dei rischi insider](insider-risk-management.md) in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9027d-113">Learn about [insider risk management](insider-risk-management.md) in Microsoft 365</span></span>
2. <span data-ttu-id="9027d-114">Pianificare la [gestione dei rischi Insider e verificare le licenze](insider-risk-management-plan.md)</span><span class="sxs-lookup"><span data-stu-id="9027d-114">Plan for [insider risk management and verify licensing](insider-risk-management-plan.md)</span></span>
3. <span data-ttu-id="9027d-115">Configurare le [impostazioni di gestione dei rischi Insider](insider-risk-management-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9027d-115">Configure [insider risk management settings](insider-risk-management-settings.md)</span></span>
4. <span data-ttu-id="9027d-116">Configurare [le autorizzazioni](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) e i prerequisiti dei criteri & [connettori](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span><span class="sxs-lookup"><span data-stu-id="9027d-116">Configure [permissions](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) and [policy prerequisites & connectors](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)</span></span>
5. <span data-ttu-id="9027d-117">Creare e configurare criteri [di gestione dei rischi Insider](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span><span class="sxs-lookup"><span data-stu-id="9027d-117">Create and configure [insider risk management policies](insider-risk-management-configure.md#step-5-create-an-insider-risk-management-policy)</span></span>

## <a name="more-information-about-insider-risk-management"></a><span data-ttu-id="9027d-118">Ulteriori informazioni sulla gestione dei rischi Insider</span><span class="sxs-lookup"><span data-stu-id="9027d-118">More information about insider risk management</span></span>

- [<span data-ttu-id="9027d-119">Gestire i criteri di rischio Insider</span><span class="sxs-lookup"><span data-stu-id="9027d-119">Manage insider risk policies</span></span>](insider-risk-management-policies.md)
- [<span data-ttu-id="9027d-120">Esaminare gli avvisi relativi ai rischi Insider</span><span class="sxs-lookup"><span data-stu-id="9027d-120">Investigate insider risk alerts</span></span>](insider-risk-management-alerts.md)
- [<span data-ttu-id="9027d-121">Agire sui casi di rischio Insider</span><span class="sxs-lookup"><span data-stu-id="9027d-121">Act on insider risk cases</span></span>](insider-risk-management-cases.md)