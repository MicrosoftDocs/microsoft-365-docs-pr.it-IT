---
title: Gestire l'accesso a Microsoft 365 Defender data in Microsoft 365 Security Center
description: Informazioni su come gestire le autorizzazioni per i dati in Microsoft 365 Defender
keywords: accesso, autorizzazioni, MTP, Microsoft Threat Protection, M365, sicurezza, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, ambito, definizione dell’ambito, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847249"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Gestire l'accesso a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Gli account assegnati ai seguenti ruoli di Azure Active Directory (AD) possono accedere alla funzionalità e ai dati di Microsoft 365 Defender:
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
È possibile controllare l'accesso ai dati di Microsoft 365 Defender utilizzando l'ambito assegnato ai gruppi di utenti in Microsoft Defender per il controllo di accesso basato sui ruoli di endpoint (RBAC). Se l'accesso non è stato impostato su un insieme specifico di dispositivi nel Defender per endpoint, si avrà accesso completo ai dati in Microsoft 365 Defender. Tuttavia, dopo aver definito l'ambito dell'account, verranno visualizzati solo i dati relativi ai dispositivi inclusi nell'ambito.

Ad esempio, se si appartiene a un solo gruppo di utenti con un ruolo Microsoft Defender per endpoint e che al gruppo di utenti è stato concesso l'accesso solo ai dispositivi di vendita, verranno visualizzati solo i dati relativi ai dispositivi di vendita in Microsoft 365 Defender. [Per ulteriori informazioni sulle impostazioni di RBAC in Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controlli di accesso in Microsoft Cloud App Security
Durante l'anteprima, Microsoft 365 Defender non applica i controlli di accesso in base alle impostazioni di protezione delle app cloud. L'accesso a Microsoft 365 Defender data non è influenzato da queste impostazioni.

## <a name="related-topics"></a>Argomenti correlati

- [Ruoli di Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender per endpoint RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Ruoli di Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
