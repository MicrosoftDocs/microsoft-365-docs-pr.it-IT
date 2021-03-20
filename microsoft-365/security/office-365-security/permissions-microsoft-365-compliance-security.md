---
title: Autorizzazioni nei centri di sicurezza e di conformità di Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Utilizzando il Centro sicurezza Microsoft 365 o il Centro conformità Microsoft 365, è possibile gestire le autorizzazioni in una posizione centralizzata per tutte le attività relative alla sicurezza o alla conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 986b6e296304470993a37c17a115182bb5e1d77f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908879"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Autorizzazioni nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

L'organizzazione deve gestire gli scenari di sicurezza e conformità che riguardano tutti i servizi di Microsoft 365. Inoltre, è necessaria flessibilità per fornire le corrette autorizzazioni di amministratore alle persone giuste nel gruppo IT dell'organizzazione. Utilizzando il Centro sicurezza Microsoft 365 o il Centro conformità Microsoft 365, è possibile gestire le autorizzazioni in una posizione centralizzata per tutte le attività relative alla sicurezza o alla conformità.

In seguito all'aggiunta di utenti a questi ruoli di amministratore da parte di un amministratore globale, questi amministratori avranno accesso a funzionalità e dati che riguardano tutti i servizi di Microsoft 365, come il Centro sicurezza Microsoft 365, il Centro conformità Microsoft 365, Azure, Office 365 ed Enterprise Mobility + Security.

## <a name="what-the-microsoft-365-roles-are"></a>Quali sono i ruoli di Microsoft 365

I ruoli visualizzati nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365 sono ruoli di Azure Active Directory. Tali ruoli sono progettati per uniformarsi alle funzioni lavorative nel gruppo IT della propria organizzazione, semplificando quindi l'assegnazione di autorizzazioni necessarie per svolgere il lavoro.

****

