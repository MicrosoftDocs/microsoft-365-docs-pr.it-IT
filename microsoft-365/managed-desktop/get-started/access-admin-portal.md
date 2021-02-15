---
title: Accedere al Portale di amministrazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
description: Come trovare e usare il portale di amministrazione, incluso il controllo dell'accesso.
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: d22cef41fb1d6dc3fde39681ad84edc510440b11
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110008"
---
# <a name="access-the-admin-portal"></a>Accedere al portale di amministrazione

Il gateway per il servizio Microsoft Managed Desktop è [Microsoft Endpoint Manager.](https://endpoint.microsoft.com/) Se non si ha familiarità con le funzionalità di questo portale per la gestione dei dispositivi, vedere la [documentazione di Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/)

> [!NOTE]
> In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) sono supportati i browser seguenti:
> - Microsoft Edge (versione più recente)
> - Microsoft Internet Explorer 11
> - Safari (versione più recente, solo Mac)
> - Chrome (versione più recente)
> - Firefox (versione più recente)

Il tuo account amministrativo avrà bisogno di autorizzazioni specifiche per accedere alle funzionalità amministrative di Microsoft Managed Desktop in Microsoft Endpoint Manager. È possibile gestire l'accesso dell'amministratore a queste funzionalità all'interno dell'organizzazione utilizzando il controllo dell'accesso basato sui ruoli. Sono disponibili diversi ruoli di amministratore di Azure Active Directory (Azure AD) e i ruoli Predefiniti di Microsoft Managed Desktop per fornire un controllo più granulare alle diverse funzionalità all'interno del portale di amministrazione di Microsoft Managed Desktop. Per ulteriori informazioni sui ruoli di Azure Active Directory, vedere [Autorizzazioni del ruolo di amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) A differenza dei ruoli di amministratore di Azure AD che si applicano a vari prodotti e servizi Microsoft, i ruoli predefiniti sono specifici di Microsoft Managed Desktop e garantiranno solo l'accesso alle funzionalità di amministrazione per questo servizio. Gli amministratori possono assegnare ruoli predefiniti agli utenti singolarmente o in combinazione con i ruoli di amministratore di Azure AD per aggiungere le autorizzazioni di Microsoft Managed Desktop agli account di amministratore esistenti.

## <a name="azure-active-directory-roles-with-microsoft-managed-desktop-access"></a>Ruoli di Azure Active Directory con accesso Microsoft Managed Desktop

|Ruolo Azure AD  |Autorizzazioni di Microsoft Managed Desktop  |
|---------|---------|
|Amministratore globale     | Gli amministratori con questo ruolo avranno le autorizzazioni di lettura e scrittura **per tutte le funzionalità** nel portale di amministrazione di Microsoft Managed Desktop.         |
|Ruolo con autorizzazioni di lettura globali     | Gli amministratori con questo ruolo avranno autorizzazioni di sola lettura **per tutte le funzionalità** nel portale di amministrazione di Microsoft Managed Desktop.         |
|Amministratore del servizio Intune     |  Gli amministratori con questo ruolo avranno autorizzazioni di lettura e scrittura **per funzionalità non** correlate alla sicurezza nel portale di amministrazione di Microsoft Managed Desktop.       |
|Amministratore del supporto tecnico     | Gli amministratori con questo  ruolo avranno autorizzazioni di sola  lettura per le funzionalità non correlate alle autorizzazioni di sicurezza e scrittura per gestire le richieste di supporto nel portale di amministrazione di Microsoft Managed Desktop.         |
|Amministratore della sicurezza | Gli amministratori con questo ruolo **diranno** autorizzazioni di sola lettura per tutte le funzionalità e di scrittura per le funzionalità correlate alla sicurezza **in** Microsoft Managed Desktop nel portale di amministrazione. |
|Ruolo con autorizzazioni di lettura per la sicurezza |Gli amministratori con questo ruolo avranno autorizzazioni di sola lettura **per tutte le funzionalità** nel portale di amministrazione di Microsoft Managed Desktop.|

