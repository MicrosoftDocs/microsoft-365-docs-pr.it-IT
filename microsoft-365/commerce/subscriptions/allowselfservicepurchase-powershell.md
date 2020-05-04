---
title: Utilizzo di AllowSelfServicePurchase per il modulo di PowerShell di MSCommerce
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 6c0bcec70eab4266674ca2a22f1b2054807a26e8
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011676"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="6c4e7-103">Utilizzo di AllowSelfServicePurchase per il modulo di PowerShell di MSCommerce</span><span class="sxs-lookup"><span data-stu-id="6c4e7-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="6c4e7-104">Il modulo di **MSCommerce** PowerShell è ora disponibile nella [raccolta di PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="6c4e7-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="6c4e7-105">Il modulo include un valore del parametro **PolicyId** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="6c4e7-106">È possibile utilizzare il modulo di **MSCommerce** PowerShell per:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="6c4e7-107">Visualizzare lo stato predefinito del valore del parametro **AllowSelfServicePurchase** , ovvero se è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="6c4e7-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="6c4e7-108">Visualizzare un elenco di prodotti applicabili e se l'acquisto in modalità self-service è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="6c4e7-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="6c4e7-109">Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarlo o disabilitarlo</span><span class="sxs-lookup"><span data-stu-id="6c4e7-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="6c4e7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c4e7-110">Requirements</span></span>

<span data-ttu-id="6c4e7-111">Per utilizzare il modulo di **MSCommerce** PowerShell, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="6c4e7-112">Un dispositivo Windows 10</span><span class="sxs-lookup"><span data-stu-id="6c4e7-112">A Windows 10 device</span></span>
- <span data-ttu-id="6c4e7-113">Autorizzazione di amministratore per il dispositivo</span><span class="sxs-lookup"><span data-stu-id="6c4e7-113">Administrator permission for the device</span></span>
- <span data-ttu-id="6c4e7-114">Ruolo di amministratore globale o di fatturazione per il tenant</span><span class="sxs-lookup"><span data-stu-id="6c4e7-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="6c4e7-115">Installare il modulo di MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c4e7-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="6c4e7-116">Installare il modulo di **MSCommerce** PowerShell nel dispositivo Windows 10 una volta e quindi importarlo in ogni sessione di PowerShell che si avvia.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="6c4e7-117">Scaricare il modulo di **MSCommerce** PowerShell dalla [raccolta di PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="6c4e7-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="6c4e7-118">Per installare il modulo di **MSCommerce** PowerShell con **PowerShellGet**, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="6c4e7-119">Importare MSCommerce nella sessione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c4e7-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="6c4e7-120">Dopo aver installato il modulo nel dispositivo Windows 10, importarlo in ogni sessione di PowerShell avviata.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="6c4e7-121">Per importarlo in una sessione di PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="6c4e7-122">Connettersi a MSCommerce con le proprie credenziali</span><span class="sxs-lookup"><span data-stu-id="6c4e7-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="6c4e7-123">Per connettersi al modulo di PowerShell con le credenziali, eseguire il comando riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="6c4e7-124">Questo comando connette la sessione corrente di PowerShell a un tenant di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="6c4e7-125">Il comando richiede un nome utente e una password per il tenant a cui si desidera effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="6c4e7-126">Se è abilitata l'autenticazione a più fattori per le proprie credenziali, è possibile utilizzare l'opzione Interactive per eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="6c4e7-127">Visualizzare i dettagli per AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="6c4e7-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="6c4e7-128">Per visualizzare una descrizione del valore del parametro **AllowSelfServicePurchase** e lo stato predefinito, in base all'organizzazione, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="6c4e7-129">Visualizzare un elenco di prodotti per l'acquisto in modalità self-service e il relativo stato</span><span class="sxs-lookup"><span data-stu-id="6c4e7-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="6c4e7-130">Per visualizzare un elenco di tutti i prodotti di acquisto self-service disponibili e lo stato di ogni, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="6c4e7-131">Nella tabella seguente sono elencati i prodotti disponibili e il relativo **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="6c4e7-132">Prodotto</span><span class="sxs-lookup"><span data-stu-id="6c4e7-132">Product</span></span> | <span data-ttu-id="6c4e7-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="6c4e7-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="6c4e7-134">Power Apps per utente</span><span class="sxs-lookup"><span data-stu-id="6c4e7-134">Power Apps per user</span></span> | <span data-ttu-id="6c4e7-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="6c4e7-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="6c4e7-136">Automatizzare l'alimentazione per utente</span><span class="sxs-lookup"><span data-stu-id="6c4e7-136">Power Automate per user</span></span> | <span data-ttu-id="6c4e7-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="6c4e7-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="6c4e7-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="6c4e7-138">Power BI Pro</span></span> | <span data-ttu-id="6c4e7-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="6c4e7-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="6c4e7-140">Visualizzare o impostare lo stato di AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="6c4e7-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="6c4e7-141">Dopo aver visualizzato l'elenco dei prodotti disponibili per l'acquisto in modalità self-service, è possibile visualizzare o modificare l'impostazione di un prodotto specifico.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="6c4e7-142">Per ottenere l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="6c4e7-143">Per abilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="6c4e7-144">Per disabilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="6c4e7-145">Script di esempio per disabilitare AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="6c4e7-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="6c4e7-146">Nell'esempio seguente viene illustrato come importare il modulo **MSCommerce** , accedere con l'account, ottenere il **ProductID** per automatizzare l'alimentazione e quindi disabilitare **AllowSelfServicePurchase** per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="6c4e7-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="6c4e7-147">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="6c4e7-147">Troubleshooting</span></span>

<span data-ttu-id="6c4e7-148">**Problema**</span><span class="sxs-lookup"><span data-stu-id="6c4e7-148">**Problem**</span></span>

<span data-ttu-id="6c4e7-149">Viene visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="6c4e7-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="6c4e7-150">Questo può essere dovuto a una versione precedente di TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="6c4e7-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="6c4e7-151">Per connettere questo servizio è necessario utilizzare TLS 1,2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="6c4e7-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="6c4e7-152">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="6c4e7-152">**Solution**</span></span>

<span data-ttu-id="6c4e7-153">Eseguire l'aggiornamento a TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="6c4e7-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
