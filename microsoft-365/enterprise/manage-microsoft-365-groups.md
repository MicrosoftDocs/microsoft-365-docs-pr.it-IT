---
title: Gestire i gruppi di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Informazioni su come gestire i gruppi di Microsoft 365.
ms.openlocfilehash: a01bf5dcc0b87cbdce8d7044b666cfb3a16a5aa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328521"
---
# <a name="manage-microsoft-365-groups"></a>Gestire i gruppi di Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

È possibile gestire i gruppi Microsoft 365 in vari modi, a seconda della configurazione. È possibile gestire gli account utente nell'interfaccia di [amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), PowerShell, in servizi di dominio Active Directory (ad DS) o nell'interfaccia di amministrazione di Azure [Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal). 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>Pianificare la posizione e la modalità di gestione dei gruppi

Il percorso e la modalità di gestione degli account utente dipendono dal modello di identità che si desidera utilizzare per Microsoft 365. I due modelli complessivi sono solo basati sul cloud e sull'ambiente ibrido.
  
### <a name="cloud-only"></a>Solo cloud

È possibile creare e gestire gruppi con:

- [L'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Interfaccia di amministrazione di Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>Ibrido

I gruppi di servizi di dominio Active Directory vengono sincronizzati con Microsoft 365 da servizi di dominio Active Directory, pertanto è necessario utilizzare gli strumenti di AD DS locali per gestire questi gruppi.

È inoltre possibile creare e gestire i gruppi di Azure AD che sono separati dai gruppi di servizi di dominio Active Directory, ma possono contenere utenti e gruppi di servizi di dominio Active Directory. In questo caso, è possibile utilizzare:

- [L'interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Interfaccia di amministrazione di Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>Consentire agli utenti di creare e gestire i propri gruppi

Azure AD consente ai gruppi che possono essere gestiti dai proprietari del gruppo invece degli amministratori IT. Detta *gestione dei gruppi in modalità self-service*, questa caratteristica consente ai proprietari del gruppo a cui non sono stati assegnati ruoli di amministrazione per creare e gestire gruppi di sicurezza. 

Gli utenti possono richiedere l'appartenenza a un gruppo di sicurezza e la richiesta passa al proprietario del gruppo invece che a un amministratore IT. Ciò permette che il controllo quotidiano dell'appartenenza al gruppo sia delegato ai proprietari del team, di progetto o aziendali che capiscano l'uso del gruppo e che possono gestirne l'appartenenza.

>[!Note]
>La gestione dei gruppi in modalità self-service è disponibile solo per specifici gruppi di sicurezza di Azure AD e Microsoft 365. Non è disponibile per i gruppi abilitati alla posta, le liste di distribuzione o qualsiasi gruppo sincronizzato da servizi di dominio Active Directory.
>

Per ulteriori informazioni, vedere le [istruzioni per configurare un gruppo Azure AD per la gestione in modalità self-service](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management).

## <a name="set-up-dynamic-group-membership"></a>Configurare l'appartenenza a gruppi dinamici

Azure AD supporta la configurazione di una serie di regole che aggiungono o rimuovono automaticamente gli account utente come membri di un gruppo di Azure AD. Questa operazione è denominata *appartenenza dinamica al gruppo*. Le regole si basano sugli attributi dell’account utente, come il reparto o paese.

Ecco come vengono applicate le regole:

- Se un nuovo account utente è conforme a tutte le regole relative al gruppo, può essere aggiunto come membro.
- Se un account utente non è un membro del gruppo, ma i suoi attributi vengono modificati per soddisfare le regole del gruppo, allora può essere aggiunto come membro.
- Se un account utente non è conforme alle regole del gruppo, non può essere aggiunto come membro.
- Se un account utente è già membro del gruppo, ma i suoi attributi vengono modificati in modo da non essere più conformi alle regole, l'account verrà rimosso dal gruppo.

Per utilizzare l'appartenenza dinamica, è necessario determinare i set di gruppi che possiedono un set comune di attributi di account utente. Per esempio, tutti i membri del reparto Vendite dovrebbero far parte del gruppo Vendite di Azure AD, avendo impostato l'attributo Reparto dell'account utente su "Vendite".

Vedere le [istruzioni per creare e configurare le regole per un gruppo dinamico di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

## <a name="set-up-automatic-licensing"></a>Configurare l'assegnazione automatica delle licenze

È possibile configurare i gruppi di sicurezza di Azure ad per assegnare automaticamente le licenze da un set di sottoscrizioni a tutti i membri del gruppo. Questa operazione è denominata *licenze basate sui gruppi*. Se un account utente viene aggiunto o rimosso dal gruppo, le licenze per gli abbonamenti del gruppo verranno automaticamente assegnate o rimosse dall'account utente.

Per Microsoft 365 Enterprise è necessario configurare i gruppi di sicurezza di Azure AD per assegnare la licenza di Microsoft 365 Enterprise appropriata.

Assicurarsi di avere a disposizione abbastanza licenze per tutti i membri del gruppo. Se le licenze a disposizione terminano, i nuovi utenti non potranno ottenerne una finché non ne saranno di nuovo disponibili.

>[!Note]
>Non è necessario configurare l'assegnazione delle licenze basate su gruppo per i gruppi contenenti account Azure business to business (B2B).
>

Per ulteriori informazioni, vedere [nozioni di base sulla gestione delle licenze basate su gruppo in Azure ad](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).

Vedere le [istruzioni per configurare la gestione delle licenze basate su gruppo per un gruppo di sicurezza di Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).
