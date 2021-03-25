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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: In questo articolo viene illustrato come pubblicare i certificati appropriati in Office 365 prima di inviare messaggi protetti con S/MIME in Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 387f9f405afd45254c6568aa92334a7ee5b4171f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206452"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a>Sincronizzare i certificati dell'utente con Office 365 per S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Prima che chiunque possa inviare messaggi protetti con S/MIME in Exchange Online, è necessario configurare i certificati appropriati. Per inviare messaggi crittografati tramite Exchange Online, l'app di posta elettronica del mittente utilizza il certificato pubblico del destinatario per crittografare il messaggio. Il certificato X.509 pubblico deve essere pubblicato in Office 365.

## <a name="to-sync-certificates-that-support-smime"></a>Per sincronizzare i certificati che supportano S/MIME

Iniziare a configurare S/MIME emettendo i certificati e pubblicandoli nei servizi di dominio Active Directory locali. Per ulteriori informazioni, vedere [Panoramica sui Servizi certificati Active Directory](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).

Dopo la pubblicazione dei certificati, usare lo strumento Azure AD Connect per sincronizzare i dati utente dall'ambiente Exchange locale a Office 365. Per ulteriori informazioni su questo processo, vedere [Sincronizzazione di Azure AD Connect: informazioni e personalizzazione della sincronizzazione.](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

Oltre a sincronizzare altri dati della directory, per scopi S/MIME, lo strumento sincronizza gli attributi  **userCertificate** e **userSMIMECertificate** per ogni oggetto utente in modo che i dati possano essere utilizzati per firmare e crittografare i messaggi.

## <a name="more-information"></a>Ulteriori informazioni

[S/MIME per la crittografia e firma dei messaggi](s-mime-for-message-signing-and-encryption.md)

[Cos'è Azure AD Connect?](/azure/active-directory/hybrid/whatis-azure-ad-connect)