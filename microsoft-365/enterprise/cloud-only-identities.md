---
title: Identità solo cloud di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descrive come creare utenti e gruppi quando l'abbonamento a Microsoft 365 usa l'identità solo cloud.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327928"
---
# <a name="microsoft-365-cloud-only-identity"></a>Identità solo cloud di Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Con l'identità solo cloud, tutti gli utenti, i gruppi e i contatti vengono archiviati nel tenant di Azure Active Directory (Azure AD) dell'abbonamento a Microsoft 365. Ecco i componenti di base dell'identità solo cloud.
 
![Componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

Gli utenti e i relativi account utente nelle organizzazioni possono essere categorizzati in diversi modi. Ad esempio, alcuni sono dipendenti e hanno uno stato permanente. Alcuni sono fornitori, terzisti o partner con uno stato temporaneo. Alcuni sono utenti esterni che non dispongono di account utente, ma devono comunque disporre dell'accesso a servizi e risorse specifici per supportare l'interazione e la collaborazione. Ad esempio:

- Gli account tenant rappresentano gli utenti all'interno dell'organizzazione con la licenza per i servizi cloud

- Gli account Business to Business (B2B) rappresentano gli utenti esterni all'organizzazione che vengono invitati a collaborare.

Prendere in controllo i tipi di utenti nell'organizzazione. Quali sono i raggruppamenti? È ad esempio possibile raggruppare gli utenti in base alla funzione o allo scopo di alto livello dell'organizzazione.

Inoltre, alcuni servizi cloud possono essere condivisi al di fuori dell'organizzazione senza alcun account utente. È necessario identificare anche questi gruppi di utenti.

È possibile usare i gruppi in Azure AD per diversi scopi che semplificano la gestione dell'ambiente cloud. Ad esempio, con i gruppi di Azure AD, puoi:

- Usare le licenze basate su gruppo per assegnare automaticamente le licenze per Microsoft 365 agli account utente non appena vengono aggiunti come membri.
- Aggiungere account utente a gruppi specifici in modo dinamico in base agli attributi degli account utente, ad esempio il nome del reparto.
- Effettuare automaticamente il provisioning degli utenti per le applicazioni Software as a Service (SaaS) e proteggere l'accesso a tali applicazioni con l'autenticazione a più fattori (MFA) e altri criteri di accesso condizionale.
- Eseguire il provisioning delle autorizzazioni e dei livelli di accesso per i siti del team di SharePoint Online.

## <a name="next-steps-for-cloud-only-identity"></a>Passaggi successivi per l'identità solo cloud

- [Gestione degli account utente](manage-microsoft-365-accounts.md)
- [Assegnare licenze agli account utente](assign-licenses-to-user-accounts.md).
- [Gestire i gruppi e l'appartenenza ai gruppi](manage-microsoft-365-groups.md)
- [Gestire le password degli account utente](manage-microsoft-365-passwords.md)
