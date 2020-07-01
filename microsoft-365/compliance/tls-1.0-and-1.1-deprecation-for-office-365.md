---
title: Deprecation TLS 1,0 e 1,1 per Office 365
description: Descrive le funzionalità TLS 1,0 e 1,1 Deprecation per Office 365.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937344"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a><span data-ttu-id="1ae6e-103">Deprecation TLS 1,0 e 1,1 per Office 365</span><span class="sxs-lookup"><span data-stu-id="1ae6e-103">TLS 1.0 and 1.1 deprecation for Office 365</span></span>

<span data-ttu-id="1ae6e-104">Al 31 ottobre 2018, i protocolli Transport Layer Security (TLS) 1,0 e 1,1 sono deprecati per il servizio Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-104">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Office 365 service.</span></span> <span data-ttu-id="1ae6e-105">L'effetto per gli utenti finali dovrebbe essere minimo.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-105">The effect for end-users is expected to be minimal.</span></span> <span data-ttu-id="1ae6e-106">Questa modifica è stata pubblicizzata per quasi due anni, con il primo annuncio pubblico effettuato nel dicembre 2017.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-106">This change was publicized for almost two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="1ae6e-107">Questo articolo è destinato solo a coprire il client locale di Office 365 in relazione al servizio Office 365, ma può anche essere applicato ai problemi di TLS locali con Office e Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-107">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

## <a name="office-and-tls-overview"></a><span data-ttu-id="1ae6e-108">Panoramica di Office e TLS</span><span class="sxs-lookup"><span data-stu-id="1ae6e-108">Office and TLS overview</span></span>

<span data-ttu-id="1ae6e-109">Il client di Office si basa sul servizio Web Windows (WINHTTP) per l'invio e la ricezione del traffico su protocolli TLS.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-109">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="1ae6e-110">Il client di Office può utilizzare TLS 1,2 Se il servizio Web del computer locale può utilizzare TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-110">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="1ae6e-111">Tutti i client di Office possono utilizzare i protocolli TLS, in quanto i protocolli TLS e SSL fanno parte del sistema operativo e non sono specifici del client di Office.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-111">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="1ae6e-112">In Windows 8 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1ae6e-112">On Windows 8 and later versions</span></span>

<span data-ttu-id="1ae6e-113">Per impostazione predefinita, i protocolli TLS 1,2 e 1,1 sono disponibili se non sono configurati dispositivi di rete per rifiutare il traffico TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-113">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="1ae6e-114">In Windows 7</span><span class="sxs-lookup"><span data-stu-id="1ae6e-114">On Windows 7</span></span>

<span data-ttu-id="1ae6e-115">I protocolli TLS 1,1 e 1,2 non sono disponibili senza l'aggiornamento di [KB 3140245](https://support.microsoft.com/help/3140245) .</span><span class="sxs-lookup"><span data-stu-id="1ae6e-115">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="1ae6e-116">L'aggiornamento consente di risolvere il problema e di aggiungere la seguente chiave secondaria del registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="1ae6e-116">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="1ae6e-117">Gli utenti di Windows 7 che non dispongono di questo aggiornamento sono intaccati al 31 ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-117">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="1ae6e-118">[KB 3140245](https://support.microsoft.com/help/3140245) contiene informazioni dettagliate su come modificare le impostazioni di WinHTTP per abilitare i protocolli TLS.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-118">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="1ae6e-119">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="1ae6e-119">More information</span></span>

<span data-ttu-id="1ae6e-120">Il valore della chiave del registro di sistema **DefaultSecureProtocols** descritta nell'articolo della Knowledge base determina i protocolli di rete che è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="1ae6e-120">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="1ae6e-121">Valore di DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="1ae6e-121">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="1ae6e-122">Protocollo abilitato</span><span class="sxs-lookup"><span data-stu-id="1ae6e-122">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="1ae6e-123">0x00000008</span><span class="sxs-lookup"><span data-stu-id="1ae6e-123">0x00000008</span></span>|<span data-ttu-id="1ae6e-124">Consente di abilitare SSL 2.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1ae6e-124">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="1ae6e-125">0x00000020</span><span class="sxs-lookup"><span data-stu-id="1ae6e-125">0x00000020</span></span>|<span data-ttu-id="1ae6e-126">Consente di abilitare SSL 3.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1ae6e-126">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="1ae6e-127">0x00000080</span><span class="sxs-lookup"><span data-stu-id="1ae6e-127">0x00000080</span></span>|<span data-ttu-id="1ae6e-128">Consente di abilitare TLS 1.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1ae6e-128">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="1ae6e-129">0x00000200</span><span class="sxs-lookup"><span data-stu-id="1ae6e-129">0x00000200</span></span>|<span data-ttu-id="1ae6e-130">Consente di abilitare TLS 1.1 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1ae6e-130">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="1ae6e-131">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1ae6e-131">0x00000800</span></span>|<span data-ttu-id="1ae6e-132">Consente di abilitare TLS 1.2 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="1ae6e-132">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="1ae6e-133">Client di Office e chiavi del registro di sistema TLS</span><span class="sxs-lookup"><span data-stu-id="1ae6e-133">Office clients and TLS registry keys</span></span>

