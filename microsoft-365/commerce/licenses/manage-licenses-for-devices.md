---
title: Gestire le licenze per i dispositivi
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638184"
---
# <a name="manage-licenses-for-devices"></a>Gestire le licenze per i dispositivi

Se si dispone di Microsoft 365 Apps for Enterprise (Device) o Microsoft 365 Apps for Education (Device), è possibile assegnare licenze ai dispositivi mediante i gruppi di Azure AD. Quando un dispositivo dispone di una licenza, chiunque utilizza tale dispositivo può utilizzare Microsoft 365 Apps for Enterprise (in precedenza denominato Office 365 ProPlus). Ad esempio, si supponga di disporre di 20 laptop e tablet utilizzati dagli utenti dell'organizzazione. Quando si assegna una licenza a ogni dispositivo, ogni persona che accede a uno dei dispositivi utilizza Microsoft 365 Apps for Enterprise senza che sia necessaria la propria licenza.

> [!IMPORTANT]
> La gestione delle licenze basate su dispositivo per Microsoft 365 Apps for Enterprise è disponibile solo come licenza per i componenti aggiuntivi per alcuni clienti commerciali e per alcuni clienti dell'istruzione. Per i clienti commerciali, la licenza è *Microsoft 365 Apps for Enterprise (Device)* ed è disponibile solo tramite la sottoscrizione Enterprise Agreement/Enterprise Agreement. Per i clienti dell'istruzione, la licenza è *Microsoft 365 Apps for Education (Device)* ed è disponibile solo tramite la registrazione per Education Solutions (SEO). Per ulteriori informazioni, leggere il post di Blog sulla [disponibilità dell'istruzione](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Per la disponibilità commerciale, contattare il rappresentante dell'account Microsoft.

Per iniziare, è necessario creare un gruppo nell'interfaccia di amministrazione di Azure Active Directory e quindi assegnare i dispositivi al gruppo. Per ulteriori informazioni sulle licenze per dispositivi, inclusi i requisiti per i dispositivi, sui tipi di gruppi che è possibile utilizzare e su come configurare le app Microsoft 365 per Enterprise per l'utilizzo delle licenze per dispositivi, vedere [Device-Based Licensing for Microsoft 365 Apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Per completare le attività descritte in questo articolo, è necessario essere un amministratore globale.

## <a name="assign-licenses-to-devices"></a>Assegnare licenze ai dispositivi

Quando si assegnano le licenze a un gruppo, si assegnano le licenze a tutti i dispositivi all'interno del gruppo. È possibile assegnare una sola sottoscrizione a un singolo gruppo.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla **Billing**  >  pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.
2. Nella pagina **licenze** scegliere **Microsoft 365 Apps for Education (Device)** o **Microsoft 365 Apps for Enterprise (Device)**.
3. Nella pagina successiva, scegliere un abbonamento, quindi fare clic su **assegna licenze**.
4. Nel riquadro **assegna licenze a un gruppo** , iniziare a digitare il nome di un gruppo e quindi sceglierlo dai risultati per aggiungerlo all'elenco.
5. Scegliere **assegna**, quindi **Chiudi**.

## <a name="unassign-licenses-from-devices"></a>Annullamento dell'assegnazione delle licenze ai dispositivi

Quando si annulla l'assegnazione delle licenze da un gruppo, si rimuovono le licenze da tutti i dispositivi all'interno del gruppo. Tutte le app e i dati associati sono quindi di sola lettura.

1. Nell'interfaccia di amministrazione, andare alla **Billing**  >  pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.
2. Nella pagina **licenze** scegliere **Microsoft 365 Apps for Education (Device)** o **Microsoft 365 Apps for Enterprise (Device)**.
3. Nella pagina successiva, scegliere un abbonamento, scegliere **altre azioni**, quindi fare clic su **Annulla assegnazione licenze**.
4. Nella finestra di dialogo **Annulla assegnazione licenze** scegliere **Annulla assegnazione**.