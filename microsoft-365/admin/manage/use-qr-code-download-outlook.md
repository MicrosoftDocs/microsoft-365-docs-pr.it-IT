---
title: Usare un codice QR per accedere alle app outlook per dispositivi mobili
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
description: Informazioni su come utilizzare un codice QR per autenticare e scaricare Outlook mobile.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914967"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="38229-103">Usare un codice QR per accedere alle app outlook per dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="38229-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38229-104">Questa funzionalità è disponibile solo per le organizzazioni che hanno attivato Rilascio mirato nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38229-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="38229-105">Per attivare rilascio mirato e altre informazioni su come funziona, vedi Configurare le opzioni di rilascio [Standard o Mirato.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="38229-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="38229-106">L'anteprima pubblica verrà espansa a più organizzazioni nelle prossime settimane.</span><span class="sxs-lookup"><span data-stu-id="38229-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="38229-107">L'anteprima pubblica consente l'accesso anticipato alle funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38229-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="38229-108">L'amministratore di Microsoft 365 può consentire agli utenti di accedere all'app Outlook per Android o iOS nei propri dispositivi mobili senza dover immettere il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="38229-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="38229-109">Tramite l'analisi di un codice QR, gli utenti possono autenticarsi e accedere in modo sicuro a Outlook mobile.</span><span class="sxs-lookup"><span data-stu-id="38229-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="38229-110">In Outlook sul Web o in altre applicazioni desktop di Outlook, gli utenti possono visualizzare notifiche che informano che possono utilizzare Outlook sul proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="38229-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="38229-111">Queste notifiche possono essere gestite dall'amministratore tramite PowerShell di Exchange.</span><span class="sxs-lookup"><span data-stu-id="38229-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="38229-112">Se gli utenti scelgono di inviare un SMS per scaricare l'app sul dispositivo mobile, sul computer verrà visualizzato un codice QR.</span><span class="sxs-lookup"><span data-stu-id="38229-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="38229-113">Saranno in grado di analizzare il codice QR per accedere a Outlook sul proprio telefono o tablet.</span><span class="sxs-lookup"><span data-stu-id="38229-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="38229-114">Questo codice QR è un token di breve durata che può essere riscattato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="38229-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="38229-115">In alcuni casi, gli utenti doranno eseguire di nuovo l'autenticazione nel computer per generare il codice QR.</span><span class="sxs-lookup"><span data-stu-id="38229-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="38229-116">Utilizzare PowerShell di Exchange</span><span class="sxs-lookup"><span data-stu-id="38229-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="38229-117">Questa funzionalità è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="38229-117">This feature is on by default.</span></span> <span data-ttu-id="38229-118">Per disabilitare questa funzionalità, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="38229-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="38229-119">[Connettersi a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="38229-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="38229-120">Utilizzando PowerShell, è possibile disabilitare le notifiche che informano gli utenti sulle app outlook per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="38229-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="38229-121">Questo impedirà anche la visualizzazione del flusso di accesso del codice QR.</span><span class="sxs-lookup"><span data-stu-id="38229-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="38229-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="38229-122">Related topics</span></span>

[<span data-ttu-id="38229-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="38229-123">Set-OrganizationConfig</span></span>](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)