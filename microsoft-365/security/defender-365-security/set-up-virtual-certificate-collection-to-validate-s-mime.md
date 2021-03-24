---
title: Configurare la raccolta certificati virtuali - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Gli amministratori possono imparare a creare una raccolta di certificati virtuali che verrà utilizzata per convalidare i certificati S/MIME in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064517"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Configurare la raccolta certificati virtuali in Exchange Online per convalidare S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Come amministratore, sarà necessario configurare una raccolta di certificati virtuali in Exchange Online che verrà utilizzata per convalidare i certificati S/MIME. Questa raccolta di certificati virtuali viene impostata come archivio certificati con estensione SST. Il file SST contiene tutti i certificati radice e intermedi utilizzati durante la convalida del certificato S/MIME.

## <a name="create-and-save-an-sst"></a>Creare e salvare un SST

È possibile creare questo file dell'archivio certificati SST esportando i certificati da un computer attendibile utilizzando il cmdlet **Export-Certificate** in Windows PowerShell e specificando il valore _Type_ come SST. Per istruzioni, vedere [Export-Certificate](/powershell/module/pkiclient/export-certificate).

Dopo aver creato il file dell'archivio certificati SST, utilizzare la sintassi seguente in PowerShell di Exchange Online per salvare il contenuto del file SST nell'archivio certificati virtuali di Exchange Online. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In questo esempio viene importato il file SST C:\My Documents\Exported Certificate Store.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)

## <a name="ensuring-a-certificate-is-valid"></a>Assicurasi che un certificato sia valido

In Exchange Online, solo l'SST viene utilizzato per la convalida del certificato.

## <a name="more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)