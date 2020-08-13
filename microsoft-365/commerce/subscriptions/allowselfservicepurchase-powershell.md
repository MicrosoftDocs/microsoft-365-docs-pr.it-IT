---
title: Utilizzo di AllowSelfServicePurchase per il modulo di PowerShell di MSCommerce
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
description: Informazioni su come utilizzare il cmdlet di AllowSelfServicePurchase PowerShell per abilitare o disabilitare l'acquisto in modalità self-service.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653714"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Utilizzo di AllowSelfServicePurchase per il modulo di PowerShell di MSCommerce

Il modulo di **MSCommerce** PowerShell è ora disponibile nella [raccolta di PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery). Il modulo include un valore del parametro **PolicyId** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.

È possibile utilizzare il modulo di **MSCommerce** PowerShell per:

- Visualizzare lo stato predefinito del valore del parametro **AllowSelfServicePurchase** , ovvero se è abilitato o disabilitato
- Visualizzare un elenco di prodotti applicabili e se l'acquisto in modalità self-service è abilitato o disabilitato
- Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarlo o disabilitarlo

## <a name="requirements"></a>Requisiti

Per utilizzare il modulo di **MSCommerce** PowerShell, è necessario eseguire le operazioni seguenti:

- Un dispositivo Windows 10
- Autorizzazione di amministratore per il dispositivo
- Ruolo di amministratore globale o di fatturazione per il tenant

## <a name="install-the-mscommerce-powershell-module"></a>Installare il modulo di MSCommerce PowerShell

Installare il modulo di **MSCommerce** PowerShell nel dispositivo Windows 10 una volta e quindi importarlo in ogni sessione di PowerShell che si avvia. Scaricare il modulo di **MSCommerce** PowerShell dalla [raccolta di PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Per installare il modulo di **MSCommerce** PowerShell con **PowerShellGet**, eseguire il comando riportato di seguito:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importare MSCommerce nella sessione di PowerShell

Dopo aver installato il modulo nel dispositivo Windows 10, importarlo in ogni sessione di PowerShell avviata. Per importarlo in una sessione di PowerShell, eseguire il comando riportato di seguito:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Connettersi a MSCommerce con le proprie credenziali

Per connettersi al modulo di PowerShell con le credenziali, eseguire il comando riportato di seguito.

```powershell
Connect-MSCommerce
```

Questo comando connette la sessione corrente di PowerShell a un tenant di Azure Active Directory. Il comando richiede un nome utente e una password per il tenant a cui si desidera effettuare la connessione. Se è abilitata l'autenticazione a più fattori per le proprie credenziali, è possibile utilizzare l'opzione Interactive per eseguire l'accesso.

## <a name="view-details-for-allowselfservicepurchase"></a>Visualizzare i dettagli per AllowSelfServicePurchase

Per visualizzare una descrizione del valore del parametro **AllowSelfServicePurchase** e lo stato predefinito, in base all'organizzazione, eseguire il comando riportato di seguito:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Visualizzare un elenco di prodotti per l'acquisto in modalità self-service e il relativo stato

Per visualizzare un elenco di tutti i prodotti di acquisto self-service disponibili e lo stato di ogni, eseguire il comando riportato di seguito:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

Nella tabella seguente sono elencati i prodotti disponibili e il relativo **ProductID**.

| Prodotto | ProductId |
|-----------------------------|--------------|
| Power Apps per utente | CFQ7TTC0KP0P |
| Automatizzare l'alimentazione per utente | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| Piano del progetto 1 | CFQ7TTC0KXND |
| Piano di progetto 3 | CFQ7TTC0KXNC |
| Visio piano 1 | CFQ7TTC0KXN9 |
| Visio piano 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Visualizzare o impostare lo stato di AllowSelfServicePurchase

Dopo aver visualizzato l'elenco dei prodotti disponibili per l'acquisto in modalità self-service, è possibile visualizzare o modificare l'impostazione di un prodotto specifico.

Per ottenere l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Per abilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Per disabilitare l'impostazione dei criteri per un prodotto specifico, eseguire il comando riportato di seguito:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Script di esempio per disabilitare AllowSelfServicePurchase

Nell'esempio seguente viene illustrato come importare il modulo **MSCommerce** , accedere con l'account, ottenere il **ProductID** per automatizzare l'alimentazione e quindi disabilitare **AllowSelfServicePurchase** per il prodotto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Risoluzione dei problemi

### <a name="problem"></a>Problema

Viene visualizzato il messaggio di errore seguente:

> HandleError: failed to retrieve Policy with PolicyId ' AllowSelfServicePurchase ', ErrorMessage-la connessione sottostante è stata chiusa: si è verificato un errore imprevisto su un invio.

Questo può essere dovuto a una versione precedente di TLS (Transport Layer Security). Per connettere questo servizio è necessario utilizzare TLS 1,2 o versione successiva

### <a name="solution"></a>Soluzione

Eseguire l'aggiornamento a TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
