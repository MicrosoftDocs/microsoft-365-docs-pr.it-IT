---
title: Configurare la raccolta di certificati virtuali in Exchange Online per convalidare S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Gli amministratori possono ottenere informazioni su come creare una raccolta di certificati virtuali che verrà utilizzata per convalidare i certificati S/MIME in Exchange Online.
ms.openlocfilehash: 232f45b63a38ce4591c83e4ec7a9c09a03c339d4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598323"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Configurare la raccolta di certificati virtuali in Exchange Online per convalidare S/MIME

Come amministratore, sarà necessario configurare una raccolta di certificati virtuali in Exchange Online che verrà utilizzata per convalidare i certificati S/MIME. Questa raccolta di certificati virtuali è configurata come archivio certificati con estensione del nome di file SST. Il file SST contiene tutti i certificati radice e intermedi utilizzati durante la convalida del certificato S/MIME.

## <a name="create-and-save-an-sst"></a>Creare e salvare un SST

È possibile creare questo file dell'archivio certificati SST esportando i certificati da un computer attendibile utilizzando il cmdlet **Export-Certificate** in Windows PowerShell e specificando il valore _Type_ come SST. Per istruzioni, vedere [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

Dopo aver utilizzato il file dell'archivio certificati SST, utilizzare la sintassi seguente in Exchange Online PowerShell per salvare il contenuto del file SST nell'archivio certificati virtuale di Exchange Online. Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

In questo esempio viene importato il file SST C:\My Documents\exported Rules Certificate Store. SST.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Assicurasi che un certificato sia valido

In Exchange Online, viene utilizzato solo lo SST per la convalida dei certificati.

## <a name="more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig)
