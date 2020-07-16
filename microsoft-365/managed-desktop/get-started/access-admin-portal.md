---
title: Accedere al portale di amministrazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146268"
---
# <a name="access-the-admin-portal"></a>Accedere al portale di amministrazione

Il gateway per il servizio Microsoft Managed Desktop è il [portale](https://portal.azure.com)di Microsoft Azure. Per ulteriori informazioni sull'utilizzo e la personalizzazione dell'esperienza del portale di Azure in genere, vedere la [documentazione relativa al portale di Azure](https://docs.microsoft.com/azure/azure-portal/). 

L'account amministrativo deve disporre di autorizzazioni specifiche per accedere al portale di amministrazione di Microsoft Managed Desktop. È possibile gestire l'accesso dell'amministratore a queste funzionalità all'interno dell'organizzazione utilizzando il controllo di accesso basato sui ruoli (RBAC). Per ulteriori informazioni sui ruoli di Azure Active Directory, vedere autorizzazioni dei ruoli [di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Assegnare agli account utente di amministratore uno dei ruoli seguenti per garantire l'accesso:

|Ruolo di Azure AD  |Autorizzazioni di Microsoft Managed Desktop  |
|---------|---------|
|Amministratore globale     | Gli amministratori con questo ruolo avranno **autorizzazioni di lettura e scrittura** per tutte le funzionalità nel portale di amministrazione di Microsoft Managed Desktop.         |
|Ruolo con autorizzazioni di lettura globali     | Gli amministratori con questo ruolo avranno le **autorizzazioni di sola lettura** per tutte le funzionalità nel portale di amministrazione di Microsoft Managed Desktop.         |
|Amministratore del servizio Intune     |  Gli amministratori con questo ruolo avranno **autorizzazioni di lettura e scrittura** per tutte le funzionalità nel portale di amministrazione di Microsoft Managed Desktop.       |
|Amministratore del supporto tecnico     | Gli amministratori con questo ruolo avranno **autorizzazioni di lettura e scrittura** per tutte le funzionalità nel portale di amministrazione di Microsoft Managed Desktop.         |

> [!IMPORTANT]
> Solo il ruolo amministratore globale dispone delle autorizzazioni necessarie per *registrare* la propria organizzazione in Microsoft Managed Desktop. Tenere presente che i ruoli di Azure Active Directory forniranno i privilegi degli account utente in una vasta gamma di servizi Microsoft. Dopo aver completato la registrazione con Microsoft Managed Desktop, è consigliabile utilizzare sempre il ruolo con i privilegi *minimi* necessari per eseguire le altre attività.

## <a name="assigning-roles-to-administrators"></a>Assegnazione di ruoli agli amministratori

Se si ha bisogno di assistenza per l'assegnazione dei ruoli di Azure Active Directory, vedere [autorizzazioni per il ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).
