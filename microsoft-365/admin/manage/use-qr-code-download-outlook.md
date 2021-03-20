---
title: Usare un codice QR per accedere alle app outlook per dispositivi mobili
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
description: Informazioni su come utilizzare un codice QR per autenticare e scaricare Outlook mobile.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914967"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usare un codice QR per accedere alle app outlook per dispositivi mobili

> [!IMPORTANT]
> Questa funzionalità è disponibile solo per le organizzazioni che hanno attivato Rilascio mirato nell'interfaccia di amministrazione di Microsoft 365. Per attivare rilascio mirato e altre informazioni su come funziona, vedi Configurare le opzioni di rilascio [Standard o Mirato.](release-options-in-office-365.md) L'anteprima pubblica verrà espansa a più organizzazioni nelle prossime settimane. L'anteprima pubblica consente l'accesso anticipato alle funzionalità di Microsoft 365.

L'amministratore di Microsoft 365 può consentire agli utenti di accedere all'app Outlook per Android o iOS nei propri dispositivi mobili senza dover immettere il nome utente e la password. Tramite l'analisi di un codice QR, gli utenti possono autenticarsi e accedere in modo sicuro a Outlook mobile.

In Outlook sul Web o in altre applicazioni desktop di Outlook, gli utenti possono visualizzare notifiche che informano che possono utilizzare Outlook sul proprio dispositivo mobile. Queste notifiche possono essere gestite dall'amministratore tramite PowerShell di Exchange. Se gli utenti scelgono di inviare un SMS per scaricare l'app sul dispositivo mobile, sul computer verrà visualizzato un codice QR. Saranno in grado di analizzare il codice QR per accedere a Outlook sul proprio telefono o tablet. Questo codice QR è un token di breve durata che può essere riscattato una sola volta.

> [!NOTE]
> In alcuni casi, gli utenti doranno eseguire di nuovo l'autenticazione nel computer per generare il codice QR.

## <a name="use-exchange-powershell"></a>Utilizzare PowerShell di Exchange

Questa funzionalità è attivata per impostazione predefinita. Per disabilitare questa funzionalità, eseguire la procedura seguente.

1. [Connettersi a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. Utilizzando PowerShell, è possibile disabilitare le notifiche che informano gli utenti sulle app outlook per dispositivi mobili. Questo impedirà anche la visualizzazione del flusso di accesso del codice QR.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Argomenti correlati

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)