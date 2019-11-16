---
title: Utilizzo di AllowSelfServicePurchase per abilitare o disabilitare gli acquisti in modalità self-service
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Informazioni su come utilizzare il cmdlet di AllowSelfServicePurchase PowerShell per abilitare o disabilitare l'acquisto in modalità self-service.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9093e018ed24a9e9735f5b6b71084246967cb59d
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676269"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="f54a2-103">Utilizzo di AllowSelfServicePurchase per il modulo di PowerShell di MSCommerce</span><span class="sxs-lookup"><span data-stu-id="f54a2-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="f54a2-104">Il modulo di **MSCommerce** PowerShell è ora disponibile nella [raccolta di PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="f54a2-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="f54a2-105">Il modulo include un valore del parametro **PolicyId** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="f54a2-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="f54a2-106">È possibile utilizzare il modulo di **MSCommerce** PowerShell per:</span><span class="sxs-lookup"><span data-stu-id="f54a2-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="f54a2-107">Visualizzare lo stato predefinito del valore del parametro **AllowSelfServicePurchase** , ovvero se è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="f54a2-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="f54a2-108">Visualizzare un elenco di prodotti applicabili e se l'acquisto in modalità self-service è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="f54a2-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="f54a2-109">Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarlo o disabilitarlo</span><span class="sxs-lookup"><span data-stu-id="f54a2-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="f54a2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f54a2-110">Requirements</span></span>

<span data-ttu-id="f54a2-111">Per utilizzare il modulo di **MSCommerce** PowerShell, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f54a2-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="f54a2-112">Un dispositivo Windows 10</span><span class="sxs-lookup"><span data-stu-id="f54a2-112">A Windows 10 device</span></span>
- <span data-ttu-id="f54a2-113">Autorizzazione di amministratore per il dispositivo</span><span class="sxs-lookup"><span data-stu-id="f54a2-113">Administrator permission for the device</span></span>
- <span data-ttu-id="f54a2-114">Ruolo di amministratore globale o di fatturazione per il tenant</span><span class="sxs-lookup"><span data-stu-id="f54a2-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="f54a2-115">Installare il modulo di MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="f54a2-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="f54a2-116">Installare il modulo di **MSCommerce** PowerShell nel dispositivo Windows 10 una volta e quindi importarlo in ogni sessione di PowerShell che si avvia.</span><span class="sxs-lookup"><span data-stu-id="f54a2-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="f54a2-117">Scaricare il modulo di **MSCommerce** PowerShell dalla [raccolta di PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="f54a2-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="f54a2-118">Per installare il modulo di **MSCommerce** PowerShell con **PowerShellGet**, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f54a2-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="f54a2-119">Importare MSCommerce nella sessione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f54a2-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="f54a2-120">Dopo aver installato il modulo nel dispositivo Windows 10, importarlo in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="f54a2-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="f54a2-121">Per importarlo in una sessione di PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f54a2-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="f54a2-122">Connettersi a MSCommerce con le proprie credenziali</span><span class="sxs-lookup"><span data-stu-id="f54a2-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="f54a2-123">Per connettersi al modulo di PowerShell con le credenziali, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f54a2-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="f54a2-124">Questo comando connette la sessione corrente di PowerShell a un tenant di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f54a2-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="f54a2-125">Il comando richiede un nome utente e una password per il tenant a cui si desidera effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="f54a2-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="f54a2-126">Se è abilitata l'autenticazione a più fattori per le proprie credenziali, è possibile utilizzare l'opzione Interactive per eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f54a2-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="f54a2-127">Visualizzare i dettagli per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="f54a2-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="f54a2-128">Per visualizzare una descrizione del valore del parametro **AllowSelfServicePurchase** e lo stato predefinito, in base all'organizzazione, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f54a2-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="f54a2-129">Visualizzare un elenco di prodotti per l'acquisto in modalità self-service e il relativo stato</span><span class="sxs-lookup"><span data-stu-id="f54a2-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="f54a2-130">Per visualizzare un elenco di tutti i prodotti di acquisto self-service disponibili e lo stato di ogni, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f54a2-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="f54a2-131">Nella tabella seguente sono elencati i prodotti disponibili e il relativo **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="f54a2-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="f54a2-132">Prodotto</span><span class="sxs-lookup"><span data-stu-id="f54a2-132">Product</span></span> | <span data-ttu-id="f54a2-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="f54a2-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="f54a2-134">Power Apps per utente</span><span class="sxs-lookup"><span data-stu-id="f54a2-134">Power Apps per user</span></span> | <span data-ttu-id="f54a2-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="f54a2-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="f54a2-136">Automatizzare l'alimentazione per utente</span><span class="sxs-lookup"><span data-stu-id="f54a2-136">Power Automate per user</span></span> | <span data-ttu-id="f54a2-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="f54a2-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="f54a2-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="f54a2-138">Power BI Pro</span></span> | <span data-ttu-id="f54a2-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="f54a2-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="f54a2-140">Visualizzare o impostare lo stato di AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="f54a2-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="f54a2-141">Dopo aver visualizzato l'elenco dei prodotti disponibili per l'acquisto in modalità self-service, è possibile visualizzare o modificare l'impostazione di un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="f54a2-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="f54a2-142">Per ottenere l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f54a2-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="f54a2-143">Per abilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f54a2-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="f54a2-144">Per disabilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f54a2-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="f54a2-145">Script di esempio per disabilitare AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="f54a2-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="f54a2-146">Nell'esempio seguente viene illustrato come importare il modulo **MSCommerce** , accedere con l'account, ottenere il **ProductID** per automatizzare l'alimentazione e quindi disabilitare **AllowSelfServicePurchase** per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="f54a2-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->