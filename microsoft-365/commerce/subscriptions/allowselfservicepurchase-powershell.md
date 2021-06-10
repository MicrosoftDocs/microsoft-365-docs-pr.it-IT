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
ms.openlocfilehash: 012874a8794e006d97c4f74014e92e1f7f3c2709
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536131"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="a77a1-103">Usare AllowSelfServicePurchase per il modulo di PowerShell MSCommerce</span><span class="sxs-lookup"><span data-stu-id="a77a1-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="a77a1-104">Il **modulo MSCommerce** PowerShell è ora disponibile in [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="a77a1-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="a77a1-105">Il modulo include un valore del parametro **PolicyID** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="a77a1-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="a77a1-106">È possibile utilizzare il **modulo ms-Commerce** PowerShell per:</span><span class="sxs-lookup"><span data-stu-id="a77a1-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="a77a1-107">Visualizzare lo stato predefinito del **valore del parametro AllowSelfServicePurchase,** indipendentemente dal fatto che sia abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="a77a1-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="a77a1-108">Visualizzare un elenco dei prodotti applicabili e se l'acquisto in self-service è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="a77a1-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="a77a1-109">Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarla o disabilitarla</span><span class="sxs-lookup"><span data-stu-id="a77a1-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="a77a1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a77a1-110">Requirements</span></span>

<span data-ttu-id="a77a1-111">Per usare il **modulo ms-Commerce** PowerShell, è necessario:</span><span class="sxs-lookup"><span data-stu-id="a77a1-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="a77a1-112">Un Windows 10 dispositivo</span><span class="sxs-lookup"><span data-stu-id="a77a1-112">A Windows 10 device</span></span>
- <span data-ttu-id="a77a1-113">PowerShell 5 o versioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a77a1-113">PowerShell 5 or below.</span></span> <span data-ttu-id="a77a1-114">Attualmente, PowerShell 6.x/7.x non è supportato con questo modulo.</span><span class="sxs-lookup"><span data-stu-id="a77a1-114">Currently, PowerShell 6.x/7.x isn't supported with this module.</span></span>
- <span data-ttu-id="a77a1-115">Autorizzazione di amministratore per il dispositivo</span><span class="sxs-lookup"><span data-stu-id="a77a1-115">Administrator permission for the device</span></span>
- <span data-ttu-id="a77a1-116">Ruolo amministratore globale o fatturazione per il tenant</span><span class="sxs-lookup"><span data-stu-id="a77a1-116">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="a77a1-117">Installare il modulo ms-Commerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="a77a1-117">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="a77a1-118">Il modulo **MSCommerce** PowerShell viene installato nel dispositivo Windows 10 una sola volta e quindi importato in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="a77a1-118">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="a77a1-119">Scaricare il **modulo MSCommerce** PowerShell da [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="a77a1-119">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="a77a1-120">Per installare il **modulo ms-Commerce** PowerShell con **PowerShellGet,** eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a77a1-120">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="a77a1-121">Importare MSCommerce nella sessione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="a77a1-121">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="a77a1-122">Dopo aver installato il modulo nel dispositivo Windows 10, importarlo in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="a77a1-122">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="a77a1-123">Per importarlo in una sessione di PowerShell, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a77a1-123">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="a77a1-124">Connessione a MSCommerce con le credenziali</span><span class="sxs-lookup"><span data-stu-id="a77a1-124">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="a77a1-125">Per connettersi al modulo di PowerShell con le credenziali, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="a77a1-125">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="a77a1-126">Questo comando connette la sessione di PowerShell corrente a un tenant Azure Active Directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a77a1-126">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="a77a1-127">Il comando richiede un nome utente e una password per il tenant a cui si desidera connettersi.</span><span class="sxs-lookup"><span data-stu-id="a77a1-127">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="a77a1-128">Se per le credenziali è abilitata l'autenticazione a più fattori, si utilizza l'opzione interattiva per accedere.</span><span class="sxs-lookup"><span data-stu-id="a77a1-128">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="a77a1-129">Visualizzare i dettagli per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="a77a1-129">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="a77a1-130">Per visualizzare una descrizione del valore del parametro **AllowSelfServicePurchase** e dello stato predefinito, in base all'organizzazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a77a1-130">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="a77a1-131">Visualizzare un elenco di prodotti di acquisto self-service e il relativo stato</span><span class="sxs-lookup"><span data-stu-id="a77a1-131">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="a77a1-132">Per visualizzare un elenco di tutti i prodotti di acquisto self-service disponibili e lo stato di ognuno di essi, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a77a1-132">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="a77a1-133">Nella tabella seguente sono elencati i prodotti disponibili e il **relativo ProductId.**</span><span class="sxs-lookup"><span data-stu-id="a77a1-133">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="a77a1-134">Prodotto</span><span class="sxs-lookup"><span data-stu-id="a77a1-134">Product</span></span> | <span data-ttu-id="a77a1-135">ProductId</span><span class="sxs-lookup"><span data-stu-id="a77a1-135">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="a77a1-136">Power Apps per utente</span><span class="sxs-lookup"><span data-stu-id="a77a1-136">Power Apps per user</span></span> | <span data-ttu-id="a77a1-137">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="a77a1-137">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="a77a1-138">Power Automate per utente</span><span class="sxs-lookup"><span data-stu-id="a77a1-138">Power Automate per user</span></span> | <span data-ttu-id="a77a1-139">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="a77a1-139">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="a77a1-140">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="a77a1-140">Power Automate RPA</span></span> | <span data-ttu-id="a77a1-141">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="a77a1-141">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="a77a1-142">Power BI Premium (autonomo)</span><span class="sxs-lookup"><span data-stu-id="a77a1-142">Power BI Premium (standalone)</span></span> | <span data-ttu-id="a77a1-143">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="a77a1-143">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="a77a1-144">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="a77a1-144">Power BI Pro</span></span> | <span data-ttu-id="a77a1-145">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="a77a1-145">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="a77a1-146">Project - Piano 1</span><span class="sxs-lookup"><span data-stu-id="a77a1-146">Project Plan 1</span></span> | <span data-ttu-id="a77a1-147">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="a77a1-147">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="a77a1-148">Project - Piano 3</span><span class="sxs-lookup"><span data-stu-id="a77a1-148">Project Plan 3</span></span> | <span data-ttu-id="a77a1-149">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="a77a1-149">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="a77a1-150">Visio - Piano 1</span><span class="sxs-lookup"><span data-stu-id="a77a1-150">Visio Plan 1</span></span> | <span data-ttu-id="a77a1-151">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="a77a1-151">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="a77a1-152">Visio - Piano 2</span><span class="sxs-lookup"><span data-stu-id="a77a1-152">Visio Plan 2</span></span> | <span data-ttu-id="a77a1-153">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="a77a1-153">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="a77a1-154">Visualizzare o impostare lo stato per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="a77a1-154">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="a77a1-155">Dopo aver visualizzato l'elenco dei prodotti disponibili per l'acquisto in self-service, è possibile visualizzare o modificare l'impostazione per un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="a77a1-155">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="a77a1-156">Per ottenere l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a77a1-156">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="a77a1-157">Per abilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a77a1-157">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="a77a1-158">Per disabilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a77a1-158">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="a77a1-159">Script di esempio per disabilitare AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="a77a1-159">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="a77a1-160">L'esempio seguente illustra come importare il modulo **MS Commerce,** accedere con l'account, ottenere **ProductId** per Power Automate e quindi **disabilitare AllowSelfServicePurchase** per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="a77a1-160">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="a77a1-161">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a77a1-161">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="a77a1-162">Problema</span><span class="sxs-lookup"><span data-stu-id="a77a1-162">Problem</span></span>

<span data-ttu-id="a77a1-163">Viene visualizzato il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="a77a1-163">You see the following error message:</span></span>

> <span data-ttu-id="a77a1-164">HandleError: impossibile recuperare i criteri con PolicyId 'AllowSelfServicePurchase', ErrorMessage - La connessione sottostante è stata chiusa: si è verificato un errore imprevisto durante un invio.</span><span class="sxs-lookup"><span data-stu-id="a77a1-164">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="a77a1-165">Ciò potrebbe essere dovuto a una versione precedente di Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="a77a1-165">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="a77a1-166">Per connettere questo servizio, è necessario utilizzare TLS 1.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="a77a1-166">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="a77a1-167">Soluzione</span><span class="sxs-lookup"><span data-stu-id="a77a1-167">Solution</span></span>

<span data-ttu-id="a77a1-168">Eseguire l'aggiornamento a TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="a77a1-168">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a><span data-ttu-id="a77a1-169">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="a77a1-169">Related content</span></span>

<span data-ttu-id="a77a1-170">[Gestire gli acquisti in modalità self-service (amministratore)](manage-self-service-purchases-admins.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="a77a1-170">[Manage self-service purchases (Admin)](manage-self-service-purchases-admins.md) (article)</span></span>

<span data-ttu-id="a77a1-171">[Domande frequenti sull'acquisto in self-service](self-service-purchase-faq.yml) (articolo)</span><span class="sxs-lookup"><span data-stu-id="a77a1-171">[Self-service purchase FAQ](self-service-purchase-faq.yml) (article)</span></span>