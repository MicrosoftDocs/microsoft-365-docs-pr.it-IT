---
title: Ruoli personalizzati per il controllo dell'accesso basato sui ruoli
description: Informazioni su come gestire i ruoli personalizzati nel Centro sicurezza Microsoft 365
keywords: access, permissions, MTP, Microsoft Threat Protection, M365, security, MCAS, MDATP, Cloud App Security, Microsoft Defender Advanced Threat Protection, scope, scoping, RBAC, roles-based access, custom roles-based access, roles-based auth, RBAC in MDO, roles, rolegroups, permissions inheritance, fine-grained permissions
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6582e4e940dc9910e7d341c92b525379b924f35b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199958"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Ruoli personalizzati nel controllo di accesso basato sui ruoli per Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Si applica a:**

- Microsoft 365 Defender
 
Esistono due tipi di ruoli che possono essere usati per accedere a Microsoft 365 Defender:
- **Ruoli globali di Azure Active Directory (AD)**
- **Ruoli personalizzati**

L'accesso a Microsoft 365 Defender può essere gestito collettivamente utilizzando [i ruoli globali in Azure Active Directory (AAD)](m365d-permissions.md)

Se è necessaria una maggiore flessibilità e un maggiore controllo sull'accesso a dati di prodotto specifici, l'accesso a Microsoft 365 Defender può essere gestito anche con la creazione di ruoli personalizzati tramite ogni rispettivo portale di sicurezza.  

Ad esempio, un ruolo personalizzato creato tramite Microsoft Defender per Endpoint consentirebbe l'accesso ai dati di prodotto pertinenti, inclusi i dati dell'endpoint all'interno del Centro sicurezza Microsoft 365. Analogamente, un ruolo personalizzato creato tramite Microsoft Defender per Office 365 consentirebbe l'accesso ai dati di prodotto pertinenti, inclusi i dati di collaborazione di Email & all'interno del Centro sicurezza Microsoft 365.

Gli utenti con ruoli personalizzati esistenti possono accedere ai dati nel Centro sicurezza Microsoft 365 in base alle autorizzazioni del carico di lavoro esistenti senza alcuna configurazione aggiuntiva necessaria.

## <a name="create-and-manage-custom-roles"></a>Creare e gestire ruoli personalizzati
I ruoli e le autorizzazioni personalizzati possono essere creati e gestiti singolarmente tramite ognuno dei portali di sicurezza seguenti: 

