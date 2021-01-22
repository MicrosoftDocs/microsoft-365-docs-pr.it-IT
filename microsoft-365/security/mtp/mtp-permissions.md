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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930139"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Gestire l'accesso a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Gli account assegnati ai ruoli di Azure Active Directory (AD) seguenti possono accedere alle funzionalità e ai dati di Microsoft 365 Defender:
- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali
- Ruolo con autorizzazioni di lettura per la sicurezza

Per rivedere gli account con questi ruoli, [vedere Autorizzazioni nel Centro sicurezza Microsoft 365](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Accesso alle funzionalità
L’accesso alle funzionalità specifiche è determinato dal [ruolo di Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Rivolgersi a un amministratore globale se è necessario accedere a funzionalità specifiche per le quali deve essere assegnato un nuovo ruolo a un utente o a un gruppo di utenti.

### <a name="approve-pending-automated-tasks"></a>Approva attività automatiche in sospeso
[L’indagine automatizzata e la correzione](mtp-autoir-actions.md) possono intervenire sui messaggi di posta elettronica, le regole di invio, i file, i meccanismi di salvataggio e altri elementi trovati durante l’indagine. Per approvare o rifiutare azioni in sospeso che richiedono un'approvazione esplicita, è necessario possedere determinati ruoli in Microsoft 365. Per altre informazioni, vedere [Autorizzazioni del centro notifiche](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Accesso ai dati
L'accesso ai dati di Microsoft 365 Defender può essere controllato utilizzando l'ambito assegnato ai gruppi di utenti in Microsoft Defender for Endpoint role-based access control (RBAC). Se l'ambito dell'accesso non è stato limitato a un set specifico di dispositivi in Defender for Endpoint, si avrà accesso completo ai dati in Microsoft 365 Defender. Tuttavia, dopo aver definito l'ambito dell'account, verranno visualizzati solo i dati relativi ai dispositivi inclusi nell'ambito.

Ad esempio, se si appartiene a un solo gruppo di utenti con un ruolo Microsoft Defender for Endpoint e a tale gruppo di utenti è stato assegnato l'accesso solo ai dispositivi di vendita, verranno visualizzati solo i dati relativi ai dispositivi di vendita in Microsoft 365 Defender. [Altre informazioni sulle impostazioni RBAC in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controlli di accesso in Microsoft Cloud App Security
Durante l'anteprima, Microsoft 365 Defender non applica i controlli di accesso in base alle impostazioni di Cloud App Security. L'accesso ai dati di Microsoft 365 Defender non è influenzato da queste impostazioni.

## <a name="related-topics"></a>Argomenti correlati

- [Ruoli di Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Controllo degli accessi in base al ruolo di Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Ruoli di Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
