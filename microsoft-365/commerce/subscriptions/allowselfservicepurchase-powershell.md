---
title: Usare AllowSelfServicePurchase per il modulo MSSelf PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Informazioni su come usare il cmdlet Di PowerShell AllowSelfServicePurchase per attivare o disattivare l'acquisto self-service.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653714"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="2021e-103">Usare AllowSelfServicePurchase per il modulo MSSelf PowerShell</span><span class="sxs-lookup"><span data-stu-id="2021e-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="2021e-104">Il **modulo MSPivot** PowerShell è ora disponibile in [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="2021e-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="2021e-105">Il modulo include un valore del parametro **PolicyID** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="2021e-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="2021e-106">È possibile utilizzare il **modulo MS Commerce** PowerShell per:</span><span class="sxs-lookup"><span data-stu-id="2021e-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="2021e-107">Visualizzare lo stato predefinito del valore del parametro **AllowSelfServicePurchase,** indipendentemente dal fatto che sia abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="2021e-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="2021e-108">Visualizzare un elenco di prodotti applicabili e se l'acquisto self-service è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="2021e-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="2021e-109">Visualizzare o modificare l'impostazione corrente di un prodotto specifico per abilitarla o disabilitarla</span><span class="sxs-lookup"><span data-stu-id="2021e-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="2021e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2021e-110">Requirements</span></span>

<span data-ttu-id="2021e-111">Per usare il **modulo MS Commerce** PowerShell, è necessario:</span><span class="sxs-lookup"><span data-stu-id="2021e-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="2021e-112">Un dispositivo Windows 10</span><span class="sxs-lookup"><span data-stu-id="2021e-112">A Windows 10 device</span></span>
- <span data-ttu-id="2021e-113">Autorizzazione di amministratore per il dispositivo</span><span class="sxs-lookup"><span data-stu-id="2021e-113">Administrator permission for the device</span></span>
- <span data-ttu-id="2021e-114">Ruolo di amministratore globale o di fatturazione per il tenant</span><span class="sxs-lookup"><span data-stu-id="2021e-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="2021e-115">Installare il modulo MS Commerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="2021e-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="2021e-116">Si installa il **modulo MS Commerce** PowerShell nel dispositivo Windows 10 una sola volta e quindi lo si importa in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="2021e-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="2021e-117">Scaricare il **modulo MSPivot** PowerShell da [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="2021e-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="2021e-118">Per installare il **modulo MS Commerce** PowerShell con **PowerShellGet,** eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="2021e-119">Importare MS Commerce nella sessione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="2021e-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="2021e-120">Dopo aver installato il modulo nel dispositivo Windows 10, importalo in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="2021e-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="2021e-121">Per importarlo in una sessione di PowerShell, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="2021e-122">Connettersi a MS Commerce con le credenziali</span><span class="sxs-lookup"><span data-stu-id="2021e-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="2021e-123">Per connettersi al modulo di PowerShell con le credenziali, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="2021e-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="2021e-124">Questo comando connette la sessione di PowerShell corrente a un tenant di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2021e-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="2021e-125">Il comando richiede un nome utente e una password per il tenant a cui si desidera connettersi.</span><span class="sxs-lookup"><span data-stu-id="2021e-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="2021e-126">Se l'autenticazione a più fattori è abilitata per le credenziali, è possibile utilizzare l'opzione interattiva per accedere.</span><span class="sxs-lookup"><span data-stu-id="2021e-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="2021e-127">Visualizzare i dettagli per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="2021e-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="2021e-128">Per visualizzare una descrizione del valore del parametro **AllowSelfServicePurchase** e dello stato predefinito, in base all'organizzazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="2021e-129">Visualizzare un elenco di prodotti di acquisto self-service e il relativo stato</span><span class="sxs-lookup"><span data-stu-id="2021e-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="2021e-130">Per visualizzare un elenco di tutti i prodotti di acquisto self-service disponibili e lo stato di ognuno di essi, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="2021e-131">Nella tabella seguente sono elencati i prodotti disponibili e il **relativo ProductId.**</span><span class="sxs-lookup"><span data-stu-id="2021e-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="2021e-132">Prodotto</span><span class="sxs-lookup"><span data-stu-id="2021e-132">Product</span></span> | <span data-ttu-id="2021e-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="2021e-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="2021e-134">Power Apps per utente</span><span class="sxs-lookup"><span data-stu-id="2021e-134">Power Apps per user</span></span> | <span data-ttu-id="2021e-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="2021e-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="2021e-136">Power Automate per utente</span><span class="sxs-lookup"><span data-stu-id="2021e-136">Power Automate per user</span></span> | <span data-ttu-id="2021e-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="2021e-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="2021e-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="2021e-138">Power BI Pro</span></span> | <span data-ttu-id="2021e-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="2021e-139">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="2021e-140">Piano di progetto 1</span><span class="sxs-lookup"><span data-stu-id="2021e-140">Project Plan 1</span></span> | <span data-ttu-id="2021e-141">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="2021e-141">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="2021e-142">Piano di progetto 3</span><span class="sxs-lookup"><span data-stu-id="2021e-142">Project Plan 3</span></span> | <span data-ttu-id="2021e-143">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="2021e-143">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="2021e-144">Visio Piano 1</span><span class="sxs-lookup"><span data-stu-id="2021e-144">Visio Plan 1</span></span> | <span data-ttu-id="2021e-145">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="2021e-145">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="2021e-146">Visio Piano 2</span><span class="sxs-lookup"><span data-stu-id="2021e-146">Visio Plan 2</span></span> | <span data-ttu-id="2021e-147">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="2021e-147">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="2021e-148">Visualizzare o impostare lo stato per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="2021e-148">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="2021e-149">Dopo aver visualizzato l'elenco dei prodotti disponibili per l'acquisto self-service, è possibile visualizzare o modificare l'impostazione di un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="2021e-149">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="2021e-150">Per ottenere l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-150">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="2021e-151">Per abilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-151">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="2021e-152">Per disabilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-152">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="2021e-153">Script di esempio per disabilitare AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="2021e-153">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="2021e-154">L'esempio seguente illustra come importare il modulo **MS Commerce,** accedere con il proprio account, ottenere **il ProductId** per Power Automate e quindi **disabilitare AllowSelfServicePurchase** per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="2021e-154">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="2021e-155">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="2021e-155">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="2021e-156">Problema</span><span class="sxs-lookup"><span data-stu-id="2021e-156">Problem</span></span>

<span data-ttu-id="2021e-157">Viene visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="2021e-157">You see the following error message:</span></span>

> <span data-ttu-id="2021e-158">HandleError: impossibile recuperare il criterio con PolicyId 'AllowSelfServicePurchase', ErrorMessage - La connessione sottostante è stata chiusa: si è verificato un errore imprevisto durante un invio.</span><span class="sxs-lookup"><span data-stu-id="2021e-158">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="2021e-159">Ciò potrebbe essere dovuto a una versione precedente di Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="2021e-159">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="2021e-160">Per connettere questo servizio, è necessario utilizzare TLS 1.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="2021e-160">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="2021e-161">Soluzione</span><span class="sxs-lookup"><span data-stu-id="2021e-161">Solution</span></span>

<span data-ttu-id="2021e-162">Eseguire l'aggiornamento a TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="2021e-162">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
