---
title: Utilizzare un codice QR per accedere alle app outlook per dispositivi mobili
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Informazioni su come utilizzare un codice QR per autenticare e scaricare Outlook Mobile.
ms.openlocfilehash: b9e433e0c7d3f5f3466924b318e242e5ac29181c
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122373"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="a4333-103">Utilizzare un codice QR per accedere alle app outlook per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="a4333-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4333-104">Questa funzionalità di Microsoft 365 è in anteprima pubblica.</span><span class="sxs-lookup"><span data-stu-id="a4333-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="a4333-105">L'anteprima pubblica consente l'accesso anticipato alle funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4333-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="a4333-106">L'amministratore di Microsoft 365 può consentire agli utenti di accedere a Outlook per Android o app iOS nei dispositivi mobili senza dover immettere nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="a4333-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="a4333-107">L'analisi di un codice QR consente agli utenti di autenticarsi e accedere in modo sicuro a Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="a4333-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="a4333-108">In Outlook sul Web o in altre applicazioni outlook desktop, gli utenti possono visualizzare notifiche che informano che possono utilizzare Outlook sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="a4333-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="a4333-109">Queste notifiche possono essere gestite dall'amministratore tramite Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4333-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="a4333-110">Se gli utenti scelgono di inviare a se stessi un SMS per scaricare l'app sul dispositivo mobile, sul computer verrà visualizzato un codice QR.</span><span class="sxs-lookup"><span data-stu-id="a4333-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="a4333-111">Saranno in grado di analizzare il codice QR per accedere a Outlook sul proprio telefono o tablet.</span><span class="sxs-lookup"><span data-stu-id="a4333-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="a4333-112">Questo codice QR è un token di breve durata che può essere riscattato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a4333-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="a4333-113">In alcuni casi, gli utenti doranno eseguire nuovamente l'autenticazione nel proprio computer per generare il codice QR.</span><span class="sxs-lookup"><span data-stu-id="a4333-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="a4333-114">Utilizzare Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4333-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="a4333-115">Questa esperienza è disponibile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a4333-115">This experience is on by default.</span></span> <span data-ttu-id="a4333-116">Per disabilitare questa funzionalità, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="a4333-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="a4333-117">[Connettersi a Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="a4333-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="a4333-118">Utilizzando PowerShell, è possibile disabilitare le notifiche che informano gli utenti sulle app outlook per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="a4333-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="a4333-119">In questo modo si impedisce anche la visualizzazione del flusso di accesso del codice QR.</span><span class="sxs-lookup"><span data-stu-id="a4333-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="a4333-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a4333-120">Related topics</span></span>

[<span data-ttu-id="a4333-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="a4333-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
