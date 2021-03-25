---
title: Risolvere i problemi di installazione per Microsoft Defender ATP per Mac
description: Risolvere i problemi di installazione in Microsoft Defender ATP per Mac.
keywords: microsoft, defender, atp, mac, install
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 60b50f3944a2cdd995b4877e22123018267ff044
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062237"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="1f23b-104">Risolvere i problemi di installazione per Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="1f23b-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1f23b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1f23b-105">**Applies to:**</span></span>

- [<span data-ttu-id="1f23b-106">Microsoft Defender per Endpoint per Mac</span><span class="sxs-lookup"><span data-stu-id="1f23b-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="1f23b-107">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1f23b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1f23b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f23b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1f23b-109">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1f23b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1f23b-110">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1f23b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="1f23b-111">Installazione non riuscita</span><span class="sxs-lookup"><span data-stu-id="1f23b-111">Installation failed</span></span>

<span data-ttu-id="1f23b-112">Per l'installazione manuale, nella pagina Riepilogo dell'installazione guidata viene visualizzato il messaggio "Si è verificato un errore durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1f23b-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="1f23b-113">Il programma di installazione ha rilevato un errore che ha causato l'errore dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="1f23b-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="1f23b-114">Contattare il produttore del software per assistenza."</span><span class="sxs-lookup"><span data-stu-id="1f23b-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="1f23b-115">Per le distribuzioni MDM, viene visualizzato anche come errore di installazione generico.</span><span class="sxs-lookup"><span data-stu-id="1f23b-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="1f23b-116">Anche se non viene visualizzato un errore esatto per l'utente finale, si mantiene un file di registro con lo stato di avanzamento dell'installazione in `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="1f23b-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="1f23b-117">Ogni sessione di installazione viene aggiunta a questo file di registro.</span><span class="sxs-lookup"><span data-stu-id="1f23b-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="1f23b-118">È possibile utilizzare solo `sed` per l'output dell'ultima sessione di installazione:</span><span class="sxs-lookup"><span data-stu-id="1f23b-118">You can use `sed` to output the last installation session only:</span></span>

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

<span data-ttu-id="1f23b-119">In questo esempio, il motivo effettivo è preceduto da `[ERROR]` .</span><span class="sxs-lookup"><span data-stu-id="1f23b-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="1f23b-120">L'installazione non è riuscita perché non è supportato un downgrade tra queste versioni.</span><span class="sxs-lookup"><span data-stu-id="1f23b-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="1f23b-121">Registro di installazione MDATP mancante o non aggiornato</span><span class="sxs-lookup"><span data-stu-id="1f23b-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="1f23b-122">In rari casi, l'installazione non lascia traccia nel file /Library/Logs/Microsoft/mdatp/install.log di MDATP.</span><span class="sxs-lookup"><span data-stu-id="1f23b-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="1f23b-123">Puoi verificare che sia stata eseguita un'installazione e analizzare i possibili errori tramite query sui log macOS (questa operazione è utile nella distribuzione MDM, quando non è disponibile un'interfaccia utente client).</span><span class="sxs-lookup"><span data-stu-id="1f23b-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="1f23b-124">È consigliabile utilizzare un intervallo di tempo ristretto per eseguire una query e filtrare in base al nome del processo di registrazione, in quanto saranno disponibili un'enorme quantità di informazioni.</span><span class="sxs-lookup"><span data-stu-id="1f23b-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```