---
title: Gestire l'accesso ai dati di Microsoft Threat Protection nel Centro sicurezza Microsoft 365
description: Informazioni su come gestire le autorizzazioni per i dati in Microsoft Threat Protection
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
ms.openlocfilehash: 0450bf5e37775ed721b307fed1034556ab73a08a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600053"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Gestire l’accesso a Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Gli account assegnati ai seguenti ruoli di Azure Active Directory (AD) possono accedere alle funzionalità e ai dati di Microsoft Threat Protection:
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
È possibile controllare l'accesso ai dati di Microsoft Threat Protection tramite l'ambito assegnato ai gruppi di utenti nel controllo dell'accesso in base ai ruoli di Microsoft Defender ATP. Se l'ambito di accesso non è stato applicato a un set di dispositivi specifico in Microsoft Defender ATP, si avrà accesso completo ai dati di Microsoft Threat Protection. Tuttavia, dopo aver definito l'ambito dell'account, verranno visualizzati solo i dati relativi ai dispositivi inclusi nell'ambito.

Ad esempio, se si appartiene a un solo gruppo di utenti con un ruolo di Microsoft Defender ATP a cui è stato concesso l'accesso solo ai dispositivi di vendita, verranno visualizzati solo i dati relativi ai dispositivi di vendita in Microsoft Threat Protection. [Scopri di più sulle impostazioni del controllo dell'accesso in base ai ruoli in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controlli di accesso in Microsoft Cloud App Security
Durante l'anteprima Microsoft Threat Protection non applica i controlli di accesso in base alle impostazioni di Cloud App Security. L'accesso ai dati di Microsoft Threat Protection non dipende da queste impostazioni.

## <a name="related-topics"></a>Argomenti correlati

- [Ruoli di Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Controllo dell'accesso in base ai ruoli di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Ruoli di Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)