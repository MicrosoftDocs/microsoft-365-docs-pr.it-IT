---
title: Deprecazione TLS 1.0 e 1.1 per Office 365
description: Descrive la deprecazione di TLS 1.0 e 1.1 per Office 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777058"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="b259b-103">Deprecazione TLS 1.0 e 1.1 per Office 365</span><span class="sxs-lookup"><span data-stu-id="b259b-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>
> [!IMPORTANT]
> <span data-ttu-id="b259b-104">Abbiamo temporaneamente interrotto l'applicazione della deprecazione di TLS 1.0 e 1.1 per i clienti commerciali a causa di COVID-19, ma poiché le catene di approvvigionamento sono state modificate e alcuni paesi si aprono di nuovo, stiamo reimpostando l'applicazione TLS per iniziare il 15 ottobre 2020 e l'implementazione continuerà nelle settimane e nei mesi successivi.</span><span class="sxs-lookup"><span data-stu-id="b259b-104">We temporarily halted deprecation enforcement of TLS 1.0 and 1.1 for commercial customers due to COVID-19, but as supply chains have adjusted and certain countries open back up, we are resetting the TLS enforcement to begin October 15, 2020, and rollout will continue over the following weeks and months.</span></span> 

<span data-ttu-id="b259b-105">A partire dal 31 ottobre 2018, i protocolli Transport Layer Security (TLS) 1.0 e 1.1 sono deprecati per il servizio Office 365.</span><span class="sxs-lookup"><span data-stu-id="b259b-105">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="b259b-106">L'effetto per gli utenti finali dovrebbe essere minimo.</span><span class="sxs-lookup"><span data-stu-id="b259b-106">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="b259b-107">Questa modifica è stata resa pubblica per oltre due anni, con il primo annuncio pubblico effettuato a dicembre 2017.</span><span class="sxs-lookup"><span data-stu-id="b259b-107">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="b259b-108">Questo articolo ha lo scopo di coprire solo il client locale di Office 365 in relazione al servizio Office 365, ma può essere applicato anche a problemi TLS locali con Office e Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="b259b-108">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="b259b-109">Panoramica di Office e TLS</span><span class="sxs-lookup"><span data-stu-id="b259b-109">Office and TLS overview</span></span>

<span data-ttu-id="b259b-110">Il client Office si basa sul servizio Web Windows (WINHTTP) per inviare e ricevere traffico tramite protocolli TLS.</span><span class="sxs-lookup"><span data-stu-id="b259b-110">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="b259b-111">Il client di Office può utilizzare TLS 1.2 se il servizio Web del computer locale può utilizzare TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b259b-111">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="b259b-112">Tutti i client di Office possono utilizzare i protocolli TLS, in quanto i protocolli TLS e SSL fanno parte del sistema operativo e non sono specifici del client di Office.</span><span class="sxs-lookup"><span data-stu-id="b259b-112">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="b259b-113">In Windows 8 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="b259b-113">On Windows 8 and later versions</span></span>

<span data-ttu-id="b259b-114">Per impostazione predefinita, i protocolli TLS 1.2 e 1.1 sono disponibili se nessun dispositivo di rete è configurato per rifiutare il traffico TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b259b-114">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="b259b-115">In Windows 7</span><span class="sxs-lookup"><span data-stu-id="b259b-115">On Windows 7</span></span>

