---
title: Promuovi Microsoft 365 Defender ambiente di valutazione a Produzione, Microsoft 365 Defender valutazione, prova una valutazione, mantieni una valutazione, valutazione della produzione
description: Usa questo articolo per promuovere gli eval di MDI, MDO, MDE e MCAS nell'ambiente reale in Microsoft 365 Defender o M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458343"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="f7512-103">Promuovere l'Microsoft 365 Defender di valutazione dell'ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="f7512-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="f7512-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="f7512-104">**Applies to:**</span></span>
- <span data-ttu-id="f7512-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7512-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="f7512-106">Per promuovere l'Microsoft 365 Defender di valutazione all'ambiente di produzione, acquistare innanzitutto la licenza necessaria.</span><span class="sxs-lookup"><span data-stu-id="f7512-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="f7512-107">Segui i passaggi descritti in [Creare l'ambiente eval](eval-create-eval-environment.md) e acquistare la licenza Office 365 E5 (invece di selezionare Avvia versione di valutazione gratuita).</span><span class="sxs-lookup"><span data-stu-id="f7512-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="f7512-108">Successivamente, completare qualsiasi configurazione aggiuntiva ed espandere i gruppi pilota fino a quando questi non hanno raggiunto la produzione completa.</span><span class="sxs-lookup"><span data-stu-id="f7512-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="f7512-109">Microsoft Defender per identità</span><span class="sxs-lookup"><span data-stu-id="f7512-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="f7512-110">Defender for Identity non richiede alcuna configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="f7512-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="f7512-111">Assicurati di aver acquistato le licenze necessarie e di aver installato il sensore in tutti i controller di dominio Active Directory e nei server Active Directory Federation Services (AD FS).</span><span class="sxs-lookup"><span data-stu-id="f7512-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="f7512-112">Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="f7512-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="f7512-113">Dopo aver valutato correttamente o pilotato MDO, può essere promosso all'intero ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f7512-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="f7512-114">Acquistare ed effettuare il provisioning delle licenze necessarie e assegnarle agli utenti di produzione.</span><span class="sxs-lookup"><span data-stu-id="f7512-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="f7512-115">Eseguire di nuovo le configurazioni dei criteri di base consigliate (Standard o Strict) nel dominio di posta elettronica di produzione o in gruppi specifici di utenti.</span><span class="sxs-lookup"><span data-stu-id="f7512-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="f7512-116">Facoltativamente, creare e configurare eventuali criteri MDO personalizzati in base al dominio di posta elettronica di produzione o ai gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="f7512-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="f7512-117">Tenere tuttavia presente che tutti i criteri di base assegnati avranno sempre la precedenza sui criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f7512-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="f7512-118">Aggiornare il record MX pubblico per il dominio di posta elettronica di produzione in modo che si risolva direttamente in EOP.</span><span class="sxs-lookup"><span data-stu-id="f7512-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="f7512-119">Rimuovere eventuali gateway SMTP di terze parti e disabilitare o eliminare eventuali connettori EXO associati a questo inoltro.</span><span class="sxs-lookup"><span data-stu-id="f7512-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="f7512-120">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="f7512-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="f7512-121">Per promuovere l'ambiente di valutazione di Microsoft Defender for Endpoint da un progetto pilota a un ambiente di produzione, è sufficiente eseguire il onboard di più endpoint al servizio usando uno degli [strumenti e dei metodi supportati.](/defender-endpoint/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="f7512-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="f7512-122">Usa le linee guida generali seguenti per eseguire l'onboard di più dispositivi in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7512-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="f7512-123">Verificare che il dispositivo soddisfa i [requisiti minimi](/defender-endpoint/minimum-requirements).</span><span class="sxs-lookup"><span data-stu-id="f7512-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="f7512-124">A seconda del dispositivo, segui i passaggi di configurazione forniti nella sezione onboarding del portale defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7512-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="f7512-125">Usa lo strumento di gestione e il metodo di distribuzione appropriati per i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f7512-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="f7512-126">Eseguire un test di rilevamento per verificare che i dispositivi siano stati correttamente onboarded e che siano stati segnalati al servizio.</span><span class="sxs-lookup"><span data-stu-id="f7512-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="f7512-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f7512-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="f7512-128">Microsoft Cloud App Security non richiede alcuna configurazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="f7512-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="f7512-129">Assicurati di aver acquistato le licenze necessarie.</span><span class="sxs-lookup"><span data-stu-id="f7512-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="f7512-130">Se l'ambito della distribuzione è stato esteso a determinati gruppi di utenti, aumentare l'ambito di tali gruppi fino a raggiungere la scala di produzione.</span><span class="sxs-lookup"><span data-stu-id="f7512-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

