---
title: Sincronizzare i certificati dell'utente con Office 365 per S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: Prima che chiunque possa inviare messaggi protetti con S/MIME, è necessario configurare i certificati appropriati. Per inviare messaggi crittografati tramite Exchange Online, il programma di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio. Il certificato X.509 pubblico deve essere pubblicato in Office 365.
ms.openlocfilehash: 7b42f757ade54e362afc65f920096252bf69eb31
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38030840"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="01c92-105">Sincronizzare i certificati dell'utente con Office 365 per S/MIME</span><span class="sxs-lookup"><span data-stu-id="01c92-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="01c92-106">Prima che chiunque possa inviare messaggi protetti con S/MIME in Exchange Online, è necessario configurare i certificati corretti.</span><span class="sxs-lookup"><span data-stu-id="01c92-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="01c92-107">Per inviare messaggi crittografati tramite Exchange Online, l'app di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="01c92-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="01c92-108">Il certificato X.509 pubblico deve essere pubblicato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="01c92-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="01c92-109">Per sincronizzare i certificati che supportano S/MIME</span><span class="sxs-lookup"><span data-stu-id="01c92-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="01c92-110">Iniziare a configurare S/MIME emettendo i certificati e pubblicandoli nei servizi di dominio Active Directory locali.</span><span class="sxs-lookup"><span data-stu-id="01c92-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="01c92-111">Per ulteriori informazioni sulla gestione dei certificati in Exchange Server, vedere [Digital certificates and SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span><span class="sxs-lookup"><span data-stu-id="01c92-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="01c92-112">Dopo la pubblicazione dei certificati, utilizzare lo strumento di sincronizzazione di Azure Active Directory per sincronizzare i dati degli utenti dall'ambiente di Exchange locale a Office 365.</span><span class="sxs-lookup"><span data-stu-id="01c92-112">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="01c92-113">Per ulteriori informazioni su questo processo, vedere [DirSync: Directory Sync Tool version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span><span class="sxs-lookup"><span data-stu-id="01c92-113">For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="01c92-114">Insieme alla sincronizzazione di altri dati di directory, per scopi S/MIME, lo strumento Sincronizza gli attributi **userCertificate** e **userSMIMECertificate** per ogni oggetto utente in modo che i dati possano essere utilizzati per firmare e crittografare i messaggi.</span><span class="sxs-lookup"><span data-stu-id="01c92-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="01c92-115">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="01c92-115">More Information</span></span>

[<span data-ttu-id="01c92-116">S/MIME per la crittografia e firma dei messaggi</span><span class="sxs-lookup"><span data-stu-id="01c92-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="01c92-117">strumento di sincronizzazione di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="01c92-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
