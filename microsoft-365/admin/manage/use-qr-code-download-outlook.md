---
title: Usare un codice QR per accedere alle app Outlook mobili
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
- AdminTemplateSet
description: Scopri come usare un codice QR per autenticare e scaricare Outlook mobile.
ms.openlocfilehash: c13fbeabd320c64925165ba16797d5a3471961ad
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53391340"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usare un codice QR per accedere alle app Outlook mobili

> [!IMPORTANT]
> Questa funzionalità è disponibile solo per le organizzazioni che hanno attivato Rilascio mirato nel interfaccia di amministrazione di Microsoft 365. Per attivare rilascio mirato e altre informazioni su come funziona, vedi Configurare le opzioni di rilascio [Standard o Mirato.](release-options-in-office-365.md) L'anteprima pubblica verrà espansa a più organizzazioni nelle prossime settimane. L'anteprima pubblica consente l'accesso Microsoft 365 funzionalità.

In quanto amministratore Microsoft 365, puoi consentire agli utenti di accedere a Outlook per l'app Android o iOS nei dispositivi mobili senza dover immettere nome utente e password. Tramite l'analisi di un codice QR, gli utenti possono autenticarsi e accedere in modo sicuro Outlook mobile.

In Outlook sul web o in altre applicazioni Outlook desktop, gli utenti possono visualizzare notifiche che informano gli utenti che possono usare Outlook sul dispositivo mobile. Queste notifiche possono essere gestite dall'amministratore tramite Exchange PowerShell. Se gli utenti scelgono di inviare un SMS per scaricare l'app sul dispositivo mobile, sul computer verrà visualizzato un codice QR. Saranno in grado di analizzare il codice QR per accedere Outlook sul proprio telefono o tablet. Questo codice QR è un token di breve durata che può essere riscattato una sola volta.

> [!NOTE]
> In alcuni casi, gli utenti devono eseguire nuovamente l'autenticazione nel computer per generare il codice QR.

## <a name="use-exchange-powershell"></a>Usare Exchange PowerShell

Questa funzionalità è attivata per impostazione predefinita. Per disabilitare questa funzionalità, eseguire la procedura seguente.

1. [Connessione a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
2. Usando PowerShell, è possibile disabilitare le notifiche che informano gli utenti sulle Outlook per dispositivi mobili. In questo modo si impedisce anche la visualizzazione del flusso di accesso del codice QR.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>Contenuto correlato

[Configurare le opzioni di rilascio Standard o Mirato](release-options-in-office-365.md) (articolo)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (articolo)