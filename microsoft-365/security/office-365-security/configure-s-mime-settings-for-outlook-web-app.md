---
title: Configurare le impostazioni S/MIME - Exchange Online per Outlook sul Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Breve descrizione delle attività necessarie agli amministratori di Exchange Online per visualizzare e configurare le impostazioni S/MIME in Outlook sul Web in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ab1aaabf0e7651a5a84642c178c28961430eea0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906481"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurare le impostazioni S/MIME in Exchange Online per Outlook sul Web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In quanto amministratore di Exchange Online, è possibile configurare Outlook sul Web (in precedenza noto come Outlook Web App) per consentire l'invio e la ricezione di messaggi protetti con S/MIME. Utilizzare i cmdlet **Get-SmimeConfig** e **Set-SmimeConfig** per visualizzare e gestire questa funzionalità in PowerShell di Exchange Online. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) e [Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Considerazioni sul nuovo Microsoft Edge (basato su Chromium)

Per utilizzare S/MIME in Outlook sul Web nel nuovo Web browser [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) è necessario impostare e configurare il criterio del browser Microsoft Edge denominato **ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME nel nuovo Microsoft Edge. Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . L'applicazione di questo criterio richiede dispositivi aggiunti a un dominio o aggiunti ad Azure AD, quindi l'uso di S/MIME nel nuovo browser Microsoft Edge richiede effettivamente dispositivi aggiunti a un dominio o aggiunti ad Azure AD.

Per informazioni dettagliate **sul criterio ExtensionInstallForcelist,** vedere [ExtensionInstallForcelist.](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)

Questo passaggio è un prerequisito per l'uso del nuovo Microsoft Edge. non sostituisce il controllo S/MIME installato dagli utenti. Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME. In alternativa, gli utenti possono passare in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.

## <a name="considerations-for-chrome"></a>Considerazioni su Chrome

Per utilizzare S/MIME in Outlook sul Web nel Web browser Google Chrome, è necessario impostare e configurare il criterio Chromium **denominato ExtensionInstallForcelist** per installare l'estensione Microsoft S/MIME in Chrome. Il valore del criterio è `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . Inoltre, l'applicazione di questo criterio richiede computer aggiunti a un dominio, quindi l'uso di S/MIME in Chrome richiede effettivamente computer aggiunti a un dominio.

Per informazioni dettagliate **sul criterio ExtensionInstallForcelist,** vedere [ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)

Questo passaggio è un prerequisito per l'uso di Chrome. non sostituisce il controllo S/MIME installato dagli utenti. Agli utenti viene richiesto di scaricare e installare il controllo S/MIME in Outlook sul Web durante il primo utilizzo di S/MIME. In alternativa, gli utenti possono passare in modo proattivo a **S/MIME** nelle impostazioni di Outlook sul Web per ottenere il collegamento di download per il controllo.

## <a name="for-more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)