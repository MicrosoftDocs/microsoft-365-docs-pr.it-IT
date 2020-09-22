---
title: Configurare la raccolta di certificati virtuali-Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Gli amministratori possono ottenere informazioni su come creare una raccolta di certificati virtuali che verrà utilizzata per convalidare i certificati S/MIME in Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aabd234f344778b2bfad34a7046bb51c55ed4b3d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197202"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="0c750-103">Configurare la raccolta di certificati virtuali in Exchange Online per convalidare S/MIME</span><span class="sxs-lookup"><span data-stu-id="0c750-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0c750-104">Come amministratore, sarà necessario configurare una raccolta di certificati virtuali in Exchange Online che verrà utilizzata per convalidare i certificati S/MIME.</span><span class="sxs-lookup"><span data-stu-id="0c750-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="0c750-105">Questa raccolta di certificati virtuali è configurata come archivio certificati con estensione del nome di file SST.</span><span class="sxs-lookup"><span data-stu-id="0c750-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="0c750-106">Il file SST contiene tutti i certificati radice e intermedi utilizzati durante la convalida del certificato S/MIME.</span><span class="sxs-lookup"><span data-stu-id="0c750-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="0c750-107">Creare e salvare un SST</span><span class="sxs-lookup"><span data-stu-id="0c750-107">Create and save an SST</span></span>

<span data-ttu-id="0c750-108">È possibile creare questo file dell'archivio certificati SST esportando i certificati da un computer attendibile utilizzando il cmdlet **Export-Certificate** in Windows PowerShell e specificando il valore _Type_ come SST.</span><span class="sxs-lookup"><span data-stu-id="0c750-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="0c750-109">Per istruzioni, vedere [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="0c750-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="0c750-110">Dopo aver utilizzato il file dell'archivio certificati SST, utilizzare la sintassi seguente in Exchange Online PowerShell per salvare il contenuto del file SST nell'archivio certificati virtuale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c750-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="0c750-111">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0c750-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="0c750-112">In questo esempio viene importato il file SST C:\My Documents\exported Rules Certificate Store. SST.</span><span class="sxs-lookup"><span data-stu-id="0c750-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="0c750-113">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="0c750-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="0c750-114">Assicurasi che un certificato sia valido</span><span class="sxs-lookup"><span data-stu-id="0c750-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="0c750-115">In Exchange Online, viene utilizzato solo lo SST per la convalida dei certificati.</span><span class="sxs-lookup"><span data-stu-id="0c750-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="0c750-116">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="0c750-116">More Information</span></span>

[<span data-ttu-id="0c750-117">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="0c750-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="0c750-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="0c750-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
