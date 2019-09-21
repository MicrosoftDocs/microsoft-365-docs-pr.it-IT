---
title: Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Una breve descrizione di cosa devono fare gli amministratori di Exchange Online per visualizzare e configurare le impostazioni S/MIME in Outlook sul Web in Exchange Online.
ms.openlocfilehash: 6e390e377369dc0de73d5e063a6a21fd549c3bef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084731"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web

In qualità di amministratore di Exchange Online, è possibile configurare Outlook sul Web (in precedenza noto come Outlook Web App) per consentire l'invio e la ricezione di messaggi protetti con S/MIME. Utilizzare i cmdlet **Get-SmimeConfig** e **set-SmimeConfig** per visualizzare e gestire questa funzionalità in PowerShell di Exchange Online. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) e [set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).

## <a name="considerations-for-chrome"></a>Considerazioni su Chrome

Per utilizzare S/MIME in Outlook sul Web nel browser Web di Google Chrome, è necessario che l'utente (o un altro amministratore) debba impostare e configurare il criterio di cromo denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME in Chrome. Il valore del criterio `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`è. Si noti che l'applicazione di questo criterio richiede i computer aggiunti a un dominio, in modo che l'utilizzo di S/MIME in Chrome richiede effettivamente i computer aggiunti a un dominio.

Per informazioni dettagliate sul criterio **ExtensionInstallForcelist** , vedere [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).

Questo passaggio è un prerequisito per l'utilizzo di Chrome. non sostituisce il controllo S/MIME installato dagli utenti. Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME. In alternativa, gli utenti possono accedere in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.

## <a name="for-more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)
