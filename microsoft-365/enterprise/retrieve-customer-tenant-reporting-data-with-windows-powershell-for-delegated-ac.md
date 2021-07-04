---
title: Recuperare i dati dei report dei tenant dei clienti con Windows PowerShell per i partner DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Riepilogo: Usare Windows PowerShell remoto di Microsoft Exchange Online per recuperare i report dei tenant di un singolo cliente.'
ms.openlocfilehash: 8a244e1178e64d27d5e0f061d094dccd39bb8275
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290076"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Recuperare i dati di report dei tenant dei clienti con Windows PowerShell per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Usare le Windows PowerShell remote per Microsoft Exchange Online per recuperare i report dai tenant dei singoli clienti.

I partner di syndication e Cloud Solution Provider (CSP) possono accedere ai dati che costituisce i report del tenant dei clienti direttamente tramite Windows PowerShell remoto per Exchange Online PowerShell. Ciò consente ai partner di raccogliere e salvare i dati di report, per poi eseguire operazioni su di essi. Dopo avere aperto una connessione remota, il recupero dei dati di report relativi al tenancy di un cliente è identico all'esecuzione di qualsiasi cmdlet per il tenancy di un cliente.

In questo articolo si utilizza l'Windows PowerShell per Exchange Online per connettersi a una tenancy di un singolo cliente e recuperare un report. Per impostazione predefinita, Windows PowerShell non supporta l'aggregazione dei dati di report dai tenancy di più clienti. I report recuperati con questa procedura sono solo per il  _DelegatedOrg_ al quale ci si connette.

## <a name="before-you-begin"></a>Prima di iniziare

- È necessario connettersi al tenant Exchange Online tramite Windows PowerShell remoto. Per istruzioni, vedere [Connettersi ai tenant Exchange Online con Windows PowerShell remoto per i partner di autorizzazione accesso delegato (DAP, Delegated Access Permission)](/powershell/exchange/connect-to-exchange-online-powershell)

## <a name="run-the-get-stalemailboxreport-sample"></a>Eseguire il cmdlet di esempio Get-StaleMailboxReport

Dopo avere aperto una sessione remota in Exchange Online, eseguire questo comando per recuperare il cmdlet **Get-StaleMailboxReport** per l'intervallo di date compreso tra il 25/03/2015 e il 31/03/2015.

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

Sono disponibili molti altri cmdlet di report per Exchange Online, Lync Online e SharePoint Online, e altri per il controllo dei messaggi. Per ulteriori informazioni sui cmdlet di report disponibili e sul servizio Web per la creazione di report di Office 365, vedere gli argomenti riportati nella sezione seguente.

## <a name="see-also"></a>Vedere anche

[Servizio Web per la creazione di report di Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))

[Cmdlet per la creazione di report in Exchange Online](/powershell/module/exchange/get-csclientdevicedetailreport)

[Guida per partner](https://go.microsoft.com/fwlink/p/?LinkID=533477)