<span data-ttu-id="b259b-116">I protocolli TLS 1.1 e 1.2 non sono disponibili senza l'aggiornamento [KB 3140245.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="b259b-116">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="b259b-117">L'aggiornamento risolve questo problema e aggiunge la seguente chiave secondaria del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="b259b-117">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="b259b-118">Gli utenti di Windows 7 che non dispongono di questo aggiornamento sono interessati dal 31 ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="b259b-118">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="b259b-119">[KB 3140245](https://support.microsoft.com/help/3140245) include informazioni dettagliate su come modificare le impostazioni WINHTTP per abilitare i protocolli TLS.</span><span class="sxs-lookup"><span data-stu-id="b259b-119">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="b259b-120">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b259b-120">More information</span></span>

<span data-ttu-id="b259b-121">Il valore della chiave **del Registro di sistema DefaultSecureProtocols** descritta nell'articolo della Knowledge Base determina quali protocolli di rete possono essere utilizzati:</span><span class="sxs-lookup"><span data-stu-id="b259b-121">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="b259b-122">Valore DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="b259b-122">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="b259b-123">Protocollo abilitato</span><span class="sxs-lookup"><span data-stu-id="b259b-123">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="b259b-124">0x00000008</span><span class="sxs-lookup"><span data-stu-id="b259b-124">0x00000008</span></span>|<span data-ttu-id="b259b-125">Consente di abilitare SSL 2.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b259b-125">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="b259b-126">0x00000020</span><span class="sxs-lookup"><span data-stu-id="b259b-126">0x00000020</span></span>|<span data-ttu-id="b259b-127">Consente di abilitare SSL 3.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b259b-127">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="b259b-128">0x00000080</span><span class="sxs-lookup"><span data-stu-id="b259b-128">0x00000080</span></span>|<span data-ttu-id="b259b-129">Consente di abilitare TLS 1.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b259b-129">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="b259b-130">0x00000200</span><span class="sxs-lookup"><span data-stu-id="b259b-130">0x00000200</span></span>|<span data-ttu-id="b259b-131">Consente di abilitare TLS 1.1 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b259b-131">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="b259b-132">0x00000800</span><span class="sxs-lookup"><span data-stu-id="b259b-132">0x00000800</span></span>|<span data-ttu-id="b259b-133">Consente di abilitare TLS 1.2 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b259b-133">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="b259b-134">Client di Office e chiavi del Registro di sistema TLS</span><span class="sxs-lookup"><span data-stu-id="b259b-134">Office clients and TLS registry keys</span></span>

<span data-ttu-id="b259b-135">È possibile fare riferimento a KB 4057306 Preparazione per l'uso obbligatorio di [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="b259b-135">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="b259b-136">Questo è un articolo generale per gli amministratori IT ed è la documentazione ufficiale sulla modifica di TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="b259b-136">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="b259b-137">La tabella seguente mostra i valori delle chiavi del Registro di sistema appropriati nei client di Office 365 dopo il 31 ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="b259b-137">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="b259b-138">Protocolli abilitati per il servizio Office 365 dopo il 31 ottobre 2018</span><span class="sxs-lookup"><span data-stu-id="b259b-138">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="b259b-139">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="b259b-139">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="b259b-140">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="b259b-140">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="b259b-141">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="b259b-141">0x00000A80</span></span>|
|<span data-ttu-id="b259b-142">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="b259b-142">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="b259b-143">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="b259b-143">0x00000A00</span></span>|
|<span data-ttu-id="b259b-144">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="b259b-144">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="b259b-145">0x00000880</span><span class="sxs-lookup"><span data-stu-id="b259b-145">0x00000880</span></span>|
|<span data-ttu-id="b259b-146">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="b259b-146">TLS 1.2</span></span>|<span data-ttu-id="b259b-147">0x00000800</span><span class="sxs-lookup"><span data-stu-id="b259b-147">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="b259b-148">Non è consigliabile utilizzare i protocolli SSL 2.0 e 3.0, che possono essere impostati anche utilizzando la chiave **DefaultSecureProtocols.**</span><span class="sxs-lookup"><span data-stu-id="b259b-148">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="b259b-149">SSL 2.0 e 3.0 sono considerati protocolli deprecati.</span><span class="sxs-lookup"><span data-stu-id="b259b-149">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="b259b-150">La procedura consigliata consiste nel terminare l'utilizzo di SSL 2.0 e SSL 3.0, anche se la decisione di eseguire questa operazione dipende in ultima analisi da ciò che meglio soddisfa le esigenze del prodotto.</span><span class="sxs-lookup"><span data-stu-id="b259b-150">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="b259b-151">Per ulteriori informazioni sulle vulnerabilità di SSL 3.0, vedere [kb 3009008.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="b259b-151">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="b259b-152">Puoi usare lo Strumento di calcolo Windows predefinito in modalità programmatore per configurare gli stessi valori delle chiavi del Registro di sistema di riferimento.</span><span class="sxs-lookup"><span data-stu-id="b259b-152">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="b259b-153">Per ulteriori informazioni, vedere [l'aggiornamento KB 3140245 per abilitare TLS 1.1 e TLS 1.2](https://support.microsoft.com/help/3140245)come protocolli sicuri predefiniti in WinHTTP in Windows.</span><span class="sxs-lookup"><span data-stu-id="b259b-153">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="b259b-154">Indipendentemente dal fatto che l'aggiornamento di Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) sia installato o meno, la chiave secondaria del Registro di sistema DefaultSecureProtocols non è presente e deve essere aggiunta manualmente o tramite un oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b259b-154">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="b259b-155">In altri casi, a meno che non sia necessario personalizzare i protocolli sicuri abilitati o limitati, questa chiave non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="b259b-155">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="b259b-156">È necessario solo l'aggiornamento di Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="b259b-156">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