Per assistenza nell'assegnazione dei ruoli di Azure Active Directory, vedere [Autorizzazioni del ruolo amministratore in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

> [!IMPORTANT]
> Solo il ruolo Amministratore globale dispone delle autorizzazioni necessarie per *registrare* l'organizzazione in Microsoft Managed Desktop. Tenere presente che i ruoli di Azure Active Directory offriranno privilegi agli account utente in un'ampia gamma di servizi Microsoft. Dopo aver completato la registrazione con Microsoft Managed Desktop, è consigliabile usare sempre il ruolo con i privilegi minimi necessari per eseguire le altre attività. 

## <a name="built-in-roles-provided-by-microsoft-managed-desktop"></a>Ruoli predefiniti forniti da Microsoft Managed Desktop


|Ruolo incorporato  |Autorizzazioni di Microsoft Managed Desktop  |
|---------|---------|
|Amministratore di Microsoft Managed Desktop Service  | Quando viene assegnato a un utente, questo ruolo assegna all'amministratore le autorizzazioni di lettura e scrittura per le funzionalità non correlate alla sicurezza **nel** portale di amministrazione di Microsoft Managed Desktop.  |
|Microsoft Managed Desktop Service Reader | Quando viene assegnato a un utente, questo ruolo concede all'amministratore le autorizzazioni di sola lettura **per** le funzionalità non correlate alla sicurezza nel portale di amministrazione di Microsoft Managed Desktop. |
|Microsoft Managed Desktop Security Manager |Quando viene assegnato a un utente, questo ruolo concede all'amministratore le autorizzazioni di lettura e scrittura solo per le funzionalità correlate alla sicurezza **nel** portale di amministrazione di Microsoft Managed Desktop.   |

> [!NOTE]
> Le funzionalità di sicurezza includono comunicazioni relative alla sicurezza, gestione dei contatti di sicurezza, gestione delle richieste di supporto relative alla sicurezza e accesso a report correlati alla sicurezza. 

### <a name="assigning-built-in-roles-to-user"></a>Assegnazione di ruoli predefiniti all'utente

Per una gestione semplice dei ruoli incorporati, è disponibile un gruppo di sicurezza per ogni ruolo personalizzato con il nome "Ruoli moderni dell'area di lavoro _-_ Nome ruolo", ad esempio "Ruoli moderni dell'area di lavoro – Responsabile della sicurezza". Per assegnare gli utenti a uno di questi gruppi di sicurezza, eseguire la procedura seguente:
1.  Accedere al portale di Microsoft Endpoint Manager.
2.  Seleziona **Gruppi** sul lato sinistro.
3.  Cercare Ruoli **moderni dell'area di** lavoro e quindi selezionare il gruppo associato al ruolo che si desidera assegnare. 
4.  Selezionare **Membri** sul lato sinistro e quindi **+ Aggiungi membri** sulla barra dei comandi.
5.  Immettere il messaggio di posta elettronica della persona da aggiungere. Se sono guest, è necessario invitarli prima di poter assegnare il gruppo.
6.  Selezionare **Seleziona** nella parte inferiore.

> [!NOTE]
> L'annidamento dei gruppi di sicurezza per l'assegnazione di ruolo non è attualmente supportato. 

### <a name="assigning-built-in-roles-to-groups"></a>Assegnazione di ruoli incorporati ai gruppi

Se è necessario assegnare uno o più ruoli incorporati a un gruppo esistente, eseguire la procedura seguente:
1. Passare a [portal.azure.com](https://portal.azure.com/).
2. Cercare e aprire le **applicazioni enterprise.**
3. Modificare il **filtro del tipo** di applicazione in Applicazioni _Microsoft_ e quindi selezionare **Applica.**
4. Cerca e seleziona _LE API dei clienti di Workplace moderno._
5. Selezionare **Utenti e gruppi** nel riquadro a sinistra, quindi selezionare + Aggiungi **utente/gruppo.**
6. Cercare il gruppo desiderato da **Utenti e gruppi.**
7. Cercare il ruolo applicabile in **Selezionare un ruolo** e quindi selezionarlo.
8. Selezionare **Assegna.**
 
