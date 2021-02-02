---
title: Utilizzare un codice QR per accedere alle app outlook per dispositivi mobili
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
description: Informazioni su come utilizzare un codice QR per autenticare e scaricare Outlook Mobile.
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050775"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Utilizzare un codice QR per accedere alle app outlook per dispositivi mobili

> [!IMPORTANT]
> Questa funzionalità di Microsoft 365 è in anteprima pubblica. L'anteprima pubblica consente l'accesso anticipato alle funzionalità di Microsoft 365.

L'amministratore di Microsoft 365 può consentire agli utenti di accedere a Outlook per Android o app iOS nei dispositivi mobili senza dover immettere nome utente e password. L'analisi di un codice QR consente agli utenti di autenticarsi e accedere in modo sicuro a Outlook Mobile.

In Outlook sul Web o in altre applicazioni desktop di Outlook, gli utenti possono visualizzare notifiche che informano che possono utilizzare Outlook sul dispositivo mobile. Queste notifiche possono essere gestite dall'amministratore tramite Exchange PowerShell. Se gli utenti scelgono di inviare a se stessi un SMS per scaricare l'app sul dispositivo mobile, sul computer verrà visualizzato un codice QR. Saranno in grado di analizzare il codice QR per accedere a Outlook sul proprio telefono o tablet. Questo codice QR è un token di breve durata che può essere riscattato una sola volta.

> [!NOTE]
> In alcuni casi, gli utenti doranno eseguire nuovamente l'autenticazione nel proprio computer per generare il codice QR.

## <a name="use-exchange-powershell"></a>Utilizzare Exchange PowerShell

Questa esperienza è disponibile per impostazione predefinita. Per disabilitare questa funzionalità, eseguire la procedura seguente.

1. [Connettersi a Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Utilizzando PowerShell, è possibile disabilitare le notifiche che informano gli utenti sulle app outlook per dispositivi mobili. In questo modo si impedisce anche la visualizzazione del flusso di accesso del codice QR.

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

Argomenti correlati

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)