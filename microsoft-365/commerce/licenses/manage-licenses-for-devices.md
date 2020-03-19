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
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826280"
---
# <a name="manage-licenses-for-devices"></a>Gestire le licenze per i dispositivi

Se si dispone di Office 365 ProPlus (Device) o Office 365 ProPlus for Education (Device), è possibile assegnare licenze ai dispositivi mediante i gruppi di Azure AD. Quando un dispositivo dispone di una licenza, tutti gli utenti che utilizzano tale dispositivo possono utilizzare Office 365. Ad esempio, si supponga di disporre di 20 laptop e tablet utilizzati dagli utenti dell'organizzazione. Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi utilizza Office 365 senza la necessità di disporre di una licenza.

> [!IMPORTANT]
> La gestione delle licenze basate su dispositivo per Office 365 ProPlus è disponibile solo come licenza per i componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione. Per i clienti commerciali, la licenza è *Office 365 ProPlus (dispositivo)* ed è disponibile solo tramite sottoscrizione Enterprise Agreement/Enterprise Agreement. Per i clienti dell'istruzione, la licenza è *Office 365 ProPlus for Education (Device)* ed è disponibile solo tramite la registrazione per Education Solutions (SEO). Per ulteriori informazioni, leggere il post di Blog sulla [disponibilità dell'istruzione](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.

Per iniziare, è necessario creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo. Per ulteriori informazioni sulle licenze per dispositivi, inclusi i requisiti dei dispositivi, sui tipi di gruppi che è possibile utilizzare e su come configurare Office 365 ProPlus per l'utilizzo delle licenze per i dispositivi, vedere [Device-Based Licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Per completare le attività descritte in questo articolo, è necessario essere un amministratore globale.

## <a name="assign-licenses-to-devices"></a>Assegnare licenze ai dispositivi

Quando si assegnano le licenze a un gruppo, si assegnano le licenze a tutti i dispositivi all'interno del gruppo. È possibile assegnare una sola sottoscrizione a un singolo gruppo.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.
2. Nella pagina **licenze** scegliere **Office 365 ProPlus per Education (Device)** o **Office ProPlus (Device)**.
3. Nella pagina successiva, scegliere un abbonamento, quindi fare clic su **assegna licenze**.
4. Nel riquadro **assegna licenze a un gruppo** , iniziare a digitare il nome di un gruppo e quindi sceglierlo dai risultati per aggiungerlo all'elenco.
5. Scegliere **assegna**, quindi **Chiudi**.

## <a name="unassign-licenses-from-devices"></a>Annullamento dell'assegnazione delle licenze ai dispositivi

Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo. Tutte le app e i dati associati sono quindi di sola lettura.

1. Nell'interfaccia di amministrazione, andare alla pagina **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.
2. Nella pagina **licenze** scegliere **Office 365 ProPlus per Education (Device)** o **Office ProPlus (Device)**.
3. Nella pagina successiva, scegliere un abbonamento, scegliere **altre azioni**, quindi fare clic su **Annulla assegnazione licenze**.
4. Nella finestra di dialogo **Annulla assegnazione licenze** scegliere **Annulla assegnazione**.