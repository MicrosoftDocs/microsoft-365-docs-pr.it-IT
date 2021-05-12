---
title: Usare AllowSelfServicePurchase per il modulo di PowerShell MSCommerce
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: Informazioni su come usare il cmdlet Di PowerShell AllowSelfServicePurchase per attivare o disattivare l'acquisto in modalità self-service.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 09161f69e72babe8270b339243d73444b93d9959
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333375"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="abc34-103">Usare AllowSelfServicePurchase per il modulo di PowerShell MSCommerce</span><span class="sxs-lookup"><span data-stu-id="abc34-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="abc34-104">Il **modulo MSCommerce** PowerShell è ora disponibile in [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="abc34-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="abc34-105">Il modulo include un valore del parametro **PolicyID** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="abc34-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="abc34-106">È possibile utilizzare il **modulo ms-Commerce** PowerShell per:</span><span class="sxs-lookup"><span data-stu-id="abc34-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="abc34-107">Visualizzare lo stato predefinito del **valore del parametro AllowSelfServicePurchase,** indipendentemente dal fatto che sia abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="abc34-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="abc34-108">Visualizzare un elenco dei prodotti applicabili e se l'acquisto in self-service è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="abc34-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="abc34-109">Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarla o disabilitarla</span><span class="sxs-lookup"><span data-stu-id="abc34-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="abc34-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="abc34-110">Requirements</span></span>

<span data-ttu-id="abc34-111">Per usare il **modulo ms-Commerce** PowerShell, è necessario:</span><span class="sxs-lookup"><span data-stu-id="abc34-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="abc34-112">Un dispositivo Windows 10</span><span class="sxs-lookup"><span data-stu-id="abc34-112">A Windows 10 device</span></span>
- <span data-ttu-id="abc34-113">Autorizzazione di amministratore per il dispositivo</span><span class="sxs-lookup"><span data-stu-id="abc34-113">Administrator permission for the device</span></span>
- <span data-ttu-id="abc34-114">Ruolo amministratore globale o fatturazione per il tenant</span><span class="sxs-lookup"><span data-stu-id="abc34-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="abc34-115">Installare il modulo ms-Commerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="abc34-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="abc34-116">Il modulo **MSCommerce** PowerShell viene installato nel dispositivo Windows 10 una sola volta e quindi importato in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="abc34-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="abc34-117">Scaricare il **modulo MSCommerce** PowerShell da [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="abc34-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="abc34-118">Per installare il **modulo ms-Commerce** PowerShell con **PowerShellGet,** eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abc34-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="abc34-119">Importare MSCommerce nella sessione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="abc34-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="abc34-120">Dopo aver installato il modulo nel dispositivo Windows 10, importalo in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="abc34-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="abc34-121">Per importarlo in una sessione di PowerShell, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abc34-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="abc34-122">Connettersi a MSCommerce con le credenziali</span><span class="sxs-lookup"><span data-stu-id="abc34-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="abc34-123">Per connettersi al modulo di PowerShell con le credenziali, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="abc34-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="abc34-124">Questo comando connette la sessione di PowerShell corrente a un tenant di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abc34-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="abc34-125">Il comando richiede un nome utente e una password per il tenant a cui si desidera connettersi.</span><span class="sxs-lookup"><span data-stu-id="abc34-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="abc34-126">Se per le credenziali è abilitata l'autenticazione a più fattori, si utilizza l'opzione interattiva per accedere.</span><span class="sxs-lookup"><span data-stu-id="abc34-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="abc34-127">Visualizzare i dettagli per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="abc34-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="abc34-128">Per visualizzare una descrizione del valore del parametro **AllowSelfServicePurchase** e dello stato predefinito, in base all'organizzazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abc34-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="abc34-129">Visualizzare un elenco di prodotti di acquisto self-service e il relativo stato</span><span class="sxs-lookup"><span data-stu-id="abc34-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="abc34-130">Per visualizzare un elenco di tutti i prodotti di acquisto self-service disponibili e lo stato di ognuno di essi, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abc34-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="abc34-131">Nella tabella seguente sono elencati i prodotti disponibili e il **relativo ProductId.**</span><span class="sxs-lookup"><span data-stu-id="abc34-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="abc34-132">Prodotto</span><span class="sxs-lookup"><span data-stu-id="abc34-132">Product</span></span> | <span data-ttu-id="abc34-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="abc34-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="abc34-134">Power Apps per utente</span><span class="sxs-lookup"><span data-stu-id="abc34-134">Power Apps per user</span></span> | <span data-ttu-id="abc34-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="abc34-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="abc34-136">Power Automate per utente</span><span class="sxs-lookup"><span data-stu-id="abc34-136">Power Automate per user</span></span> | <span data-ttu-id="abc34-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="abc34-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="abc34-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="abc34-138">Power Automate RPA</span></span> | <span data-ttu-id="abc34-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="abc34-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="abc34-140">Power BI Premium (autonomo)</span><span class="sxs-lookup"><span data-stu-id="abc34-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="abc34-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="abc34-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="abc34-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="abc34-142">Power BI Pro</span></span> | <span data-ttu-id="abc34-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="abc34-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="abc34-144">Piano di progetto 1</span><span class="sxs-lookup"><span data-stu-id="abc34-144">Project Plan 1</span></span> | <span data-ttu-id="abc34-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="abc34-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="abc34-146">Piano di progetto 3</span><span class="sxs-lookup"><span data-stu-id="abc34-146">Project Plan 3</span></span> | <span data-ttu-id="abc34-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="abc34-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="abc34-148">Visio Piano 1</span><span class="sxs-lookup"><span data-stu-id="abc34-148">Visio Plan 1</span></span> | <span data-ttu-id="abc34-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="abc34-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="abc34-150">Visio Piano 2</span><span class="sxs-lookup"><span data-stu-id="abc34-150">Visio Plan 2</span></span> | <span data-ttu-id="abc34-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="abc34-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="abc34-152">Visualizzare o impostare lo stato per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="abc34-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="abc34-153">Dopo aver visualizzato l'elenco dei prodotti disponibili per l'acquisto in self-service, è possibile visualizzare o modificare l'impostazione per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="abc34-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="abc34-154">Per ottenere l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abc34-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="abc34-155">Per abilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abc34-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="abc34-156">Per disabilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="abc34-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="abc34-157">Script di esempio per disabilitare AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="abc34-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="abc34-158">L'esempio seguente illustra come importare il modulo **MS Commerce,** accedere con l'account, ottenere **ProductId** per Power Automate e quindi **disabilitare AllowSelfServicePurchase** per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="abc34-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="abc34-159">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="abc34-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="abc34-160">Problema</span><span class="sxs-lookup"><span data-stu-id="abc34-160">Problem</span></span>

<span data-ttu-id="abc34-161">Viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="abc34-161">You see the following error message:</span></span>

> <span data-ttu-id="abc34-162">HandleError: impossibile recuperare i criteri con PolicyId 'AllowSelfServicePurchase', ErrorMessage - La connessione sottostante è stata chiusa: si è verificato un errore imprevisto durante un invio.</span><span class="sxs-lookup"><span data-stu-id="abc34-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="abc34-163">Ciò potrebbe essere dovuto a una versione precedente di Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="abc34-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="abc34-164">Per connettere questo servizio, è necessario utilizzare TLS 1.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="abc34-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="abc34-165">Soluzione</span><span class="sxs-lookup"><span data-stu-id="abc34-165">Solution</span></span>

<span data-ttu-id="abc34-166">Eseguire l'aggiornamento a TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="abc34-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
