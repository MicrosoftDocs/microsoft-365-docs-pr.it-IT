---
title: Configurare le impostazioni S/MIME-Exchange Online per Outlook sul Web
f1.keywords:
- NOCSH
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9f4e6c33369640ad66956568959dd02b01c4fb9
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517486"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web

In qualità di amministratore di Exchange Online, è possibile configurare Outlook sul Web (in precedenza noto come Outlook Web App) per consentire l'invio e la ricezione di messaggi protetti con S/MIME. Utilizzare i cmdlet **Get-SmimeConfig** e **set-SmimeConfig** per visualizzare e gestire questa funzionalità in PowerShell di Exchange Online. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) e [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Considerazioni per il nuovo Edge Microsoft (basato sul cromo)

Per utilizzare S/MIME in Outlook sul Web nel nuovo Web browser [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , l'utente (o un altro amministratore) deve impostare e configurare il criterio del browser Microsoft Edge denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME nel nuovo Microsoft Edge. Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Si noti che l'applicazione di questo criterio richiede l'aggiunta di un dominio o di un dispositivo di Azure AD-join, in modo che l'utilizzo di S/MIME nel nuovo browser Microsoft Edge richieda effettivamente i dispositivi associati a un dominio o di Azure AD.

Per informazioni dettagliate sul criterio **ExtensionInstallForcelist** , vedere [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Questo passaggio è un prerequisito per l'utilizzo di nuovo Microsoft Edge. non sostituisce il controllo S/MIME installato dagli utenti. Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME. In alternativa, gli utenti possono accedere in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.

## <a name="considerations-for-chrome"></a>Considerazioni su Chrome

Per utilizzare S/MIME in Outlook sul Web nel browser Web di Google Chrome, è necessario che l'utente (o un altro amministratore) debba impostare e configurare il criterio di cromo denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME in Chrome. Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Si noti che l'applicazione di questo criterio richiede i computer aggiunti a un dominio, in modo che l'utilizzo di S/MIME in Chrome richiede effettivamente i computer aggiunti a un dominio.

Per informazioni dettagliate sul criterio **ExtensionInstallForcelist** , vedere [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Questo passaggio è un prerequisito per l'utilizzo di Chrome. non sostituisce il controllo S/MIME installato dagli utenti. Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME. In alternativa, gli utenti possono accedere in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.

## <a name="for-more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)
