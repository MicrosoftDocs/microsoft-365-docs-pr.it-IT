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
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizzare i certificati dell'utente con Office 365 per S/MIME

Prima che chiunque possa inviare messaggi protetti con S/MIME in Exchange Online, è necessario configurare i certificati corretti. Per inviare messaggi crittografati tramite Exchange Online, l'app di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio. Il certificato X.509 pubblico deve essere pubblicato in Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Per sincronizzare i certificati che supportano S/MIME

Iniziare a configurare S/MIME emettendo i certificati e pubblicandoli nei servizi di dominio Active Directory locali. Per ulteriori informazioni sulla gestione dei certificati in Exchange Server, vedere [Digital certificates and SSL](https://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).

Dopo la pubblicazione dei certificati, utilizzare lo strumento di sincronizzazione di Azure Active Directory per sincronizzare i dati degli utenti dall'ambiente di Exchange locale a Office 365. Per ulteriori informazioni su questo processo, vedere [DirSync: Directory Sync Tool version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).

Insieme alla sincronizzazione di altri dati di directory, per scopi S/MIME, lo strumento Sincronizza gli attributi **userCertificate** e **userSMIMECertificate** per ogni oggetto utente in modo che i dati possano essere utilizzati per firmare e crittografare i messaggi.

## <a name="more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)

[strumento di sincronizzazione di Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=392587)
