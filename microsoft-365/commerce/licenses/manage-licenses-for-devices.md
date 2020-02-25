---
title: Gestire le licenze per i dispositivi
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Informazioni su come assegnare licenze ai gruppi per l'utilizzo con i dispositivi.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242324"
---
# <a name="manage-licenses-for-devices"></a>Gestire le licenze per i dispositivi

Se si dispone di Office 365 ProPlus for Education (Device), è possibile assegnare licenze ai dispositivi mediante i gruppi di Azure AD. Quando un dispositivo dispone di una licenza, tutti gli utenti che utilizzano tale dispositivo possono utilizzare Office 365. Ad esempio, si supponga di disporre di 20 laptop e tablet utilizzati dagli utenti dell'organizzazione. Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi utilizza Office 365 senza la necessità di disporre di una licenza.

> [!IMPORTANT]
> Office 365 ProPlus for Education (Device) è disponibile solo per i clienti con contratti multilicenza di Education a3 e a5.

Per iniziare, è necessario creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo. Per ulteriori informazioni sulle licenze per i dispositivi, compresi i requisiti dei dispositivi, i tipi di gruppi che è possibile utilizzare e come configurare Office 365 ProPlus per l'utilizzo delle licenze per i dispositivi, vedere [device licensing for Office 365 ProPlus for Education Customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Per completare le attività descritte in questo articolo, è necessario essere un amministratore globale.

## <a name="assign-licenses-to-devices"></a>Assegnare licenze ai dispositivi

Quando si assegnano le licenze a un gruppo, si assegnano le licenze a tutti i dispositivi all'interno del gruppo. È possibile assegnare una sola sottoscrizione a un singolo gruppo.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.
2. Nella pagina **licenze** scegliere **Office 365 ProPlus for Education (Device)**.
3. Nella pagina **Office 365 ProPlus for Education (Device)** , scegliere un abbonamento, quindi scegliere **assegna licenze**.
4. Nel riquadro **assegna licenze a un gruppo** , iniziare a digitare il nome di un gruppo e quindi sceglierlo dai risultati per aggiungerlo all'elenco.
6. Scegliere **assegna**, quindi **Chiudi**.

## <a name="unassign-licenses-from-devices"></a>Annullamento dell'assegnazione delle licenze ai dispositivi

Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo. Tutte le app e i dati associati sono quindi di sola lettura.

1. Nell'interfaccia di amministrazione, andare alla pagina **** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.
2. Nella pagina **licenze** scegliere **Office 365 ProPlus for Education (Device)**.
3. Nella pagina **Office 365 ProPlus for Education (Device)** , scegliere un abbonamento, scegliere **altre azioni**, quindi fare clic su **Annulla assegnazione licenze**.
5. Nella finestra di dialogo **Annulla assegnazione licenze** scegliere **Annulla assegnazione**.