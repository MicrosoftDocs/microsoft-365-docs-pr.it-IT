---
title: Risolvere i problemi di onboarding e i messaggi di errore
description: Risolvere i problemi di onboarding e il messaggio di errore durante il completamento della configurazione di Microsoft Defender per Endpoint.
keywords: risoluzione dei problemi, risoluzione dei problemi, Azure Active Directory, onboarding, messaggio di errore, messaggi di errore, microsoft defender per endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 1b769c1b3e4201802ea6150358568bf57894d305
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185809"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="30b05-104">Risolvere i problemi di accesso a sottoscrizioni e portali</span><span class="sxs-lookup"><span data-stu-id="30b05-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="30b05-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="30b05-105">**Applies to:**</span></span>
- [<span data-ttu-id="30b05-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="30b05-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="30b05-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30b05-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="30b05-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="30b05-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="30b05-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="30b05-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="30b05-110">Questa pagina fornisce la procedura dettagliata per risolvere i problemi che potrebbero verificarsi durante la configurazione del servizio Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="30b05-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="30b05-111">Se ricevi un messaggio di errore, Microsoft Defender Security Center fornirà una spiegazione dettagliata sul problema e verranno forniti collegamenti pertinenti.</span><span class="sxs-lookup"><span data-stu-id="30b05-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="30b05-112">Nessuna sottoscrizione trovata</span><span class="sxs-lookup"><span data-stu-id="30b05-112">No subscriptions found</span></span>

<span data-ttu-id="30b05-113">Se durante l'accesso **a** Microsoft Defender Security Center viene visualizzato il messaggio Nessuna sottoscrizione trovata, significa che Azure Active Directory (Azure AD) utilizzato per accedere all'utente al portale non dispone di una licenza di Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="30b05-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="30b05-114">Possibili motivi:</span><span class="sxs-lookup"><span data-stu-id="30b05-114">Potential reasons:</span></span>
- <span data-ttu-id="30b05-115">Le licenze di Windows E5 e Office E5 sono licenze distinte.</span><span class="sxs-lookup"><span data-stu-id="30b05-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="30b05-116">La licenza è stata acquistata ma non ne è stato eseguito il provisioning in questa istanza di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="30b05-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="30b05-117">Potrebbe trattarsi di un problema di provisioning delle licenze.</span><span class="sxs-lookup"><span data-stu-id="30b05-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="30b05-118">Potrebbe essere stato inavvertitamente effettuato il provisioning della licenza a un Microsoft Azure AD diverso da quello utilizzato per l'autenticazione nel servizio.</span><span class="sxs-lookup"><span data-stu-id="30b05-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="30b05-119">Per entrambi i casi, è consigliabile contattare il supporto Microsoft [all'indirizzo General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) o Volume license [support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span><span class="sxs-lookup"><span data-stu-id="30b05-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Immagine di nessuna sottoscrizione trovata](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="30b05-121">L'abbonamento è scaduto</span><span class="sxs-lookup"><span data-stu-id="30b05-121">Your subscription has expired</span></span>

<span data-ttu-id="30b05-122">Se durante l'accesso a Microsoft Defender Security Center viene visualizzato un messaggio **L'abbonamento** è scaduto, l'abbonamento al servizio online è scaduto.</span><span class="sxs-lookup"><span data-stu-id="30b05-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="30b05-123">L'abbonamento a Microsoft Defender for Endpoint, come qualsiasi altro abbonamento al servizio online, ha una data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="30b05-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="30b05-124">Puoi scegliere di rinnovare o estendere la licenza in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="30b05-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="30b05-125">Quando si accede al portale  dopo la data di scadenza, verrà visualizzata un'opzione per scaricare il pacchetto di offboarding del dispositivo se si sceglie di non rinnovare la licenza.</span><span class="sxs-lookup"><span data-stu-id="30b05-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="30b05-126">Per motivi di sicurezza, il pacchetto usato per i dispositivi offboard scadrà 30 giorni dopo la data di download.</span><span class="sxs-lookup"><span data-stu-id="30b05-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="30b05-127">I pacchetti di offboarding scaduti inviati a un dispositivo verranno rifiutati.</span><span class="sxs-lookup"><span data-stu-id="30b05-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="30b05-128">Durante il download di un pacchetto di offboarding, ti verrà notificata la data di scadenza dei pacchetti e verrà incluso anche nel nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="30b05-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Immagine della sottoscrizione scaduta](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="30b05-130">Non si è autorizzati ad accedere al portale</span><span class="sxs-lookup"><span data-stu-id="30b05-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="30b05-131">Se si riceve un Messaggio Non si è autorizzati ad accedere al **portale,** tenere presente che Microsoft Defender for Endpoint è un prodotto di monitoraggio della sicurezza, analisi degli incidenti e risposta e, di conseguenza, l'accesso ad esso è limitato e controllato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="30b05-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="30b05-132">Per ulteriori informazioni, vedere [**Assegnare l'accesso utente al portale.**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="30b05-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Immagine di utenti non autorizzati ad accedere al portale](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="30b05-134">I dati attualmente non sono disponibili in alcune sezioni del portale</span><span class="sxs-lookup"><span data-stu-id="30b05-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="30b05-135">Se nel dashboard del portale e in altre sezioni viene visualizzato un messaggio di errore, ad esempio "I dati attualmente non sono disponibili":</span><span class="sxs-lookup"><span data-stu-id="30b05-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![Immagine dei dati attualmente non disponibile](images/atp-data-not-available.png)

<span data-ttu-id="30b05-137">Dovrai consentire il sottodominio e tutti `securitycenter.windows.com` i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="30b05-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="30b05-138">Ad esempio, `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="30b05-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="30b05-139">Problemi di comunicazione del portale</span><span class="sxs-lookup"><span data-stu-id="30b05-139">Portal communication issues</span></span>
<span data-ttu-id="30b05-140">Se si verificano problemi di accesso al portale, dati mancanti o accesso limitato a parti del portale, è necessario verificare che gli URL seguenti siano consentiti e aperti per la comunicazione.</span><span class="sxs-lookup"><span data-stu-id="30b05-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