<span data-ttu-id="1ae6e-134">È possibile fare riferimento a [KB 4057306 prepararsi per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306).</span><span class="sxs-lookup"><span data-stu-id="1ae6e-134">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="1ae6e-135">Questo è un articolo generale per gli amministratori IT, ed è la documentazione ufficiale relativa alla modifica di TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-135">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="1ae6e-136">Nella tabella seguente vengono illustrati i valori della chiave del registro di sistema corretti nei client di Office 365 dopo il 31 ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-136">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="1ae6e-137">Protocolli abilitati per il servizio Office 365 dopo il 31 ottobre 2018</span><span class="sxs-lookup"><span data-stu-id="1ae6e-137">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="1ae6e-138">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="1ae6e-138">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="1ae6e-139">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1ae6e-139">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="1ae6e-140">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="1ae6e-140">0x00000A80</span></span>|
|<span data-ttu-id="1ae6e-141">TLS 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1ae6e-141">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="1ae6e-142">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="1ae6e-142">0x00000A00</span></span>|
|<span data-ttu-id="1ae6e-143">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="1ae6e-143">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="1ae6e-144">0x00000880</span><span class="sxs-lookup"><span data-stu-id="1ae6e-144">0x00000880</span></span>|
|<span data-ttu-id="1ae6e-145">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="1ae6e-145">TLS 1.2</span></span>|<span data-ttu-id="1ae6e-146">0x00000800</span><span class="sxs-lookup"><span data-stu-id="1ae6e-146">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="1ae6e-147">Non è consigliabile utilizzare i protocolli SSL 2,0 e 3,0, che possono essere impostati anche utilizzando la chiave **DefaultSecureProtocols** .</span><span class="sxs-lookup"><span data-stu-id="1ae6e-147">We don't recommend that you use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="1ae6e-148">I protocolli SSL 2,0 e 3,0 sono considerati obsoleti.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-148">SSL 2.0 and 3.0 are considered deprecated protocols.</span></span> <span data-ttu-id="1ae6e-149">La procedura consigliata consiste nel terminare l'utilizzo di SSL 2,0 e SSL 3,0, anche se la decisione di eseguire questa operazione dipende in ultima analisi da ciò che soddisfa meglio le esigenze del prodotto.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-149">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="1ae6e-150">Per ulteriori informazioni sulle vulnerabilità di SSL 3,0, fare riferimento a [KB 3009008](https://support.microsoft.com/help/3009008).</span><span class="sxs-lookup"><span data-stu-id="1ae6e-150">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="1ae6e-151">È possibile utilizzare la calcolatrice predefinita di Windows in modalità Programmatore per impostare gli stessi valori di chiave del registro di sistema di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-151">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="1ae6e-152">Per ulteriori informazioni, vedere [aggiornamento di KB 3140245 per abilitare tls 1,1 e tls 1,2 come protocolli di sicurezza predefiniti in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span><span class="sxs-lookup"><span data-stu-id="1ae6e-152">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="1ae6e-153">Indipendentemente dal caso in cui l'aggiornamento di Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) sia installato o meno, la chiave secondaria del registro di sistema DefaultSecureProtocols non è presente e deve essere aggiunta manualmente o tramite un oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-153">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="1ae6e-154">In altre informazioni, a meno che non sia necessario personalizzare i protocolli protetti abilitati o limitati, questa chiave non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="1ae6e-154">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="1ae6e-155">È necessario solo l'aggiornamento di Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).</span><span class="sxs-lookup"><span data-stu-id="1ae6e-155">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>
