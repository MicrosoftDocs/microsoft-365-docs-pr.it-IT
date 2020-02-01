---
title: Sincronizzare i certificati dell'utente con Office 365 per S/MIME
f1.keywords:
- NOCSH
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
ms.openlocfilehash: a62af3b176f29ec2bd8c97ae02178c87b7a63544
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598193"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizzare i certificati dell'utente con Office 365 per S/MIME

Prima che chiunque possa inviare messaggi protetti con S/MIME in Exchange Online, è necessario configurare i certificati corretti. Per inviare messaggi crittografati tramite Exchange Online, l'app di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio. Il certificato X.509 pubblico deve essere pubblicato in Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Per sincronizzare i certificati che supportano S/MIME

Iniziare a configurare S/MIME emettendo i certificati e pubblicandoli nei servizi di dominio Active Directory locali. Per ulteriori informazioni, vedere [Panoramica sui Servizi certificati Active Directory](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Dopo la pubblicazione dei certificati, utilizzare lo strumento Azure AD Connect per sincronizzare i dati degli utenti dall'ambiente di Exchange locale a Office 365. Per ulteriori informazioni su questo processo, vedere sincronizzazione di [Azure ad Connect: understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

Insieme alla sincronizzazione di altri dati di directory, per scopi S/MIME, lo strumento Sincronizza gli attributi **userCertificate** e **userSMIMECertificate** per ogni oggetto utente in modo che i dati possano essere utilizzati per firmare e crittografare i messaggi.

## <a name="more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)

[Che cos'è Azure AD Connect?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
