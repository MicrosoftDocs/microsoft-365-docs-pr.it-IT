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
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242355"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="eb2b4-103">Utilizzare un codice QR per accedere alle app outlook per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="eb2b4-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb2b4-104">Questa funzionalità è disponibile solo per le organizzazioni che hanno attivato Targeted Release nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="eb2b4-105">Per attivare Targeted Release e altre informazioni su come funziona, vedi [Configurare le opzioni Standard o Targeted Release.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b4-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="eb2b4-106">We'll be expanding to more organizations in the coming weeks through public preview.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="eb2b4-107">L'anteprima pubblica consente l'accesso anticipato alle funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="eb2b4-108">L'amministratore di Microsoft 365 può consentire agli utenti di accedere a Outlook per Android o app iOS nei dispositivi mobili senza dover immettere nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="eb2b4-109">L'analisi di un codice QR consente agli utenti di autenticarsi e accedere in modo sicuro a Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="eb2b4-110">In Outlook sul Web o in altre applicazioni desktop di Outlook, gli utenti possono visualizzare notifiche che informano che possono utilizzare Outlook sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="eb2b4-111">Queste notifiche possono essere gestite dall'amministratore tramite Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="eb2b4-112">Se gli utenti scelgono di inviare a se stessi un SMS per scaricare l'app sul dispositivo mobile, sul computer verrà visualizzato un codice QR.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="eb2b4-113">Saranno in grado di analizzare il codice QR per accedere a Outlook sul proprio telefono o tablet.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="eb2b4-114">Questo codice QR è un token di breve durata che può essere riscattato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="eb2b4-115">In alcuni casi, gli utenti doranno eseguire nuovamente l'autenticazione nel proprio computer per generare il codice QR.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="eb2b4-116">Utilizzare Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb2b4-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="eb2b4-117">Questa funzionalità è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-117">This feature is on by default.</span></span> <span data-ttu-id="eb2b4-118">Per disabilitare questa funzionalità, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="eb2b4-119">[Connettersi a Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="eb2b4-119">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="eb2b4-120">Utilizzando PowerShell, è possibile disabilitare le notifiche che informano gli utenti sulle app outlook per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="eb2b4-121">In questo modo si impedisce anche la visualizzazione del flusso di accesso del codice QR.</span><span class="sxs-lookup"><span data-stu-id="eb2b4-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="eb2b4-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="eb2b4-122">Related topics</span></span>

[<span data-ttu-id="eb2b4-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="eb2b4-123">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