- Microsoft Defender for Endpoint - [Modificare i ruoli in Microsoft Defender for Endpoint](../defender-endpoint/user-roles.md)
- Microsoft Defender per Office 365 - [Autorizzazioni nel Centro sicurezza & conformità](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security - [Gestire l'accesso amministratore](/cloud-app-security/manage-admins)

Ogni ruolo personalizzato creato tramite un singolo portale consente di accedere ai dati del portale del prodotto pertinente. Ad esempio, un ruolo personalizzato creato tramite Microsoft Defender per Endpoint consentirà solo l'accesso a Defender per i dati dell'endpoint.

> [!TIP]
> È inoltre possibile accedere alle autorizzazioni e ai ruoli tramite il Centro sicurezza Microsoft 365 selezionando Autorizzazioni & ruoli nel riquadro di spostamento. L'accesso a Microsoft Cloud App Security (MCAS) viene gestito tramite il portale MCAS e controlla anche l'accesso a Microsoft Defender for Identity.  Vedere [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> Anche i ruoli personalizzati creati in Microsoft Cloud App Security hanno accesso ai dati di Microsoft Defender for Identity. Gli utenti con ruoli Amministratore gruppo utenti o Amministratore app/istanza di Microsoft Cloud App Security non sono in grado di accedere ai dati di Microsoft Cloud App Security tramite il Centro sicurezza Microsoft 365.

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>Gestire autorizzazioni e ruoli nel Centro sicurezza Microsoft 365
Le autorizzazioni e i ruoli possono essere gestiti anche nel Centro sicurezza Microsoft 365:

1. Accedere al Centro sicurezza Microsoft 365 all'security.microsoft.com.
2. Nel riquadro di spostamento selezionare **Autorizzazioni & ruoli**.
3. **Nell'intestazione Autorizzazioni** selezionare **Ruoli**.

> [!NOTE]
> Questo vale solo per Defender per Office 365 e Defender for Endpoint. L'accesso ad altri carichi di lavoro deve essere eseguito nei portali pertinenti.


## <a name="required-roles-and-permissions"></a>Ruoli e autorizzazioni necessari
Nella tabella seguente vengono descritti i ruoli e le autorizzazioni necessari per accedere a ogni esperienza unificata in ogni carico di lavoro. I ruoli definiti nella tabella seguente fanno riferimento ai ruoli personalizzati nei singoli portali e non sono connessi ai ruoli globali in Azure AD, anche se denominati in modo analogo.

> [!NOTE]
> La gestione degli eventi imprevisti richiede autorizzazioni di gestione per tutti i prodotti che fanno parte dell'evento imprevisto.
 
| **Uno dei ruoli seguenti è necessario per Microsoft 365 Defender**  | **Uno dei ruoli seguenti è obbligatorio per Defender per Endpoint**  | **Uno dei ruoli seguenti è necessario per Defender per Office 365** | **Uno dei ruoli seguenti è obbligatorio per Cloud App Security** | 
|---------|---------|---------|---------|
| Visualizzazione dei dati dell'indagine: <ul><li>Pagina avviso</li> <li>Coda avvisi</li> <li>Eventi imprevisti</li>  <li>Coda eventi imprevisti</li> <li>Centro notifiche</li></ul>| Visualizzare le operazioni di sicurezza dei dati | <ul><li>Sola visualizzazione Gestisci avvisi </li> <li>Configurazione organizzazione</li><li>Log di controllo</li> <li>Log di controllo di sola visualizzazione</li> <li>Amministratore che legge i dati di sicurezza</li> <li>Amministratore della sicurezza</li><li>Destinatari di sola visualizzazione</li></ul>  | <ul><li>Amministratore globale</li> <li>Amministratore della sicurezza</li> <li>Amministratore di conformità</li> <li>Operatore della sicurezza</li> <li>Amministratore che legge i dati di sicurezza</li> <li>Ruolo con autorizzazioni di lettura globali</li></ul> |
| Visualizzazione dei dati di ricerca | Visualizzare le operazioni di sicurezza dei dati | <ul><li>Amministratore che legge i dati di sicurezza</li> <li>Amministratore della sicurezza</li> <li>Destinatari di sola visualizzazione</li> | <ul><li>Amministratore globale</li> <li>Amministratore della sicurezza</li> <li>Amministratore di conformità</li> <li>Operatore della sicurezza</li> <li>Amministratore che legge i dati di sicurezza</li> <li>Ruolo con autorizzazioni di lettura globali</li></ul> |
| Gestione di avvisi ed eventi imprevisti | Analisi degli avvisi | <ul><li>Gestire gli avvisi</li> <li>Amministratore della sicurezza</li> | <ul><li>Amministratore globale</li> <li>Amministratore della sicurezza</li> <li>Amministratore di conformità</li> <li>Operatore della sicurezza</li> <li>Amministratore che legge i dati di sicurezza</li></ul> |
| Correzione del centro notifiche | Azioni di correzione attive - operazioni di sicurezza | Ricerca ed eliminazione | |
| Impostazione di rilevamenti personalizzati | Gestire le impostazioni di sicurezza |<ul><li>Gestire gli avvisi</li> <li>Amministratore della sicurezza</li></ul> | <ul><li>Amministratore globale</li> <li>Amministratore della sicurezza</li> <li>Amministratore di conformità</li> <li>Operatore della sicurezza</li> <li>Amministratore che legge i dati di sicurezza</li> <li>Ruolo con autorizzazioni di lettura globali</li></ul> |
| Analisi delle minacce | Dati relativi a avvisi e eventi imprevisti: <ul><li>Visualizzare le operazioni di sicurezza dei dati</li></ul>Mitigazioni TVM:<ul><li>Visualizzazione dei dati - Gestione delle minacce e delle vulnerabilità</li></ul> | Dati relativi a avvisi e eventi imprevisti:<ul> <li>Sola visualizzazione Gestisci avvisi</li> <li>Gestire gli avvisi</li> <li>Configurazione organizzazione</li><li>Log di controllo</li> <li>Log di controllo di sola visualizzazione</li><li>Amministratore che legge i dati di sicurezza</li> <li>Amministratore della sicurezza</li><li>Destinatari di sola visualizzazione</li> </ul> Tentativi di posta elettronica non consentiti: <ul><li>Amministratore che legge i dati di sicurezza</li> <li>Amministratore della sicurezza</li><li>Destinatari di sola visualizzazione</li> | Non disponibile per gli utenti MCAS o MDI |

Ad esempio, per visualizzare i dati di ricerca da Microsoft Defender per Endpoint, sono necessarie autorizzazioni per le operazioni di sicurezza dei dati.  

Analogamente, per visualizzare i dati di ricerca da Microsoft Defender per Office 365, gli utenti richiedono uno dei ruoli seguenti:  

- Visualizzare le operazioni di sicurezza dei dati
- Amministratore che legge i dati di sicurezza
- Amministratore della sicurezza
- Destinatari di sola visualizzazione

## <a name="related-topics"></a>Argomenti correlati
- [Gestire l'accesso a Microsoft 365 Defender](m365d-permissions.md)
- [Gestire l'accesso amministratore per MCAS](/cloud-app-security/manage-admins)
