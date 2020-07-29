---
title: Accedere al Portale di amministrazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 17696b18b4109b568bb1d616813ba40e2a9dccdc
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430472"
---
# <a name="access-the-admin-portal"></a>Accedere al portale di amministrazione

Il gateway per il servizio Microsoft Managed Desktop è il [portale](https://portal.azure.com)di Microsoft Azure. Per ulteriori informazioni sull'utilizzo e la personalizzazione dell'esperienza del portale di Azure in genere, vedere la [documentazione relativa al portale di Azure](https://docs.microsoft.com/azure/azure-portal/). Disponibile in anteprima ora, è anche possibile trovare Microsoft Managed Desktop in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Se non si ha familiarità con le funzionalità di questo portale per la gestione dei dispositivi, vedere la [documentazione di Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

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
