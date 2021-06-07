---
title: Accedere al Portale di amministrazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
description: Come trovare e usare il portale di amministrazione, incluso il controllo dell'accesso a esso.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 2facd506497cbdab42f2d8b051fbd50f82432927
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770602"
---
# <a name="access-the-admin-portal"></a>Accedere al portale di amministrazione

Il gateway al servizio Microsoft Managed Desktop è [Microsoft Endpoint Manager](https://endpoint.microsoft.com/). Se non si ha familiarità con le funzionalità di questo portale per la gestione dei dispositivi, vedere la Microsoft Endpoint Manager [documentazione.](/mem/)

> [!NOTE]
> In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) sono supportati i browser seguenti:
> - Microsoft Edge (versione più recente)
> - Safari (versione più recente, solo Mac)
> - Chrome (versione più recente)
> - Firefox (versione più recente)

L'account amministrativo avrà bisogno di autorizzazioni specifiche per accedere alle Microsoft Managed Desktop amministrative in Microsoft Endpoint Manager. È possibile gestire l'accesso dell'amministratore a queste funzionalità all'interno dell'organizzazione utilizzando il controllo di accesso basato sui ruoli. Sono disponibili Azure Active Directory diversi ruoli di amministratore (Azure AD) e ruoli Microsoft Managed Desktop predefiniti per fornire un controllo più granulare alle diverse funzionalità all'interno del portale di Microsoft Managed Desktop admin. Per ulteriori informazioni sui ruoli Azure Active Directory, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). A differenza dei ruoli di amministratore di Azure AD che si applicano a vari prodotti e servizi Microsoft, i ruoli predefiniti sono specifici di Microsoft Managed Desktop e garantiranno solo l'accesso alle funzionalità di amministrazione per questo servizio. Gli amministratori possono assegnare ruoli predefiniti agli utenti singolarmente o in combinazione con i ruoli di amministratore di Azure AD per aggiungere Microsoft Managed Desktop agli account di amministratore esistenti.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Azure Active Directory ruoli con Microsoft Managed Desktop accesso

|Ruolo Azure AD  |Microsoft Managed Desktop autorizzazioni  |
|---------|---------|
|Amministratore globale     | Gli amministratori con questo ruolo avranno le autorizzazioni di lettura e scrittura **per tutte le funzionalità** nel portale Microsoft Managed Desktop di amministrazione.         |
|Lettore globale     | Gli amministratori con questo ruolo avranno autorizzazioni di sola **lettura per tutte** le funzionalità nel Microsoft Managed Desktop di amministrazione.         |
|Amministratore del servizio Intune     |  Gli amministratori con questo ruolo avranno autorizzazioni di lettura e scrittura per **le** funzionalità non correlate alla sicurezza nel portale Microsoft Managed Desktop di amministrazione.       |
|Service Support Administrator     | Gli amministratori con questo  ruolo avranno autorizzazioni di sola  lettura per le funzionalità non correlate alle autorizzazioni di sicurezza e scrittura per gestire le richieste di supporto nel Microsoft Managed Desktop di amministrazione.         |
|Amministratore della sicurezza | Gli amministratori con questo ruolo **avranno** autorizzazioni di sola lettura per tutte le funzionalità e autorizzazioni di scrittura per le funzionalità correlate alla sicurezza **in** Microsoft Managed Desktop nel portale di amministrazione. |
|Ruolo con autorizzazioni di lettura per la sicurezza |Gli amministratori con questo ruolo avranno autorizzazioni di sola **lettura per tutte** le funzionalità nel Microsoft Managed Desktop di amministrazione.|

Per assistenza nell'assegnazione di Azure Active Directory ruoli, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

> [!IMPORTANT]
> Solo il ruolo Amministratore globale dispone delle autorizzazioni necessarie per *registrare* l'organizzazione in Microsoft Managed Desktop. Tenere presente che Azure Active Directory ruoli assegnano privilegi agli account utente in un'ampia gamma di servizi Microsoft. Dopo aver completato la registrazione con Microsoft Managed Desktop, è  consigliabile utilizzare sempre il ruolo con i privilegi minimi necessari per eseguire altre attività.

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Ruoli incorporati forniti da Microsoft Managed Desktop


|Ruolo incorporato  |Microsoft Managed Desktop autorizzazioni  |
|---------|---------|
|Microsoft Managed Desktop Amministratore del servizio  | Quando viene assegnato a un utente, questo ruolo concede all'amministratore le autorizzazioni di lettura e scrittura per le funzionalità non correlate alla sicurezza nel Microsoft Managed Desktop di amministrazione.   |
|Microsoft Managed Desktop Lettore di servizi | Quando viene assegnato a un utente, questo ruolo concede all'amministratore autorizzazioni di sola lettura per le funzionalità non correlate alla sicurezza nel portale Microsoft Managed Desktop admin.  |
|Microsoft Managed Desktop Gestione sicurezza |Quando viene assegnato a un utente, questo ruolo concede all'amministratore le autorizzazioni di lettura e scrittura solo per le funzionalità correlate alla sicurezza **nel** portale Microsoft Managed Desktop admin.   |

> [!NOTE]
> Le funzionalità di sicurezza includono le comunicazioni correlate alla sicurezza, la gestione dei contatti di sicurezza, la gestione delle richieste di supporto relative alla sicurezza e l'accesso ai report correlati alla sicurezza. 

### <a name="assigning-built-in-roles-to-user"></a>Assegnazione di ruoli predefiniti all'utente

Per una gestione semplice dei ruoli predefiniti, è disponibile un gruppo di sicurezza per ogni ruolo personalizzato con il nome "Ruoli moderni dell'area di lavoro _-_ Nome ruolo", ad esempio "Ruoli moderni dell'area di lavoro - Responsabile della sicurezza". Per assegnare gli utenti a uno di questi gruppi di sicurezza, attenersi alla seguente procedura:
1.  Accedere al Microsoft Endpoint Manager portale.
2.  Seleziona **Gruppi** sul lato sinistro.
3.  Cercare Ruoli **moderni dell'area di** lavoro e quindi selezionare il gruppo associato al ruolo che si desidera assegnare. 
4.  Selezionare **Membri** a sinistra e quindi **+ Aggiungi membri** sulla barra dei comandi.
5.  Immetti il messaggio di posta elettronica della persona da aggiungere. Se sono guest, è necessario invitarli prima di poter assegnare il gruppo.
6.  Seleziona **Seleziona** nella parte inferiore.

> [!NOTE]
> L'annidamento dei gruppi di sicurezza per l'assegnazione di ruolo non è attualmente supportato. 

### <a name="assigning-built-in-roles-to-groups"></a>Assegnazione di ruoli predefiniti ai gruppi

Se è necessario assegnare uno o più ruoli incorporati a un gruppo esistente, eseguire la procedura seguente:
1. Vai a [portal.azure.com](https://portal.azure.com/).
2. Cercare e aprire Enterprise **applicazioni**.
3. Modificare il **filtro Tipo di** applicazione in Applicazioni _Microsoft_ e quindi selezionare **Applica**.
4. Cerca e seleziona _LE API dei clienti moderni di Workplace._
5. Selezionare **Utenti e gruppi** nel riquadro a sinistra, quindi selezionare + Aggiungi **utente/gruppo.**
6. Cercare il gruppo desiderato da **Utenti e gruppi**.
7. Cercare il ruolo applicabile in **Selezionare un ruolo** e quindi selezionarlo.
8. Selezionare **Assegna**.