|Ruolo|Descrizione|
|---|---|
|**Amministratore globale**|Ha accesso a tutte le funzionalità amministrative presenti in ogni servizio di Microsoft 365. Solo gli amministratori globali possono assegnare altri ruoli di amministratore. Per altre informazioni, vedere [Amministratore globale / Amministratore aziendale](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Amministratore dati di conformità**|Tiene traccia dei dati dell'organizzazione su Microsoft 365, si assicura che siano protetti e ottiene informazioni dettagliate su eventuali problemi, in modo da attenuarne i rischi. Per ulteriori informazioni, vedere [Amministratore dati di conformità](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Amministratore di conformità**|Aiuta l'organizzazione a rimanere conforme ai requisiti normativi, gestire i casi di eDiscovery e mantenere i criteri di governance dei dati nelle posizioni, identità e app di Microsoft 365. Per ulteriori informazioni, vedere [Amministratore di conformità](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operatore della sicurezza**|Può visualizzare, analizzare e rispondere alle minacce attive a utenti, dispositivi e contenuti di Microsoft 365. Per altre informazioni, vedere [Operatore della sicurezza](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Ruolo con autorizzazioni di lettura per la sicurezza**|Può visualizzare, analizzare e rispondere alle minacce attive a utenti, dispositivi e contenuti di Microsoft 365 ma, a differenza del ruolo di Operatore della sicurezza, non ha le autorizzazioni necessarie per intervenire. Per altre informazioni, vedere [Ruolo con autorizzazioni di lettura per la sicurezza](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Amministratore della sicurezza**|Può controllare la sicurezza complessiva dell'organizzazione gestendo i criteri di sicurezza, esaminando l'analisi e i report della sicurezza nei prodotti di Microsoft 365 e tenendosi informato sul panorama delle minacce. Per altre informazioni, vedere [Amministratore di sicurezza](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Ruolo con autorizzazioni di lettura globali**|La versione di sola lettura del ruolo **Amministratore globale**. Può visualizzare tutte le impostazioni e le informazioni amministrative in Microsoft 365. Per altre informazioni, vedere [Ruolo con autorizzazioni di lettura globali](/azure/active-directory/roles/permissions-reference#global-reader).|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>Gli amministratori globali possono gestire i ruoli in Azure Active Directory

Quando un ruolo viene selezionato nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365, è possibile visualizzarne le assegnazioni. Tuttavia, per gestire tali assegnazioni, è necessario accedere ad Azure Active Directory.

Per altre informazioni, vedere [Visualizzare e assegnare i ruoli di amministratore in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

![Collegamento per gestire le autorizzazioni in Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Gestione dei ruoli in un servizio anziché in Azure Active Directory

I ruoli visualizzati nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365 sono visualizzati anche nei servizi per cui si hanno le autorizzazioni necessarie. Ad esempio, è possibile visualizzare questi ruoli nel Centro sicurezza e conformità.

![Ruoli nel Centro sicurezza e conformità](../../media/m365-roles-in-o365-scc.png)

Per informazioni sull'uso di questi ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

### <a name="breaking-inheritance"></a>Interruzione dell'ereditarietà

È importante tenere presente che quando si gestiscono questi ruoli in Azure Active Directory, **tutti** i servizi di Microsoft 365 sono gestiti in una posizione centralizzata. Tuttavia, quando si gestisce un ruolo in un servizio specifico, come il Centro sicurezza e conformità, si sta gestendo il ruolo **solo** per quel servizio specifico. Le assegnazioni e le autorizzazioni per un ruolo in un servizio hanno la precedenza su tutte le autorizzazioni concesse al ruolo di Azure Active Directory.

Questo può essere utile. Ad esempio, se viene assegnato il ruolo di amministratore della sicurezza a un utente, questo non dispone delle autorizzazioni necessarie per gestire gli incidenti. È tuttavia possibile utilizzare le autorizzazioni in Microsoft Defender per endpoint per fornirgli le autorizzazioni specifiche per la gestione degli incidenti in quel servizio.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Dove trovare le informazioni sui ruoli per ogni servizio Microsoft 365

Assegnando uno dei ruoli di amministratore di conformità o di sicurezza di Microsoft 365 a un utente, gli vengono concesse le autorizzazioni a una gamma di servizi di Microsoft 365. Utilizzare i collegamenti seguenti per trovare ulteriori informazioni sulle autorizzazioni specifiche per un ruolo in ciascun servizio.

****

|Servizio Microsoft 365|Informazioni sul ruolo|
|---|---|
|Ruoli di amministratore nei piani di Office 365 e Microsoft 365 per le aziende|[Ruoli di amministratore di Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Azure Active Directory (Azure AD) e Azure AD Identity Protection|[Ruoli di amministratore di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Che cosa è Microsoft Defender per identità?|[Ruoli dei gruppi Microsoft Defender per identità](/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Ruoli di amministratore di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Compliance Manager|[Compliance Manager](../../compliance/compliance-manager-setup.md#set-user-permissions-and-assign-roles)|
|Exchange Online|[Controllo degli accessi in base al ruolo di Exchange](/exchange/permissions-exo/permissions-exo)|
|Intune|[Controllo degli accessi in base al ruolo di Intune](/intune/role-based-access-control)|
|Managed Desktop|[Ruoli di amministratore di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[Controllo degli accessi in base al ruolo](/cloud-app-security/manage-admins)|
|Centro sicurezza e conformità|[Ruoli di amministratore di Microsoft 365](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Ruoli di amministratore di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Secure Score|[Ruoli di amministratore di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Ruoli di amministratore di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Informazioni sul ruolo di amministratore di SharePoint in Office 365](/sharepoint/sharepoint-admin-role)|
|Teams/Skype for Business|[Ruoli di amministratore di Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender per endpoint|[Controllo degli accessi in base al ruolo di Microsoft Defender per endpoint](/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>Presto disponibile

Le autorizzazioni nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365 sono ancora in fase di sviluppo. Ad esempio, è in fase di sviluppo il supporto per:

- Gestire i ruoli nel Centro conformità Microsoft 365 e nel Centro sicurezza Microsoft 365, senza dover accedere ad Azure Active Directory.
- Personalizzare i ruoli aggiungendo o rimuovendo autorizzazioni specifiche.
- Creare ruoli personalizzati con le autorizzazioni scelte.