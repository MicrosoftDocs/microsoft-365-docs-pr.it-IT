---
title: Accedere al centro notifiche per visualizzare e approvare le indagini automatizzate e le attività di correzione
description: Utilizzare il centro notifiche per visualizzare dettagli relativi alle indagini automatizzate e approvare le azioni in sospeso
keywords: Centro notifiche, protezione dalla minacce, indagine, avviso, in sospeso, automatizzata, rilevamento
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 950dec4c0b0a2de2bdc60a73a12f6c7895189ea4
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911282"
---
# <a name="go-to-the-action-center-to-view-remediation-actions"></a>Accedere al centro notifiche per visualizzare le azioni correttive

**Si applica a:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

## <a name="a-single-pane-of-glass-experience"></a>Un'esperienza a "riquadro unico"

![Centro notifiche](../images/air-actioncenter.png)

Utilizzare il centro notifiche per visualizzare i risultati delle indagini attuali e passate sui dispositivi e le cassette postali dell'organizzazione. A seconda del tipo di minaccia e del [conseguente verdetto](mtp-autoir-results.md#remediation-actions-following-automated-investigation), le azioni di correzione e si verificano automaticamente o previa approvazione da parte del team addetto alle operazioni di sicurezza della propria organizzazione. Tutte le azioni correttive, siano esse in attesa di approvazione o già approvate, vengono consolidate nel centro notifiche. 

Il centro notifiche include un "riquadro unico" per le attività, ad esempio:
- approvazione delle azioni di correzione in sospeso;
- visualizzazione di un log di controllo delle azioni di correzione già approvate;
- revisione delle azioni di correzione completate.

Il team delle operazioni di sicurezza può lavorare in modo più efficace ed efficiente, poiché il centro notifiche offre una visione completa del funzionamento di Microsoft Threat Protection.

## <a name="remediation-actions"></a>Azioni correttive

Nella tabella seguente sono elencate le azioni correttive attualmente supportate nel centro notifiche: 

|Azioni correttive degli endpoint  |Azioni correttive della posta elettronica  |
|---------|---------|
|Quarantena del file<br/>Rimozione della chiave del Registro di sistema<br/>Termine del processo <br/>Interruzione del servizio <br/>Rimozione della chiave del Registro di sistema <br/>Disabilitazione del driver <br/>Rimozione di attività pianificate      |Eliminazione temporanea di messaggi di posta elettronica o cluster<br/>Blocco di URL (al momento del clic)<br/>Disattivazione dell'inoltro della posta elettronica esterna          |

## <a name="go-to-the-action-center"></a>Accedere al centro notifiche

1. Andare su [https://security.microsoft.com](https://security.microsoft.com) ed eseguire l’accesso. 

2. Nel riquadro di spostamento scegliere fare clic su **Centro notifiche**. 

3. Nel centro notifiche, saranno visualizzate due schede: **In sospeso** e **Cronologia**.

    - Nella scheda **In sospeso** sono elencate le indagini che richiedono la revisione e l'approvazione da parte di qualcuno nel team delle operazioni di sicurezza per continuare. Assicurarsi di rivedere e agire sugli elementi in sospeso visualizzati nella scheda.

    - Nella scheda **Cronologia** sono elencate le indagini precedenti e le azioni correttive intraprese automaticamente. È possibile visualizzare i dati relativi all'ultimo giorno, mese, all'ultima settimana o agli ultimi sei mesi.

4. Per visualizzare solo le colonne desiderate, selezionare **Personalizza colonne**.<br/>![Centro notifiche in Microsoft Threat Protection](../images/mtp-action-center.png)

5. Selezionare un elemento nell'elenco per visualizzare maggiori dettagli relativi a un'indagine. Si aprirà la visualizzazione dei dettagli dell'indagine.<br/>![Dettagli indagine](../images/mtp-air-investdetails.png)

    - Se l'indagine riguarda il contenuto della posta elettronica (ad esempio, se l'entità è una cassetta postale), i dettagli dell'indagine vengono aperti nel Centro sicurezza e conformità di Office 365 ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)). 

    - Se l'indagine riguarda un dispositivo, i dettagli dell'indagine vengono aperti nel Centro sicurezza ([https://security.microsoft.com](https://security.microsoft.com)). 

## <a name="required-permissions-for-action-center-tasks"></a>Autorizzazioni necessarie per le attività del centro notifiche

Per approvare o rifiutare le azioni in sospeso nel centro notifiche, è necessario disporre delle autorizzazioni elencate nella tabella seguente:

|Azione correttiva |Ruoli e autorizzazioni necessari |
|--|----|
|Correzione di Microsoft Defender ATP (dispositivi) |Ruolo di **amministratore della protezione** assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- o ---<br/>Ruolo di **azioni correttive attive** assegnato in Microsoft Defender ATP <br/> <br/> Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Creare e gestire ruoli per il controllo dell'accesso basato sui ruoli (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Correzione di Office 365 ATP (contenuti e messaggi di posta elettronica di Office)  |Ruolo di **amministratore della protezione** assegnato in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o nell'interfaccia di amministrazione di Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>--- e --- <br/>Ruolo di **ricerca ed eliminazione** assegnato nel Centro sicurezza e conformità di Office 365 ([https://protection.office.com](https://protection.office.com)) <br/><br/>**IMPORTANTE**: se il ruolo di amministratore della protezione è assegnato solo nel Centro sicurezza e conformità di Office 365, non sarà possibile accedere al centro notifiche o alle funzionalità di Microsoft Threat Protection. È necessario avere il ruolo di amministratore della protezione assegnato in Azure Active Directory o nell'interfaccia di amministrazione di Microsoft 365. <br/><br/>Per altre informazioni, vedere le risorse seguenti: <br/>- [Autorizzazioni del ruolo di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Autorizzazioni nel Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Gli utenti che hanno il ruolo di **amministratore globale** assegnato in Azure Active Directory possono approvare o rifiutare qualsiasi azione in sospeso nel centro notifiche. Tuttavia, come procedura consigliata, l'organizzazione dovrebbe limitare il numero di persone a cui è assegnato il ruolo di amministratore globale. È consigliabile usare i ruoli di **amministratore della protezione**, **azioni correttive attive** e **ricerca ed eliminazione** elencati in precedenza per le autorizzazioni del centro notifiche.

## <a name="next-steps"></a>Passaggi successivi 

- [Ulteriori informazioni sugli incidenti in Microsoft Threat Protection](incidents-overview.md)
- [Visualizzare i risultati di un'indagine automatizzata](mtp-autoir-results.md)
- [Informazioni sulla ricerca in Microsoft Threat Protection](advanced-hunting-overview.md)

