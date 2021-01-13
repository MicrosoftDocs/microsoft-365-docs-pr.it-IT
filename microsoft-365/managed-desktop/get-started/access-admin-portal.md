---
title: Accedere al Portale di amministrazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
description: Come trovare e utilizzare il portale di amministrazione, incluso il controllo dell'accesso.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 09427d163b8b5e47911b6df26e5acf0fcd1f3524
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841352"
---
# <a name="access-the-admin-portal"></a>Accedere al portale di amministrazione

Il gateway per il servizio Microsoft Managed Desktop è il [portale](https://portal.azure.com)di Microsoft Azure. Per ulteriori informazioni sull'utilizzo e la personalizzazione dell'esperienza del portale di Azure in genere, vedere la [documentazione relativa al portale di Azure](https://docs.microsoft.com/azure/azure-portal/). Disponibile in anteprima ora, è anche possibile trovare Microsoft Managed Desktop in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Se non si ha familiarità con le funzionalità di questo portale per la gestione dei dispositivi, vedere la [documentazione di Microsoft Endpoint Manager](https://docs.microsoft.com/mem/).

> [!NOTE]
> Tuttavia, se si sceglie di accedere a Microsoft Managed Desktop, in [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) o nel [portale di Azure](https://portal.azure.com), sono supportati i seguenti browser:
> - Microsoft Edge (versione più recente)
> - Microsoft Internet Explorer 11
> - Safari (versione più recente, solo Mac)
> - Chrome (versione più recente)
> - Firefox (ultima versione)

Per poter accedere alle funzionalità amministrative di Microsoft Managed Desktop in Azure Portal o Microsoft Endpoint Manager, è necessario disporre di autorizzazioni specifiche per l'account amministrativo. È possibile gestire l'accesso dell'amministratore a queste funzionalità all'interno dell'organizzazione utilizzando il controllo di accesso basato sui ruoli (RBAC). Sono disponibili diversi ruoli di amministratore di Azure Active Directory (Azure AD) e ruoli personalizzati incorporati per fornire un controllo più granulare a diverse funzionalità all'interno del portale di amministrazione di Microsoft Managed Desktop. Per ulteriori informazioni sui ruoli di Azure Active Directory, vedere autorizzazioni dei ruoli [di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). A differenza dei ruoli di amministratore di Azure AD che si applicano a diversi prodotti e servizi Microsoft, i ruoli personalizzati sono specifici di Microsoft Managed Desktop e garantiscono l'accesso solo alle funzionalità di amministratore per questo servizio. Gli amministratori possono assegnare ruoli personalizzati agli utenti singolarmente o in combinazione con i ruoli di Azure AD Administrator per aggiungere le autorizzazioni di Microsoft Managed Desktop agli account di amministratore esistenti.

È possibile assegnare ognuno dei ruoli riportati di seguito per fornire diversi livelli di accesso:

|Ruolo di Azure AD  |Autorizzazioni di Microsoft Managed Desktop  |
|---------|---------|
|Amministratore globale     | Gli amministratori con questo ruolo avranno **autorizzazioni di lettura e scrittura per tutte le funzionalità** nel portale di amministrazione di Microsoft Managed Desktop.         |
|Ruolo con autorizzazioni di lettura globali     | Gli amministratori con questo ruolo avranno le **autorizzazioni di sola lettura per tutte le funzionalità** nel portale di amministrazione di Microsoft Managed Desktop.         |
|Amministratore del servizio Intune     |  Gli amministratori con questo ruolo avranno **autorizzazioni di lettura e scrittura per le caratteristiche non correlate alla sicurezza** nel portale di amministrazione di Microsoft Managed Desktop.       |
|Amministratore del supporto tecnico     | Gli amministratori con questo ruolo avranno le **autorizzazioni di sola lettura per le funzionalità non correlate alla sicurezza** e alle **autorizzazioni di scrittura per gestire le richieste di supporto** nel portale di amministrazione di Microsoft Managed Desktop.         |
|Amministratore della sicurezza | Gli amministratori con questo ruolo avranno le **autorizzazioni di sola lettura per tutte le caratteristiche** e le **autorizzazioni di scrittura per le funzionalità relative alla sicurezza** in Microsoft Managed Desktop nel portale di amministrazione. |
|Ruolo con autorizzazioni di lettura per la sicurezza |Gli amministratori con questo ruolo avranno le **autorizzazioni di sola lettura per tutte le funzionalità** nel portale di amministrazione di Microsoft Managed Desktop.|

> [!IMPORTANT]
> Solo il ruolo amministratore globale dispone delle autorizzazioni necessarie per *registrare* la propria organizzazione in Microsoft Managed Desktop. Tenere presente che i ruoli di Azure Active Directory forniranno i privilegi degli account utente in una vasta gamma di servizi Microsoft. Dopo aver completato la registrazione con Microsoft Managed Desktop, è consigliabile utilizzare sempre il ruolo con i privilegi *minimi* necessari per eseguire le altre attività.

 
|Ruolo personalizzato  |Autorizzazioni di Microsoft Managed Desktop  |
|---------|---------|
|Amministratore del servizio Microsoft Managed Desktop  | Quando viene assegnato a un utente, questo ruolo fornisce all'amministratore **autorizzazioni di lettura e scrittura per le caratteristiche non correlate alla sicurezza** nel portale di amministrazione di Microsoft Managed Desktop.  |
|Lettore di servizi Microsoft Managed Desktop | Quando viene assegnato a un utente, questo ruolo fornisce all'amministratore le **autorizzazioni di sola lettura per le funzionalità non correlate alla sicurezza** nel portale di amministrazione di Microsoft Managed Desktop. |
|Gestione della sicurezza di Microsoft Managed Desktop |Quando viene assegnato a un utente, questo ruolo fornisce all'amministratore **autorizzazioni di lettura e scrittura solo per le funzionalità relative alla sicurezza** nel portale di amministrazione di Microsoft Managed Desktop.   |

> [!NOTE]
> Le funzionalità di sicurezza includono le comunicazioni relative alla sicurezza, la gestione dei contatti di sicurezza, la gestione delle richieste di supporto correlate alla sicurezza e l'accesso ai report relativi alla sicurezza. 

## <a name="assigning-roles-to-administrators"></a>Assegnazione di ruoli agli amministratori

Per informazioni sull'assegnazione dei ruoli di Azure Active Directory, vedere [autorizzazioni per il ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

Per semplificare la gestione dei ruoli incorporati, è presente un gruppo di sicurezza per ogni ruolo personalizzato, ad esempio "ruoli di lavoro moderni – responsabile della sicurezza". Per assegnare gli utenti a uno dei gruppi di sicurezza, eseguire la procedura seguente:
1.  Andare al portale di Microsoft Endpoint Manager.
2.  Seleziona **gruppi** a sinistra.
3.  Cercare i **ruoli di lavoro moderni** e quindi selezionare il gruppo associato al ruolo che si desidera assegnare. 
4.  Selezionare **i membri** a sinistra, quindi selezionare **+ Aggiungi membri** sulla barra dei comandi.
5.  Immettere l'indirizzo di posta elettronica dell'utente che si sta aggiungendo. Se si tratta di un ospite, è necessario invitarlo prima di poter assegnare il gruppo.
6.  Selezionare **Seleziona** nella parte inferiore.

> [!NOTE]
> La nidificazione di gruppi di sicurezza per l'assegnazione di ruolo non è attualmente supportata. 
