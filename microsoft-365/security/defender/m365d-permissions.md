---
title: Gestire l'accesso ai dati di Microsoft 365 Defender nel Centro sicurezza Microsoft 365
description: Informazioni su come gestire le autorizzazioni per i dati in Microsoft 365 Defender
keywords: accesso, autorizzazioni, MTP, Microsoft Threat Protection, M365, sicurezza, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, ambito, definizione dell’ambito, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1be2cf4d5510b2a31a61f848d7d99d6a6704d49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068613"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Gestire l'accesso a Microsoft 365 Defender con i ruoli globali di Azure Active Directory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Esistono due modi per gestire l'accesso a Microsoft 365 Defender
- **Ruoli globali di Azure Active Directory (AD)**
- **Accesso al ruolo personalizzato**

Gli account assegnati ai ruoli **globali di Azure Active Directory (AD)** seguenti possono accedere ai dati e alle funzionalità di Microsoft 365 Defender:
- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali
- Ruolo con autorizzazioni di lettura per la sicurezza

Per rivedere gli account con questi ruoli, [vedere Autorizzazioni nel Centro sicurezza Microsoft 365](https://security.microsoft.com/permissions).

**L'accesso** ai ruoli personalizzati è una nuova funzionalità di Microsoft 365 Defender e consente di gestire l'accesso a dati, attività e funzionalità specifici in Microsoft Defender 365. I ruoli personalizzati offrono un maggiore controllo rispetto ai ruoli globali di Azure AD, fornendo agli utenti solo l'accesso necessario con i ruoli meno permissivi necessari.  I ruoli personalizzati possono essere creati oltre ai ruoli globali di Azure AD. [Ulteriori informazioni sui ruoli personalizzati.](custom-roles.md)

> ! [NOTA] Questo articolo si applica solo alla gestione dei ruoli globali di Azure Active Directory. Per ulteriori informazioni sull'utilizzo del controllo di accesso basato sui ruoli personalizzato, vedere Ruoli personalizzati per il controllo di [accesso basato sui ruoli.](custom-roles.md)

## <a name="access-to-functionality"></a>Accesso alle funzionalità
L’accesso alle funzionalità specifiche è determinato dal [ruolo di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Rivolgersi a un amministratore globale se è necessario accedere a funzionalità specifiche per le quali deve essere assegnato un nuovo ruolo a un utente o a un gruppo di utenti.

### <a name="approve-pending-automated-tasks"></a>Approva attività automatiche in sospeso
[L’indagine automatizzata e la correzione](m365d-autoir-actions.md) possono intervenire sui messaggi di posta elettronica, le regole di invio, i file, i meccanismi di salvataggio e altri elementi trovati durante l’indagine. Per approvare o rifiutare azioni in sospeso che richiedono un'approvazione esplicita, è necessario possedere determinati ruoli in Microsoft 365. Per altre informazioni, vedere [Autorizzazioni del centro notifiche](m365d-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Accesso ai dati
L'accesso ai dati di Microsoft 365 Defender può essere controllato utilizzando l'ambito assegnato ai gruppi di utenti in Microsoft Defender for Endpoint role-based access control (RBAC). Se l'ambito dell'accesso non è stato limitato a un set specifico di dispositivi in Defender for Endpoint, si avrà accesso completo ai dati in Microsoft 365 Defender. Tuttavia, dopo aver definito l'ambito dell'account, verranno visualizzati solo i dati relativi ai dispositivi inclusi nell'ambito.

Ad esempio, se apparteni a un solo gruppo di utenti con un ruolo Microsoft Defender for Endpoint e a tale gruppo di utenti è stato assegnato l'accesso solo ai dispositivi di vendita, in Microsoft 365 Defender verranno visualizzati solo i dati relativi ai dispositivi di vendita. [Altre informazioni sulle impostazioni RBAC in Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controlli di accesso in Microsoft Cloud App Security
Durante l'anteprima, Microsoft 365 Defender non applica i controlli di accesso in base alle impostazioni di Cloud App Security. L'accesso ai dati di Microsoft 365 Defender non è influenzato da queste impostazioni.

## <a name="related-topics"></a>Argomenti correlati
- [Ruoli personalizzati nel controllo di accesso basato sui ruoli per Microsoft 365 Defender](custom-roles.md)
- [Ruoli di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Controllo degli accessi in base al ruolo di Microsoft Defender per endpoint](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Ruoli di Cloud App Security](/cloud-app-security/manage-admins)