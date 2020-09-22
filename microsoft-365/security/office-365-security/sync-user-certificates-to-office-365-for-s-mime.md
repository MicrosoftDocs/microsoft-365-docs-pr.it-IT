---
title: Sincronizzare i certificati dell'utente con Office 365 per S/MIME
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: In questo articolo verrà illustrato come pubblicare i certificati adeguati in Office 365 prima di inviare messaggi protetti con S/MIME in Exchange Online.
ms.openlocfilehash: 3551dbacc3cc6279d319860f1133d059216ae591
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202104"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="c269d-103">Sincronizzare i certificati dell'utente con Office 365 per S/MIME</span><span class="sxs-lookup"><span data-stu-id="c269d-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c269d-104">Prima che chiunque possa inviare messaggi protetti con S/MIME in Exchange Online, è necessario configurare i certificati corretti.</span><span class="sxs-lookup"><span data-stu-id="c269d-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="c269d-105">Per inviare messaggi crittografati tramite Exchange Online, l'app di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="c269d-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="c269d-106">Il certificato X.509 pubblico deve essere pubblicato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c269d-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="c269d-107">Per sincronizzare i certificati che supportano S/MIME</span><span class="sxs-lookup"><span data-stu-id="c269d-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="c269d-108">Iniziare a configurare S/MIME emettendo i certificati e pubblicandoli nei servizi di dominio Active Directory locali.</span><span class="sxs-lookup"><span data-stu-id="c269d-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="c269d-109">Per ulteriori informazioni, vedere [Panoramica sui Servizi certificati Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="c269d-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="c269d-110">Dopo la pubblicazione dei certificati, utilizzare lo strumento Azure AD Connect per sincronizzare i dati degli utenti dall'ambiente di Exchange locale a Office 365.</span><span class="sxs-lookup"><span data-stu-id="c269d-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="c269d-111">Per ulteriori informazioni su questo processo, vedere sincronizzazione di [Azure ad Connect: understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span><span class="sxs-lookup"><span data-stu-id="c269d-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="c269d-112">Insieme alla sincronizzazione di altri dati di directory, per scopi S/MIME, lo strumento Sincronizza gli attributi  **userCertificate** e **userSMIMECertificate** per ogni oggetto utente in modo che i dati possano essere utilizzati per firmare e crittografare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c269d-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="c269d-113">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="c269d-113">More Information</span></span>

[<span data-ttu-id="c269d-114">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="c269d-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="c269d-115">Cos'è Azure AD Connect?</span><span class="sxs-lookup"><span data-stu-id="c269d-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
