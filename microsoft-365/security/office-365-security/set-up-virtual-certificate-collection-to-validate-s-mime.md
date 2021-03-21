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
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916657"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="d2bef-103">Configurare la raccolta certificati virtuali in Exchange Online per convalidare S/MIME</span><span class="sxs-lookup"><span data-stu-id="d2bef-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d2bef-104">Come amministratore, sarà necessario configurare una raccolta di certificati virtuali in Exchange Online che verrà utilizzata per convalidare i certificati S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d2bef-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="d2bef-105">Questa raccolta di certificati virtuali viene impostata come archivio certificati con estensione SST.</span><span class="sxs-lookup"><span data-stu-id="d2bef-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="d2bef-106">Il file SST contiene tutti i certificati radice e intermedi utilizzati durante la convalida del certificato S/MIME.</span><span class="sxs-lookup"><span data-stu-id="d2bef-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="d2bef-107">Creare e salvare un SST</span><span class="sxs-lookup"><span data-stu-id="d2bef-107">Create and save an SST</span></span>

<span data-ttu-id="d2bef-108">È possibile creare questo file dell'archivio certificati SST esportando i certificati da un computer attendibile utilizzando il cmdlet **Export-Certificate** in Windows PowerShell e specificando il valore _Type_ come SST.</span><span class="sxs-lookup"><span data-stu-id="d2bef-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="d2bef-109">Per istruzioni, vedere [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="d2bef-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="d2bef-110">Dopo aver creato il file dell'archivio certificati SST, utilizzare la sintassi seguente in PowerShell di Exchange Online per salvare il contenuto del file SST nell'archivio certificati virtuali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2bef-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="d2bef-111">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d2bef-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="d2bef-112">In questo esempio viene importato il file SST C:\My Documents\Exported Certificate Store.sst.</span><span class="sxs-lookup"><span data-stu-id="d2bef-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="d2bef-113">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="d2bef-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="d2bef-114">Assicurasi che un certificato sia valido</span><span class="sxs-lookup"><span data-stu-id="d2bef-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="d2bef-115">In Exchange Online, solo l'SST viene utilizzato per la convalida del certificato.</span><span class="sxs-lookup"><span data-stu-id="d2bef-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="d2bef-116">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="d2bef-116">More Information</span></span>

[<span data-ttu-id="d2bef-117">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="d2bef-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="d2bef-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="d2bef-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)