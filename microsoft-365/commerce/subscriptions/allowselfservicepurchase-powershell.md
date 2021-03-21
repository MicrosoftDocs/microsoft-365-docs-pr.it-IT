---
title: Usare AllowSelfServicePurchase per il modulo di PowerShell MSCommerce
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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Informazioni su come usare il cmdlet Di PowerShell AllowSelfServicePurchase per attivare o disattivare l'acquisto in modalità self-service.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9fb5593855f9523198a3d70548e444a831e82c80
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918243"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Usare AllowSelfServicePurchase per il modulo di PowerShell MSCommerce

Il **modulo MSCommerce** PowerShell è ora disponibile in [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery) Il modulo include un valore del parametro **PolicyID** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.

È possibile utilizzare il **modulo ms-Commerce** PowerShell per:

- Visualizzare lo stato predefinito del **valore del parametro AllowSelfServicePurchase,** indipendentemente dal fatto che sia abilitato o disabilitato
- Visualizzare un elenco dei prodotti applicabili e se l'acquisto in self-service è abilitato o disabilitato
- Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarla o disabilitarla

## <a name="requirements"></a>Requisiti

Per usare il **modulo ms-Commerce** PowerShell, è necessario:

- Un dispositivo Windows 10
- Autorizzazione di amministratore per il dispositivo
- Ruolo amministratore globale o fatturazione per il tenant

## <a name="install-the-mscommerce-powershell-module"></a>Installare il modulo ms-Commerce PowerShell

Il modulo **MSCommerce** PowerShell viene installato nel dispositivo Windows 10 una sola volta e quindi importato in ogni sessione di PowerShell avviata. Scaricare il **modulo MSCommerce** PowerShell da [PowerShell Gallery.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Per installare il **modulo ms-Commerce** PowerShell con **PowerShellGet,** eseguire il comando seguente:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importare MSCommerce nella sessione di PowerShell

Dopo aver installato il modulo nel dispositivo Windows 10, importalo in ogni sessione di PowerShell avviata. Per importarlo in una sessione di PowerShell, eseguire il comando seguente:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Connettersi a MSCommerce con le credenziali

Per connettersi al modulo di PowerShell con le credenziali, eseguire il comando seguente.

```powershell
Connect-MSCommerce
```

Questo comando connette la sessione di PowerShell corrente a un tenant di Azure Active Directory. Il comando richiede un nome utente e una password per il tenant a cui si desidera connettersi. Se per le credenziali è abilitata l'autenticazione a più fattori, si utilizza l'opzione interattiva per accedere.

## <a name="view-details-for-allowselfservicepurchase"></a>Visualizzare i dettagli per AllowSelfServicePurchase

Per visualizzare una descrizione del valore del parametro **AllowSelfServicePurchase** e dello stato predefinito, in base all'organizzazione, eseguire il comando seguente:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Visualizzare un elenco di prodotti di acquisto self-service e il relativo stato

Per visualizzare un elenco di tutti i prodotti di acquisto self-service disponibili e lo stato di ognuno di essi, eseguire il comando seguente:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

Nella tabella seguente sono elencati i prodotti disponibili e il **relativo ProductId.**

| Prodotto | ProductId |
|-----------------------------|--------------|
| Power Apps per utente | CFQ7TTC0KP0P |
| Power Automate per utente | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (autonomo) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Piano di progetto 1 | CFQ7TTC0KXND |
| Piano di progetto 3 | CFQ7TTC0KXNC |
| Visio Piano 1 | CFQ7TTC0KXN9 |
| Visio Piano 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Visualizzare o impostare lo stato per AllowSelfServicePurchase

Dopo aver visualizzato l'elenco dei prodotti disponibili per l'acquisto in self-service, è possibile visualizzare o modificare l'impostazione per un prodotto specifico.

Per ottenere l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Per abilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Per disabilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando seguente:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Script di esempio per disabilitare AllowSelfServicePurchase

L'esempio seguente illustra come importare il modulo **MS Commerce,** accedere con l'account, ottenere **ProductId** per Power Automate e quindi **disabilitare AllowSelfServicePurchase** per il prodotto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="problem"></a>Problema

Viene visualizzato il seguente messaggio di errore:

> HandleError: impossibile recuperare i criteri con PolicyId 'AllowSelfServicePurchase', ErrorMessage - La connessione sottostante è stata chiusa: si è verificato un errore imprevisto durante un invio.

Ciò potrebbe essere dovuto a una versione precedente di Transport Layer Security (TLS). Per connettere questo servizio, è necessario utilizzare TLS 1.2 o versione successiva

### <a name="solution"></a>Soluzione

Eseguire l'aggiornamento a TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->