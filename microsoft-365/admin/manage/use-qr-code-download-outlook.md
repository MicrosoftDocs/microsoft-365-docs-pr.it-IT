---
title: Usare un codice QR per accedere alle app Outlook mobili
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
description: Scopri come usare un codice QR per autenticare e scaricare Outlook mobile.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635999"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="56d44-103">Usare un codice QR per accedere alle app Outlook mobili</span><span class="sxs-lookup"><span data-stu-id="56d44-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56d44-104">Questa funzionalità è disponibile solo per le organizzazioni che hanno attivato Rilascio mirato nell'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="56d44-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="56d44-105">Per attivare rilascio mirato e altre informazioni su come funziona, vedi Configurare le opzioni di rilascio [Standard o Mirato.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="56d44-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="56d44-106">L'anteprima pubblica verrà espansa a più organizzazioni nelle prossime settimane.</span><span class="sxs-lookup"><span data-stu-id="56d44-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="56d44-107">L'anteprima pubblica consente l'accesso Microsoft 365 funzionalità.</span><span class="sxs-lookup"><span data-stu-id="56d44-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="56d44-108">In quanto amministratore Microsoft 365, puoi consentire agli utenti di accedere a Outlook per l'app Android o iOS nei dispositivi mobili senza dover immettere nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="56d44-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="56d44-109">Tramite l'analisi di un codice QR, gli utenti possono autenticarsi e accedere in modo sicuro Outlook mobile.</span><span class="sxs-lookup"><span data-stu-id="56d44-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="56d44-110">In Outlook sul Web o in altre applicazioni Outlook desktop, gli utenti possono visualizzare notifiche che informano che possono usare Outlook sul proprio dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="56d44-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="56d44-111">Queste notifiche possono essere gestite dall'amministratore tramite Exchange PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56d44-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="56d44-112">Se gli utenti scelgono di inviare un messaggio SMS sms per scaricare l'app sul dispositivo mobile, sul computer verrà visualizzato un codice QR.</span><span class="sxs-lookup"><span data-stu-id="56d44-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="56d44-113">Saranno in grado di analizzare il codice QR per accedere Outlook sul proprio telefono o tablet.</span><span class="sxs-lookup"><span data-stu-id="56d44-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="56d44-114">Questo codice QR è un token di breve durata che può essere riscattato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="56d44-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="56d44-115">In alcuni casi, gli utenti devono eseguire nuovamente l'autenticazione nel computer per generare il codice QR.</span><span class="sxs-lookup"><span data-stu-id="56d44-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="56d44-116">Usare Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="56d44-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="56d44-117">Questa funzionalità è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="56d44-117">This feature is on by default.</span></span> <span data-ttu-id="56d44-118">Per disabilitare questa funzionalità, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="56d44-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="56d44-119">[Connessione a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="56d44-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="56d44-120">Usando PowerShell, è possibile disabilitare le notifiche che informano gli utenti sulle Outlook per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="56d44-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="56d44-121">In questo modo si impedisce anche la visualizzazione del flusso di accesso del codice QR.</span><span class="sxs-lookup"><span data-stu-id="56d44-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="56d44-122">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="56d44-122">Related content</span></span>

<span data-ttu-id="56d44-123">[Configurare le opzioni di rilascio Standard o Mirato](release-options-in-office-365.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="56d44-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="56d44-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (articolo)</span><span class="sxs-lookup"><span data-stu-id="56d44-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (article)</span></span>