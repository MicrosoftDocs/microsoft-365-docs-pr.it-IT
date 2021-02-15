---
title: Disabilitazione di TLS 1.0 e 1.1 per Microsoft 365
description: Descrive la deprecazione e la disabilitazione di TLS 1.0 e 1.1 per Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 669ab53739bfd108bdbe9077762272e6a4901865
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233098"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="318f6-103">Disabilitazione di TLS 1.0 e 1.1 per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="318f6-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="318f6-104">Abbiamo temporaneamente interrotto la disabilitazione di TLS 1.0 e 1.1 per i clienti commerciali a causa di COVID-19.</span><span class="sxs-lookup"><span data-stu-id="318f6-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="318f6-105">Con la regolazione delle catene di approvvigionamento e l'apertura di alcuni paesi, l'implementazione di TLS 1.2 è stata riavviata il 15 ottobre 2020.</span><span class="sxs-lookup"><span data-stu-id="318f6-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="318f6-106">L'implementazione continuerà nelle settimane e nei mesi successivi.</span><span class="sxs-lookup"><span data-stu-id="318f6-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="318f6-107">A partire dal 31 ottobre 2018, i protocolli Transport Layer Security (TLS) 1.0 e 1.1 sono deprecati per il servizio Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="318f6-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="318f6-108">L'effetto per gli utenti finali è minimo.</span><span class="sxs-lookup"><span data-stu-id="318f6-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="318f6-109">Questa modifica è stata resa pubblica per oltre due anni, con il primo annuncio pubblico effettuato a dicembre 2017.</span><span class="sxs-lookup"><span data-stu-id="318f6-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="318f6-110">Questo articolo ha lo scopo di coprire solo il client locale di Office 365 in relazione al servizio Office 365, ma può essere applicato anche a problemi TLS locali con Office e Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="318f6-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="318f6-111">Per SharePoint e OneDrive, è necessario aggiornare e configurare .NET per supportare TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="318f6-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="318f6-112">Per informazioni, vedere [Come abilitare TLS 1.2 nei client.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="318f6-112">For information, see [How to enable TLS 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="318f6-113">Panoramica di Office 365 e TLS</span><span class="sxs-lookup"><span data-stu-id="318f6-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="318f6-114">Il client di Office si basa sul servizio Web Windows (WINHTTP) per inviare e ricevere traffico tramite protocolli TLS.</span><span class="sxs-lookup"><span data-stu-id="318f6-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="318f6-115">Il client di Office può utilizzare TLS 1.2 se il servizio Web del computer locale può utilizzare TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="318f6-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="318f6-116">Tutti i client di Office possono utilizzare i protocolli TLS, in quanto i protocolli TLS e SSL fanno parte del sistema operativo e non sono specifici del client di Office.</span><span class="sxs-lookup"><span data-stu-id="318f6-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="318f6-117">In Windows 8 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="318f6-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="318f6-118">Per impostazione predefinita, i protocolli TLS 1.2 e 1.1 sono disponibili se nessun dispositivo di rete è configurato per rifiutare il traffico TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="318f6-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="318f6-119">In Windows 7</span><span class="sxs-lookup"><span data-stu-id="318f6-119">On Windows 7</span></span>

<span data-ttu-id="318f6-120">I protocolli TLS 1.1 e 1.2 non sono disponibili senza l'aggiornamento [KB 3140245.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="318f6-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="318f6-121">L'aggiornamento risolve questo problema e aggiunge la seguente chiave secondaria del Registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="318f6-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="318f6-122">Gli utenti di Windows 7 che non dispongono di questo aggiornamento sono interessati dal 31 ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="318f6-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="318f6-123">[KB 3140245](https://support.microsoft.com/help/3140245) include informazioni dettagliate su come modificare le impostazioni WINHTTP per abilitare i protocolli TLS.</span><span class="sxs-lookup"><span data-stu-id="318f6-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="318f6-124">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="318f6-124">More information</span></span>

<span data-ttu-id="318f6-125">Il valore della chiave **del Registro di sistema DefaultSecureProtocols** descritta nell'articolo della Knowledge Base determina quali protocolli di rete possono essere utilizzati:</span><span class="sxs-lookup"><span data-stu-id="318f6-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="318f6-126">Valore DefaultSecureProtocols</span><span class="sxs-lookup"><span data-stu-id="318f6-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="318f6-127">Protocollo abilitato</span><span class="sxs-lookup"><span data-stu-id="318f6-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="318f6-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="318f6-128">0x00000008</span></span>|<span data-ttu-id="318f6-129">Consente di abilitare SSL 2.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="318f6-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="318f6-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="318f6-130">0x00000020</span></span>|<span data-ttu-id="318f6-131">Consente di abilitare SSL 3.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="318f6-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="318f6-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="318f6-132">0x00000080</span></span>|<span data-ttu-id="318f6-133">Consente di abilitare TLS 1.0 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="318f6-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="318f6-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="318f6-134">0x00000200</span></span>|<span data-ttu-id="318f6-135">Consente di abilitare TLS 1.1 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="318f6-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="318f6-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="318f6-136">0x00000800</span></span>|<span data-ttu-id="318f6-137">Consente di abilitare TLS 1.2 per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="318f6-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="318f6-138">Client di Office e chiavi del Registro di sistema TLS</span><span class="sxs-lookup"><span data-stu-id="318f6-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="318f6-139">È possibile fare riferimento a KB 4057306 Preparazione per l'uso obbligatorio di [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306)</span><span class="sxs-lookup"><span data-stu-id="318f6-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="318f6-140">Questo è un articolo generale per gli amministratori IT ed è la documentazione ufficiale sulla modifica di TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="318f6-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="318f6-141">La tabella seguente mostra i valori delle chiavi del Registro di sistema appropriati nei client di Office 365 dopo il 31 ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="318f6-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="318f6-142">Protocolli abilitati per il servizio Office 365 dopo il 31 ottobre 2018</span><span class="sxs-lookup"><span data-stu-id="318f6-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="318f6-143">Valore esadecimale</span><span class="sxs-lookup"><span data-stu-id="318f6-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="318f6-144">TLS 1.0 + 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="318f6-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="318f6-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="318f6-145">0x00000A80</span></span>|
|<span data-ttu-id="318f6-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="318f6-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="318f6-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="318f6-147">0x00000A00</span></span>|
|<span data-ttu-id="318f6-148">TLS 1.0 + 1.2</span><span class="sxs-lookup"><span data-stu-id="318f6-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="318f6-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="318f6-149">0x00000880</span></span>|
|<span data-ttu-id="318f6-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="318f6-150">TLS 1.2</span></span>|<span data-ttu-id="318f6-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="318f6-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="318f6-152">Non utilizzare i protocolli SSL 2.0 e 3.0, che possono essere impostati anche utilizzando la chiave **DefaultSecureProtocols.**</span><span class="sxs-lookup"><span data-stu-id="318f6-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="318f6-153">SSL 2.0 e 3.0 sono considerati protocolli obsoleti e non sicuri.</span><span class="sxs-lookup"><span data-stu-id="318f6-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="318f6-154">La procedura consigliata consiste nel terminare l'utilizzo di SSL 2.0 e SSL 3.0, anche se la decisione di eseguire questa operazione dipende in ultima analisi da ciò che meglio soddisfa le esigenze del prodotto.</span><span class="sxs-lookup"><span data-stu-id="318f6-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="318f6-155">Per ulteriori informazioni sulle vulnerabilità di SSL 3.0, vedere [kb 3009008.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="318f6-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="318f6-156">Puoi usare lo Strumento di calcolo Windows predefinito in modalità Programmatore per configurare gli stessi valori delle chiavi del Registro di sistema di riferimento.</span><span class="sxs-lookup"><span data-stu-id="318f6-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="318f6-157">Per ulteriori informazioni, vedere [l'aggiornamento KB 3140245 per abilitare TLS 1.1 e TLS 1.2](https://support.microsoft.com/help/3140245)come protocolli sicuri predefiniti in WinHTTP in Windows.</span><span class="sxs-lookup"><span data-stu-id="318f6-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="318f6-158">Indipendentemente dal fatto che l'aggiornamento di Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) sia installato o meno, la chiave secondaria del Registro di sistema DefaultSecureProtocols non è presente e deve essere aggiunta manualmente o tramite un oggetto Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="318f6-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="318f6-159">In altri casi, a meno che non sia necessario personalizzare i protocolli sicuri abilitati o limitati, questa chiave non è necessaria.</span><span class="sxs-lookup"><span data-stu-id="318f6-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="318f6-160">È necessario solo l'aggiornamento di Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="318f6-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="318f6-161">Aggiornare e configurare .NET Framework per supportare TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="318f6-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="318f6-162">Dovrai aggiornare le applicazioni che chiamano le API di Microsoft 365 su TLS 1.0 o TLS 1.1 per usare TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="318f6-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="318f6-163">.NET 4.5 viene utilizzato per impostazione predefinita su TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="318f6-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="318f6-164">Per aggiornare la configurazione di .NET, vedere [Come abilitare Transport Layer Security (TLS) 1.2 nei client.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="318f6-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="318f6-165">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="318f6-165">More information</span></span>

<span data-ttu-id="318f6-166">Per ulteriori informazioni, vedere [Preparazione per l'uso obbligatorio di TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="318f6-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
