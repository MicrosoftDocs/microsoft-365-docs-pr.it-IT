---
title: Utilizzare i cmdlet di PowerShell per configurare ed eseguire Microsoft Defender AV
description: In Windows 10, è possibile utilizzare i cmdlet di PowerShell per eseguire analisi, aggiornare Security intelligence e modificare le impostazioni in Antivirus Microsoft Defender.
keywords: analisi, riga di comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765300"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Utilizzare i cmdlet di PowerShell per configurare e gestire Antivirus Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile utilizzare PowerShell per eseguire varie funzioni in Windows Defender. Analogamente al prompt dei comandi o alla riga di comando, PowerShell è una shell da riga di comando basata su attività e un linguaggio di script progettato appositamente per l'amministrazione del sistema. Per altre informazioni, vedere [l'hub di PowerShell su MSDN.](/previous-versions/msdn10/mt173057(v=msdn.10))

Per un elenco dei cmdlet, delle relative funzioni e dei parametri disponibili, vedere [l'argomento Cmdlet defender.](/powershell/module/defender)

I cmdlet di PowerShell sono particolarmente utili negli ambienti Windows Server che non si basano su un'interfaccia utente grafica (GUI) per configurare il software.

> [!NOTE]
> I cmdlet di PowerShell non devono essere utilizzati in sostituzione di [un'infrastruttura](https://www.microsoft.com/download/101445)di gestione dei criteri di rete completa, ad esempio [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) [Microsoft Endpoint Configuration Manager,](/configmgr)Console Gestione Criteri di gruppo o Antivirus Microsoft Defender modelli ADMX di Criteri di gruppo.

Le modifiche apportate con PowerShell influiranno sulle impostazioni locali nell'endpoint in cui le modifiche vengono distribuite o apportate. Ciò significa che le distribuzioni dei criteri con Criteri di gruppo, Microsoft Endpoint Configuration Manager o Microsoft Intune possono sovrascrivere le modifiche apportate con PowerShell.

È possibile [configurare le impostazioni che possono essere ignorate localmente con le sostituzioni dei criteri locali.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

PowerShell viene in genere installato nella cartella `%SystemRoot%\system32\WindowsPowerShell` .

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Utilizzare Antivirus Microsoft Defender cmdlet di PowerShell

1. Nella barra Windows ricerca digitare **powershell.**
2. Selezionare **Windows PowerShell** dai risultati per aprire l'interfaccia.
3. Immettere il comando PowerShell e gli eventuali parametri.

> [!NOTE]
> Potrebbe essere necessario aprire PowerShell in modalità amministratore. Fare clic con il pulsante destro del mouse sull'elemento nel menu Start, scegliere Esegui come **amministratore** e fare clic su **Sì** al prompt delle autorizzazioni.

Per aprire la Guida in linea per uno dei cmdlet, digitare quanto segue:

```PowerShell
Get-Help <cmdlet> -Online
```

Omettere il `-online` parametro per ottenere la Guida memorizzata localmente nella cache.

## <a name="related-topics"></a>Argomenti correlati

- [Argomenti di riferimento per gli strumenti di gestione e configurazione](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus Microsoft Defender Cmdlet](/powershell/module/defender)